# Voice Agent (Android, Kotlin)

## চালানোর নিয়ম
1. Android Studio-তে এই ফোল্ডারটি Open করুন → Gradle sync (প্রথমবার ইন্টারনেট লাগবে)।
2. Android 11+ ফোনে (USB debugging চালু) Run করুন।
3. অ্যাপে Anthropic API key বসান (console.anthropic.com)।
4. "Accessibility সেটিংস খুলুন" → Installed apps → Voice Agent Control → চালু করুন।
   (Android 13+ এ "Restricted setting" দেখালে: Settings → Apps → Voice Agent → ⋮ → Allow restricted settings)
5. কাজ বলুন/লিখুন, যেমন: "Chrome খুলে আজকের আবহাওয়া সার্চ করো" → ▶ চাপুন।

## ফাইল
- AgentAccessibilityService.kt — স্ক্রিনশট, UI ট্রি, ট্যাপ/সোয়াইপ/টাইপ/Back/Home/অ্যাপ খোলা
- ClaudeClient.kt — Claude API (tool use), মডেল নাম MODEL ধ্রুবকে
- Agent.kt — Observe→Think→Act→Verify লুপ (সর্বোচ্চ ২৫ ধাপ)
- MainActivity.kt — UI, ভয়েস ইনপুট (bn-BD), TTS

## সীমাবদ্ধতা
- FLAG_SECURE স্ক্রিন (ব্যাংকিং, পাসওয়ার্ড) স্ক্রিনশটে কালো দেখায়।
- রিয়েল-টাইম গেমে প্রতিক্রিয়া ধীর (১–৩ সেকেন্ড); টার্ন-বেসড গেমে ঠিক আছে।
- অনলাইন গেমে অটোমেশন ব্যান হতে পারে।
- API key ফোনে রাখা শুধু ব্যক্তিগত পরীক্ষার জন্য; প্রকাশ করলে নিজের সার্ভার প্রক্সি ব্যবহার করুন।
- কোডটি এখানে বিল্ড করে পরীক্ষা করা হয়নি; Android Studio-তে ছোটখাটো ত্রুটি আসতে পারে।
