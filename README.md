# YoloV3 custom model face_detector and personal color discriminator

![image](https://user-images.githubusercontent.com/75519839/172169889-6ec9035f-496a-4dff-a476-c3b41c9b48b7.png)

Language : Python
<img src = "https://user-images.githubusercontent.com/75519839/153009836-fc8e76bd-754c-4061-81c8-7a3a396b8144.png" width="30px">

---

## Contents ๐

### How to use โก๏ธ
- [1. Install](#install-)
- [2. File info](#-file-information-and-how-to-use-)

### Introduce Project ๐จ๐ปโ๐ป
- [1. Introduction](#1-ํ๋ก์ ํธ-์๊ฐ-)
- [2. Project process](#2-์ ์-๊ณผ์ -๋ฐ-๊ฐ์ค-์๋ฆฝ-)
- [3. Face detector result](#3-์ผ๊ตด-์ธ์-๊ฒฐ๊ณผ-)
- [4. Result](#4-๊ฐ์ค๊ฒ์ -๊ฒฐ๊ณผ-%EF%B8%8F)
- [5. Service](#)

---

## Install ๐ฎ
<pre><code>pip install -r requirements.txt</code></pre>
The file was produced in Python version 3.8. ๐ง


## ๐ File Information and How to use ๐
### ๐๐ปโ๏ธ We've broken down the folders for future convenience!

- Data_files are the files needed to spin the model.
- Use make_weights to learn the model of Darknet.
- We have saved the weights we have learned since then in data_files(weights, model).
- Make a model similar to yolo using make_yolo_model.
- Use the weight of data_files(weights, model) to learn transitions in the model you created.
- Save the transferred model in data_files(weights, model).
- Based on the model, use face_detection to detect objects (face recognition).
- Separate the face through crop_face.
- Analyze only the skin of the face separated by face_color.
- Sample and outputs are the locations where you store the pictures that you turn to the model.

๐ฐ๐ท ํ์ผ ์ ๋ณด ๋ฐ ์ฌ์ฉ๋ฒ ๐ฐ๐ท
### ๐๐ปโโ๏ธ ์ถํ์ ์ฌ์ฉํ๊ธฐ ํธํ๊ธฐ ์ํด ํด๋๋ฅผ ์ธ๋ถํํด์ ๋๋์์ต๋๋ค!

- data_files ํด๋๋ ํด๋น ๋ชจ๋ธ์ ๋๋ฆฌ๊ธฐ์ํด ํ์ํ ํ์ผ๋ค์๋๋ค.
- make_weights ํด๋๋ฅผ ์ฌ์ฉํด์ Darknet์ ๋ชจ๋ธ์ ํ์ต์ํต๋๋ค.
- ์ดํ ํ์ต์ํจ ๊ฐ์ค์น๋ฅผ data_files(weights, model)ํด๋์ ์ ์ฅํด๋์์ต๋๋ค.
- make_yolo_modelํด๋์ ์ฌ์ฉํด์ yolo์ ๋น์ทํ ํํ์ ๋ชจ๋ธ์ ๋ง๋ญ๋๋ค.
- ๋ง๋  ๋ชจ๋ธ์ data_files(weights, model)ํด๋์ ๊ฐ์ค์น๋ฅผ ์ฌ์ฉํ์ฌ ์ ์ดํ์ตํฉ๋๋ค.
- ์ ์ดํ์ต ์ํจ ๋ชจ๋ธ์ data_files(weights, model)ํด๋์ ์ ์ฅํฉ๋๋ค.
- ๋ชจ๋ธ์ ๊ธฐ๋ฐ์ผ๋ก face_detectionํด๋๋ฅผ ์ด์ฉํ์ฌ ๊ฐ์ฒด ํ์ง(์ผ๊ตด ์ธ์)์ ํฉ๋๋ค.
- crop_faceํด๋๋ฅผ ํตํด ์ผ๊ตด์ ๋ฐ๋ก ๋ถ๋ฆฌํฉ๋๋ค.
- face_colorํด๋๋ฅผ ํตํด ๋ฐ๋ก ๋ถ๋ฆฌํ ์ผ๊ตด์ ํผ๋ถ๋ง ๋ถ๋ฆฌํ์ฌ ๋ถ์ํฉ๋๋ค.
- sampleํด๋์ outputsํด๋๋ ๋ชจ๋ธ์ ๋๋ฆฌ๋ ์ฌ์ง๋ค์ ๋ณด๊ดํ๋ ์์น์๋๋ค.

---

## ๐ฐ๐ท The contents below are written in Korean.
If you are curious about the project, please use a translator!

## 1. ํ๋ก์ ํธ ์๊ฐ ๐
- ํด๋น ํ๋ก์ ํธ๊ฐ ์ถ๊ตฌํ๋ **์ต์ข ๋ชฉํ๋ ์ผ๊ตด์ธ์๋ชจ๋ธ์ ๋ง๋ค์ด ์ต์ข์ ์ผ๋ก ํผ์ค๋ ์ปฌ๋ฌ์ ์ถ์ฒํด์ฃผ๋ ์๋น์ค**์๋๋ค.
- ํ์ฌ๋ก์ ๊ตฌํ๋ ๊ธฐ๋ฅ์ ๊ธฐ์กด์ ์ผ๊ตด ์ธ์๋ชจ๋ธ๋ณด๋ค **ํฅ์๋ ์ฑ๋ฅ์ ์ปค์คํ ๋ชจ๋ธ**์ ๋ง๋ค์์ต๋๋ค.
- ํ๋ก์ ํธ์ ์ฌ์ฉ๋ ๋ชจ๋ธ์ ๊ธฐ๋ฐ์ Joseph Redmon์ด ๋ง๋  ํ๋ ์์ํฌ darknet์๋๋ค.
- <img src = "https://user-images.githubusercontent.com/75519839/172173445-c961bebd-8e28-4b57-b592-9f41b2828633.png" width="150px"></img>
    - pjreddie์ ๋คํฌ๋ท ๋งํฌ : [pjreddie's Darknet github](https://github.com/pjreddie/darknet)
    - pjreddie์ ์ฌ์ดํธ : [pjreddie site](https://pjreddie.com/) 


## 2. ์ ์ ๊ณผ์  ๋ฐ ๊ฐ์ค ์๋ฆฝ ๐ฟ
<img width="1151" alt="image" src="https://user-images.githubusercontent.com/75519839/172172896-f6a553bb-50b8-40ed-be48-eb601023a5c5.png">

- ๊ฐ์ค ์๋ฆฝ
    - ๋ชจ๋ธ์ ์ง์  ๊ตฌํํ๋ค๋ฉด ๊ธฐ์กด ๋ชจ๋ธ๋ณด๋ค ์ฑ๋ฅ์ด ์ข์๊น?
    - ์ฌ์ ํ์ต์ ๋ด๊ฐ ๋ง๋ ๋ค๋ฉด ์ด๋ค ์ ์ด ๋ค๋ฅผ๊น?
    - OpenCV๋ฅผ ์ฌ์ฉํ ๊ฒ๊ณผ ์ํ ๊ฒ์ ์ฐจ์ด๋ ๋ฌด์์ด ์์๊น?
    - ๋ด ์ผ๊ตด์ ํผ์ค๋ ์ปฌ๋ฌ๋ ๋ฌด์์ธ๊ฐ?

## 3. ์ผ๊ตด ์ธ์ ๊ฒฐ๊ณผ ๐


<img width="1328" alt="image" src="https://user-images.githubusercontent.com/75519839/172174854-5087e018-68fd-416c-9ff1-a35db09b3b58.png"></img>
- ์ข : ๊ธฐ์กด์ YoloV3
- ์ฐ : ์ปค์คํ ๋ชจ๋ธ

## 4. ๊ฐ์ค๊ฒ์  ๊ฒฐ๊ณผ โญ๏ธ

<img width="840" alt="image" src="https://user-images.githubusercontent.com/75519839/172175878-f11f884c-0e26-459e-856a-9b18808d35ff.png">
<img width="700" alt="image" src="https://user-images.githubusercontent.com/75519839/172175356-d46e0a1d-2659-4b01-b842-c7f06f681d5e.png">

- Q. ๋ชจ๋ธ์ ์ง์  ๊ตฌํํ๋ค๋ฉด ๊ธฐ์กด ๋ชจ๋ธ๋ณด๋ค ์ฑ๋ฅ์ด ์ข์๊น?
    - A-1. ๋์์ธ์ ๋ํ ์ธ์์ ๊ธฐ์กด์ ๋ชจ๋ธ์ด ์ฑ๋ฅ์ด ๋ ์ข์๋ค.
    - A-2. ์ผ๋ถ ์ด๋ฏธ์ง(๋์์ธ์ค ์๊ตฌ์ ์ธ ์ผ๊ตด, ์ผ๊ตด์ด๋ฏธ์ง๊ฐ ํ์คํ ๊ฒฝ์ฐ)์๋ ์ง์  ๊ตฌํํ ๋ชจ๋ธ์ด ์ฑ๋ฅ์ด ๋ ์ข์๋ค.
    - A-3. ์ ์ฒด์ ์ธ ์ฑ๋ฅ์ ๊ธฐ์กด ๋ชจ๋ธ ๋๋ OpenCV๊ฐ ์ ๊ฐ ๋ง๋  ๋ชจ๋ธ์ ๋นํด์ ๋ ์ข์๋ค.ย 

- Q. ์ฌ์ ํ์ต์ ๋ด๊ฐ ๋ง๋ ๋ค๋ฉด ์ด๋ค ์ ์ด ๋ค๋ฅผ๊น?
    - A-1. ๋ด ์๋ง์ ๋ง๊ฒ๋ ์ปค์คํํ  ์ ์๋ค๋ ์ ์๋ค.
    - A-2. ๋ฐ์ดํฐ๋ง ์ ์ฐพ๋๋ค๋ฉด ํด๋น ๋ชจ๋ธ์ด ๊ธฐ์กด ๋ชจ๋ธ๋ณด๋ค ์ข์๊ฑฐ๋ผ๋ ์๊ฐ์ด ๋ ๋ค.
    
- Q. OpenCV๋ฅผ ์ฌ์ฉํ ๊ฒ๊ณผ ์ํ ๊ฒ์ ์ฐจ์ด๋ ๋ฌด์์ด ์์๊น?
    - A-1. ์ง์  ๊ตฌํํ๋ ๋งํผ ์ปค์คํ์ด ๊ฐ๋ฅํ๋ค.
    - A-2. ๋ด๊ฐ ๊ตฌํํ๋ฉด ๋ฌธ์ ๋ ๋ง๊ณ , ๋ฐ์ดํฐ์ ์์ง๊ณผ ํ์ต์ ์ ํ์ด ๋ง๋ค.
    - A-3. ์ง์  ๊ตฌํ์ ํ ๊ฒ์ ๋ชจ๋ธ์ด ๋ฌด๊ฒ๊ธฐ ๋๋ฌธ์ ์ค์ฌ์ฉ์ ์ด๋ ค์ธ ๊ฒ์ด๋ค.

- Q. ๋ด ์ผ๊ตด์ ํผ์ค๋ ์ปฌ๋ฌ๋ ๋ฌด์์ธ๊ฐ?
    - ๊ตฌํ์ค

## 5. ์๋น์ค ๊ตฌํ ๐

- 
