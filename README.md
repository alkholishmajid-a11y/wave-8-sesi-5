# Yang akan kita kerjakan

1. Sedia static directory
2. Implementasi endpoint chatbot (POST /api/chat)
 - Mulai endpoint baru
 - Kita buat handler untuk meng-handle request POST /api/chat dari browser
 - buat beberapa guard clause (satpam)
    1. handle payload `conversation` dari `req.body` apakah berupa Array atau tidak
    2. handle setiap message yang ada pada payload `conversation` cek apakah setiap messagenya berupa object dengan isinya `{role: 'user'|'model', message: string}`;
        - Jika ada elemen yang tidak sesuai (tipe data-nya lain dari `object` atau nilainya `null`)
        - Setiap elemen tidak memiliki 2 property persis, dan tidak memiliki `role` dan `model` pada object-nya
        - `role` tidak berupa `user` atau `model`, atau `message` tidak bertipe `string` atau berisi string kosong(`""` atau `''`)
- Lakukan mapping agar bisa dikirim ke Google Gemini AI dengan function/method `generateContent()`
- Message yang diterima oleg Google Gemini API nanti akan dikirimkan kembali ke user dengan format `{success: boolean, message: string, data: string}