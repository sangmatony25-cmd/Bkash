# Android APK Build & GitHub CI/CD Setup

এই রিপোজিটরিতে **অটোমেটিক (Auto)** এবং **ম্যানুয়াল (Manual)** উভয় উপায়ে APK বিল্ড করার সম্পূর্ণ GitHub Actions CI/CD কনফিগারেশন যোগ করা হয়েছে (`.github/workflows/build-apk.yml`)।

---

## ১. অটোমেটিক এপিকে বিল্ড (Auto Build)
- যখনই আপনি নতুন কোনো কোড এই রিপোজিটরির `main` অথবা `master` ব্রাঞ্চে **Push** করবেন বা কোনো **Pull Request** করবেন, GitHub Actions ব্যাকগ্রাউন্ডে স্বয়ংক্রিয়ভাবে APK বিল্ড শুরু করে দেবে।
- বিল্ড সম্পন্ন হলে GitHub Actions এর **Artifacts** সেকশনে সরাসরি ডাউনলোডযোগ্য `app-debug-apk` ফাইল পেয়ে যাবেন।

---

## ২. ম্যানুয়ালি এপিকে বিল্ড (Manual Build via GitHub Actions)
যেকোনো সময় কোড পুশ না করেও এক ক্লিকে ম্যানুয়ালি APK তৈরি করতে পারবেন:
1. আপনার GitHub রিপোজিটরি ওপেন করুন (`sangmatony25-cmd/A-C-AK87`)।
2. উপরের মেনু থেকে **Actions** ট্যাবে যান।
3. বাঁ পাশের তালিকা থেকে **"Build Android APK (Auto & Manual)"** সিলেক্ট করুন।
4. ডান পাশের **"Run workflow"** ড্রপডাউন বাটনে ক্লিক করুন।
5. বিল্ডের ধরন নির্বাচন করুন:
   - `debug` (টেস্টিং এবং ইন্সটলের জন্য)
   - `release` (প্রোডাকশন/রিলিজ এর জন্য)
6. সবুজ **"Run workflow"** বাটনে চাপ দিন। ১-২ মিনিটের মধ্যে APK তৈরি হয়ে যাবে এবং ডাউনলোড করতে পারবেন।

---

## ৩. লোকাল মেশিনে ম্যানুয়ালি বিল্ড করার কমান্ড (Terminal / CMD)
যদি আপনার কম্পিউটারে অ্যান্ড্রয়েড স্টুডিও বা টার্মিনাল থাকে:
- **Debug APK তৈরি করতে:**
  ```bash
  ./gradlew assembleDebug
  ```
  *(ফাইল লোকেশন: `app/build/outputs/apk/debug/app-debug.apk`)*

- **Release APK তৈরি করতে:**
  ```bash
  ./gradlew assembleRelease
  ```
  *(ফাইল লোকেশন: `app/build/outputs/apk/release/app-release-unsigned.apk`)*
