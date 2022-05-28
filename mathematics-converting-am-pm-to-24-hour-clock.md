# Convertisseur d'horloge de 24 heures : Comment convertir AM/PM en heure de 24 heures

![image cover](https://www.freecodecamp.org/news/content/images/size/w2000/2022/01/pexels-cottonbro-5185163.jpg)
    Il existe deux méthodes principales pour indiquer l'heure. Tout d'abord, il y a l'horloge de 12 heures qui utilise AM et PM, puis il y a l'horloge de 24 heures.

La plupart des pays préfèrent la méthode de l'horloge de 24 heures, mais l'horloge de 12 heures est largement utilisée en Amérique latine et dans les pays anglophones. Dans la méthode de l'horloge de 12 heures, il est 12 heures deux fois par jour, à minuit (AM) et à midi (PM).

Le tableau ci-dessous indique la conversion entre les systèmes d'horloge de 12 heures et de 24 heures :

```
12 hour clock  | 24 hour clock 
============   |===============
12:00 AM 	   | 00:00
01:00 AM 	   | 01:00
02:00 AM 	   | 02:00
03:00 AM 	   | 03:00
04:00 AM 	   | 04:00
05:00 AM 	   | 05:00
06:00 AM 	   | 06:00
07:00 AM 	   | 07:00
08:00 AM 	   | 08:00
09:00 AM 	   | 09:00
10:00 AM 	   | 10:00
11:00 AM 	   | 11:00
12:00 PM 	   | 12:00
01:00 PM 	   | 13:00
02:00 PM 	   |14:00
03:00 PM 	   |15:00
04:00 PM 	   |16:00
05:00 PM 	   |17:00
06:00 PM 	   |18:00
07:00 PM 	   |19:00
08:00 PM 	   |20:00
09:00 PM 	   |21:00
10:00 PM 	   |22:00
11:00 PM 	   |23:00
```

### Horloge de 12 heures

La journée est divisée en deux périodes de 12 heures allant de minuit à midi (heures AM) et de midi à minuit (heures PM).

Les abréviations AM et PM viennent du latin :

+ AM : ante meridiem, avant midi
+ PM : post meridiem, après midi.

### Horloge de 24 heures

La journée s'étend de minuit à minuit et est divisée en 24 heures de 0 (minuit) à 23. Le temps est indiqué en heures et minutes depuis minuit.
Conversion d'une horloge de 12 heures en une horloge de 24 heures

À partir de la première heure de la journée (de 0 h ou minuit à 0 h 59), soustrayez 12 heures :

## Conversion d'une horloge de 12 heures en une horloge de 24 heures

En partant de la première heure du jour (12:00 AM ou minuit à 12:59 AM), soustrayez 12 heures :

+ 12:00 AM = 0:00
+ 12 H 15 = 0 H 15

De 1h00 du matin à 12h59, les heures et les minutes restent les mêmes :

+ 9:00 AM = 9:00
+ 12:59 PM = 12:59

Pour les heures entre 13h00 et 23h59, ajoutez 12 heures :

+ 15:17 PM = 15:17
+ 11:59 PM = 23:59.

Conversion d'une horloge de 24 heures en une horloge de 12 heures

En partant de la première heure de la journée (0:00 / minuit à 0:59), ajoutez 12 heures et AM à l'heure :

+ 0:30 = 12:30 AM
+ 0:55 = 12:55 AM

De 1:00 à 11:59, il suffit d'ajouter AM à l'heure :

+ 2:25 = 2:25 AM
+ 9:30 = 9:30 AM

Pour les heures comprises entre 13:00 et 23:59, soustrayez 12 heures et ajoutez PM à l'heure :

+ 16:55 = 4:55 PM
+ 21:45 = 9:45 PM


