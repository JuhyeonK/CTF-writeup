# TRUSTCTF-writeup

44등 – 디미고가고싶은주현이

비록 두 문제 풀었지만 라이트업 써볼래요,,


### MIC CHECK!-100

TRUST{Welcome_CTF_Have_FUN!}

이 플래그 슥 붙여넣으면 된다

```Flag : TRUST{Welcome_CTF_Have_FUN!}```

### MESS – 100
 
~~Ida 다운이 잘못되었는지 실행이 안된다. 
급한대로~~ 올리디버거로 까서 플래그를 출력하는 부분을 찾았다 ~~(노가다…)~~
그 위에 실행시 출력되는 코드가 있다. 
프로그램 실행시 나오는 "X8HWj<UF:x\5wI" 위치에 
"S3CRe7PA5sW0rD"가 있길래 input에 집어넣었더니 
나왔다

```Flag : TRUST{bBRWt>UHD?5wQ}```

### Easy Taebo - 100

태보를 이모티콘으로 하란다…
생각나는대로 Pwntool로 일일이 치환해줬다

```
from pwn import *

p = remote("server.trustctf.com", 44923)

start = p.recvuntil("Taebo 1 :")

left_jab = '@==(^0^)@ '
left_mid_jab = '@=(^0^)@ '
mid_jab = '@(^0^)@ '
right_mid_jab = '@(^0^)=@ '
right_jab = '@(^0^)==@ '
left_hook = '@(^0^)@== '
right_hook = '==@(^0^)@ '
left_speedball = '@@@(^0^) '
right_speedball = '(^0^)@@@ '
left_kick = '@||(^0^)==@ '
mid_kick = '@==(^||^)==@ '
right_kick = '@==(^0^)||@ '

for i in range(1, 101):
    taebo = p.recvuntil(">>")
    repp = taebo.replace("+", "")
    repb = repp.replace(" ", "")
    sentence = repb.replace(">>", "")
    c1 = sentence.replace("left_jab", left_jab)
    c2 = c1.replace("right_mid_jab", right_mid_jab)
    c3 = c2.replace("left_mid_jab", left_mid_jab)
    c4 = c3.replace("mid_jab", mid_jab)
    c5 = c4.replace("right_jab", right_jab)
    c6 = c5.replace("left_hook", left_hook)
    c7 = c6.replace("right_hook", right_hook)
    c8 = c7.replace("left_speedball", left_speedball)
    c9 = c8.replace("right_speedball", right_speedball)
    c10 = c9.replace("left_kick", left_kick)
    c11 = c10.replace("mid_kick", mid_kick)
    c12 = c11.replace("right_kick", right_kick)
    print(taebo)
    print(c12)
    p.sendline(c12)
    print("send~!")
    if(i==100):
        break
    start = p.recvuntil(":")

flag = p.recvuntil("}")
print(flag)
```
~~정말 보기 싫은 코드다~~
 
```Flag : TRUST{w0w_y0u_9o7_4_w0nd3fu1_b0dy_lik3_m3}```
