# Esercizi algebra relazionale

## Esercizio 1 - database università

Si consideri lo schema di base di dati sulle relazioni
    
    MATERIE(Codice, Facoltà, Denominazione, Professore)
    STUDENTI(Matricola, Cognome, Nome, Facoltà)
    PROFESSORI(Matricola, Cognome, Nome)
    ESAMI(Studente, Materia, Voto, Data)
    PIANIDISTUDIO(Studente, Materia, Anno)

*Formulare, in algebra relazionale, in calcolo su domini, in calcolo su tuple e in Datalog le interrogazioni che producono*

1. **Gli studenti che hanno riportato in almeno un esame una votazione pari a 30, mostrando, per ciascuno di essi, nome e cognome e data della prima di tali occasioni;**

    $S = \Pi_{(Matricola, \ Cognome, \ Nome)} \ STUDENTI$
    
    $E = \Pi_{(Studente, \ Voto, \ Data)} \ ESAMI$

    $T = \sigma_{(Voto \ = \ 30)}( S \bowtie_{(S.Matricola \ = \ E.Studente)} E)$
    
    $T_1 = T$
    
    $R = T1 \bowtie_{(T_1.Matricola \ = \ T.Matricola \ \land \ T1.Data \ < \ T.Data)} T$
    
    $RESULT = \Pi_{(Nome, \ Cognome, \ Data)} R$
    

2. per ogni insegnamento della facoltà di ingegneria, gli studenti che hanno superato l'esame nell'ultima seduta svolta;

3. gli studenti che hanno superato tutti gli esami previsti dal rispettivo piano di studio;

4. per ogni insegnamento della facoltà di lettere, lo studente (o gli studenti) che hanno superato l'esame con il voto più alto;

5. gli studenti che hanno in piano di studio solo insegnamenti della propria facoltà; 

6. nome e cognome degli studenti che hanno sostenuto almeno un esame con un professore che ha il loro stesso nome proprio.