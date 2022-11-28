from time import sleep
import random
from random import randint


status= "on"
pul = 0
help_score = 2
jokerler = ["A) 50/50", "B) Tamasacilar", "C) Telefon"]


def sual_cavab(sual, cavabs, duzcvb, mebleg, tamasacij, telefon):
  print(sual)
  sleep(3)
  for cavab in cavabs:
    print(cavab)
    sleep(1)
  yarismaci_cvb = input("Sizin cavabiniz nedir??(A-D veya Joker ucun J) ")
  if yarismaci_cvb.upper() == "J":
    secm_joker(duzcvb, mebleg, tamasacij, telefon)
  elif yarismaci_cvb.upper() == duzcvb:
    print(" ")
    duz_cavab(mebleg)
    sleep(2)        
  else:
    global help_score
    if help_score > 0:
      komek()
      for cavab in cavabs:
        print(cavab)
        sleep(1)
      yarismaci_cvb2 = input("Cavabiniz nedir??(A-D veya Joker ucun J) ")
      if yarismaci_cvb2.upper() == "J":
        secm_joker(duzcvb, mebleg, tamasacij, telefon)
      elif yarismaci_cvb2.upper() == duzcvb:
        print(" ")
        duz_cavab(mebleg)
        sleep(2)
      else:
        print(" ")
        game_over()
    else:
      print(" ")
      game_over()






def duz_cavab(mebleg):
  sleep(1)
  print("Sizin cavabiniz..")
  sleep(1)
  print("Dogrudurr!!")
  print(" ")
  sleep(1)
  print("*Alqis sesleri*")  
  global pul
  pul = mebleg
  print(" ")
  sleep(1)
  print(f"Çox yaxşi {name}, {pul} dollar qazandin!")
  print(" ")
  sleep(1)





def  secm_joker(duzcvb, mebleg, tamasacij, telefon):
  print(" ")  
  global jokerler
  if len(jokerler) == 0:
    print("Bağişlayin, jokeriniz qalmadi!")
    sleep(2)
    yarismaci_cvb = input("Sizin cavabiniz nedir? ")
    if yarismaci_cvb.upper() == duzcvb:
      print(" ")
      duz_cavab(mebleg)
      sleep(2)
    else:
      print(" ")
      game_over()    
  else:    
    print("Asagidaki jokerleriniz var:")
    sleep(2)
    for joker in jokerler:
      print(f"{joker}-Joker")
      sleep(1)
    joker_selection = input("Hansi jokerden istifade edirsiniz?")
    if joker_selection.upper() == "A":
      jokerler.remove("A) 50/50")
      jokerA(duzcvb, mebleg)
    elif joker_selection.upper() == "B":
      jokerler.remove("B) Tamasacilar")
      jokerB(duzcvb, mebleg, tamasacij)
    elif joker_selection.upper() == "C":
      jokerler.remove("C) Telefon")
      jokerC(duzcvb, mebleg, telefon)





def jokerA(duzcvb, mebleg):
  answers = ["A", "B", "C", "D"]
  joker_cvb= [duzcvb]  
  answers.remove(duzcvb)
  number = randint(0, 2)
  joker_cvb.append(answers[number])
  joker_cvb.sort()
  sleep(1)
  print(".")
  sleep(1)
  print("..")
  sleep(1)
  print("...")
  sleep(1)  
  print(f"Qalan cavablar{joker_cvb[0]} and {joker_cvb[1]}")
  sleep(3)
  yarismaci_cvb = input("Sizin cavabiniz nedir? ")
  if yarismaci_cvb.upper() == duzcvb:
    print(" ")
    duz_cavab(mebleg)
    sleep(2)
  else:
    print(" ")
    game_over()


def jokerB(duzcvb, mebleg, tamasacij):
  sleep(1)
  print(".")
  sleep(1)
  print("..")
  sleep(1)
  print("...")
  sleep(1)
  print(f"Tamasacilarin cavabi: {tamasacij}")
  sleep(3)
  yarismaci_cvb = input("Sizin cavabiniz nedir? ")
  if yarismaci_cvb.upper() == duzcvb:
    print(" ")
    duz_cavab(mebleg)
    sleep(2)
  else:
    print(" ")
    game_over()




def jokerC(duzcvb, mebleg, telefon):
  sleep(1)
  print(".")
  sleep(1)
  print("..")
  sleep(1)
  print("...")
  sleep(1)
  print(f"Sizin telefon jokeriniz bele deyir:")
  sleep(1.5)
  print(telefon)
  sleep(3)
  yarismaci_cvb = input("Sizin cavabiniz nedir? ")
  if yarismaci_cvb.upper() == duzcvb:
    print(" ")
    duz_cavab(mebleg)
    sleep(2)
  else:
    print(" ")
    game_over()





def komek():
  global help_score
  help_score -= 1
  sleep(1.5)
  print(" ")
  print("Duzgun cavab verdiyinizden eminsiniz??")
  sleep(2)
  print("yeniden cehd edin:")
  sleep(2)    



def game_over():
  global status
  status = "off"
  print("Sizin cavabiniz...")
  sleep(1)
  print("YANLISDIRRR!")
  print(" ")
  sleep(1)
  print(f"teessufler olsunki {name}, sen uduzdun!")
  print(" ")
  print(" ")
  sleep(1)
  print("OYUN BITTI!")



def getmek_qalmaq():
    global status
    status="on"
    print(f"{name} siz {pul} dollar pul qazandin")
    sleep(0.5)
    print("davam edirsiz yoxsa pulu goturub gedirsiz?")
    global cavb
    cavb=int(input("Qerarinizi bura daxil edin:"))

    if cavb=="Devam":
        print("yaxsi")
    elif cavb=="pulu goturub gedirem" or "Pulu goturub gedirem":
        game_over()

print(" ")
print(" ")
print(" ")  
print("Xanimlarr vee beylerrr ekrann basindaa bizii izleyenlerr")
print(" ")
sleep(1.3)
print("Verlisimizin yeni bolumune xos geldiniz")
print(" ")
sleep(0.7)
print("Kim")
sleep(0.7)
print("Milyoncu")
sleep(0.7)
print("Olmaq")
sleep(0.7)
print("Isteyir")
sleep(0.7)
print("Baslayirr")
sleep(0.7)


print("Gunun ilkk yarismacisiii")
sleep(1.5)
print("...eeeee....")
print(" ")
sleep(1.5)
name = input("Cox uzr istirem adiniz tekrar deye bilersiz? ")
print("aa caox sag olun ele ise devam edek")
print(" ")
sleep(1.5)
print(f"Eziz tamasacilar zehmet olmasa {name.upper()}!  bey/xanima Alqislarrr" )
print(" ")
sleep(2)
print("*Alqis sesleri*")
print(" ")
sleep(2)

print("Demeli sizin cemi  3 joker haqqiniz var:")
sleep(2)
for joker in jokerler:
  print(f"{joker}-Joker")
  sleep(1.5)
print("ve siz bu jokkerleri cemi bir defe istifade ede bilersiniz.")
sleep(2.5)
print(" ")
print(" ")
print("Hazirsinizsa baslayaq?")
print(" ")
sleep(1.5)
print("Aha baslayaq")
sleep(1.5)




sual1 = "Azerbaycanin paytaxti haradir?"
cavab1 = ["A.Italya","B.Istanbul","C.Qax","D.Baki"]
duzgun_cvb1 = "D"
qazanilan_pul1 = 50
tamasacij1 = ["A: 0%", "B: 2%", "C: 0%", "D: 98%"]
telefon1 = ("Elbetdeki Baki")




sual2= "Pythonda kodu ekrana hansi funksiya cap edir?"
cavab2 = ["A.sep=""","B.print()","C.end=""","D.list=[]"]
duzgun_cvb2 = "B"
qazanilan_pul2 = 100
tamasacij2=  ["A: 2%", "B: 95%", "C: 2%", "D: 1%"]
telefon2 =("Deqiq bilmirem amma mence printdir")







sual3="Azerbaycan elifbasinda nece  ses var"
cavab3 = ["A.34","B.9","C.32","D.30"]
duzgun_cvb3 = "A"
qazanilan_pul3 = 200
tamasacij3= ["A: 15%", "B: 10%", "C: 75%", "D: 0%"]
telefon3 = ("34 ses vardir")




sual4="Riyaziyyatda nece emel var"
cavab4 = ["A.2","B.4","C.5","D.6"]
duzgun_cvb4 ="B" 
qazanilan_pul4 = 300
tamasacij4= ["A: 28%", "B: 3%", "C: 68%", "D: 1%"]
telefon4 =("4 emel var")

 

sual5="Step it academy Azerbaycana necenci ilde gelmisdir" 
cavab5 = ["A.2016","B.2015","C.2020","D.1998"]
duzgun_cvb5 = "A"
qazanilan_pul5 = 500
tamasacij5= ["A: 21%", "B: 12%", "C: 19%", "D: 48%"]
telefon5 =("Sehv etmiremse 2016ci ilde")




sual6= "Azerbaycan dilinde nece samit ses var?"
cavab6 = ["A.20","B.19","C.23","D.11"]
duzgun_cvb6 = "C"
qazanilan_pul6 = 1000
tamasacij6= ["A: 21%", "B: 4%", "C: 58%", "D: 17%"]
telefon6 = ("Cavab  23 dur beli 23")






sual7="Turkiyenin paytaxti haradir?" 
cavab7 =  ["A.Seki","B.Qax","C.Istanbul","D.Ankara"] 
duzgun_cvb7 = "D"
qazanilan_pul7 = 2000
tamasacij7= ["A: 4%", "B: 3%", "C: 11%", "D: 82%"]
telefon7 = ("Bunun cavabi cox asanddir  elbetdeki Ankara")







sual8= "Step it academynin nece  olkede filiali var"
cavab8 =  ["A.21","B.1","C.30","D.13"] 
duzgun_cvb8 = "A"
qazanilan_pul8 = 4000
tamasacij8= ["A: 72%", "B: 12%", "C: 14%", "D: 2%"]
telefon8 = ("Ayda bunu deqiq bilmirem deyesen  30 olmali idi")






sual9 = "Facebookun  quruscusu kimdir?"
cavab9 = ["A.Mark Zukerberq","B.Ferid Camalov","C.Eliaga Hesenov","D.Cavid Huseynov"]
duzgun_cvb9 = "A"
qazanilan_pul9 = 8000
tamasacij9= ["A: 48%", "B: 38%", "C: 14%", "D: 0%"]
telefon9= ("eee deyesen  Mark Zukerberq idi")






sual10 = "Pythonun qurucusu kimdir?"
cavab10 = ["A.Mark Zukerberq","B.Ferid Camalov","C.Guido van Rossum","D.Ismayil Qehremanli"]
duzgun_cvb10 = "C"
qazanilan_pul10 = 16000
tamasacij10 =  ["A: 15%", "B: 8%", "C: 77%", "D: 0%"]
telefon10 =("Ahaa bunu bilirem  cavab Guido van Rossumdur")






sual11 = "Cizgi film qehramani pinokyanun burnu ne edende uzanirdi?"
cavab11 = ["A.Yemek yeyende","B.Su icende","C.Yalan danisanda","D.Oturanda"]
duzgun_cvb11 = "C"
qazanilan_pul11= 32000
tamasacij11 = ["A: 17%", "B: 42%", "C: 39%", "D: 2%"]
telefon11 = ("Eeee..  sehv etmiremse  yalan danisanda burnu uzanirdi")






sual12 ="Azerbaycan dilinde nece sait ses var?" 
cavab12 = ["A.10","B.9","C.16","D.23"]
duzgun_cvb12 = "B"
qazanilan_pul12 = 64000
tamasacij12 = ["A: 19%", "B: 26%", "C: 28%", "D: 27%"]
telefon12 =("Ciddisen?! buna gorede joker istifade ederler hec elbetdeki  B varianti")





sual13 ="Milyoncu verlisini pythonda duzelden sexsin adi nedir?"
cavab13 = ["A.Ferid","B.Elekber","C.Cavid","D.Mahmud"]
duzgun_cvb13 = "A"
qazanilan_pul13 = 125000
tamasacij13 = ["A: 32%", "B: 29%", "C: 28%", "D: 11%"]
telefon13 = ("Bunuda bilmemek olar? elbetdeki Ferid")




sual14 = "Visual codeni windows neceye yuklemek olmur?"
cavab14 =  ["A.Windows 11","B.Windows 10","C.Windows 10 pro","D.Windows 7"]
duzgun_cvb14 = "D"
qazanilan_pul14 = 500000
tamasacij14 = ["A: 9%", "B: 31%", "C: 11%", "D: 49%"]
telefon14 =("Cavab  A variantidir mence")






sual15 = "2-ci qarabag muharibesi nece gun devam etmirdir?"
cavab15 = ["A.44","B.30","C.45","D.50"]
duzgun_cvb15 = "A"
qazanilan_pul15 = 1000000








sual_cavab(sual1, cavab1, duzgun_cvb1, qazanilan_pul1, tamasacij1, telefon1)

if status == "on":
    sual_cavab(sual2, cavab2, duzgun_cvb2, qazanilan_pul2, tamasacij2, telefon2)

if status == "on":
    sual_cavab(sual3, cavab3, duzgun_cvb3, qazanilan_pul3, tamasacij3, telefon3)

if status == "on":
    sual_cavab,getmek_qalmaq(sual4, cavab4, duzgun_cvb4, qazanilan_pul4, tamasacij4, telefon4)

if status == "on":
    sual_cavab(sual5, cavab5, duzgun_cvb5, qazanilan_pul5, tamasacij5, telefon5)

if status == "on":
    sual_cavab(sual6, cavab6, duzgun_cvb6, qazanilan_pul6, tamasacij6, telefon6)

if status == "on":
    sual_cavab(sual7, cavab7, duzgun_cvb7, qazanilan_pul7, tamasacij7, telefon7)

if status == "on":
    sual_cavab(sual8, cavab8, duzgun_cvb8, qazanilan_pul8, tamasacij8, telefon8)

if status == "on":
    sual_cavab(sual9, cavab9, duzgun_cvb9, qazanilan_pul9, tamasacij9, telefon9)

if status == "on":
    sual_cavab(sual10, cavab10, duzgun_cvb10, qazanilan_pul10, tamasacij10, telefon10)

if status == "on":
    sual_cavab(sual11, cavab11, duzgun_cvb11, qazanilan_pul11, tamasacij11, telefon11)

if status == "on":
    sual_cavab(sual12, cavab12, duzgun_cvb12, qazanilan_pul12, tamasacij12, telefon12)

if status == "on":
    sual_cavab(sual13, cavab13, duzgun_cvb13, qazanilan_pul13, tamasacij13, telefon13)

if status == "on":
    sual_cavab(sual14, cavab14, duzgun_cvb14, qazanilan_pul14, tamasacij14, telefon14)

if status == "on":
    sual_cavab(sual15, cavab15, duzgun_cvb15, qazanilan_pul15)






    if status == "on":
        print("Tebriklerr!!!!!!")
    sleep(2)
    print(" ")
    print("Siz qazandinizz ")
    sleep(2)
    print("Bir")
    sleep(1)
    print("Milyon!!")
    sleep(1)
    print("Dollar!!!!!!!!!!!!!!!!")
    print(" ")
    print(" ")
    sleep(2)
    sleep(3)
    print("O ARIQ")
    print(" ")
    sleep(1.5)
    print("Unudulmaz yeni milyonerdir: ")
    print(" ")
    sleep(3)
    print(f"{name.upper()}!!!")
    sleep(1.5)
    print("*Alqis sesleri*")
    sleep(1.5)
    print(f"   {name.upper()}!!!")
    sleep(1)
    print(f"   {name.upper()}!!!")
    sleep(1)
    print(f"   {name.upper()}!!!")
    sleep(1)
    print(f"   {name.upper()}!!!")
    sleep(1)
    print("   ...")
    sleep(3)
    print(" ")
    print(" ")
    print(" ")
    print("SON")



