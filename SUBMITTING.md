# Zgłaszanie motywów i pluginów / Submitting themes and plugins

Zinc Launcher pobiera katalog z `catalog.json` w tym repozytorium. Każdy wpis zawiera bezpośredni
adres pliku (`installUrl`) oraz sumę kontrolną SHA-256, którą launcher weryfikuje **przed**
instalacją. Dzięki temu nie musisz publikować niczego w tym repozytorium samodzielnie — wystarczy
publiczny plik i zgłoszenie (issue).

Zgłoszenia przyjmujemy przez formularze GitHub Issues. Po wysłaniu zgłoszenie otrzymuje etykietę
**`submission`**; na jej podstawie prowadzimy kolejkę recenzji. Odrzucone lub zatwierdzone
zgłoszenia są zamykane z komentarzem wyjaśniającym.

## Motywy / Themes

1. **Przygotuj plik.** Motyw to pojedynczy plik `.css`, który nadpisuje wyłącznie zmienne tokenów
   (CSS custom properties) z `tokens.css` launchera. Wzór znajdziesz w plikach `themes/*.css`
   w tym repozytorium (np. `themes/ember.css`). Nie zmieniaj układu ani struktury komponentów,
   nie dodawaj `@import` ani odwołań `url()` do zewnętrznych hostów.
2. **Opublikuj plik.** Wgraj `.css` do publicznego repozytorium GitHub, gistu lub jako asset
   wydania (release). Adres musi być bezpośredni i publiczny — najlepiej
   `https://raw.githubusercontent.com/...`, a nie strona HTML podglądu.
3. **Wypełnij formularz** „Theme submission”. Pole `installUrl` to bezpośredni link do pliku
   `.css`, `previewUrl` (opcjonalnie) to link do zrzutu ekranu.
4. **Weryfikacja.** Launcher pobiera plik, liczy SHA-256 i porównuje z wartością zapisaną
   w katalogu. Jeśli plik zmieni się po zatwierdzeniu, instalacja zostanie odrzucona —
   aktualizacja motywu wymaga nowego zgłoszenia (nowej wersji).

## Pluginy / Plugins

1. **Przygotuj archiwum.** Plugin to plik `.zip` zawierający manifest i kod pluginu. Archiwum
   musi być samowystarczalne i nie może wykonywać nieoczekiwanych operacji sieciowych ani
   plikowych.
2. **Opublikuj plik.** Wgraj `.zip` jako asset wydania GitHub lub do publicznego repozytorium.
   Link musi prowadzić bezpośrednio do archiwum.
3. **Wypełnij formularz** „Plugin submission”. Opisz dokładnie, co plugin robi w launcherze.
   Pole `game` jest opcjonalne — wypełnij je, jeśli plugin dotyczy konkretnej gry.
4. **Weryfikacja.** Analogicznie do motywów: launcher sprawdza SHA-256 archiwum przed
   rozpakowaniem i instalacją.

## Hosting

- Publiczne repozytorium GitHub (raw URL lub release asset) — zalecane.
- Publiczny gist (dla pojedynczych plików `.css`).
- Dowolny publiczny hosting statyczny podający plik bezpośrednio (bez logowania i przekierowań
  na strony HTML).

Pliki muszą być dostępne bez uwierzytelniania. Linki do prywatnych repozytoriów, dysków
chmurowych wymagających logowania lub stron z licznikiem pobierania nie będą akceptowane.

## Etykieta `submission`

Wszystkie zgłoszenia motywów i pluginów otrzymują etykietę **`submission`**. Używamy jej do
filtrowania kolejki (`is:issue is:open label:submission`) i automatyzacji zatwierdzania.
Nie usuwaj jej ze swojego zgłoszenia.

---

# Submitting themes and plugins (English)

Zinc Launcher reads its catalog from `catalog.json` in this repository. Every entry contains a
direct file URL (`installUrl`) and a SHA-256 checksum that the launcher verifies **before**
installing. You do not need to publish anything inside this repository yourself — a public file
plus an issue is enough.

Submissions are handled through GitHub issue forms. Every submission receives the **`submission`**
label, which drives our review queue. Accepted and rejected submissions are closed with an
explanatory comment.

## Themes

1. **Prepare the file.** A theme is a single `.css` file that overrides only the design tokens
   (CSS custom properties) from the launcher's `tokens.css`. Use `themes/*.css` in this repository
   as a reference (e.g. `themes/ember.css`). Do not change layout or component structure and do not
   add `@import` or `url()` references to third-party hosts.
2. **Publish the file.** Upload the `.css` to a public GitHub repository, a gist or a release
   asset. The URL must be direct and public — prefer `https://raw.githubusercontent.com/...` over an
   HTML preview page.
3. **Fill in the** “Theme submission” form. `installUrl` is the direct `.css` link; `previewUrl`
   (optional) points to a screenshot.
4. **Verification.** The launcher downloads the file, computes SHA-256 and compares it with the
   value stored in the catalog. If the file changes after approval, installation is rejected —
   updating a theme requires a new submission (new version).

## Plugins

1. **Prepare the archive.** A plugin is a `.zip` containing the manifest and the plugin code. It
   must be self-contained and must not perform unexpected network or filesystem access.
2. **Publish the file.** Upload the `.zip` as a GitHub release asset or to a public repository.
   The link must point directly to the archive.
3. **Fill in the** “Plugin submission” form. Describe exactly what the plugin does in the launcher.
   The `game` field is optional — use it when the plugin targets a specific game.
4. **Verification.** As with themes, the launcher verifies the archive's SHA-256 before unpacking
   and installing it.

## Hosting

- Public GitHub repository (raw URL or release asset) — recommended.
- Public gist (for single `.css` files).
- Any public static host serving the file directly (no login, no redirects to HTML pages).

Files must be reachable without authentication. Links to private repositories, cloud drives that
require login, or download-counter pages will not be accepted.

## The `submission` label

All theme and plugin submissions receive the **`submission`** label. We use it to filter the queue
(`is:issue is:open label:submission`) and to automate approvals. Please do not remove it.
