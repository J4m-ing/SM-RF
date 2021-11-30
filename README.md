# SM-RF

import tkinter as tk
import tkinter.messagebox as tkMessageBox
import time



Ypp = tk.Tk()
Ypp.title('열정을 품은 파이썬')
Ypp.geometry('1366x768+100+100')
Ypp.resizable(0,0)

lab1= tk.Label(Ypp, text = "열품파", font ="Verdana 30 bold")
lab1.pack(side = "top", ipady = 40)

lab2 = tk.Label(Ypp, text= "오늘 할일", font = "Verdana 22 bold")
lab2.place(relx= 0.15, rely = 0.1)

frame_L = tk.Frame(Ypp, relief = "solid", bd = 1, bg = 'white') 
frame_L.pack(side = "left", fill = "both", expand =True)

frame_R = tk.Frame(Ypp, relief = "solid", bd = 1) 
frame_R.pack(side = "right", fill = "both", expand = True)

listbox = tk.Listbox(frame_L, selectmode = 'extended', bd = 0, height = 7, width = 40, font = ("Verdana 25 bold"))
listbox.place(relx=0, rely=0)

ListN = tk.StringVar()

def listup():
    aList = ListN.get()
    listbox.insert('end',aList)
    entry.delete(0, len(entry.get()))
 
entry= tk.Entry(frame_L, width=40, font = ("Verdana 17 bold"), textvariable = ListN)
entry.place(relx = 0, rely = 0.94)

button= tk.Button(frame_L, text = " 입력 ", width=8, font = ("Verdana 16 bold"), command = listup)
button.place(relx = 0.82, rely = 0.94)


'''
entry.bind("<Return>", ent_p()) 

'''

entry.insert(0, "ex)수학 공부하기")

def clear(event):
    if entry.get() == "ex)수학 공부하기":
        entry.delete(0, len(entry.get()))

entry.bind("<Button-1>", clear)
def delete():
    entry.bind()

def listdel():
    listbox.delete(0)
    

buttondel = tk.Button(frame_L, text = "삭제", width = 7, font = ("Verdana 15 bold"), command = listdel)
buttondel.place(relx = 0.85, rely = 0)

def listdel1():
    listbox.delete(1)


buttondel1 = tk.Button(frame_L, text = "삭제", width = 7, font = ("Verdana 15 bold"), command = listdel1)
buttondel1.place(relx = 0.85, rely = 0.065)

def listdel2():
    listbox.delete(2)


buttondel2 = tk.Button(frame_L, text = "삭제", width = 7, font = ("Verdana 15 bold"), command = listdel2)
buttondel2.place(relx = 0.85, rely = 0.13)

def listdel3():
    listbox.delete(3)


buttondel3 = tk.Button(frame_L, text = "삭제", width = 7, font = ("Verdana 15 bold"), command = listdel3)
buttondel3.place(relx = 0.85, rely = 0.195)

def listdel4():
    listbox.delete(4)


buttondel4 = tk.Button(frame_L, text = "삭제", width = 7, font = ("Verdana 15 bold"), command = listdel4)
buttondel4.place(relx = 0.85, rely = 0.26)

def listdel5():
    listbox.delete(5)


buttondel5 = tk.Button(frame_L, text = "삭제", width = 7, font = ("Verdana 15 bold"), command = listdel5)
buttondel5.place(relx = 0.85, rely = 0.325)

def listdel6():
    listbox.delete(6)


buttondel6 = tk.Button(frame_L, text = "삭제", width = 7, font = ("Verdana 15 bold"), command = listdel6)
buttondel6.place(relx = 0.85, rely = 0.39)



#################


from datetime import datetime
counter = 54000
running = False
def counter_label(label): 
    def count(): 
        if running: 
            global counter 
            if counter==54000:             
                display="Starting..."
            else:
                tt = datetime.fromtimestamp(counter)
                string = tt.strftime("%H:%M:%S")
                display=string 
    
            label['text']=display   
            label.after(1000, count)  
            counter += 1
    
    count()      
    
def Start(label): 
    global running 
    running=True
    counter_label(label) 
    start['state']='disabled'
    stop['state']='normal'
    reset['state']='normal'
    
def Stop(): 
    global running 
    start['state']='normal'
    stop['state']='disabled'
    reset['state']='normal'
    running = False
    
def Reset(label): 
    global counter 
    counter=54000
    
    if running==False:       
        reset['state']='disabled'
        label['text']='Welcome!'
    
    else:                
        label['text']='Starting...'
    

label_f =tk.Label(frame_R, width=40)
label_f.place(relx = 0.1, rely = 0.01 )
start = tk.Button(label_f, text='Start', width=6, command=lambda:Start(label),font="Verdana 10 bold") 
stop = tk.Button(label_f, text='Stop',width=6,state='disabled', command=Stop, font="Verdana 10 bold") 
reset = tk.Button(label_f, text='Reset',width=6, state='disabled', command=lambda:Reset(label), font="Verdana 10 bold") 
start.pack(side="left") 
stop.pack(side ="left") 
reset.pack(side="left")
label = tk.Label(frame_R, text="Welcome!", fg="pink", font="Verdana 23 bold") 
label.place(relx = 0.5, rely = 0)


counter1 = 54000
running1 = False
def counter_label1(label1): 
    def count1(): 
        if running1: 
            global counter1 
    
            if counter1==54000:             
                display1="Starting..."
            else:
                tt1 = datetime.fromtimestamp(counter1)
                string1 = tt1.strftime("%H:%M:%S")
                display1=string1
    
            label1['text']=display1   
            label.after(1000, count1)  
            counter1 += 1
    
    count1()      
    
def Start1(label1): 
    global running1 
    running1=True
    counter_label1(label1) 
    start1['state']='disabled'
    stop1['state']='normal'
    reset1['state']='normal'
    
def Stop1(): 
    global running1 
    start1['state']='normal'
    stop1['state']='disabled'
    reset1['state']='normal'
    running1 = False
    
def Reset1(label): 
    global counter1 
    counter1=54000
    
    if running1==False:       
        reset1['state']='disabled'
        label1['text']='Welcome!'
    
    else:                
        label1['text']='Starting...'
    

label_f1 =tk.Label(frame_R, width=40)
label_f1.place(relx = 0.1, rely = 0.075 )
start1 = tk.Button(label_f1, text='Start', width=6, command=lambda:Start1(label1),font="Verdana 10 bold") 
stop1 = tk.Button(label_f1, text='Stop',width=6,state='disabled', command=Stop1,font="Verdana 10 bold") 
reset1 = tk.Button(label_f1, text='Reset',width=6, state='disabled', command=lambda:Reset1(label1),font="Verdana 10 bold") 
start1.pack(side="left") 
stop1.pack(side ="left") 
reset1.pack(side="left")
label1 = tk.Label(frame_R, text="Welcome!", fg="pink", font="Verdana 23 bold") 
label1.place(relx = 0.5, rely = 0.065)


counter2 = 54000
running2 = False
def counter_label2(label2): 
    def count2(): 
        if running2: 
            global counter2 
    
            if counter2==54000:             
                display2="Starting..."
            else:
                tt2 = datetime.fromtimestamp(counter2)
                string2 = tt2.strftime("%H:%M:%S")
                display2=string2
    
            label2['text']=display2    
            label.after(1000, count2)  
            counter2 += 1
    
    count2()      
    
def Start2(label2): 
    global running2
    running2=True
    counter_label2(label2) 
    start2['state']='disabled'
    stop2['state']='normal'
    reset2['state']='normal'
    
def Stop2(): 
    global running2 
    start2['state']='normal'
    stop2['state']='disabled'
    reset2['state']='normal'
    running2 = False
    
def Reset2(label): 
    global counter2
    counter2=54000
    
    if running2==False:       
        reset2['state']='disabled'
        label2['text']='Welcome!'
    
    else:                
        label2['text']='Starting...'
    

label_f2 =tk.Label(frame_R, width=40)
label_f2.place(relx = 0.1, rely = 0.14 )
start2 = tk.Button(label_f2, text='Start', width=6, command=lambda:Start2(label2),font="Verdana 10 bold") 
stop2 = tk.Button(label_f2, text='Stop',width=6,state='disabled', command=Stop2,font="Verdana 10 bold") 
reset2 = tk.Button(label_f2, text='Reset',width=6, state='disabled', command=lambda:Reset2(label2),font="Verdana 10 bold") 
start2.pack(side="left") 
stop2.pack(side ="left") 
reset2.pack(side="left")
label2 = tk.Label(frame_R, text="Welcome!", fg="pink", font="Verdana 23 bold") 
label2.place(relx = 0.5, rely = 0.13)

counter3 = 54000
running3 = False
def counter_label3(label3): 
    def count3(): 
        if running3: 
            global counter3 
    
            if counter3==54000:             
                display3="Starting..."
            else:
                tt3 = datetime.fromtimestamp(counter3)
                string3 = tt3.strftime("%H:%M:%S")
                display3=string3
    
            label3['text']=display3   
            label.after(1000, count3)  
            counter3 += 1
    
    count3()      
    
def Start3(label3): 
    global running3
    running3=True
    counter_label3(label3) 
    start3['state']='disabled'
    stop3['state']='normal'
    reset3['state']='normal'
    
def Stop3(): 
    global running3 
    start3['state']='normal'
    stop3['state']='disabled'
    reset3['state']='normal'
    running3 = False
    
def Reset3(label3): 
    global counter3
    counter3=54000
    
    if running3==False:       
        reset3['state']='disabled'
        label3['text']='Welcome!'
    
    else:                
        label3['text']='Starting...'
    

label_f3 =tk.Label(frame_R, width=40)
label_f3.place(relx = 0.1, rely = 0.205)
start3 = tk.Button(label_f3, text='Start', width=6, command=lambda:Start3(label3),font="Verdana 10 bold") 
stop3 = tk.Button(label_f3, text='Stop',width=6,state='disabled', command=Stop3,font="Verdana 10 bold") 
reset3 = tk.Button(label_f3, text='Reset',width=6, state='disabled', command=lambda:Reset3(label3),font="Verdana 10 bold") 
start3.pack(side="left") 
stop3.pack(side ="left") 
reset3.pack(side="left")
label3 = tk.Label(frame_R, text="Welcome!", fg="pink", font="Verdana 23 bold") 
label3.place(relx = 0.5, rely = 0.195)

counter4 = 54000
running4 = False
def counter_label4(label4): 
    def count4(): 
        if running4: 
            global counter4 
    
            if counter4==54000:             
                display4="Starting..."
            else:
                tt4 = datetime.fromtimestamp(counter4)
                string4 = tt4.strftime("%H:%M:%S")
                display4=string4
    
            label4['text']=display4   
            label.after(1000, count4)  
            counter4 += 1
    
    count4()      
    
def Start4(label4): 
    global running4
    running4=True
    counter_label4(label4) 
    start4['state']='disabled'
    stop4['state']='normal'
    reset4['state']='normal'
    
def Stop4(): 
    global running4 
    start4['state']='normal'
    stop4['state']='disabled'
    reset4['state']='normal'
    running4 = False
    
def Reset4(label4): 
    global counter4
    counter4=54000
    
    if running4==False:       
        reset4['state']='disabled'
        label4['text']='Welcome!'
    
    else:                
        label4['text']='Starting...'
    

label_f4 =tk.Label(frame_R, width=40)
label_f4.place(relx = 0.1, rely = 0.27 )
start4 = tk.Button(label_f4, text='Start', width=6, command=lambda:Start4(label4),font="Verdana 10 bold") 
stop4 = tk.Button(label_f4, text='Stop',width=6,state='disabled', command=Stop4,font="Verdana 10 bold") 
reset4 = tk.Button(label_f4, text='Reset',width=6, state='disabled', command=lambda:Reset4(label4),font="Verdana 10 bold") 
start4.pack(side="left") 
stop4.pack(side ="left") 
reset4.pack(side="left")
label4 = tk.Label(frame_R, text="Welcome!", fg="pink", font="Verdana 23 bold") 
label4.place(relx = 0.5, rely = 0.26)

counter5 = 54000
running5 = False
def counter_label5(label5): 
    def count5(): 
        if running5: 
            global counter5 
    
            if counter5==54000:             
                display5="Starting..."
            else:
                tt5 = datetime.fromtimestamp(counter5)
                string5 = tt5.strftime("%H:%M:%S")
                display5=string5
    
            label5['text']=display5   
            label.after(1000, count5)  
            counter5 += 1
    
    count5()      
    
def Start5(label5): 
    global running5
    running5=True
    counter_label5(label5) 
    start5['state']='disabled'
    stop5['state']='normal'
    reset5['state']='normal'
    
def Stop5(): 
    global running5 
    start5['state']='normal'
    stop5['state']='disabled'
    reset5['state']='normal'
    running5 = False
    
def Reset5(label5): 
    global counter5
    counter5=54000
    
    if running5==False:       
        reset5['state']='disabled'
        label5['text']='Welcome!'
    
    else:                
        label5['text']='Starting...'
    

label_f5 =tk.Label(frame_R, width=40)
label_f5.place(relx = 0.1, rely = 0.335 )
start5 = tk.Button(label_f5, text='Start', width=6, command=lambda:Start5(label5),font="Verdana 10 bold") 
stop5 = tk.Button(label_f5, text='Stop',width=6,state='disabled', command=Stop5,font="Verdana 10 bold") 
reset5 = tk.Button(label_f5, text='Reset',width=6, state='disabled', command=lambda:Reset5(label5),font="Verdana 10 bold") 
start5.pack(side="left") 
stop5.pack(side ="left") 
reset5.pack(side="left")
label5 = tk.Label(frame_R, text="Welcome!", fg="pink", font="Verdana 23 bold") 
label5.place(relx = 0.5, rely = 0.325)

counter6 = 54000
running6 = False
def counter_label6(label6): 
    def count6(): 
        if running6: 
            global counter6 
    
            if counter6==54000:             
                display6="Starting..."
            else:
                tt6 = datetime.fromtimestamp(counter6)
                string6 = tt6.strftime("%H:%M:%S")
                display6=string6
    
            label6['text']=display6   
            label.after(1000, count6)  
            counter6 += 1
    
    count6()      
    
def Start6(label6): 
    global running6
    running6=True
    counter_label6(label6) 
    start6['state']='disabled'
    stop6['state']='normal'
    reset6['state']='normal'
    
def Stop6(): 
    global running6 
    start6['state']='normal'
    stop6['state']='disabled'
    reset6['state']='normal'
    running6 = False
    
def Reset6(label6): 
    global counter6
    counter6=54000
    
    if running6==False:       
        reset6['state']='disabled'
        label6['text']='Welcome!'
    
    else:                
        label6['text']='Starting...'
    

label_f6 =tk.Label(frame_R, width=40)
label_f6.place(relx = 0.1, rely = 0.4 )
start6 = tk.Button(label_f6, text='Start', width=6, command=lambda:Start6(label6),font="Verdana 10 bold") 
stop6 = tk.Button(label_f6, text='Stop',width=6,state='disabled', command=Stop6,font="Verdana 10 bold") 
reset6 = tk.Button(label_f6, text='Reset',width=6, state='disabled', command=lambda:Reset6(label6),font="Verdana 10 bold") 
start6.pack(side="left") 
stop6.pack(side ="left") 
reset6.pack(side="left")
label6 = tk.Label(frame_R, text="Welcome!", fg="pink", font="Verdana 23 bold") 
label6.place(relx = 0.5, rely = 0.39)

def popup():
    OpenS = tk.Toplevel(Ypp)
    OpenS.geometry('1366x768')
    image1=tk.PhotoImage(file=r"C:\Users\김혜수\Desktop/수고했어 오늘도.png")
    ILabel= tk.Label(OpenS, image=image1)
    ILabel.pack()
    OpenS.mainloop()

def pop():
   OpenF = tk.Toplevel(Ypp)
   OpenF.geometry('1366x768')
   image2=tk.PhotoImage(file=r"C:\Users\김혜수\Desktop/내일도 파이팅.png")
   ILabe2= tk.Label(OpenF, image=image2)
   ILabe2.pack()
   OpenF.mainloop()
   
button1 = tk.Button(Ypp, text="완료", width = 5, font=("Verdana 20 bold"), command = popup)
button1.place(x=860, y=700)

button2 = tk.Button(Ypp, text="실패", width = 5, font=("Verdana 20 bold"), command = pop)
button2.place(x=1040, y=700)

Ypp.mainloop()

