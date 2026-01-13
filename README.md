# elia-internt.github.io
مركز ايليا
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title id="site-title-tag">شركة إيليا للانترنيت</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Cairo:wght@400;700;900&display=swap');
        body { font-family: 'Cairo', sans-serif; background-color: #f1f5f9; scroll-behavior: smooth; }
        .admin-only { display: none; }
        body.is-admin .admin-only { display: block; }
        .hero-bg { background: linear-gradient(135deg, #1e3a8a 0%, #1e40af 100%); }
    </style>
</head>
<body>

    <button onclick="accessAdmin()" class="fixed bottom-4 left-4 z-[100] bg-slate-800 text-white p-3 rounded-full shadow-xl opacity-50 hover:opacity-100 transition">
        <i class="fas fa-user-shield"></i>
    </button>

    <div id="admin-panel" class="admin-only fixed inset-0 bg-slate-900/95 z-[99] overflow-y-auto p-6">
        <div class="max-w-4xl mx-auto bg-white rounded-2xl p-8 shadow-2xl">
            <div class="flex justify-between items-center mb-8 border-b pb-4">
                <h2 class="text-3xl font-black text-blue-600">لوحة تحكم إيليا</h2>
                <button onclick="exitAdmin()" class="bg-red-500 text-white px-4 py-1 rounded font-bold">حفظ وخروج</button>
            </div>

            <div class="grid grid-cols-1 md:grid-cols-2 gap-8 text-black">
                <div class="bg-blue-50 p-6 rounded-xl">
                    <h3 class="font-bold mb-4 border-b pb-2 text-blue-800 italic">1. المعلومات العامة</h3>
                    <div class="space-y-4">
                        <div>
                            <label class="block text-xs font-bold mb-1">اسم الشركة:</label>
                            <input type="text" id="edit-name" class="w-full p-2 border rounded shadow-sm">
                        </div>
                        <div>
                            <label class="block text-xs font-bold mb-1">رقم الهاتف:</label>
                            <input type="text" id="edit-phone" class="w-full p-2 border rounded shadow-sm">
                        </div>
                        <div>
                            <label class="block text-xs font-bold mb-1">عنوان الشركة:</label>
                            <input type="text" id="edit-address" class="w-full p-2 border rounded shadow-sm">
                        </div>
                    </div>
                </div>

                <div class="bg-green-50 p-6 rounded-xl text-black">
                    <h3 class="font-bold mb-4 border-b pb-2 text-green-800 italic">2. إضافة باقة جديدة</h3>
                    <div class="space-y-3">
                        <input type="text" id="new-p-name" placeholder="اسم الباقة (مثل: البرونزية)" class="w-full p-2 border rounded">
                        <input type="text" id="new-p-price" placeholder="السعر (مثلاً: 35,000)" class="w-full p-2 border rounded">
                        <input type="text" id="new-p-speed" placeholder="السرعة (مثلاً: 25 Mbps)" class="w-full p-2 border rounded">
                        <button onclick="addNewPackage()" class="w-full bg-green-600 text-white py-2 rounded font-bold hover:bg-green-700 transition">إضافة الباقة الآن</button>
                    </div>
                </div>
            </div>

            <div class="mt-8">
                <h3 class="font-bold mb-4 text-slate-700 border-b pb-2 italic">3. التحكم بالباقات الحالية (حذف)</h3>
                <div id="admin-packages-list" class="grid grid-cols-1 md:grid
