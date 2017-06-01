## Basic Ankhbot Gamble File

This is a basic txt file that lists $addpoints and $removepoints commands to mimic the revlo gambling command. 

## Code Example

By using ankhbot's $readrandline() a random output will be selected from the file. The file consists of lines like the ones below. 0-59 is a loss. 60-97 is a win. 98-100 will give the user 2x the payout.

$removepoints("$user","$num2","$num2","Rolled 59 $user lost $value $currencyname","Something borked","true")
$addpoints("$user","$num2","$num2","Rolled 60 $user won $value $currencyname","Something borked")

$addpoints("$user","$num2","$num2","Rolled 98  $user won $value $currencyname","Something borked") $addpoints("$user","$num2","$num2","AND $value BONUS $currencyname","Something borked")

The currency name must be specified after the gamble command and before the bet amount.

!gamble points 100

Points being the currency name. Changes to currency name won't affect the command. So long as users type the new currency name.

## Motivation

Since Revlo is shutting down I figured I'd come up with a quick and dirty solution to use ankhbot to have a similar gambling game for viewers.

## Installation

I recommend placing the txt file here C:\ProgramData\Microsoft\Windows\Start Menu\Programs\AnkhHeart\AnkhBotR2\

Create your command in ankhbot and in the "response" field put the following.

$readrandline(C:\ProgramData\Microsoft\Windows\Start Menu\Programs\AnkhHeart\AnkhBotR2\gamble.txt)

Alternatively if you decided to put the file somewhere else, specify the location accordingly.