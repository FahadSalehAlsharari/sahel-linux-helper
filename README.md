# سهل (sahel)

**سهل** أداة صيانة وتحديث احترافية لأوبنتو سطح المكتب، مبنية بـ Bash وبواجهة عربية واضحة وآمنة افتراضيًا.

- **المطور:** Fahad Alsharari
- **الموقع:** https://fahadalsharari.sa
- **الترخيص:** MIT
- **الإصدار الحالي:** 2.1.0

## ماذا يقدم سهل؟

- صيانة آمنة يومية: تحديث فهارس الحزم + ترقية + تنظيف.
- معاينة قبل التنفيذ (Dry Run) بدون أي تعديل فعلي.
- وضع متقدم عبر `dist-upgrade` مع تحذير واضح وتأكيد.
- دعم `apt` و `snap` و `flatpak` عند توفرها.
- ملخص نهائي دقيق وصادق (نجاح/تخطي/فشل/تحذير) بدون أرقام مضللة.
- تسجيل تفصيلي لكل تشغيل في ملف Log مستقل.

## النطاق وحدود الأداة

سهل **يقوم بـ**:

- تحديث فهارس الحزم وترقية النظام ضمن نفس إصدار Ubuntu.
- تنظيف عناصر النظام الشائعة بشكل محافظ وآمن.
- فحص الحاجة إلى إعادة التشغيل بعد الصيانة.

سهل **لا يقوم بـ**:

- ترقية إصدار Ubuntu نفسه.
- تعديل مصادر الحزم (`sources.list`).
- تنفيذ تغييرات أمنية خارج نطاق الصيانة المعتادة.

## المتطلبات

- Ubuntu Desktop 20.04+
- Bash 4.4+
- صلاحيات `sudo`

## التثبيت

```bash
git clone https://github.com/FahadSalehAlsharari/sahel-linux-helper.git
cd sahel-linux-helper
chmod +x sahel
sudo install -m 755 sahel /usr/local/bin/sahel
```

## الاستخدام

### الوضع التفاعلي

```bash
sudo sahel
```

### أوامر CLI

```bash
sudo sahel --safe
sudo sahel --preview
sudo sahel --advanced --yes
sudo sahel --cleanup
sudo sahel --status
sahel --about
sahel --help
```

## الأوضاع

- `--safe`: الصيانة الآمنة (موصى به).
- `--preview`: معاينة بدون تنفيذ.
- `--advanced`: صيانة متقدمة باستخدام `dist-upgrade`.
- `--yes`: تأكيد تلقائي للوضع المتقدم (`--advanced`) في التشغيل غير التفاعلي.
- `--cleanup`: تنظيف فقط.
- `--status`: عرض حالة النظام.
- `--about`: معلومات الأداة.

## التسجيل (Logs)

- المسار الافتراضي: `/var/log/sahel/`
- fallback تلقائي عند الحاجة: `/tmp/sahel-logs/`

## استكشاف الأعطال

- **ظهور قفل apt/dpkg**: انتظر انتهاء عمليات النظام (مثل unattended-upgrades).
- **فشل الاتصال**: تأكد من الوصول إلى مخازن Ubuntu.
- **فشل جزئي في snap/flatpak**: قد تكون حزم قيد الاستخدام أو توجد عملية تحديث معلقة.
- **فشل preflight**: راجع الملخص النهائي وملف السجل.

## هيكل المشروع

```text
.
├── sahel
├── README.md
├── CHANGELOG.md
├── LICENSE
├── CONTRIBUTING.md
└── .github/
    ├── ISSUE_TEMPLATE/
    │   └── bug_report.md
    └── pull_request_template.md
```

## المساهمة

راجع [CONTRIBUTING.md](./CONTRIBUTING.md).

## الترخيص

MIT License — التفاصيل في [LICENSE](./LICENSE).

## حقوق الملكية

هذا المشروع يحمل هوية **سهل** ومملوك لـ **Fahad Alsharari**.
