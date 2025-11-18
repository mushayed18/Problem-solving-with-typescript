```markdown
# 🎯 TypeScript Interview Questions - Blog Answers

## 1️⃣ Differences Between Interface and Type in TypeScript

TypeScript-এ object structure define করার জন্য সাধারণত দুইটি উপায় ব্যবহৃত হয়—**interface** এবং **type**। অনেক ক্ষেত্রে এরা একই কাজ করতে পারে, কিন্তু দুটির মধ্যে কিছু গুরুত্বপূর্ণ পার্থক্য আছে।

### ✅ 1. Interface “open”, কিন্তু Type “closed”

Interface পুনরায় ডিক্লেয়ার করলে সেটি merge হয়ে যায় (**declaration merging**):

```ts
interface User {
  name: string;
}

interface User {
  age: number;
}

const u: User = { name: "A", age: 20 }; // ✅ কোনো এরর নেই
```

অর্থাৎ, interface পরবর্তীতে বাড়ানো যায়।

কিন্তু type alias পুনরায় declare করা যায় না:

```ts
type User = { name: string };
type User = { age: number }; // ❌ Error: Duplicate identifier 'User'.
```

### ✅ 2. Interfaces সাধারণত শুধু object structure বর্ণনা করতে ব্যবহৃত হয়।

Type দিয়ে আরও বেশি ধরনের বিষয় define করা যায়।  
Type alias শুধু object shape নয়, বরং:

- union  
- tuple  
- primitive  
- intersection  

ইত্যাদি define করতে পারে।

```ts
type Status = "success" | "error"; // Interface এ করা যায় না
```
