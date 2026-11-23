%1_zad
ostatni(_,[]).
ostatni(X,[X]).
ostatni(X,[_|T]) :- ostatni(X,T).

%2_zad
suma([],0).
suma([H|T], Wynik) :- suma(T,Wynik1), Wynik is Wynik1 + H.

%3_zad
ile_razy(_,[],0).
ile_razy(X,[X|Ogon],N) :- ile_razy(X, Ogon,N1), N is N1 +1.
ile_razy(X, [_|Ogon], N) :- ile_razy(X, Ogon, N).

%6_zad
usun_wszystkie(_,[],[]).
usun_wszystkie(X, [X|T], Wynik) :- usun_wszystkie(X, T, Wynik).
usun_wszystkie(X, [Y|T], [Y|Wynik1]) :- X \= Y, usun_wszystkie(X, T, Wynik1).

%14_zad
podziel(_, [], [], []).
podziel(Os, [H|T], [H|Mniejsze], Wieksze) :- H =< Os, podziel(Os, T, Mniejsze, Wieksze).
podziel(Os, [H|T], Mniejsze, [H|Wieksze]) :- H > Os, podziel(Os, T, Mniejsze, Wieksze).
