**_Alice 2 (Charlie)_**
## Mission 1 : Establishing Classical Communication
*80 minutes of gameplay [70/200 points]*

As a "security" company which mainly focuses on spying on other companies, you obtain an intel from your informant that Alice and Bob is developing a new communication channel based on old TV remotes.

The companies Alice and Bob are reputable, and you want to test the reliability and security of their technology. Thanks to the abilities of your informant, he managed to make a copy of the necessary tecnical documents. **The aim of this mission is to understand what Alice and Bob are up to (by developing the same IR communication channel), and then look for a way to spy on their channel.**

This mission is divided into smaller tasks, which consist of compulsory and optional tasks. The compulsory tasks are marked with either [Checkpoint], [Final Task], or [Secret Task] flags, while the unmarked tasks are optional (if you are lazy). It is thus a priority to complete all the flagged tasks before the optional tasks, as one will not be able to revisit these tasks after the deadline. The compulsory tasks are very important for the upcoming missions. You are also strongly advised to plan the distribution of tasks among your teammates.
<br><br>

#### [10 points] BREAK the ice, STOMP the ground, LIFT the air
> *This is sort of compulsory, but only to get the group going :P*

Objectives:
1. Choose a team captain,
1. Write down a short company manifesto, and
1. Take a team photo.

Point allocation scheme:
* [Max] points upon completion of the objectives.

Guidelines on how to form a team:
1. A good team is a team whose members knows each other pretty well.
1. A good team is also a team which can split the tasks in an efficient manner. Actually sooner or later, your team might be split into 2 (or even 3) subteams. So, plan well ahead.

#### [30 points] [Checkpoint] Without the electronics, there is NONE
> *Resistor: I'm gonna ask you this one time, where is the circuit?*

> *Transistor: Yeah, I'll do you one better, WHO is the circuit?*

> *Diode: I'll do YOU one better, WHY is the circuit?*

> *- 1 divided by 0*

Objective: Construct two circuits, one capable of sending IR signals, and one capable of receiving IR signals. This means, you need to emulate both Alice and Bob. You might also want to split the team into 2, taking on the roles of the `sender / Alice` and the `receiver / Bob`. The objective is accomplished when both sender and receiver circuits are built and working properly.

Upon the completion of this task, you **might receive** another copy of sender and receiver ciruit. Why? Because the `GameMasters`might be nice and lend you another copy of the circuit :)

**Very important notes**: Read the safety precautions in Section 1.2.1 of the technical documents. This is *extremely important*, as you will get tested about this at the end of the session (not joking, we'll definitely test you!).

Point allocation scheme:
* [Max] points upon correct, efficient, and stable implementation of the circuits, or
* [80%] of total points upon successful implementation of the circuits, but not necessarily correct, efficient, nor stable.
* An incentive would be awarded if your cover is not blown.

Step by step walkthrough:
1. Gather all the necessary components, and note down the polarity and the pin assignments. The facilitator will give a short lecture and demonstration about using the breadboard, but in case you missed it, you can refer to Section 1.2.3.
1. Construct the circuit according to the diagram, noting the polarity and the pin assignment. *If the polarity or pin assignment is incorrect, you might burn the components.* If you are unsure about anything, feel free to ask the facilitator.
1. There are two ways to proceed. <br>
**[First way: the open way]** Construct the sender and receiver circuit on the same breadboard using the same Arduino. However, you will need the help from the `GameMaster` to send/receive IR signals from the main computer. You may disrupt Alice and Bob in the process, as they will be performing similar tasks at the same time. Your cover might be blown... <br>
**[Second way: the discreet way]** Construct the sender and receiver facing each other, each connected to different Arduinos, and preferably two different computers. You can send with one Arduino and receive with another one. However, you might want to cover up the devices with a box or something similar, because you don't want Alice or Bob to detect your IR signal. Though they might ask you what the box is for...
1. Upload the Arduino program `ArduinoClassical.ino` to the correct device. You might want to use terminal command `dmesg` to look for the device address, typically in the form of `/dev/ttyACM0` or `/dev/ttyUSB0`.
1. When the upload completes, you can open the serial monitor with `Shift+Ctrl+M`. Try to send `HELP` to the Arduino, and look at the reply. Try to send blinking signal with `SBLINK`  or receive blinking signal with `RBLINK`. For sender, you should be able to see the blinking IR light with your phone camera (except iPhone. Haha!). For the receiver, you should see the indicator light blinking, and the serial monitor prints `BLINK!`.
<br><br>

#### [10 points] Asymmetrical cryptography handout
> *When cryptography is outlawed, bayl bhgynjf jvyy unir cevinpl.*

> *-  John Perry Barlow*

Objective: Complete the `Asymmetrical Cryptography` handout. No cheating or copying from Eve allowed [insert stern warning].

Point allocation scheme:
* Based on the number of correct responses in the handout.

Note: Only do this when there is free time or when there is a member in your group who happens to be free.
<br><br>

#### [20 points] [Final Task] Let's make them chat
> *The Internet: transforming society and shaping the future through chat.*

> *- Dave Barry*

Objectives:
1. Successfully communicate a message from sender to receiver via the IR link by using the program `send_message.py` and `recv_message.py`,
1. Chatting (i.e. send a few messages back and forth) by using the program `chatting.py`.

Point allocation scheme:
* [Max] points by completing all the objectives **within 60 minutes** from the start of Mission 1 (leaving 10 more minutes to wrap up other tasks), or,
* [80%] of total points by completing all the objectives within the time limit, or,
* Maximum of [80%] of total points, proportional to the effort and the number of completed tasks at the end of the time limit.

Step by step walkthrough:
1. With the new copy of the circuit, emulate the role of Alice and Bob who tries to chat. Construct it such that the receivers and senders (for both sides) are facing each other, and that each sides are connected to a different Arduino, and also preferably different computers. You might or might not need the cover box, depending on the choice that you made previously.  
1. First, test the fidelity of the signal. The sender can run `send_testQ.py` and the receiver can run `recv_testQ.py`. The programs will just send and receive `Qc!8` repeatedly. Test also for the other direction of communication. Note that you may need to modify the device address at `devloc_classical.txt`.
1. To try sending a longer messages, the sender can run `send_message.py` and the receiver can run `recv_message.py`.
1. If everything works nicely, both sides can run `chatting.py`. One side can turn into listening mode by pressing an `Enter` button. By now you should be able to chat across computers, like what Alice and Bob is doing right now.
