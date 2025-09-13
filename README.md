# Inventroy Management System Portal 🛍️

A modern web application built with Next.js for sales representatives to manage products, customers, orders and their profiles.

## ✨ Features

- 🔐 Secure authentication with JWT
- 👤 User profile management 
- 📦 Product management (CRUD operations)
- 🛒 Shopping cart functionality
- 📋 Order history
- 👥 Customer management
- 🖼️ Image upload support
- 🎨 Beautiful UI with Tailwind CSS & DaisyUI

## 🚀 Tech Stack

- [Next.js 14](https://nextjs.org/) - React Framework
- [TypeScript](https://www.typescriptlang.org/) - Type Safety
- [Tailwind CSS](https://tailwindcss.com/) - Styling
- [DaisyUI](https://daisyui.com/) - UI Components
- [Axios](https://axios-http.com/) - HTTP Client
- [React Hot Toast](https://react-hot-toast.com/) - Toast Notifications

## 🛠️ Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/sales-portal.git
cd sales-portal
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env.local` file:
```env
NEXT_PUBLIC_API_URL=http://localhost:3001
```

4. Run the development server:
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) to view the application.

## 📂 Project Structure

```
├── app/
│   ├── Sales_Representatives/
│   │   ├── add_address/
│   │   ├── add_customer/
│   │   ├── add_product/
│   │   ├── cart/
│   │   ├── components/
│   │   ├── dashboard/
│   │   ├── show_order/
│   │   ├── show_profile/
│   │   └── ...
│   ├── layout.tsx
│   └── page.tsx
├── public/
├── package.json
├── tailwind.config.ts
└── tsconfig.json
```

## 🔒 Authentication

The application uses JWT-based authentication:

```typescript
const handleSignIn = async () => {
  try {
    const response = await axios.post('/auth/login', credentials);
    localStorage.setItem('token', response.data.access_token);
    localStorage.setItem('username', credentials.username);
  } catch (error) {
    console.error('Sign in failed:', error);
  }
};
```

## 🎯 Key Features Implementation

### Protected Routes

```typescript
const Session = () => {
  useEffect(() => {
    const token = localStorage.getItem('token');
    if (!token) {
      router.push('/sign_in');
    }
  }, []);
};
```

### File Upload

```typescript
const handleFileUpload = async (e: React.ChangeEvent<HTMLInputElement>) => {
  const file = e.target.files?.[0];
  const formData = new FormData();
  formData.append('file', file);
  
  await axios.post('/upload', formData);
};
```

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🤝 Contributing

Contributions, issues and feature requests are welcome! Feel free to check the [issues page](issues).

## 👨‍💻 Author

- Your Name
- GitHub: [@yourusername](https://github.com/yourusername)
