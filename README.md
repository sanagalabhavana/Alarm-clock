from tkinter import *
import time 
import datetime 
from threading import *
import winsound

clock = Tk()
clock.geometry("450x250")

def Threading():
    t1 = Thread(target=alarm)
    t1.start()

def alarm():
    while True:
        Set_Alarm = f'{hour.get()}:{minute.get()}:{second.get()}'
        current_time = datetime.datetime.now().strftime("%H:%M:%S")

        print(current_time,Set_Alarm)
    if current_time == Set_Alarm:
        print("Wake up!")
        winsound.Playsound("sound.mp3",winsound.SND_ASYNC)


Label(clock,text="Alarm clock",fg="red").pack(pady=10)
Label(clock,text="Set Time").pack()

frame = Frame(clock)
frame.pack()

hour = StringVar(clock)
hours = ('00', '01', '02', '03', '04', '05', '06', '07', '08', '09', '10', '11', '12', '13', '14', '15', '16', '17', '18', '19', '20', '21', '22', '23', '24')

hrs = OptionMenu(frame,hour,*hours)
hrs.pack(side=LEFT)

minute = StringVar(clock)
minutes = ('00', '01', '02', '03', '04', '05', '06', '07', '08', '09', '10', '11', '12', '13', '14', '15', '16', '17', '18', '19', '20', '21', '22', '23', '24'
         '25', '26', '27', '28', '29', '30', '31', '32', '33', '34', '35', '36', '37', '38', '39', '40', '41','42', '43', '44', '45', '46', '47', '48', '49', '50'
          '51','52', '53', '54', '55', '56', '57', '58', '58', '60')
mins = OptionMenu(frame,minute,*minutes)
mins.pack(side=LEFT)

second = StringVar(clock)
seconds = ('00', '01', '02', '03', '04', '05', '06', '07', '08', '09', '10', '11', '12', '13', '14', '15', '16', '17', '18', '19', '20', '21', '22', '23', '24'
         '25', '26', '27', '28', '29', '30', '31', '32', '33', '34', '35', '36', '37', '38', '39', '40', '41','42', '43', '44', '45', '46', '47', '48', '49', '50'
          '51','52', '53', '54', '55', '56', '57', '58', '58', '60')
sec = OptionMenu(frame,second,*seconds)
sec.pack(side=LEFT)

Button(clock,text="SetbAlarm",command=Threading).pack(pady=20)
clock.mainloop()
