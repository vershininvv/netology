### Вопрос 1

Done

### Вопрос 2


НЕТ.

Жесткая ссылка и файл, для которой она создавалась имеют одинаковые inode. Поэтому жесткая ссылка имеет те же права доступа, владельца и время последней модификации, что и целевой файл. Различаются только имена файлов. Фактически жесткая ссылка это еще одно имя для файла.


### Вопрос 3

![img.png](img.png)

### Вопрос 4

![img_1.png](img_1.png)

### Вопрос 5

sfdisk -d /dev/sdb | sudo sfdisk /dev/sdc –force

![img_2.png](img_2.png)

### Вопрос 6

mdadm --create --verbose /dev/md0 -l 1 -n 2 /dev/sd{b1,c1}

![img_3.png](img_3.png)

### Вопрос 7

mdadm --create --verbose /dev/md1 -l 0 -n 2 /dev/sd{b2,c2}

![img_4.png](img_4.png)

### Вопрос 8

pvcreate /dev/md126 /dev/md127

![img_5.png](img_5.png)

### Вопрос 9

vgcreate vg01 /dev/md126 /dev/md127

![img_6.png](img_6.png)

![img_7.png](img_7.png)

### Вопрос 10

lvcreate -L 100 -ntestlv vg01 /dev/md126

![img_8.png](img_8.png)

### Вопрос 11

mkfs.ext4 /dev/vg01/testlv

![img_9.png](img_9.png)


### Вопрос 12

mount /dev/vg01/testlv /tmp/new

![img_10.png](img_10.png)

### Вопрос 13

wget https://mirror.yandex.ru/ubuntu/ls-lR.gz -O /tmp/new/test.gz

### Вопрос 14

![img_11.png](img_11.png)

### Вопрос 15

![img_12.png](img_12.png)

### Вопрос 16

![img_13.png](img_13.png)

### Вопрос 17

![img_14.png](img_14.png)

### Вопрос 18

![img_15.png](img_15.png)

### Вопрос 19

![img_16.png](img_16.png)

### Вопрос 20

![img_17.png](img_17.png)