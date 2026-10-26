# শুধু Android ফোন দিয়ে APK বানানোর সহজ নিয়ম

এই প্রজেক্টে GitHub Actions workflow যোগ করা আছে। GitHub-এর cloud computer-এ APK build হবে; ফোনে Flutter/Android Studio লাগবে না।

## ধাপ ১ — ZIP আনজিপ করে আবার ZIP করবেন না
1. ফোনের browser-এ GitHub.com খুলে account তৈরি/লগইন করুন।
2. **New repository** চাপুন; নাম দিন `all-in-one-tools-bd`; Public বা Private বেছে Create repository করুন।
3. Repository-তে **Add file → Upload files** দিয়ে এই ZIP-এর ভেতরের ফাইলগুলো আপলোড করতে হবে—ZIP ফাইলটিকে একা upload করবেন না। আগে ফোনের Files app/ZIP extractor দিয়ে ZIP extract করুন।
4. Extract করা ফোল্ডারের ভেতরের সব ফাইল/ফোল্ডার একসাথে upload করুন, যেন `.github/workflows/build-apk.yml` এবং `all_in_one_tools_bd/` repository-র root-এ থাকে। Dot-folder `.github` দেখা না গেলে file manager-এর “show hidden files” চালু করুন।
5. Upload শেষে **Commit changes** চাপুন।

## ধাপ ২ — Build চালানো
1. Repository-র **Actions** tab খুলুন।
2. `Build Android APK` workflow নির্বাচন করুন। প্রয়োজনে **Run workflow → Run workflow** চাপুন।
3. Build শেষ হওয়া পর্যন্ত অপেক্ষা করুন (সাধারণত কয়েক মিনিট; ব্যর্থ হলে লাল X দেখাবে)।
4. সফল হলে workflow run-এর নিচে **Artifacts** থেকে `all-in-one-tools-bd-apk` ডাউনলোড করুন। এটি ZIP হবে; extract করলে `app-release.apk` পাবেন।
5. APK খুলে Android-এর নির্দেশনা অনুযায়ী এই ফাইলের জন্য install permission দিন, তারপর Install চাপুন। শুধু নিজের তৈরি/বিশ্বস্ত APK ইনস্টল করুন।

## গুরুত্বপূর্ণ
- এই workflow build করার চেষ্টা করে; সফল build বা Play Store approval নিশ্চিত করে না। Error হলে Actions log-এর লাল error অংশ পাঠান।
- AdMob live monetization চালুর আগে নিজের App ID ও Ad Unit ID বসাতে হবে এবং privacy/consent ও Google Play নীতিমালা ঠিক করতে হবে। টেস্ট বিজ্ঞাপন থেকে বাস্তব আয় হবে না।
- GitHub repository-তে secret, password, API key বা ব্যক্তিগত নথি আপলোড করবেন না।
