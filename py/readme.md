### Вопрос 1

  1. ни какое, будет ошибка компиляции
  2. c = str(a) + b
  3. c = a + int(b)

### Вопрос 2

#!/usr/bin/env python3

    import os
    
    path = "~/devops-netology/"
    bash_command = [f"cd {path}", "git status --long -s"]
    result_os = os.popen(' && '.join(bash_command)).read()
    is_change = False
    for result in result_os.split('\n'):
        if result.find('AM ') != -1:
            prepare_result = result.replace('AM ', '')
            print(path+prepare_result)
        if result.find('?? ') != -1:
            prepare_result = result.replace('?? ', '')
            print(path+prepare_result)


### Вопрос 3

    #!/usr/bin/env python3

    import os
    import pathlib
    
    path = input('Input address: ')
    
    path1 = pathlib.Path(f'{path}/.git/')
    
    if path1.exists():
        bash_command = [f"cd {path}", "git status --long -s"]
        result_os = os.popen(' && '.join(bash_command)).read()
        is_change = False
        for result in result_os.split('\n'):
            if result.find('AM ') != -1:
                prepare_result = result.replace('AM ', '')
                print(path + prepare_result)
            if result.find('?? ') != -1:
                prepare_result = result.replace('?? ', '')
                print(path + prepare_result)
    else:
        print("not in git repo")

### Вопрос 4
    
    ##!/usr/bin/env python3
    
    import socket as s
    import time as t
    
    servers = {'drive.google.com': '0.0.0.0', 'mail.google.com': '0.0.0.0', 'google.com': '0.0.0.0'}
    
    while 1 == 1:
        for host in servers:
            ip = s.gethostbyname(host)
            if ip != servers[host]:
                print('[ERROR] ' + str(host) + ' IP mistmatch: ' + servers[host] + ' ' + ip)
                servers[host] = ip
        t.sleep(5)
