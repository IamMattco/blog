---
layout: post
title:  "Git, z czym to się je"
date:   2016-08-22 13:47
author: Mateusz Mróz
categories: Technologie, Git, Tutoriale
tags:	technologie, git, tutoriale, jak zacząc
cover:  "/assets/instacode.png"
---

Czym jest git? Najprościej jest to rozproszony system kontorli wersji. Według wikipedi pierwsza wersja narzędzia Git została wydana 7 kwietnia 2005 roku. Najbardziej popularnymi serwisami hostingowymi dla projektów programistycznych wykorzystujących Git jest [GitHub][github], [GitLab][gitlab] oraz [BitBucket][bitbucket].

Utwórzmy sobie folder, w którym będzie nasz projekt i tam również zainicjalizujemy Git'a.

{% highlight html %}
  mkdir skycms
  cd skycms
  git init
{% endhighlight %}

Omówmy sobie wpisywane przez nas komendy. Pierwsza tworzy folder o nazwie "skycms", komenda w kolejnym wierszu pozwoli nam przejśc do utworzonego właśnie folderu. Ostatnia inicjalizuje gita, czyli utworzy nam się folder .git
a w nim plik config.

Załóżmy, że nasz projekt będziemy trzymać na GitHubie. Więc tworzymy w tym serwisie nowy projekt, podajemy nazwę oraz opis. Jako, że nasz projekt jak na razie nie zawiera żadnego pliku to wypadało by stworzyć parę plików, którymi się trochę pobawimy za pomocą gita.

{% highlight html %}
  echo "To jest nasz super projekt" >> README.md
  git add README.md
  git commit -m "our first commit"
  git remote add origin git@github.com:twoja_nazwa_użytkownika/nazwa_repo.git
  git push -u origin master
{% endhighlight %}

Co stanie się jeśli wklepiemy poszczególne linijki kodu do naszej konsoli? Pierwsza linia utworzy nam plik README.md (md to skrót od markdown) i umieści w nim tekst "To jest nasz super projekt". Tak więc ta linijka kodu utworzy nam pierwszy plik w naszym projekcie. Kolejna linijka (2) sprawi, że nasz plik zostanie dodany/zakolejkowany do przesłania na serwer. Jeśli mamy zaznaczony plik, który chcemy przesłać do GitHuba, to teraz musimy dodać jakiś komentarz, żeby potem móc łatwo odnaleźć interesujący nas plik w naszym repozytorium. Zastanawiasz się dlaczego nasz komentarz (w lini 3) jest po angielsku? Ponieważ w przyszłości pokazując swoje konto na GitHubie zagranicznemu pracodawcy, to pokażesz też, że znasz w jakimś stopniu język angielski. 4 z kolei linijka kodu dodaje adres naszego repozytorium, czyli po prostu wskazujemy miejsce gdzie przyszłe commity będą leciały. Ostatnia linijka kodu wysyła zmiany jakie zakolejkowaliśmy i skomentowaliśmy na serwer GitHuba.

### Pień i gałęzie

Załóżmy na chwilę, że plik README, który wcześniej utworzyliśmy jest aktualnie trzonem naszego projektu. Chciałbym mieć pewność, że wprowadzane przeze mnie nowe rzeczy w żaden sposób nie będą miały wpływu na trzon naszego projektu. Tak więc wklepujemy w konsoli:

{% highlight html %}
  git branch nowe-rzeczy
  git checkout nowe-rzeczy
{% endhighlight %}

Pierwsza linia kodu odpowiedzialna jest za utworzenie nowej gałęzi dołączonej do naszego projektu. Tak po ludzku to komenda git-branch 'nazwa brancha' odpowiada za sklonowanie naszego projektu i pozwoli wprowadzać zmiany w naszym projekcie bez zmiany głównego pnia projektu. Czyli co zmienimy na branchu "nowe-rzeczy" nie ma wpływu na nasz wcześniej utworzony plik README. Druga komenda przełącza nas na nową gałąź o nazwie "nowe-rzeczy".

Utwórzmy sobie teraz nowy plik index.html i wpiszmy tam słowo TEST. Następnie zakolejkujmy wszystkie zmiany i dodajmy do nich komentarz.

{% highlight html %}
  git add .
  git commit -m "create index.html file"
  git push lub git push origin nowe-rzeczy
{% endhighlight %}

Pierwsza komenda kolejkuje wszystkie pliki, które zmieniliśmy. Kolejna komentuje zmiany. Ostatnia wysyła pliki na serwer GitHuba.

### Mergowanie, czyli łączenie gałęzi z pniem

Czym jest mergowanie? Najprościej mówiąc to łączenie gałęzi z pniem. Czyli w naszym przypadku, plik index.html utworzony na gałęzi o nazwie "nowe-rzeczy" zostanie przeniesiony do pnia, gdzie jest już nasz plik README.md.

{% highlight html %}
  git checkout master
  git merge nowe-rzeczy
  git push
{% endhighlight %}

Pierwsza komenda każe dla Gita wrócić do pnia kolejna każe połączyć pliki z "nowe-rzeczy" i przenieść je do pnia projektu. Jak już może zapamiętałeś/aś git push wysyła zmiany na serwer.

### Podsumowują

Dzisiaj nauczyłeś/aś się czym jest git i jak zainicjalizować go w swoim projekcie. Wiesz już również, jak pracować i czym są branche. Mam świadomość, tego że nie poruszyłem tutaj wielu innych ciekawych funkcji Gita, ale o tym już w innych wpisach. Jeśli masz jakieś uwagi to zapraszam Cię do komentowania tego wpisu.

[github]: http://github.com
[gitlab]: http://gitlab.com
[bitbucket]: http://bitbucket.org
