# review
## host, network review
    - pdee 10.10.91.12
        - arkime 
    - ellie 10.10.91.10
    - asus router
        - wan address 173.166.130.91
            - asus route 
            - wan port 8005
            - lan ellie port 8005

## ssh tunnel set on ellie
    -$ ssh -L 10.10.91.10:8005:10.10.91.12:8005 pdee@10.10.91.12

## on tr9210 (mac two)
    - in browser
    - http://173.166.130.91:8005
    - access to akime

# created user ivwall
for IN trip