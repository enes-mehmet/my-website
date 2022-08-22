---
title: "My first big project PolyPharm"
date: 2022-07-30T12:14:34+06:00
description: "How, why and what did I do at this project"
author: "Mehmet Enes Onuş"
type: "post"
---

### How did we decide to start this project

Before moving on to how I did this project, what technologies I used, etc., I would like to explain the thinking behind this project and how we got to this point in this project. Almost all of us have a relative in our family who uses some type of medicine. Older people, in particular, take more pills than prescribed, take pills more often, and most likely sometimes forget to take their medication, due to different prescriptions. All these possibilities lead to serious medical problems for people all over the world. According to [WHO](https://www.who.int/news/item/29-03-2017-who-launches-global-effort-to-halve-medication-related-errors-in-5-years), Medication errors cause 1 death per day and 1.3 million injuries per year in the United States alone. Especially developed countries suffer from medication errors due to the fact that developed countries have a much higher elderly population than other countries. According to [EuroStat](https://ec.europa.eu/eurostat/web/products-eurostat-news/-/ddn-20210316-1), 20.6% of Europeans are over the age of 65 in 2020. This number was approximately %17 one decade ago. This high rate leads to many elderly people who live alone and have no one to follow their medication, and they often harm themselves by making medication errors. My medical student friend Furkan and I saw this growing problem and thought of a medicine tracking system that would suitably overcome these problems and started our PolyPharm project.

### What exactly is our project?

PolyPharm project is basically a smart medicine vending machine that communicates with a database and a mobile application. Vending machine is the core part of our system and it is based on a Raspberry Pi Zero 2 SBC(Single Board Computer) and an Arduino UNO microcontroller board. I selected 2 different boards since Raspberry Pi is much more convenient for IoT work and project can be much more scalable with a mini computer while Arduino is the best fit for controlling electronical parts such as motors. There are 3 types of users: Patients, people responsible for patients and doctor. Device has 9 different containers that has minimum capacity of 150 pills each so it can take at least 1350 pills* meaning device can be used approximately 3 months without loading any medicine to it. As the pill sizes are variable, the amount of pills that can be loaded may vary.

*Pills are 12mm long 4mm thick cylinders

### How does this system work?

Suppose that there is a user using our system. When the time for taking pills comes machine will sound an alarm for user to take his/her medicine. After that alarm machine’s NFC reader will be open for reading. If patient puts the special medicine taking unit which has the proper NFC tag to the exit of the device, device will read the NFC and start to give medicines that patient needs and create a record that indicates medicines are taken by patient and send this record to database. If patient does not take the medicine, device will send a notification to person/people responsible for that patient that he/she did not take the medicines at first alarm. After some time of not taking medicines device will not give medicines to patient in order to prevent overdose and create a record about that and send it to databases. That data can be seen by both doctor of that patient and people responsible for him/her. Thanks to this system, treatment follow-up will be provided very easily and safely, and the burden of medicine tracking will be reduced.

### Which technologies are used at this project?

First of all I would like to explain why did I select a Pi and an Arduino for our project and not only one of them. Pi is very convenient for things like sending data to database, controlling touchscreen and have an OS on it that can be used much easier than an Arduino. Arduino on the other side is much more convenient for controlling electronical parts such as motors than Pi since constantly sending signals from Pi’s multiple GPIO pins would cause problems at Pi so with the help of [Electron](https://www.electronjs.org/) and [Johnny-Five](http://johnny-five.io/,) I got them to join forces. I used electron to create machine’s user interface since my web development skills are much better than my GUI skills. Johnny-Five is a Firmata based JavaScript framework for controlling electronical parts via an Arduino UNO.

While developing our system, I realized that we need 2 types of databases, one of which is the local database stored in the local storage of the medicine vending machine. This local database ensures that the right medication is given to the patient at the right time and amount in case of internet connection problems. Other database is a Firebase realtime database that is being used by our medicine vending machine and mobile application. Firebase database stores users’ data and patients’ medicine records. Firebase database is used to distribute relevant patient data to doctors and people responsible from patients. 

Mechanical parts of this system is also 3D Designed by me and electronical system design was also made by me. If I talk about those parts this blog will be too much to read so let me know if you want further information about them via contact page of my website :) You can find photos and videos of project below.


### Video

{{< youtube wPaRQQW4An4 >}}

### Photos

- #### Device
{{< figure src="/images/blog/PolyPharm/renderAll.png" >}}
{{< figure src="/images/blog/PolyPharm/renderCup.jpg" >}}
{{< figure src="/images/blog/PolyPharm/ss.png" >}}

- #### UI
{{< figure src="/images/blog/PolyPharm/ui1.jpeg" >}}
{{< figure src="/images/blog/PolyPharm/ui2.jpeg" >}}
{{< figure src="/images/blog/PolyPharm/ui3.jpeg" >}}
{{< figure src="/images/blog/PolyPharm/ui4.jpeg" >}}
{{< figure src="/images/blog/PolyPharm/ui5.jpeg" >}}















