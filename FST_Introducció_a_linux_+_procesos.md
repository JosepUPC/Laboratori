# Practica 1
## Introduccó alinux + procesos

* Exercisis preliminars
* Exercisis de procesos

---

### Exercisis preliminars

1. Obre una Mate Terminal i excuta el comandament per obrir el manual de "ps". Una vegada en el manual del comandament "ps", troba i compta el número de vegades que apareix er patró **ppid**.

![picture 1](P1_sc1.png)

> execuat el comandament [man ps] y el shortcut [/ppid], s'han compat un total de 8 vegades el patró ppid.(afegint aquells que estaben en mayúscula). 

2.  Amb la mateixa terminal, executa "ps" amb els parametres correctes, per tal de poder observar el PID, el *tty* y el comandament dels actuals procesos actius que s'han aat execuat des de la terminal. Fes el mateix en la consola virtual numero 2 (/dev/tty2).

![picture 2](P1_sc2.png)

> executan el mateix codi en la consola virtual ens queda tal que:

```c
user2@eel-lab030-02:~$ ps -a
    PID     TTY     TIME        CMD
    4862    tty2    00:00:00    bash
    4876    tty2    00:00:00    ps
user2@eel-lab030-02:~$  
```

3. Executa les següents comandaments: 

```c
$ ps -o pid,comm
$ ps -o pid,cmd
```
Comenta les diferencies entre les opcions: *cmd* i *comm*.

>Aparentment, el comandament "ps", amb el parametre "comm" indica junt amb el PID, el nom del proces. A diferencia d'aquest, el paramtre "comm" afegeix al nom els parametres que s'han executat junt amb ell (el process).

![picture 3](P1_sc3.png)

4. Utilitza el comandament *pstree* per veure el arbre de procesos del sistema. Quin es el proces pare del *pstree*? i el seu avi? i qui son la reslta dels seus relatius?

![picture 4](P1_sc4.png)

5. Opre una terminal secundaria i llavors, obre un nou "TAB" probant CRL+SHIFT+t. Ara, obre una altra terminal secundaria en una altra finestra. Utilitzant el *pstree*, has de comentar la relacion entre els procesos executats en les terminals que hem obert.

![picture 5](P1_sc5.png) 

6. Escriu tipus ALT+F2 y llavors tipus *xterm*. Fixat que aquesta sequencia obre un altre nou tipus de terminal. Repteix la mateixa seqüencia per obrir un nou *xterm*. Ara, observa el arbre de procesos i comenta les diferencies respecte al resultat dels anteriors casos. 

![picture 6](P1_sc6.png)

7. Obre 3 terminals secundaries. Hauran de anotar-se com t1, t2, t3. Llavors, escriu lo següent: 

```c
t1$ xeyes -geometry 200x200 -center red
t2$ xclock &
```
Comenta que es lo que veus y també quin es el tipus de execució (frontal/fondo) de cada terminal.

> la primera linia de comandament exectua un sencill proces, *uns ulls que següeixent el cursor*. L'altre linea de comandament executa una proces que ens mostra un rellotge analógic. El primer proces d'exeuta de forma frontal (*foreground*) y el segon de fondo (*background*). 

![picture 7](P1_sc7.png)

8. Per a cada proces de les aplicacions prèvies (*xeyes* i *xclock*), adivina el PID, l'estat d'execucció, el *tty* y el PPID. Per a fer-ho, utilitza la 3a terminal (t3).

![picture 8](P1_sc8.png)

9. Utilitzant la 3a terminal(t3), envia una señal per a finalitzar el proces *xeyes*. 

![picture 9](P1_sc9.png)

10. Esciu *exit* en la 2a terminal. Desprès d'aixó, troba qui es el pare del proces *xclock*.

![picture 10](P1_sc10.png)

11. Ara, envia una señal per tal de finalitzar el proces *xclock* fent servir el seu PID. 

![picture 11](P1_sc11.png)

12. Executeu un *xclock* de "**front**" en la 1a terminal t1.

![picture 12](P1_sc12.png)

13. Envia una señal des de la 3a terminal per para el proces *xclock* y llavors enviar un altre per deixar que el proces continui. Esta el proces executa-se de *fondo* o *de front*? Finalment, executa una señal per finalitzar el proces *xclock*.

>La señal continua excutant-se de fondo

![picture 13_1](P1_sc13_1.png)

![picture 13_2](P1_sc13_2.png)

![picture 13_3](P1_sc13_3.png)

14. Utilitzant un controlador "job", repteix els mateixos pasos que abans (apartat 13.). Llista els comandaments i les combinacions has utilitzat.



15. Executa el següent comandament en una terminal secundaria:
```c
$ xclock &
$ xclock &
$ xeyes &
$ xeyes &
```
Utilitzant el controlador "job", col·loca el primer xclock de front. Llavors, posa-ho de fondo. Finalitza amb el nom els dos procesos *clock* i llavors els procesos *xeyes*. Llista els comandaments i les combinacions has utilitzat. 

16. Crea una lia de comandaent utilitzant un executador de multiples comandamnts que mostri...