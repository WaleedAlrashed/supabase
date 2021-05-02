<p align="center">
<img width="300" src="https://raw.githubusercontent.com/supabase/supabase/master/web/static/supabase-light-with-background.svg"/>
</p>

---

# Supabase

[Supabase](https://supabase.io)
هو بديل مفتوح المصدر عن Firebase ،
 نحن نقوم حالياً ببناء الميزات الخاصة بفايربيز باستخدام أدوات عالية الجودة ومفتوحة المصدر

- [x] قاعدة بيانات Postgress مستضافة
- [x] اشتراكات في الزمن الحقيقي Realtime Subscription
- [x] المصادقة والتخويل (Authentication and authorization)
- [x] Auto-generated APIs (API مولدة أوتماتيكياً)
- [x] Dashboard - لوحة تحكم 
- [x] Storage - تخزين 
- [ ] Functions (coming soon) - التوابع (قريباً)

## توثيق المشروع


للإطلاع على التوثيق الكامل للمشروع، يرجى زياة الموقع الرسمي 
 [supabase.io/docs](https://supabase.io/docs)

## المجتمع والدعم

- [Community Forum](https://github.com/supabase/supabase/discussions). Best for: المساعدة في بناء ومناقشة أفضل ممارسات قاعدة البيانات.
- [GitHub Issues](https://github.com/supabase/supabase/issues). Best for: الأخطاء والأخطاء التي تواجهها عند استخدامك Supabase.
- [Email Support](https://supabase.io/docs/support#business-support). Best for: مشاكل في قاعدة البيانات أو البنية التحتية الخاصة بمشروعك.

## حالة المشروع

- [x] Alpha: نحن هنا نختبر الميزات بشكل مغلق مع بعض العملاء
- [x] Public Alpha: يمكن لأي أحد أن يقوم بالتسجيل هنا  [app.supabase.io](https://app.supabase.io). مع ملاحظة وجود بعض المشاكل الطفيفة
- [x] Public Beta: مستقر بدرجة كافية لمعظم حالات الاستخدام غير المتعلقة بالمؤسسات
- [ ] Public: جاهز للإستخدام بشكل كامل

نحن حالياً في مرحلة ال Public Beta 
، قم بالذهاب إلى قسم ال "releases"
 في هذه الريبو لتكون على علم بأخر التحديثات 

<kbd><img src="https://gitcdn.link/repo/supabase/supabase/master/web/static/watch-repo.gif" alt="Watch this repo"/></kbd>

---

## كيف تعمل

Supabase عبارة عن مجموعة من الأدوات مفتوحة المصدر. نحن نبني ميزات Firebase باستخدام منتجات مفتوحة المصدر على مستوى المؤسسات. إذا كانت الأدوات والمجتمعات موجودة ، باستخدام MIT أو Apache 2 أو ترخيص مفتوح مكافئ ، فسنستخدم هذه الأداة وندعمها. إذا لم تكن الأداة موجودة ، فإننا نبنيها ونفتحها بأنفسنا. Supabase ليس تعيين 1 إلى 1 لـ Firebase. هدفنا هو منح المطورين تجربة مطور تشبه Firebase باستخدام أدوات مفتوحة المصدر.

**Current architecture**

Supabase is a [hosted platform](https://app.supabase.io). يمكنك التسجيل والبدء في استخدام Supabase دون تثبيت أي شيء. ما زلنا نخلق تجربة التنمية المحلية - وهذا هو تركيزنا الأساسي الآن ، إلى جانب استقرار النظام الأساسي.

![Architecture](https://supabase.io/assets/images/supabase-architecture-9050a7317e9ec7efb7807f5194122e48.png)

- [PostgreSQL](https://www.postgresql.org/) is an object-relational database system with over 30 years of active development that has earned it a strong reputation for reliability, feature robustness, and performance.
- [Realtime](https://github.com/supabase/realtime) is an Elixir server that allows you to listen to PostgreSQL inserts, updates, and deletes using websockets. Supabase listens to Postgres' built-in replication functionality, converts the replication byte stream into JSON, then broadcasts the JSON over websockets.
- [PostgREST](http://postgrest.org/) is a web server that turns your PostgreSQL database directly into a RESTful API
- [Storage](https://github.com/supabase/storage-api) provides a RESTful interface for managing Files stored in S3, using Postgres to manage permissions.
- [postgres-meta](https://github.com/supabase/postgres-meta) is a RESTful API for managing your Postgres, allowing you to fetch tables, add roles, and run queries etc.
- [GoTrue](https://github.com/netlify/gotrue) is an SWT based API for managing users and issuing SWT tokens.
- [Kong](https://github.com/Kong/kong) is a cloud-native API gateway.

#### المكتبات الإضافية Client Libraries

المكتبات هي  معيارية. كل مكتبة فرعية هي تطبيق مستقل لنظام خارجي واحد. هذه إحدى الطرق التي ندعم بها الأدوات الحالية.

- **`supabase-{lang}`**: Combines libraries and adds enrichments.
  - `postgrest-{lang}`: Client library to work with [PostgREST](https://github.com/postgrest/postgrest)
  - `realtime-{lang}`: Client library to work with [Realtime](https://github.com/supabase/realtime)
  - `gotrue-{lang}`: Client library to work with [GoTrue](https://github.com/netlify/gotrue)

| Repo                  | Official                                         | Community                                                                                                                                                                                                                  |
| --------------------- | ------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **`supabase-{lang}`** | [`JS`](https://github.com/supabase/supabase-js)  | [`C#`](https://github.com/supabase/supabase-csharp) \| [`Dart`](https://github.com/supabase/supabase-dart) \| [`Python`](https://github.com/supabase/supabase-py) \| `Rust`                                                |
| `postgrest-{lang}`    | [`JS`](https://github.com/supabase/postgrest-js) | [`C#`](https://github.com/supabase/postgrest-csharp) \| [`Dart`](https://github.com/supabase/postgrest-dart) \| [`Python`](https://github.com/supabase/postgrest-py) \| [`Rust`](https://github.com/supabase/postgrest-rs) |
| `realtime-{lang}`     | [`JS`](https://github.com/supabase/realtime-js)  | [`C#`](https://github.com/supabase/realtime-csharp) \| [`Dart`](https://github.com/supabase/realtime-dart) \| [`Python`](https://github.com/supabase/realtime-py) \| `Rust`                                                |
| `gotrue-{lang}`       | [`JS`](https://github.com/supabase/gotrue-js)    | [`C#`](https://github.com/supabase/gotrue-csharp) \| [`Dart`](https://github.com/supabase/gotrue-dart) \| [`Python`](https://github.com/supabase/gotrue-py) \| `Rust`                                                      |

## Translations

- [English](https://github.com/supabase/supabase)
- [French](https://github.com/supabase/supabase/blob/master/i18n/README.fr.md)
- [German](https://github.com/supabase/supabase/blob/master/i18n/README.de.md)
- [Japanese](https://github.com/supabase/supabase/blob/master/i18n/README.jp.md)
- [Turkish](https://github.com/supabase/supabase/blob/master/i18n/README.tr.md)
- [Traditional Chinese](https://github.com/supabase/supabase/blob/master/i18n/README.zh-tw.md)
- [Spanish](https://github.com/supabase/supabase/blob/master/i18n/README.es.md)
- [Hindi](https://github.com/supabase/supabase/blob/master/i18n/README.hi.md)
- [Portuguese](https://github.com/supabase/supabase/blob/master/i18n/README.pt.md)
- [Português Brasileiro](https://github.com/supabase/supabase/blob/master/i18n/README.pt-br.md)
---

## Sponsors

[![New Sponsor](https://user-images.githubusercontent.com/10214025/90518111-e74bbb00-e198-11ea-8f88-c9e3c1aa4b5b.png)](https://github.com/sponsors/supabase)
