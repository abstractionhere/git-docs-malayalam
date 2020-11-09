## പേര് 
#### git-clone - ഒരു പുതിയ ഡയറക്‌ടറിയിലേക്ക് ഒരു ശേഖരം ക്ലോൺ ചെയ്യുക

## സംഗ്രഹം
~~~
git clone [--template=<template_directory>]
	  [-l] [-s] [--no-hardlinks] [-q] [-n] [--bare] [--mirror]
	  [-o <name>] [-b <name>] [-u <upload-pack>] [--reference <repository>]
	  [--dissociate] [--separate-git-dir <git dir>]
	  [--depth <depth>] [--[no-]single-branch] [--no-tags]
	  [--recurse-submodules[=<pathspec>]] [--[no-]shallow-submodules]
	  [--[no-]remote-submodules] [--jobs <n>] [--sparse]
	  [--filter=<filter>] [--] <repository>
	  [<directory>]
~~~

	  
## വിവരണം

പുതുതായി സൃഷ്‌ടിച്ച ഡയറക്‌ടറിയിലേക്ക് ഒരു ശേഖരം ക്ലോൺ ചെയ്യുന്നു, ക്ലോൺ ചെയ്ത ശേഖരത്തിൽ ഓരോ ശാഖയ്‌ക്കും വിദൂര-ട്രാക്കിംഗ് ശാഖകൾ സൃഷ്ടിക്കുന്നു (Git ബ്രാഞ്ച് - റിമോട്ടുകൾ ഉപയോഗിച്ച് ദൃശ്യമാണ്), കൂടാതെ ക്ലോൺ ചെയ്ത സംഭരണിയുടെ നിലവിൽ സജീവമായ ബ്രാഞ്ചിൽ നിന്ന് ഫോർക്ക് ചെയ്ത ഒരു പ്രാരംഭ ശാഖ സൃഷ്ടിക്കുകയും പരിശോധിക്കുകയും ചെയ്യുന്നു.

ക്ലോണിനുശേഷം, ആർ‌ഗ്യുമെൻറുകൾ‌ ഇല്ലാതെ ഒരു പ്ലെയിൻ‌ Git-fetch എല്ലാ വിദൂര ട്രാക്കിംഗ് ശാഖകളും അപ്‌ഡേറ്റുചെയ്യും, കൂടാതെ ആർ‌ഗ്യുമെൻറുകൾ‌ ഇല്ലാത്ത ഒരു Git പുൾ‌ വിദൂര മാസ്റ്റർ‌ ബ്രാഞ്ചിനെ നിലവിലെ മാസ്റ്റർ‌ ബ്രാഞ്ചിലേക്ക് ലയിപ്പിക്കും.

refs/remotes/origin കീഴിലുള്ള വിദൂര ബ്രാഞ്ച് ഹെഡുകളിലേക്ക് റഫറൻസുകൾ സൃഷ്ടിച്ചും remote.origin.url, remote.origin.fetch കോൺഫിഗറേഷൻ വേരിയബിളുകൾ എന്നിവ ആരംഭിച്ചും ഈ സ്ഥിരസ്ഥിതി കോൺഫിഗറേഷൻ കൈവരിക്കാനാകും.

## ഓപ്ഷനുകൾ
~~~
-l
--local
ഒരു പ്രാദേശിക മെഷീനിൽ നിന്ന് ക്ലോൺ ചെയ്യാനുള്ള ശേഖരം ഉള്ളപ്പോൾ, ഈ ഫ്ലാഗ് സാധാരണ "ജിറ്റ് അവേർ" ട്രാൻസ്പോർട്ട് മെക്കാനിസത്തെ മറികടന്ന് HEAD ന്റെയും ഒബ്ജക്റ്റുകളുടെയും കീഴിലുള്ള എല്ലാ വസ്തുക്കളുടെയും ഒരു പകർപ്പ് ഉണ്ടാക്കി സംഭരണത്തെ ക്ലോൺ ചെയ്യുന്നു. .Git / object / directory ന് കീഴിലുള്ള ഫയലുകൾ സാധ്യമാകുമ്പോൾ സ്ഥലം ലാഭിക്കാൻ ഹാർഡ്‌ലിങ്ക് ചെയ്യുന്നു.

റിപ്പോസിറ്ററി ഒരു പ്രാദേശിക പാതയായി (ഉദാ., /Path/to/repo) വ്യക്തമാക്കിയിട്ടുണ്ടെങ്കിൽ, ഇതാണ് സ്ഥിരസ്ഥിതി, --local അടിസ്ഥാനപരമായി ഒരു നോ-ഒപ്പ് ആണ്. റിപ്പോസിറ്ററി ഒരു URL ആയി വ്യക്തമാക്കിയിട്ടുണ്ടെങ്കിൽ, ഈ ഫ്ലാഗ് അവഗണിക്കപ്പെടും (ഞങ്ങൾ ഒരിക്കലും പ്രാദേശിക ഒപ്റ്റിമൈസേഷനുകൾ ഉപയോഗിക്കില്ല). /No-ലോക്കൽ വ്യക്തമാക്കുന്നത് സ്ഥിരസ്ഥിതി ജിറ്റ് ട്രാൻസ്പോർട്ട് ഉപയോഗിച്ച് /path/to/repo നൽകുമ്പോൾ സ്ഥിരസ്ഥിതിയെ അസാധുവാക്കും.
~~~
~~~
--no-hardlinks
ഹാർഡ്‌ലിങ്കുകൾ ഉപയോഗിക്കുന്നതിന് പകരം git/object ഡയറക്ടറിക്ക് കീഴിലുള്ള ഫയലുകൾ പകർത്താൻ ഒരു പ്രാദേശിക ഫയൽസിസ്റ്റത്തിലെ ഒരു ശേഖരത്തിൽ നിന്ന് ക്ലോണിംഗ് പ്രക്രിയ നിർബന്ധിക്കുക. നിങ്ങളുടെ സംഭരണിയുടെ ബാക്കപ്പ് നിർമ്മിക്കാൻ ശ്രമിക്കുകയാണെങ്കിൽ ഇത് അഭികാമ്യമാണ്.
~~~
~~~
-s
--shared
ക്ലോണിലേക്കുള്ള ശേഖരം ലോക്കൽ മെഷീനിൽ ആയിരിക്കുമ്പോൾ, ഹാർഡ് ലിങ്കുകൾ ഉപയോഗിക്കുന്നതിനുപകരം, ഉറവിട ശേഖരണവുമായി ഒബ്ജക്റ്റുകൾ പങ്കിടുന്നതിന് .git / object / info / ഇതരമാർഗങ്ങൾ സ്വയമേവ സജ്ജമാക്കുക. തത്ഫലമായുണ്ടാകുന്ന ശേഖരം സ്വന്തമായി ഒരു വസ്തുവുമില്ലാതെ ആരംഭിക്കുന്നു.
~~~
~~~
--reference[-if-able] <repository>
റഫറൻസ് ശേഖരം പ്രാദേശിക മെഷീനിലാണെങ്കിൽ, റഫറൻസ് ശേഖരത്തിൽ നിന്ന് ഒബ്‌ജക്റ്റുകൾ ലഭിക്കുന്നതിന് .git / object / info / ഇതരമാർഗങ്ങൾ സ്വയമേവ സജ്ജമാക്കുക. ഇതിനകം നിലവിലുള്ള ഒരു ശേഖരം ഒരു ഇതരമാർഗ്ഗമായി ഉപയോഗിക്കുന്നതിന്, റിപോസിറ്ററി ക്ലോൺ ചെയ്യുന്നതിൽ നിന്ന് കുറച്ച് ഒബ്ജക്റ്റുകൾ പകർത്തേണ്ടതുണ്ട്, ഇത് നെറ്റ്‌വർക്കും പ്രാദേശിക സംഭരണ ​​ചെലവും കുറയ്ക്കും. --Reference-if-able ഉപയോഗിക്കുമ്പോൾ, ക്ലോൺ നിർത്തുന്നതിന് പകരം നിലവിലുള്ള ഒരു ഡയറക്ടറി ഒരു മുന്നറിയിപ്പ് ഉപയോഗിച്ച് ഒഴിവാക്കുന്നു.
~~~
~~~
--dissociate
നെറ്റ്‌വർക്ക് കൈമാറ്റം കുറയ്ക്കുന്നതിന് മാത്രം - റഫറൻസ് ഓപ്ഷനുകൾ ഉപയോഗിച്ച് വ്യക്തമാക്കിയ റഫറൻസ് ശേഖരണങ്ങളിൽ നിന്ന് ഒബ്ജക്റ്റുകൾ കടം വാങ്ങുക, കടമെടുത്ത വസ്തുക്കളുടെ ആവശ്യമായ പ്രാദേശിക പകർപ്പുകൾ നിർമ്മിച്ച് ഒരു ക്ലോൺ നിർമ്മിച്ചതിനുശേഷം അവയിൽ നിന്ന് കടം വാങ്ങുന്നത് നിർത്തുക. ഇതിനകം തന്നെ മറ്റൊരു ശേഖരത്തിൽ നിന്ന് വസ്തുക്കൾ കടമെടുക്കുന്ന ഒരു ശേഖരത്തിൽ നിന്ന് പ്രാദേശികമായി ക്ലോൺ ചെയ്യുമ്പോഴും ഈ ഓപ്ഷൻ ഉപയോഗിക്കാം - പുതിയ ശേഖരം അതേ ശേഖരത്തിൽ നിന്ന് വസ്തുക്കൾ കടമെടുക്കും, കടം വാങ്ങുന്നത് നിർത്താൻ ഈ ഓപ്ഷൻ ഉപയോഗിക്കാം.
~~~
~~~
-q
--quiet
നിശബ്ദമായി പ്രവർത്തിക്കുക. സാധാരണ പിശക് സ്ട്രീമിലേക്ക് പുരോഗതി റിപ്പോർട്ടുചെയ്തിട്ടില്ല.
~~~
~~~
--progress
--quiet വ്യക്തമാക്കിയിട്ടില്ലെങ്കിൽ, ഒരു ടെർമിനലിലേക്ക് അറ്റാച്ചുചെയ്യുമ്പോൾ സ്ഥിരസ്ഥിതി സ്റ്റാൻഡേർഡ് പിശക് സ്ട്രീമിൽ പുരോഗതി നില റിപ്പോർട്ടുചെയ്യുന്നു. സ്റ്റാൻഡേർഡ് പിശക് സ്ട്രീം ഒരു ടെർമിനലിലേക്ക് നയിക്കുന്നില്ലെങ്കിലും ഈ ഫ്ലാഗ് പുരോഗതി നിലയെ പ്രേരിപ്പിക്കുന്നു.
~~~
~~~
--server-option=<option>
പ്രോട്ടോക്കോൾ പതിപ്പ് 2 ഉപയോഗിച്ച് ആശയവിനിമയം നടത്തുമ്പോൾ നൽകിയ സ്ട്രിംഗ് സെർവറിലേക്ക് കൈമാറുക. തന്നിരിക്കുന്ന സ്ട്രിംഗിൽ ഒരു എൻ‌യു‌എൽ അല്ലെങ്കിൽ എൽ‌എഫ് പ്രതീകം അടങ്ങിയിരിക്കരുത്. അജ്ഞാതമായവ ഉൾപ്പെടെ സെർവർ ഓപ്ഷനുകൾ സെർവർ കൈകാര്യം ചെയ്യുന്നത് സെർവർ നിർദ്ദിഷ്ടമാണ്. ഒന്നിലധികം --server-option = <option> നൽകുമ്പോൾ, അവയെല്ലാം കമാൻഡ് ലൈനിൽ ലിസ്റ്റുചെയ്‌തിരിക്കുന്ന ക്രമത്തിൽ മറുവശത്തേക്ക് അയയ്‌ക്കും.
~~~
~~~
-n
--no-checkout
ക്ലോൺ പൂർത്തിയായതിന് ശേഷം HEAD ന്റെ ഒരു ചെക്ക് out ട്ടും നടത്തുന്നില്ല.
~~~
~~~
--bare
നഗ്നമായ ഒരു Git ശേഖരം നിർമ്മിക്കുക. അതായത്, <directory> സൃഷ്ടിച്ച് അഡ്മിനിസ്ട്രേറ്റീവ് ഫയലുകൾ <directory> /.git ൽ സ്ഥാപിക്കുന്നതിനുപകരം, <directory> തന്നെ $ GIT_DIR ആക്കുക. ഇത് വ്യക്തമായും --no- ചെക്ക് out ട്ടിനെ സൂചിപ്പിക്കുന്നു, കാരണം പ്രവർത്തിക്കുന്ന ട്രീ പരിശോധിക്കാൻ ഒരിടത്തും ഇല്ല. റിമോറ്റിലെ ബ്രാഞ്ച് ഹെഡുകളെ റെഫുകൾ / റിമോറ്റുകൾ / ഒറിജിൻ / എന്നിവയിലേക്ക് മാപ്പുചെയ്യാതെ നേരിട്ട് പ്രാദേശിക ബ്രാഞ്ച് ഹെഡുകളിലേക്ക് പകർത്തുന്നു. ഈ ഓപ്‌ഷൻ ഉപയോഗിക്കുമ്പോൾ, വിദൂര ട്രാക്കിംഗ് ശാഖകളോ അനുബന്ധ കോൺഫിഗറേഷൻ വേരിയബിളുകളോ സൃഷ്‌ടിക്കില്ല.
~~~
~~~
--sparse
വിരളമായ ചെക്ക് out ട്ട് ഫയൽ സമാരംഭിക്കുക, അങ്ങനെ പ്രവർത്തന ഡയറക്ടറി റിപ്പോസിറ്ററിയുടെ റൂട്ടിലുള്ള ഫയലുകളിൽ മാത്രം ആരംഭിക്കുന്നു. ആവശ്യാനുസരണം പ്രവർത്തിക്കുന്ന ഡയറക്‌ടറി വളർത്തുന്നതിന് വിരള-ചെക്ക് out ട്ട് ഫയൽ പരിഷ്‌ക്കരിക്കാനാകും.
~~~
~~~
--mirror
ഉറവിട ശേഖരണത്തിന്റെ ഒരു മിറർ സജ്ജമാക്കുക. ഇത് സൂചിപ്പിക്കുന്നത് - ബെയർ. --Bare, --mirror എന്നിവയുമായി താരതമ്യപ്പെടുത്തുമ്പോൾ, ഉറവിടത്തിന്റെ പ്രാദേശിക ശാഖകളെ ടാർഗറ്റിന്റെ പ്രാദേശിക ശാഖകളിലേക്ക് മാപ്പ് ചെയ്യുക മാത്രമല്ല, ഇത് എല്ലാ റെഫറുകളും (വിദൂര ട്രാക്കിംഗ് ശാഖകൾ, കുറിപ്പുകൾ മുതലായവ ഉൾപ്പെടെ) മാപ്പ് ചെയ്യുകയും ഒരു റെഫ്പെക് കോൺഫിഗറേഷൻ സജ്ജമാക്കുകയും ചെയ്യുന്നു. ടാർഗെറ്റ് ശേഖരത്തിൽ ഒരു ജിറ്റ് വിദൂര അപ്‌ഡേറ്റ് തിരുത്തിയെഴുതുന്നു.
~~~
~~~
<repository>
ക്ലോൺ ചെയ്യാനുള്ള (ഒരുപക്ഷേ വിദൂര) ശേഖരം. ശേഖരണങ്ങൾ വ്യക്തമാക്കുന്നതിനെക്കുറിച്ചുള്ള കൂടുതൽ വിവരങ്ങൾക്ക് ചുവടെയുള്ള GIT URLS വിഭാഗം കാണുക.
~~~
~~~
<directory>
ക്ലോൺ ചെയ്യുന്നതിനുള്ള ഒരു പുതിയ ഡയറക്ടറിയുടെ പേര്. ഡയറക്‌ടറിയൊന്നും വ്യക്തമായി നൽകിയിട്ടില്ലെങ്കിൽ ഉറവിട ശേഖരണത്തിന്റെ "മാനുഷിക" ഭാഗം ഉപയോഗിക്കുന്നു (/path/to/repo.git- നുള്ള റിപ്പോയും ഹോസ്റ്റ്. Xz- നുള്ള foo: foo / .git). ഡയറക്ടറി ശൂന്യമാണെങ്കിൽ മാത്രമേ നിലവിലുള്ള ഡയറക്ടറിയിലേക്ക് ക്ലോൺ ചെയ്യാൻ അനുവദിക്കൂ.
~~~

## GIT URLS

പൊതുവേ, ട്രാൻസ്പോർട്ട് പ്രോട്ടോക്കോൾ, വിദൂര സെർവറിന്റെ വിലാസം, ശേഖരണത്തിലേക്കുള്ള പാത എന്നിവയെക്കുറിച്ചുള്ള വിവരങ്ങൾ URL- കളിൽ അടങ്ങിയിരിക്കുന്നു. ട്രാൻസ്പോർട്ട് പ്രോട്ടോക്കോൾ അനുസരിച്ച്, ഈ വിവരങ്ങളിൽ ചിലത് ഇല്ലായിരിക്കാം.

ജിറ്റ് ssh, git, http, https പ്രോട്ടോക്കോളുകളെ പിന്തുണയ്ക്കുന്നു (കൂടാതെ, ലഭ്യമാക്കുന്നതിന് ftp, ftps എന്നിവ ഉപയോഗിക്കാം, പക്ഷേ ഇത് കാര്യക്ഷമമല്ലാത്തതും ഒഴിവാക്കിയതുമാണ്; ഇത് ഉപയോഗിക്കരുത്).

നേറ്റീവ് ട്രാൻസ്പോർട്ട് (അതായത് git: // URL) പ്രാമാണീകരണം നടത്തുന്നില്ല, മാത്രമല്ല സുരക്ഷിതമല്ലാത്ത നെറ്റ്‌വർക്കുകളിൽ ജാഗ്രതയോടെ ഉപയോഗിക്കുകയും വേണം.

ഇനിപ്പറയുന്ന വാക്യഘടനകൾ അവയ്‌ക്കൊപ്പം ഉപയോഗിക്കാം:

* ssh://[user@]host.xz[:port]/path/to/repo.git/
* git://host.xz[:port]/path/to/repo.git/
* http[s]://host.xz[:port]/path/to/repo.git/
* ftp[s]://host.xz[:port]/path/to/repo.git/


ssh പ്രോട്ടോക്കോളിനൊപ്പം ഇതര scp പോലുള്ള വാക്യഘടനയും ഉപയോഗിക്കാം:

* [user@]host.xz:path/to/repo.git/

ആദ്യത്തെ കോളന് മുമ്പ് സ്ലാഷുകൾ ഇല്ലെങ്കിൽ മാത്രമേ ഈ വാക്യഘടന തിരിച്ചറിയാൻ കഴിയൂ. കോളൻ അടങ്ങിയിരിക്കുന്ന ഒരു പ്രാദേശിക പാതയെ വേർതിരിച്ചറിയാൻ ഇത് സഹായിക്കുന്നു. ഉദാഹരണത്തിന്, ലോക്കൽ പാത്ത് foo: ബാർ ഒരു കേവല പാതയായി അല്ലെങ്കിൽ ./foo:bar ഒരു ssh url ആയി തെറ്റായി വ്യാഖ്യാനിക്കുന്നത് ഒഴിവാക്കാൻ കഴിയും.

ssh, git പ്രോട്ടോക്കോളുകൾ‌ ~ ഉപയോക്തൃനാമ വിപുലീകരണത്തെ പിന്തുണയ്‌ക്കുന്നു:

* ssh://[user@]host.xz[:port]/~[user]/path/to/repo.git/
* git://host.xz[:port]/~[user]/path/to/repo.git/
* [user@]host.xz:/~[user]/path/to/repo.git/

പ്രാദേശിക റിപ്പോസിറ്ററികൾക്കായി, പ്രാദേശികമായി Git പിന്തുണയ്ക്കുന്നു, ഇനിപ്പറയുന്ന വാക്യഘടനകൾ ഉപയോഗിക്കാം:

* /path/to/repo.git/
* file:///path/to/repo.git/


മുമ്പത്തെ സൂചിപ്പിക്കുന്നത് - ലോക്കൽ ഓപ്ഷൻ ഒഴികെ ഈ രണ്ട് വാക്യഘടനകളും മിക്കവാറും തുല്യമാണ്.
ഒരു പ്രത്യേക ട്രാൻസ്പോർട്ട് പ്രോട്ടോക്കോൾ എങ്ങനെ കൈകാര്യം ചെയ്യണമെന്ന് Git- ന് അറിയില്ലെങ്കിൽ, അത് നിലവിലുണ്ടെങ്കിൽ വിദൂര- <ട്രാൻസ്പോർട്ട്> വിദൂര സഹായിയെ ഉപയോഗിക്കാൻ ശ്രമിക്കുന്നു. ഒരു വിദൂര സഹായിയെ വ്യക്തമായി അഭ്യർത്ഥിക്കുന്നതിന്, ഇനിപ്പറയുന്ന വാക്യഘടന ഉപയോഗിക്കാം:

* <transport>::<address>


ഇവിടെ <address> ഒരു പാത്ത്, സെർവർ, പാത്ത് അല്ലെങ്കിൽ നിർദ്ദിഷ്ട വിദൂര സഹായിയെ അംഗീകരിച്ച ഏകപക്ഷീയമായ URL പോലുള്ള സ്ട്രിംഗ് ആകാം.

സമാനമായി പേരുള്ള വിദൂര ശേഖരണങ്ങളുടെ ഒരു വലിയ എണ്ണം ഉണ്ടെങ്കിൽ അവയ്‌ക്കായി മറ്റൊരു ഫോർമാറ്റ് ഉപയോഗിക്കാൻ നിങ്ങൾ ആഗ്രഹിക്കുന്നുവെങ്കിൽ (നിങ്ങൾ ഉപയോഗിക്കുന്ന URL- കൾ പ്രവർത്തിക്കുന്ന URL- കളിലേക്ക് മാറ്റിയെഴുതപ്പെടും), നിങ്ങൾക്ക് ഫോമിന്റെ കോൺഫിഗറേഷൻ വിഭാഗം സൃഷ്ടിക്കാൻ കഴിയും:
~~~
	[url "<actual url base>"]
		insteadOf = <other url base>
~~~

ഉദാഹരണത്തിന്, ഇതുപയോഗിച്ച്:
~~~
	[url "git://git.host.xz/"]
		insteadOf = host.xz:/path/to/
		insteadOf = work:
~~~

"വർക്ക്: repo.git" പോലുള്ള ഒരു URL അല്ലെങ്കിൽ "host.xz: /path/to/repo.git" പോലുള്ള ഒരു യുആർ‌എൽ "git: //git.host.xz/repo" ആയി എടുക്കുന്ന ഏത് സന്ദർഭത്തിലും മാറ്റിയെഴുതപ്പെടും. .git ".

പുഷിനായി മാത്രം URL കൾ മാറ്റിയെഴുതാൻ നിങ്ങൾ ആഗ്രഹിക്കുന്നുവെങ്കിൽ, നിങ്ങൾക്ക് ഫോമിന്റെ ഒരു കോൺഫിഗറേഷൻ വിഭാഗം സൃഷ്ടിക്കാൻ കഴിയും:
~~~
	[url "<actual url base>"]
		pushInsteadOf = <other url base>
~~~

ഉദാഹരണത്തിന്, ഇതുപയോഗിച്ച്:
~~~
	[url "ssh://example.org/"]
		pushInsteadOf = git://example.org/
~~~


"git: //example.org/path/to/repo.git" പോലുള്ള ഒരു URL പുഷുകൾക്കായി "ssh: //example.org/path/to/repo.git" ലേക്ക് മാറ്റിയെഴുതപ്പെടും, പക്ഷേ പുൾസ് ഇപ്പോഴും ഉപയോഗിക്കും യഥാർത്ഥ URL.

## ഉദാഹരണങ്ങൾ

* അപ്‌സ്ട്രീമിൽ നിന്ന് ക്ലോൺ ചെയ്യുക:
~~~
$ git clone git://git.kernel.org/pub/scm/.../linux.git my-linux
$ cd my-linux
$ make
~~~

* കാര്യങ്ങൾ പരിശോധിക്കാതെ നിലവിലെ ഡയറക്‌ടറിയിൽ നിന്ന് കടമെടുക്കുന്ന ഒരു പ്രാദേശിക ക്ലോൺ നിർമ്മിക്കുക:
~~~
$ git clone -l -s -n . ../copy
$ cd ../copy
$ git show-branch
~~~

* നിലവിലുള്ള പ്രാദേശിക ഡയറക്‌ടറിയിൽ‌ നിന്നും കടമെടുക്കുമ്പോൾ അപ്‌സ്ട്രീമിൽ നിന്ന് ക്ലോൺ ചെയ്യുക:
~~~
$ git clone --reference /git/linux.git \
	git://git.kernel.org/pub/scm/.../linux.git \
	my-linux
$ cd my-linux
~~~

* നിങ്ങളുടെ മാറ്റങ്ങൾ എല്ലാവർക്കുമായി പ്രസിദ്ധീകരിക്കുന്നതിന് നഗ്നമായ ഒരു ശേഖരം സൃഷ്ടിക്കുക:
~~~
$ git clone --bare -l /home/proj/.git /pub/scm/proj.git
~~~