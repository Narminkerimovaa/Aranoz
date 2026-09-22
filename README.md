# Aranoz

Aranoz — React (Vite) əsasında qurulmuş frontend və Express + MongoDB əsasında qurulmuş backend-dən ibarət tam funksional e-ticarət (online mağaza) veb tətbiqidir. İstifadəçilər məhsullara baxa, onları səbətə və istək siyahısına əlavə edə bilər, admin isə yeni məhsullar əlavə edə bilər.

## Xüsusiyyətlər

- 🏠 Ana səhifədə məhsulların siyahısı
- 🔍 Məhsulun ətraflı baxış səhifəsi (`/detail/:id`)
- 🛒 Səbət (Basket) funksionallığı
- ❤️ İstək siyahısı (Wish List)
- 🛠️ Admin paneli — məhsulların idarə olunması (`/admin`)
- ➕ Yeni məhsul əlavə etmə səhifəsi (`/adminadd`)
- 📭 404 səhifəsi

## Texnologiyalar

**Frontend (FE):**
- React 19
- React Router 7
- Vite
- Formik + Yup (form idarəetməsi və validasiya)
- ESLint

**Backend (BE):**
- Node.js
- Express 5
- MongoDB + Mongoose
- CORS
- Nodemon

## Layihə strukturu

```
Aranoz/
├── BE/                 # Backend (Express + MongoDB)
│   ├── index.js
│   └── package.json
└── FE/                 # Frontend (React + Vite)
    ├── src/
    │   ├── components/ # Header, Footer, Layout
    │   ├── context/    # Basket, WishList, Main, Request provider-ləri
    │   ├── pages/       # Home, Admin, Admin Add, Basket, Wish List, Detail Page, No Page
    │   └── App.jsx
    └── package.json
```

## Quraşdırma

### Tələblər
- [Node.js](https://nodejs.org/) (v18 və ya daha yuxarı tövsiyə olunur)
- MongoDB verilənlər bazası (yerli və ya MongoDB Atlas)

### 1. Repozitoriyanı klonlayın

```bash
git clone https://github.com/Narminkerimovaa/Aranoz.git
cd Aranoz
```

### 2. Backend-i işə salın

```bash
cd BE
npm install
```

`BE` qovluğunda `.env` faylı yaradın və MongoDB bağlantı sətrini əlavə edin:

```
MONGO_URI=your_mongodb_connection_string
```

> ⚠️ **Qeyd:** Hazırkı `index.js` faylında MongoDB bağlantı sətri birbaşa kodun içində yazılıb. Təhlükəsizlik baxımından bu sətri `.env` faylına köçürüb `dotenv` paketi ilə oxumaq tövsiyə olunur, çünki bağlantı sətrində istifadəçi adı və şifrə açıq şəkildə görünür.

Serveri başladın:

```bash
npm start
```

Backend defolt olaraq `http://localhost:3000` ünvanında işləyəcək.

### 3. Frontend-i işə salın

Yeni terminal pəncərəsində:

```bash
cd FE
npm install
npm run dev
```

Frontend defolt olaraq `http://localhost:5173` ünvanında işləyəcək (Vite-in standart portu).

## API endpoint-ləri (Backend)

| Metod  | Endpoint          | Təsvir                         |
|--------|-------------------|---------------------------------|
| GET    | `/products/`      | Bütün məhsulları gətirir       |
| GET    | `/products/:id`   | ID-yə görə bir məhsulu gətirir |
| POST   | `/products/`      | Yeni məhsul yaradır            |
| PUT    | `/products/:id`   | Mövcud məhsulu yeniləyir       |
| DELETE | `/products/:id`   | Məhsulu silir                  |

## Lisenziya

Bu layihə şəxsi/təhsil məqsədilə hazırlanıb. Lisenziya təyin edilməyibsə, istifadə şərtləri üçün repozitoriya sahibi ilə əlaqə saxlayın.
