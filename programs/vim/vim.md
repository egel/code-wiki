<img src="img/Vim_logo.png" title="Vim - Edytor tekstu" width="250" />

# Vim

To nic innego jak edytor tekstu. Występuje w wersji na Konsolę oraz Xbox 360... haha nie, nie...;) występuje w wersji dla LUI i GUI.
Można go również zainstalować prawie na każdej popularniejszej wersji systemu operacyjnego.

Wiele osób po pierwszym "zderzeniu się" z tym programem zapyta:

> Ale dlaczego on niby jest taki świetny? Jest brzydki, niemiły i w ogóle ...

Cóż jest to idelanie modalny edytor tekstu który dostacza tak wielką ilość dodatków

Projekt opiera się o program [Vim](http://www.vim.org/)

## Spis treści

  * [Useful shotcuts](#useful_shortcuts)
  * [Quick introduction](#quick_introduction)
  * [Installation and configuration](#installation_and_configuration)

## <a name="#installation_and_configuration">Installation and configuration</a>
For Debian/Ubuntu/Mint:

    $ sudo apt-get install vim


## <a name="#quick_introduction">Quick introduction</a>

    :! php %

* execute `:`
* command `!`
* name of the command `php`
* my name of the file `%`


## <a name="#useful_shortcuts">Useful shortcuts</a>

#### Undo & Redo

* `undo` - wykonujemy poprzez `u`
* `redo` - wykonujemy przez <kbd>Ctrl</kbd>+<kbd>r</kbd>


#### Kopiowanie i wklejanie

Prosta czynność :)

  - Wciskamy w trybie polecenia <kbd>v</kbd> lub <kbd>Ctrl</kbd>+<kbd>v</kbd>
  - zaznaczamy linijki które nas interesuja
  - potem klikamy <kbd>p</kbd> aby wkleić tekst


#### Zapisywanie jako root
Po otworzeniu pliku i niemocy zapisania ze względu na uprawnienia jest na to rozwiązanie:

    :w !sudo tee %


#### Zamykanie okna pomocy
Po wpisaniu np: `:help help` (pomoc na temat pomocy) okienko to możemy łatwo zamknąć przy pomocy poniższego skrótu:

<kbd>Ctrl</kbd>+<kbd>w</kbd> a następnie klikamy <kbd>q</kbd>


#### Uzupełnianie nazw zmiennych

<kbd>Ctrl</kbd>+<kbd>N</kbd>




## Konfiguracja

Warto zaprzyjaźnić się z plikiem `~/.vimrc`, a to z tego względu iż ten plik przechowuje wszystkie bazowe ustawienia vim'a które automatycznie się odpalają za każdym razem kiedy uruchamiamy naszego vim'a


### Konfiguracja pliki ~/.vimrc

Wiecej informacji znajdziesz na: [https://github.com/egel/dot-files](https://github.com/egel/dot-files)

### Włącz automatyczne wcięcia

    :set autoindent


### Właczenie numerowania wieszy

    :set number


### Podswietlanie przy wyszukiwaniu

    :set hlsearch
    :nohl


### Inkrementalne szukanie

    :set incsearch


## Szukanie słów w tekscie

    /apache





## <a name="podstawowe polecenia"></a>Postawowe polecenia


### Bufor previous

```
:bp
```


### Bufor next

```
:bn
```


## Polecenia zaawansowane


### Zakładki w Vim

```
:tabe /etc/apache2
```

`gt` - polecenie przechodzenia miedzy tabami

* g - symbolizuje `go to`
* t - odnosi się do `tab`


### Myszka w Vim

```
:set mouse=a
```

### Kolorowanie składni dla konkretnego języka

```
:set filetype=php
:set background=dark
```

## mapowanie klawiszy

Do klawisza F5 przypisz komendę która "uruchomi polecenie `php` w trybie quiet na obecnie edytowanym pliku i wcisnę enter"

```
:map <F5> :!php -q %<CR>
```

Zapisywanie pliku

```
:map <F2> :w!
```

## Mapowanie w trybie inputa

```
:imap =amk ala ma kota
```

## Wsparcie

  - Bugi, literówki proszę zgłaszać [tutaj][issue].
  - Bardzo mile widziane współdzielenie projektu i udostępnianie waszych poprawek :)

## Licencja

  Szkolenie przygotowane przez Maciej Sypień jest własnością [Akademii Rozwoju Personalnego][arp_homepage_url] oraz stanowi własność chroniona prawem autorskim oraz międzynarodowym.

  Przykłady z szkolenia dostępne są na [github][git_lecture_github_url] w zgodzie z [licencją MIT][4]

## Na podstawie

* * *

Akademia Rozroju Personalnego - [www][arp_homepage_url]

 [1]: http://egel.pl
 [git_homepage_url]: http://www.vim.org/
 [git_lecture_github_url]: http://github.com

 [4]: http://revolunet.mit-license.org
 [8]: https://github.com/revolunet/sublimetext-markdown-preview/issues/27#issuecomment-11772098
 [9]: https://github.com/revolunet/sublimetext-markdown-preview/issues/78#issuecomment-15644727
 [11]: https://sublime.wbond.net/installation
 [12]: https://github.com/revolunet/sublimetext-markdown-preview/archive/master.zip
 [issue]: https://github.com/revolunet/sublimetext-markdown-preview/issues
