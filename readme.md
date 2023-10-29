# Dokumentasi API

## Environment Variables

```env
DATABASE_URL=""
IMAGEKIT_URL_ENDPOINT=""
IMAGEKIT_PUBLIC_KEY=""
IMAGEKIT_PRIVATE_KEY=""
```

## API untuk Membuat Postingan Baru

API ini digunakan untuk membuat postingan baru dengan content type `multipart/form-data`. Berikut adalah fields yang harus diisi:

1. `title` (String) - The title of the post.
2. `description` (String) - The description of the post.
3. `image` (File) - An image file in JPEG or PNG format.

### Endpoint

```http
POST /api/v1/posts
```

### Request Body

| Field         | Type     | Required | Description               |
| :------------ | :------- | :------- | :------------------------ |
| `title`       | `string` | **Yes**  | Judul dari postingan      |
| `description` | `string` | **No**   | Deskripsi dari postingan  |
| `image`       | `file`   | **Yes**  | Gambar yang akan diunggah |

## API untuk melihat semua postingan

API ini digunakan untuk melihat semua postingan yang sudah dibuat.

### Endpoint

```http
GET /api/v1/posts
```

### Response Body

```json
[
  {
    "id": 1,
    "title": "Judul Postingan 1",
    "description": "Deskripsi Postingan 1",
    "image_url": "https://example.com/image1.jpg"
  },
  {
    "id": 2,
    "title": "Judul Postingan 2",
    "description": "Deskripsi Postingan 2",
    "image_url": "https://example.com/image2.jpg"
  }
]
```

## API untuk melihat detail dari sebuah postingan

API ini digunakan untuk melihat detail dari sebuah postingan.

### Endpoint

```http
GET /api/v1/posts/:postId
```

### Request Parameters

| Parameters | Type     | Required | Description                          |
| :--------- | :------- | :------- | :----------------------------------- |
| `postId`   | `number` | **Yes**  | ID dari postingan yang ingin dilihat |

### Response Body

```json
{
  "id": 1,
  "title": "Judul Postingan 1",
  "description": "Deskripsi Postingan 1",
  "image_url": "https://example.com/image1.jpg"
}
```

## API untuk mengubah postingan

API ini digunakan untuk mengubah `title` dan `description` pada sebuah postingan dengan content-type: `application/json`.

### Endpoint

```http
PUT /api/v1/posts/:postId
```

### Request Body

| Fields        | Type     | Required | Description              |
| :------------ | :------- | :------- | :----------------------- |
| `title`       | `string` | **Yes**  | Judul dari postingan     |
| `description` | `string` | **no**   | Deskripsi dari postingan |

## API untuk menghapus postingan

API ini digunakan untuk menghapus postingan dengan gambarnya.

### Endpoint

```http
DELETE /api/v1/posts/:postId
```

### Request Parameters

| Parameters | Type     | Required | Description                          |
| :--------- | :------- | :------- | :----------------------------------- |
| `postId`   | `number` | **Yes**  | ID dari postingan yang ingin dilihat |
