# Crestron-Pushover-Module

v1.1 - Add's support for PushOver's URL attribute.  Unfortunately, my testing showed that this doesn't work to open an app.  It only works to open a webpage from a notification.  Other people in the
PushOver community have reported this problem.  PushOver has not implemented a fix.

Licensing

The Prowl notifications module, PushOver notifications module, and Vybit notifications module all provides the ability for a Crestron program to send push notifications to a homeowner's smart phone and/or tablet.   With these modules you can, for example:

1.	Send a notification to a smart phone when the burglar alarm is tripped.  
2.	Send a notification to a smart phone when the temperature in the house gets too cold and there is risk of a pipe freezing.

There are minor differences in functionality between the three modules that may make one a better fit for a specific client than the others.

The modules are all written in Simpl# and each has an example program demonstrating its use as well as detailed help files.

This family of modules is released as shareware.  As a developer the modules are free for use on your own personal Crestron system.  Dealers are also invited to use them in their showrooms.  However, if you decide to use any, or all of them, on customer systems where you, or the dealer/csp you work for will profit from them than I ask for a single payment of $100.  

What you get is 

1) My thanks
2) Permission to use Prowl module, PushOver module, and Vybit module on as many client projects as you want
3) A copy of the Simpl# source code for each module (only a binary executable is included with each example program)
4) Good Karma

You can contact me at jay.m.basen@gmail.com to arrange for payment.

Thanks

Jay Basen

_________________________________________________________

This module works with PushOver push notifications.  It consists of the 
core S# module PushOver.clz and a Simpl+ wrapper PushOver v1.0.usp
 & PushOver v1.0.ush. The usp and ush files should be placed in 
your Crestron Usrsplus directory.  The INCLUDEPATH statement in the 
PushOver.usp file must be modified to point to the directory where you plan 
on placing the PushOver.clz file.  There have been problems reported when 
this file is simply placed in the Crestron Usrsplus directory.

An example program, Pushover Module Demo.smw is provided to further show how 
the module can be used.  

IMPORTANT
1) YOU NEED TO OBTAIN AN APPLICATION TOKEN FROM PUSHOVER TO USE THIS MODULE
YOU CAN DO THAT HERE: https://pushover.net/apps/build.  I'M NOT INCLUDING
AN APPLICATION TOKEN SO THAT EACH DEALER WILL BE RESPONSIBLE FOR THE 
VOLUME OF NOTIFICATIONS SENT BY THEIR CUSTOMERS
2) WHEN A CUSTOMER REGISTERS THEIR SMART PHONE APP WITH PUSHOVER THEY WILL BE
SENT AN EMAIL WITH THEIR USER ID THAT NEEDS TO BE INCLUDED TO ROUTE NOTIFICATIONS
TO THEM.

Inputs
    Init              - Pulse to initialize communications
    Send              - Pulse to send notification to PushOver app after the Token$,
                      - User$, Title$, and Message$ string inputs have been set.
	Priority          - -2=Lowest, -1=Low, 0=Normal, 1=High, 2=Emergency
    User$             - User to send the notification to
    Title$            - Optional Title of the notification or "" if there is none
    Sound$            - Name of sound to be played see https://pushover.net/api#sounds
    Message$          - Text of the notification

Outputs
    None
		
Paramteters
    Token$           - Application token obtained from PushOver
    Debug_Msg_Output - Where to Send Debug Messages - None, Console, Error Log, or Both
