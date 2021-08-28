# coding:utf-8
import random

a = [random.randint(0, 9),
     random.randint(0, 9),
     random.randint(0, 9),
     random.randint(0, 9)]

# 為了測試顯示答案
#print(str(a[0]) + str(a[1]) + str(a[2]) + str(a[3]))

while True :
    # Lesson 5-4的程式
    #判斷是否為4位數字
    isok = False
    while isok == False:
        b = input("輸入數字>")
        if len(b) != 4:
            print("請輸入四位數字")
        else:
            kazuok = True
            for i in range(4):
                if (b[i] < "0") or (b[i] > "9"):
                    print("並非數字 ")
                    kazuok = False
                    break
            if kazuok:
                isok = True

    # 當輸入為4位數字時
    # 判斷Hit
    hit = 0
    for i in range(4):
      if a[i] == int(b[i]):
        hit = hit + 1

    # 判斷Blow
    blow = 0
    for j in range(4):
      for i in range(4):
        if (int(b[j]) == a[i]) and (a[i] != int(b[i])) and (a[j] != int(b[j])):
          blow = blow + 1
          break

    # 顯示Hit與Blow數量
    print(" Hit " + str(hit))
    print(" Blow " +  str(blow))

    # 當Hit為4時結束
    if hit == 4:
        print("Good Job!")
        break
