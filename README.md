<img width="720" height="782" alt="4" src="https://github.com/user-attachments/assets/abc7cd18-4cba-4d9e-bbdd-ba0a8dd67375" />
<img width="1895" height="776" alt="3" src="https://github.com/user-attachments/assets/827198a3-80c1-47e7-bdc7-d71a90e8fa7d" />
<img width="1911" height="720" alt="2" src="https://github.com/user-attachments/assets/81525ab4-c518-4e12-8487-14b76386f539" />
<img width="1895" height="792" alt="1" src="https://github.com/user-attachments/assets/fc04df6e-71ec-4c7b-bd9b-eb8087f36cb5" />
# Experiment 10: Data Sharing Using Contacts Content Provider

## 1. Aim
To develop an Android application that retrieves and displays contact names and phone numbers using the Android Contacts Content Provider.

## 2. Technologies Used
- **IDE:** Android Studio
- **Language:** Kotlin
- **UI Design:** XML
- **Platform:** Android
- **Minimum SDK:** API 24
- **Concepts:** Content Provider, Runtime Permissions, ListView

## 3. Project Structure

```text
ContactsProviderApp/
│
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/
│   │   │   │   └── com/
│   │   │   │       └── example/
│   │   │   │           └── contactsproviderapp/
│   │   │   │               └── MainActivity.kt
│   │   │   │
│   │   │   ├── res/
│   │   │   │   ├── layout/
│   │   │   │   │   └── activity_main.xml
│   │   │   │   ├── values/
│   │   │   │   │   ├── strings.xml
│   │   │   │   │   ├── colors.xml
│   │   │   │   │   └── themes.xml
│   │   │   │   ├── drawable/
│   │   │   ├── xml/
│   │   │   │   ├── backup_rules.xml
│   │   │   │   └── data_extraction_rules.xml
│   │   │   │
│   │   │   └── AndroidManifest.xml
│   │   │
│   │   ├── androidTest/
│   │   └── test/
│   │
│   ├── build.gradle.kts
│   └── proguard-rules.pro
│
├── gradle/
│   └── libs.versions.toml
│
├── build.gradle.kts
├── settings.gradle.kts
├── gradlew
├── gradlew.bat
├── gradle.properties
└── README.md
```

## 4. Features
- Requests permission to read contacts.
- Retrieves contact names and phone numbers.
- Displays contacts in a `ListView`.
- Shows a message if permission is denied or no contacts are found.

## 5. Permission
The following permission is declared in `AndroidManifest.xml`:

```xml
<uses-permission android:name="android.permission.READ_CONTACTS" />
```

The application also requests this permission at runtime before accessing contacts.

## 6. Procedure
1. Create an **Empty Views Activity** project named `ContactsProviderApp`.
2. Design the user interface in `activity_main.xml`.
3. Add the contacts permission in `AndroidManifest.xml`.
4. Write the contact retrieval logic in `MainActivity.kt`.
5. Run the application on an Android phone or emulator.
6. Tap **Load Contacts** and grant permission.
7. Verify that contact names and phone numbers appear on the screen.

## 7. Working Principle
The application uses `ContactsContract.CommonDataKinds.Phone.CONTENT_URI` to query the device's Contacts Content Provider. It retrieves contact names and phone numbers through `ContentResolver` and displays the results using an `ArrayAdapter` connected to a `ListView`.

## 8. Expected Output
The application screen contains:
- **Contacts Content Provider** heading
- **Load Contacts** button
- List of saved contact names and phone numbers

If the device has no saved contacts, the application displays `No contacts found`.

## 9. Test Cases

| Test Case | Input / Action | Expected Output |
|---|---|---|
| 1 | Open the application | Title and button appear |
| 2 | Tap Load Contacts and allow permission | Saved contacts appear |
| 3 | Deny permission | Permission-denied message appears |
| 4 | No saved contacts available | No contacts found appears |


## 10. Result
The application successfully demonstrates retrieving and displaying contact names and phone numbers using Android's Contacts Content Provider with runtime permission handling.

## 11. Conclusion
This experiment explains the use of Android Content Providers, `ContactsContract`, `ContentResolver`, runtime permissions, and `ListView` for accessing and displaying device contacts.
