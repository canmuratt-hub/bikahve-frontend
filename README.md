# 🏆 BiKahve - Frontend (Turkcell CodeNight '26 Hatay Bölge Birincilik Projesi)

Bu proje, **Turkcell CodeNight 2026** maratonunda 10 saatlik süre içerisinde geliştirilen ve Hatay ayağında **birincilik** elde eden **BiKahve** platformunun frontend kodlarını içermektedir.

## 🚀 Proje Hakkında
BiKahve, kullanıcıların konum bazlı kahve dükkanı keşfi yapabildiği, aboneliklerini yönetebildiği ve QR kod ile hızlı teslimat alabildiği bir full-stack kahve abonelik uygulamasıdır. 

**Ekip İsmi:** Local Host

# Genel Bakış

`codenight` içinde iki ana uygulama bulunuyor:

- `bikahve-backend` - NestJS tabanlı API ve abonelik altyapısı
- `bikahve-frontend` - React + Vite tabanlı kullanıcı arayüzü
- `docker-compose.yml` - PostgreSQL, backend ve frontend servislerini birlikte çalıştırmak için

Bu repo, hem backend hem de frontend tarafını tek bir yerde tutmak için organize edildi.

## Proje Yapısı

- `bikahve-backend/`
  - NestJS sunucusu
  - Prisma ORM ve PostgreSQL entegrasyonu
  - JWT tabanlı yetkilendirme
- `bikahve-frontend/`
  - React uygulaması
  - Vite + TailwindCSS + React Router
  - Harita ve QR destekli kullanıcı deneyimi
- `docker-compose.yml`
  - PostgreSQL veritabanı
  - Backend servisi
  - Frontend servisi

## Gereksinimler

- Node.js 20+ (önerilen)
- npm
- Docker ve Docker Compose

## Hızlı Başlangıç

### 1) Docker ile çalıştırma

```bash
docker compose up --build
```

Bu komut aşağıdaki servisleri başlatır:

- PostgreSQL veritabanı
- NestJS backend
- React frontend

### 2) Backend kurulumu

```bash
cd bikahve-backend
npm install
npm run prisma:generate
npm run prisma:migrate
npm run start:dev
```

Backend varsayılan olarak `http://localhost:3000` üzerinde çalışır.

### 3) Frontend kurulumu

```bash
cd bikahve-frontend
npm install
npm run dev
```

Frontend varsayılan olarak `http://localhost:5173` üzerinde çalışır.

## Ortam Değişkenleri

`docker-compose.yml` içinde backend için temel ortam değişkenleri tanımlandı:

- `DATABASE_URL`
- `APP_PORT`
- `JWT_ACCESS_SECRET`
- `JWT_REFRESH_SECRET`
- `JWT_ACCESS_TTL`
- `JWT_REFRESH_TTL`
- `OTP_SIMULATION_CODE`
- `QR_HMAC_SECRET`

Bu değerler yerel geliştirme için ayarlandı ve üretim ortamında değiştirilmeli.

## Önemli Not

Bu repo tek bir kök dizin altında organize edildiği için, eğer `bikahve-backend` ve `bikahve-frontend` içinde ayrı `.git` klasörleri varsa, tek bir ana repo ile tutarlı olması için bunları silip kök dizinde `git init` yapabilirsin.

## İletişim

Projeyi GitHub'a yüklemek için aşağıdaki adımları takip et:

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/<kullaniciadi>/<repoadi>.git
git push -u origin main
```
Bu projenin fronted kısmını üstlendim bir ekip çalışmasının ürünüdür.
