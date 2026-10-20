# Absolute Cinema - System zarządzania siecią kin

Absolute Cinema to webowy system dla sieci kin, który obsługuje planowanie seansów, sprzedaż biletów online, kontrolę wejść za pomocą kodów QR oraz program lojalnościowy. Cały system to kilka aplikacji webowych działających na różnych urządzeniach i backend podzielony na 3 serwisy.

## Moduły

Każdy moduł to osobny serwis, który robi jedna osoba z zespołu

1. **Repertuar i sale** - zarządzanie kinami, salami i układem miejsc, planowanie seansów i cennika, dane o filmach
2. **Sprzedaż i rezerwacja biletów** - wybór seansu i miejsc, blokada miejsc na czas płatności, rodzaje biletów (normalny, ulgowy), generowanie biletu z kodem QR, kontrola wejścia, zwroty
3. **Program lojalnościowy** - konto klienta, naliczanie punktów za zakupy, poziomy członkostwa, wymiana punktów na zniżki i nagrody (i ewentualnie więcej, jak będzie za mało)

## Użytkownicy

- **Klient** - kupuje bilety, zbiera i wymienia punkty
- **Kontroler biletów** - skanuje kody QR przy wejściu na salę
- **Manager kina** - planuje seanse, ustala ceny, przegląda raporty
- **Administrator sieci** - zarządza kinami, salami i kontami pracowników

## Węzły systemu

- **Strona klienta** - repertuar, zakup biletów, konto lojalnościowe
- **Aplikacja kontrolera** - działa na tablecie czy telefonie przy wejściu do sali
- **Panel managera** - planowanie seansów, cennik, raporty
- **Backend** - 3 serwisy odpowiadające modułom

## Kody QR

Klient dostaje bilet z kodem QR (na e-mail i na koncie). Kontroler skanuje kod przy wejściu, system sprawdza, czy bilet jest ważny i dotyczy tego seansu, a potem oznacza go jako wykorzystany.

## Integracja wewnętrzna

- **REST API** między aplikacjami webowymi a serwisami
- **Kolejka komunikatów** (pewnie RabbitMQ) dla zdarzeń między serwisami

## Integracja z otoczeniem

- **Bramka płatności** - pewnie Stripe
- **TMDB API** - opisy filmów, obsada, plakaty itd.
- **E-mail** - wysyłka biletów

