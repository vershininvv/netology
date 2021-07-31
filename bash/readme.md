### Вопрос 1

  1) a+b - просто складывает 2 строки
  2) 1+2 - интерпритатор не понимает, что нужно складывать числа и просто берет 2 переменные и делает из них строку
  3) 3 - интерпритатор понимает, что мы будем работать с перменными как с числами

### Вопрос 2

	#!/usr/bin/env bash
	while ((1==1))
	do
			curl https://localhost:4757
			if (($? != 0))
			then
					date >> curl.log
			else
					break
			fi
	done


### Вопрос 3

    #!/usr/bin/env bash
    
    ip_table=(192.168.0.1 8.8.8.8 173.194.222.113)
    port=80
    amount_of_test=5
    
    echo START > log
    for ip in ${ip_table[@]}
    do
            i=1
            echo ------------------------------- >> log
            echo Start testing $ip >> log
            while (($i<=amount_of_test))
            do
                    nmap $ip -p $port | grep open
                    if (($?==0))
                    then
                            echo $ip port $port OPEN >> log
                    else
                            echo False >> log
                    fi
                    let "i += 1"
            done
    done

### Вопрос 4

    #!/usr/bin/env bash

    ip_table=(173.194.222.113 173.194.222.113 92.168.0.1 8.8.8.8 173.194.222.113)
    port=80
    amount_of_test=5
    
    echo START > log
    while ((1==1))
    do
            for ip in ${ip_table[@]}
            do
                    nmap $ip -p $port | grep open
                    if (($?!=0))
                    then
                            echo $ip >> log
                            exit
                    fi
            done
    
    done
