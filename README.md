# מפת בעלות משרדים — מגדלים A ו־B

אפליקציה לסימון הבעלות של כל משרד במגדלים A ו־B: **שי איילה אגם** או **לקוח פרטי**, עם שם, טלפון והערות.
כל הסימונים נשמרים ב־Firebase, ולכן כל מי שמתחבר רואה אותם בזמן אמת.

## הקבצים

| קובץ | מה הוא עושה |
|---|---|
| `index.html` | האפליקציה עצמה |
| `render.jpg` | ההדמיה של המגדלים |
| `config.js` | ההגדרות של Firebase. כל עוד הן לא מולאו, הסימונים נשמרים רק במכשיר |
| `firestore.rules` | קובע מי מורשה לראות ולסמן |

## הגדרה חד־פעמית (בערך 10 דקות)

1. **פתח פרויקט ב־Firebase:** היכנס ל־https://console.firebase.google.com, לחץ Add project ותן לו שם, למשל `office-towers`. את Google Analytics אפשר לכבות.
2. **הפעל התחברות עם Google:** במסך Build ‏> Authentication ‏> Get started ‏> Sign-in method, הפעל את Google ושמור.
3. **אשר את כתובת האתר:** באותו מסך, תחת Settings ‏> Authorized domains, הוסף את `idankru.github.io`.
4. **צור מסד נתונים:** במסך Build ‏> Firestore Database ‏> Create database, בחר מיקום (למשל `eur3`) והתחל ב־production mode.
5. **הגדר מי מורשה:** בלשונית Rules של Firestore, הדבק את התוכן של `firestore.rules` ולחץ Publish.
6. **העתק את ההגדרות:** במסך Project settings (גלגל השיניים) ‏> Your apps, לחץ על סמל ה־Web `</>`. רשום את האפליקציה והעתק את האובייקט `firebaseConfig` לקובץ `config.js`, במקום `null`. הערכים האלה לא סודיים, ומותר שהם יופיעו בקוד.
7. **הפעל את האתר:** בריפו ב־GitHub היכנס ל־Settings ‏> Pages, ובחר Branch: `main` ותיקייה `/ (root)`. אחרי דקה האתר יעלה בכתובת `https://idankru.github.io/<שם-הריפו>/`.

## להגביל מי יכול לסמן

ב־`firestore.rules` יש שתי אפשרויות: כל חשבון Google, או רשימת מיילים קבועה. כדי לעבור לרשימה, החלף ביניהן, הכנס את המיילים ולחץ Publish שוב.
