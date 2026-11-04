# دليل إعداد ونشر توثيق DEXRise على GitBook

هذا الملف هو دليل تشغيلي كامل لتهيئة صفحتك على GitBook ونشر محتوى التوثيق الموجود في مجلد `docs/` — من إنشاء المستودع على GitHub لحد ما الموقع يبقى منشور ومتاح على الإنترنت.

---

## 📁 بنية المشروع

```
docs-gitbook/
├── README.md            ← هذا الدليل (مش جزء من محتوى GitBook)
├── .gitbook.yaml        ← إعدادات ربط GitBook بالمستودع
└── docs/                ← المحتوى الفعلي اللي هيظهر على GitBook
    ├── README.md        ← صفحة الـ Introduction (أول صفحة بتظهر)
    ├── SUMMARY.md       ← جدول المحتويات (هيكل التنقل في الشريط الجانبي)
    ├── introduction/    ← تعريف بالمنصة وآلية عملها
    ├── trading/         ← التداول: اللوحة، Floor Price Protection، Slippage، الرسوم، التصنيفات
    ├── staking/         ← الـ Staking: أنواع العقود وآلية حساب العائد
    ├── presale/         ← الـ Presale: أنواع العقود ودورة حياة الحدث
    ├── airdrop/         ← الـ Airdrop
    ├── dxr-token/       ← توكن DXR: الـ Tokenomics والعناوين الرسمية والأحداث
    ├── listing/         ← رسوم واشتراطات الإدراج (للمشاريع والمطورين)
    ├── faq.md           ← الأسئلة الشائعة
    └── contact.md       ← قنوات التواصل الرسمية
```

---

## ⚙️ كيف بيشتغل الربط مع GitBook؟

GitBook بيقرأ المحتوى من المستودع مباشرة وفقًا لملفين:

### 1. ملف `.gitbook.yaml` (في جذر المستودع)

```yaml
root: ./docs/

structure:
  readme: README.md
  summary: SUMMARY.md
```

| الإعداد | وظيفته |
| --- | --- |
| `root: ./docs/` | بيحدد إن GitBook يقرأ المحتوى من مجلد `docs/` مش من جذر المستودع — عشان كده ملف الدليل ده (README.md الجذري) **مش** هيتزامن مع GitBook |
| `structure.readme` | صفحة البداية اللي بتفتح أول ما حد يدخل على التوثيق |
| `structure.summary` | ملف الفهرس اللي بيحدد هيكل التنقل بالكامل |

### 2. ملف `SUMMARY.md` (داخل `docs/`)

ده فهرس التنقل. قواعده بسيطة:

- عنوان من نوع `##` = **قسم/مجموعة** في الشريط الجانبي (زي `## Trading`).
- كل عنصر قائمة `[العنوان](الملف.md)` = **صفحة**.
- المسافة البادئة (indentation) بتحدد الصفحات الفرعية.
- كل ملف لازم يظهر **مرة واحدة فقط** في الفهرس.

عشان تضيف صفحة جديدة مستقبلًا: أنشئ ملف `.md` → أضف سطر `[اسم الصفحة](مسار-الملف.md)` في المكان المناسب داخل `SUMMARY.md` → اعمل commit وpush — وهتظهر تلقائيًا.

---

## 🚀 خطوات الإعداد والنشر (من الصفر)

### الخطوة 1 — رفع المشروع على GitHub

المجلد الحالي لسه مش مستودع Git. نفّذ الأوامر دي (في Git Bash):

```bash
cd /e/dexrise/docs-gitbook

git init
git add .
git commit -m "Initial DEXRise documentation"

# أنشئ مستودعًا فارغًا جديدًا باسم dexrise-docs على github.com أولاً (بدون أي ملفات إضافية)
git branch -M main
git remote add origin https://github.com/<اسم-حسابك>/dexrise-docs.git
git push -u origin main
```

> ⚠️ مهم: المستودع على GitHub يكون **فارغًا** وقت أول push (من غير README أو LICENSE منشورة من واجهة GitHub)، عشان ما يحصلش تعارض.

### الخطوة 2 — إنشاء الموقع على GitBook

1. سجّل دخول على [app.gitbook.com](https://app.gitbook.com) (أنشئ حسابًا لو مش عندك، ويفضّل تسجيل الدخول بحساب GitHub مباشرة).
2. من الصفحة الرئيسية للـ organization، اضغط أيقونة **+** اللي جنب **Sites**.
3. اكتب اسم واضح للموقع (مثلًا: `DEXRise Docs`) واضغط **Create**.
4. هيسألك عن نقطة البداية — اختار **Git Sync** (أو أنشئ blank section واربط الـ Git Sync من جوه الـ Space بعدها).

### الخطوة 3 — ربط GitHub (Git Sync)

> 📌 ملاحظة: Git Sync بيتم تفعيله فقط من حساب **Admin** أو **Creator** للـ organization.

1. افتح الـ Space/Site المطلوب، ثم افتح **Git Sync** من الشريط الجانبي.
2. اضغط **Connect GitHub** وسجّل دخول بحساب GitHub اللي عليه المستودع.
   - لو ظهر خطأ `Potential duplicated accounts`: معناها حساب GitHub مربوط بمستخدم GitBook تاني — سجّل دخول عن طريق GitHub sign-in وافصل الارتباط من الإعدادات الأول.
3. تحت **Source repository**: اختار المستودع (`dexrise-docs`) والـ branch (`main`).
   - لو المستودع مش ظاهر في القائمة: ثبّت [GitBook GitHub App](https://github.com/apps/gitbook-com) وامنحه صلاحية الوصول للمستودع، وبعدها ارجع وحاول تاني.
4. **اتجاه المزامنة الأولي**: اختار أن المستودع (GitHub) هو **مصدر الحقيقة** — عشان محتوى `docs/` الموجود حاليًا هو اللي يُستورد لـ GitBook. لو وجدت الاتجاه الافتراضي معكوسًا، استخدم زر **Swap direction**.
   - ⚠️ تحذير من GitBook الرسمي: لو اخترت مستودعًا فارغًا كـ مصدر في المزامنة الأولى ممكن تمسح محتوى الـ Space الحالي — راجع المستودع والـ branch والاتجاه قبل الضغط على Sync.
5. **Project directory**: سيبها على الافتراضي (جذر المستودع) — ملف `.gitbook.yaml` الموجود هيوجّه GitBook لمجلد `docs/` تلقائيًا.
6. راجع **Content mapping**: تأكد إن الـ Space مربوط بمسار المستودع الصحيح.
7. اضغط **Sync** لبدء المزامنة الأولى.

بعد انتهاء المزامنة، هتلاقي كل صفحات `docs/` ظهرت في الـ Space، والفهرس مُشكَّل حسب `SUMMARY.md`.

### الخطوة 4 — النشر (Publish)

1. من الصفحة الرئيسية للـ organization، افتح الموقع بتاعك.
2. اضغط **Publish** من هيدر الموقع — وهيبقى متاح على رابط عام فورًا.
3. **ظهور الموقع**: افتراضيًا الموقع **Public** (متاح للجميع). للتحكم في الظهور: **Settings → Audience** وخياراتها:
   - **Public** — منشور ومتاح للكل.
   - **Share links** — خاص، بيُتاح بس عبر روابط مشاركة.
   - **Authenticated Access** — محمي بتسجيل دخول OAuth.
4. (اختياري) **Domain مخصص**: من إعدادات الموقع تقدر تربط دومين زي `docs.dexrise.io` — راجع صفحة Custom Domain في توثيق GitBook.

---

## 🔄 سير العمل اليومي (كيف تُحدّث المحتوى)

المزامنة **ثنائية الاتجاه**:

| الاتجاه | النتيجة |
| --- | --- |
| **GitHub → GitBook** | أي commit يعمله push على `main` يظهر في GitBook تلقائيًا خلال ثوانٍ |
| **GitBook → GitHub** | أي تعديل تدمجه (merge change request) في محرر GitBook بينه commit على المستودع |

**الطريقة الموصى بيها**: عدّل ملفات `.md` محليًا (أو عن طريق أي محرر) → `git add` → `git commit` → `git push` — وGitBook هيتحدث تلقائيًا.

> ⚠️ تحذير رسمي من GitBook: لما Git Sync يكون مفعّلً، إدارة ملفات `README.md` و`SUMMARY.md` تكون **من المستودع** — تعديلهم من محرر GitBook ممكن يسبب تعارضات أو تكرار صفحات. تعديل باقي الصفحات من المحرر آمن.

---

## 📝 قائمة التحديثات المطلوبة لاحقًا (Placeholders)

المحتوى الحالي فيه بيانات مؤقتة لازم تتحدّث لما تكون متاحة:

| البند | الملفات المطلوب تعديلها | الوضع الحالي |
| --- | --- | --- |
| **عقد توكن DXR** | `docs/dxr-token/overview.md`<br>`docs/dxr-token/official-addresses.md` | "*To be announced*" — استبدله بعنوان العقد عند الإعلان |
| **رابط الموقع/التطبيق الرسمي** | غير موجود حاليًا | لو حبيت تضيفه: أفضل مكان هو `docs/contact.md` و`docs/introduction/what-is-dexrise.md` |

عند أي تعديل: حدّث الملفات → commit → push → هتتحدث على GitBook تلقائيًا.

---

## 🔧 استكشاف الأخطاء الشائعة

| المشكلة | الحل |
| --- | --- |
| خطأ `Potential duplicated accounts` | سجّل الدخول عبر GitHub sign-in وافصل ارتباط الحساب من إعدادات GitBook |
| المستودع مش بيظهر في قائمة الاختيار | ثبّت [GitBook GitHub App](https://github.com/apps/gitbook-com) وتأكد إن صلاحياته بتغطي المستودع |
| الـ Space طلع فاضي بعد أول مزامنة | اتجاه المزامنة الأولي كان معكوسًا — المستودع لازم يكون هو المصدر (راجع خطوة اتجاه المزامنة أعلاه) |
| صفحة موجودة في `docs/` بس مش ظاهرة في الفهرس | ملفها مش مضاف في `SUMMARY.md` — أضفه واعمل push |
| رابط بين صفحتين مش شغال | راجع المسار النسبي: الروابط داخل نفس المجلد بالاسم مباشرة (`page.md`)، والروابط العابرة للمجلدات بـ `../` (مثل `../trading/overview.md`) |
| الشبكة المؤسسية بتمنع المزامنة (Enterprise) | إتاحة عناوين IP الصادرة اللي محددها GitBook في صفحة Git Sync الرسمية |

---

## 📚 مراجع رسمية

- [Git Sync — التوثيق الرسمي](https://gitbook.com/docs/docs-as-code/git-sync)
- [إعدادات المحتوى (`.gitbook.yaml` و`SUMMARY.md`)](https://gitbook.com/docs/docs-as-code/git-sync/content-configuration)
- [تفعيل GitHub Sync خطوة بخطوة](https://gitbook.com/docs/docs-as-code/git-sync/enabling-github-sync)
- [نشر الموقع وإعدادات الظهور](https://gitbook.com/docs/publish/publish-a-docs-site)
- [GitBook GitHub App](https://github.com/apps/gitbook-com)
