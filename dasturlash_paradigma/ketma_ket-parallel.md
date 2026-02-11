# 4.1 Ketma-ket/Parallel ishlov berish (Serial/Parallel)

**Ketma-ket/parallel ishlov berish tushunchasi aslida dasturlash paradigmasi emas. Oddiy qilib aytganda, bu bir nechta vazifalarni ketma-ket yoki bir vaqtning o'zida ularga ishlov berish tartibida farqdir.**

Ketma-ket ishlov berish (Serial processing) — kod qatorlarini birin-ketin ishlov berishni anglatadi. Bu tushuncha kompyutersiz(unplugged) kodlash ta'limida ham eng asosiy mavzu bo‘lib, aslida hammamiz yaxshi biladigan oddiy tushuncha, shuning uchun alohida tushuntirishga hojat yo‘q. Parallel ishlov berish (Parallel processing) esa kompyuter muhandisligi nazariyasida murakkabroq tushuncha bo‘lib, yangi boshlovchilar uchun tushunish qiyin bo‘lishi mumkin. Bundan tashqari, Entry-Pythonda bunday darajadagi parallel ishlov berish qo‘llab-quvvatlanmaydi, shuning uchun faqat asosiy tushunchani bilib o‘tish yetarli. **Parallel ishlov berish bir nechta vazifani bir vaqtning o‘zida** ishlov berish usuli sifatida tushuntiriladi. Bunda haqiqiy vazifalar butunlay mustaqil holda bajariladimi (Parallelism, paralellik), yoki vazifalar go‘yoki bir vaqtda bajarilayotgandek ko‘rinish hosil qiluvchi texnika (Concurrency, sinxronlik) yordamida bajariladimi, bu ikki tushunchani farqlash muhim. Entry-Python ikkinchi usulga — sinxronlikka tayanadi.

Entry-Pythonda sinxronlik(concurrency) bilan bog‘liq dasturlash texnikalari (Thread(Oqimlar), Multi-processing(Ko‘p-jarayonlik) va boshqalar) qo‘llab-quvvatlanmagani sababli, bu usullardan foydalanib kod yozishni yoki sinxronlikka oid dasturlash usullarini o‘rganishni imkonsiz qiladi. Kitobning boshida ham ta'kidlanganidek, bu Entry-Pythonning cheklovidir. Shu bilan birga, Entry-Python dastlab blokli kodlashdan birinchi matnli dasturlashga o‘tganlar uchun mo‘ljallangan bo‘lib, murakkab darajadagi o‘rganish maqsad qilinmagan. Shuning uchun, asosiy tushunchalarni o‘zlashtirib, texnik tafsilotlarga chuqur kirmasdan o‘tishning o‘zi kifoya. Haqiqatan ham, bu darajadagi tushunchalar ham o‘z ahamiyatiga ega ekanligini bilish foydali bo‘ladi.

Entry blokli kodlashida, quyidagi misolda ko‘rganingizdek, biz allaqachon ko‘p bor parallel ishlov berishni kodlab ko‘rganmiz.

{% tabs %}
{% tab title="Ijro natijasi" %}
<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Blokli kodlash" %}
<figure><img src="../.gitbook/assets/sr (1).png" alt="" width="375"><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Entry-Python" %}
{% code lineNumbers="true" %}
```python
# Changyutgich robot(1)'s Python code

import Entry

def when_start():
    Entry.start_drawing()
    Entry.set_brush_color_to("#FFFFFF")
    Entry.set_brush_size(50)

def when_start():
    while True:
        Entry.move_to_direction(10)
        if Entry.is_touched("edge"):
            Entry.move_to_direction(-15)
            Entry.add_rotation(133)
```
{% endcode %}
{% endtab %}
{% endtabs %}

“Boshlash tugmasini bosganda” deb nomlangan blokni bir obyektda bir necha marta ishlatib, mustaqil ko‘rinadigan vazifalarni go‘yoki bir vaqtning o‘zida bajarilayotgandek kodlagan tajribamiz bor edi. Bu orqali biz turli dasturlashning asosiy tushunchalaridan foydalanib kelganmiz, buni o‘zimiz sezmagan holda bajargan bo‘lsak ham.

Shu sababli, Entry-Pythonda parallel ishlov berish blokli kodlashda qilgan ishlarimizdan unchalik farq qilmaydi. Faqat yuqoridagi misolda ko‘rsatilganidek, **when\_start** funksiyasini bir necha marta ishlatish mumkin. Foydalanuvchi dastur ishga tushishi uchun “Boshlash” tugmasini bosganda, har bir **when\_start** funksiyasi bir vaqtning o‘zida chaqiriladi. Shu tarzda, har bir funksiyada bajarilishi kerak bo‘lgan vazifalarni mustaqil ravishda tasvirlab, ularni go‘yoki bir vaqtda bajarilayotgandek ko‘rinish hosil qilish mumkin. Bu usulni kodlashda va dasturda samarali foydalanish kifoya qiladi.
