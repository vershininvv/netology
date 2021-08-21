### Вопрос 1

    { "info" : "Sample JSON output from our service\t",
        "elements" :[
            { "name" : "first",
            "type" : "server",
            "ip" : 7175
            },
            { "name" : "second",
            "type" : "proxy",
            "ip" : "71.78.22.43"
            }
        ]
    }

### Вопрос 2

##!/usr/bin/env python3

    import socket as s
    import time as t
    import yaml
    import json
    
    servers = {'drive.google.com': '0.0.0.0', 'mail.google.com': '0.0.0.0', 'google.com': '0.0.0.0'}
    
    while 1 == 1:
        for host in servers:
            ip = s.gethostbyname(host)
            if ip != servers[host]:
                print('[ERROR] ' + str(host) + ' IP mistmatch: ' + servers[host] + ' ' + ip)
                with open(host + ".json", 'w') as js:
                    json_data = json.dumps({host: ip})
                    js.write(json_data)
                with open(host + ".yml", 'w') as ym:
                    yaml_data = yaml.dump([{host: ip}])
                    ym.write(yaml_data)
                servers[host] = ip
        t.sleep(5)

 