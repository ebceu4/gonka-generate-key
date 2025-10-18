# 🔑 Генерация локального ключа для Gonka (macOS, Apple Silicon)

## 1. Скачать бинарник
Скачай архив:  
[inferenced-darwin-arm64.zip](https://github.com/gonka-ai/gonka/releases/download/release%2Fv0.2.3/inferenced-darwin-arm64.zip)

Распакуй его (2 раза нажать) — появится файл `inferenced`.

---

## 2. Разрешить запуск

Открой **Terminal** и перейди в папку, где лежит файл:
<pre><code><span class="cmd">cd</span> <span class="path">~/Downloads</span></code></pre>

Запусти файл:
<pre><code><span class="cmd">./inferenced</span></code></pre>

После первой попытки запуска появится предупреждение, что приложение *«inferenced» не может быть открыто*.  
Это нормально — нажми **Done**.

<img src="images/step2-warning.png" alt="Ошибка при первом запуске" style="max-width:300px; width:100%; border-radius:8px;">

Открой:
> **Системные настройки → Конфиденциальность и безопасность**  
> (System Settings → Privacy & Security)

Прокрути вниз до блока с надписью:  
> “inferenced” был заблокирован для защиты вашего Mac.

Нажми **Разрешить всё равно (Allow Anyway)**.

![Allow Anyway](images/step3-allow.png)

## 3. Сгенерировать ключ

Теперь можно создать ключ:
<pre><code><span class="cmd">./inferenced</span> <span class="arg">keys</span> <span class="arg">add</span> <span class="arg">gonka-account-key-cluster1</span> <span class="arg">--keyring-backend</span> <span class="arg">file</span> <span class="arg">--home</span> <span class="path">./gonka-keys-cluster1</span></code></pre>

macOS покажет ещё одно окно — нажми **Open Anyway (Открыть всё равно)**.  
После этого бинарник будет считаться доверенным и запускаться без ограничений.

<img src="images/step4-open-anyway.png" alt="Open Anyway" style="max-width:300px; width:100%; border-radius:8px;">

После выполнения команда создаст папку `gonka-keys-cluster1` с ключами.

---

## 4. Пример вывода при успешном создании ключа

После выполнения команды генерации ключа ты увидишь в терминале примерно такой вывод:

<pre><code><span class="cmd">./inferenced</span> <span class="arg">keys</span> <span class="arg">add</span> <span class="arg">gonka-account-key-cluster1</span> <span class="arg">--keyring-backend</span> <span class="arg">file</span> <span class="arg">--home</span> <span class="path">./gonka-keys-cluster1</span>
Enter keyring passphrase (attempt 1/3):
Re-enter keyring passphrase:

- address: gonka1w4t3gz76r96kk2d78luumkvyhgdkevkewy8qun
  name: gonka-account-key-cluster1
  pubkey: '{"@type":"/cosmos.crypto.secp256k1.PubKey","key":"AlZwl37etxe8EldJsCWJazIYikiSkVoMPPleCoLjrfzK"}'
  type: local


**Important** write this mnemonic phrase in a safe place.
It is the only way to recover your account if you ever forget your password.

trim silly skate nuclear catch forest rebel web link spoon stove fruit kiss borrow young denial youth then pistol gather noodle shop car lizard
</code></pre>

Внизу напечатана **мнeмоническая фраза (seed phrase)** — это единственный способ восстановить аккаунт:
<pre><code><span class="comment">&lt;ЗАПИШИ ЕЕ В БЕЗОПАСНОЕ МЕСТО, НЕ ПУБЛИКУЙ&gt;</span></code></pre>

---