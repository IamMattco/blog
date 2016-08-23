---
layout: post
title:  "Git, rozwinięcie tematu (część I)"
date:   2016-08-23 12:00
author: Mateusz Mróz
categories: Git, Tutoriale
tags:	git, tutoriale, jak zacząc
cover:  "/assets/posts/las.jpg"
---

W tej części tutoriala chciałbym bardziej opisać pewne scenariusze które mogą pojawić się podczas pracy z gitem i pomóc Ci rozwiązać ewentualne problemu z jego użytkowaniem. Jest wiele aplikacji ułatwiających pracę z Gitem, moim zdaniem najłatwiej pracować z nim właśnie w konsoli/terminalu.

### Co zrobić, gdy przez pomyłkę zakolejkuję zły plik?

{% highlight html %}
  git reset HEAD
{% endhighlight %}

Po wklepaniu tego w konsolę zresetujemy wszystkie pliki, które zakolejkowaliśmy za pomocą komendy git add.

### Co zrobić, w przypadku kiedy mamy konflikt

Czasem podczas pracy nad sporym projektem, gdzie codziennie są dodawane tysiące nowych linijek kodu przez wielu programistów, może zdarzyć się sytuacja w której podczas mergowania naszego brancha do mastera wystąpi konflikt plików. Wtedy wklepujemy w konsolę "git status", aby sprawdzić, które pliki nie zostały z mergowane, to właśnie w nich występują konflikty. Jak je rozwiązać? Wchodzimy w taki plik musimy go wyedytować zgodnie z tym, co zaznaczył nam git.

### Do czego służy komenda "git status"

Po wklepaniu komendy "git status" do konsoli, zostaną wyświetlone nam przez gita, wszystkie pliki jakie zostały zmienione, zakolejkowane lub zakomentowane i oczekują na wysłanie na serwer. Tak, więc dzięki tej komendzie mamy wgląd z zmienione pliki.

### git diff nazwa-pliku

Co stanie się po wpisaniu w konsoli "git diff index.html"? Git wyświetli w konsoli zmiany z pliku, którego podaliśmy ścieżkę po "git diff"

Masz jakieś pytania odnośnie gita? Zadaj je w komentarzu!
