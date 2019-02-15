# TRUSTCTF-writeup

44등 – 디미고가고싶은주현이

비록 두 문제 풀었지만 라이트업 써볼래요,,

~~사진은 나중에 첨부~~

### MIC CHECK!-100

TRUST{Welcome_CTF_Have_FUN!}

이 플래그 슥 붙여넣으면 된다

Flag : TRUST{Welcome_CTF_Have_FUN!}

### MESS – 100
다운받고 실행하면 이런다.
 
~~Ida 다운이 잘못되었는지 실행이 안된다. 
급한대로~~ 올리디버거로 까서 플래그를 출력하는 부분을 찾았다 ~~(노가다…)~~
 
그 위에 실행시 출력되는 코드가 있다. 
프로그램 실행시 나오는 "X8HWj<UF:x\5wI" 위치에 
"S3CRe7PA5sW0rD"가 있길래 input에 집어넣었더니 
나왔다

Flag : TRUST{bBRWt>UHD?5wQ}

### Easy Taebo - 100

태보를 이모티콘으로 하란다…
생각나는대로 Pwntool로 일일이 치환해줬다
 
Flag : TRUST{w0w_y0u_9o7_4_w0nd3fu1_b0dy_lik3_m3}
