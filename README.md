# 🌸✨🍓 Lucyberry.SQLite 🍒💖  

The **Lucyberry.SQLite** library is here to sprinkle some berrylicious magic on your SQLite database interactions in .NET! 🌟 It’s sweet, fun, and makes your database life so much easier. Think of it as your adorable database BFF, ready to help you with CRUD operations, initialization, and more—all while keeping things super safe and secure! 💾💋  

---

## 💖✨ Features 🍓  

- **🍒 Magical Database Initialization**: Creates your SQLite database file automagically if it doesn’t exist. Easy peasy!  
- **🍓 Sweet CRUD Operations**: Insert, update, delete, or query data with a flick of your coding wand. 🪄  
- **💞 Injection-Proof Queries**: Safeguards your queries like a knight in shiny berry armor. ⚔️🍒  
- **🍰 Flexible Setup**: Includes optional base image URI support for extra cuteness. 📸✨  

---

## 🍓✨ Installation 🍒  

Follow these steps to invite Lucyberry.SQLite into your project:  

1. Add the **Lucyberry.SQLite** class to your project.  
2. Install the `System.Data.SQLite` NuGet package to give it all the berry juice it needs! 🍇  

```bash  
dotnet add package System.Data.SQLite  
```  

---

## 🌸 How to Use 🍓  

### 💞 1. Initialize Lucyberry  

```csharp  
using Lucyberry.SQLite;

// 🍓🌸 Create your dreamy *Berry Basket* database! 🍒✨  
var berryBasketHelper = new SQLiteHelper("C:\\BerryParadise", "ChocoBerryTreats.db", new Uri("http://example.com/berryland"));

// 🎀 Want a simpler basket? Skip the extras and keep it chic! 🍓💖
var simpleBerryHelper = new SQLiteHelper("C:\\BerryParadise", "ChocoBerryTreats.db");
```  

---

💖 **What’s happening here?**  
1️⃣ **First Line:** 🌸 We’re creating a *berry-tastic* database named **ChocoBerryTreats.db** 🍓🍫, stored in your **BerryParadise** folder! Plus, it’s linked to a *juicy online berryland* for a cherry-on-top experience! 🌟✨  

2️⃣ **Second Line:** 🍒 Prefer it simple? We’re keeping it fresh and girly by focusing just on the database without the extra sprinkles! 🌸💕

---

💻✨ **Why Lucyberry.SQLite?**  
- 🍓 *Keeps your data sweet*: Like perfectly organized berries in a cute little basket! 🎀  
- 💖 *Flexible & chic*: Whether it’s a dazzling berry URI or a simple berry treat, it’s all covered! 🍒✨  

---

**💡 Pro Tip:** When life gives you berries, turn them into a *berry-licious* database! 🍓💖  

Sprinkle some **#BerryMagic** in your next project and let it shine brighter than a cherry-filled sundae! 🍒✨

---

### 🍒 2. Insert Some Juicy Data  

#### 🍓 Insert a Berrylicious Collection  

```csharp  
var data = new List<Dictionary<string, object>>  
{  
    new Dictionary<string, object> { { "Name", "Lucyberry" }, { "Type", "Berry" } },  
    new Dictionary<string, object> { { "Name", "Cherry" }, { "Type", "Fruit" } },  
};  

await helper.InsertDataAsync("Products", data);  
```  

#### 💖 Insert Data and Fetch the Last Berry ID  

```csharp  
int lastId = await helper.InsertReturnDataAsync("Products", data);  
Console.WriteLine($"🍓 Last inserted ID: {lastId}");  
```  

---

### ✨ 3. Query Your Berryland  

#### 🌸 Read All Rows (Get All the Berries!)  

```csharp  
var rows = await helper.ReadAllDataAsync("Products");  
foreach (var row in rows)  
{  
    Console.WriteLine(string.Join(", ", row.Select(kvp => $"{kvp.Key}: {kvp.Value}")));  
}  
```  

#### 🍓 Read Rows with Sweet Conditions  

```csharp  
var conditions = new Dictionary<string, object> { { "Type", "Berry" } };  
var rowsWithConditions = await helper.ReadDataAsync("Products", conditions);  
```  

---

### 💖 4. Update Your Berries  

#### 🍰 Sweetly Update Rows  

```csharp  
var updatedValues = new Dictionary<string, object> { { "Name", "Sweet Lucyberry" } };  
var conditions = new Dictionary<string, object> { { "Name", "Lucyberry" } };  

await helper.UpdateDataAsync("Products", updatedValues, conditions);  
```  

---

### ✨ 5. Delete a Berry (But Why Tho? 😢)  

```csharp  
var conditions = new Dictionary<string, object> { { "Name", "Lucyberry" } };  

await helper.DeleteDataAsync("Products", conditions);  
```  

---

## 🌸 Notes for the Cutie Coders 🍒  

- **🍓 Connection Love**: Lucyberry takes care of opening and closing your database connections for you. No stress, just magic!  
- **💞 Thread Safety**: She’s reliable, but make sure to synchronize threads if things get super busy. 💼✨  
- **🍒 Stay Safe**: Always use parameterized queries—no sneaky injections here!  

---

## 🌸 How to Contribute 💖  

We’d love your ideas! 🌟 If you find a bug 🐞 or dream of a new feature, send us a pull request or file an issue. Let’s make Lucyberry sparkle even brighter together! 💎  

---

## 🌸✨ License 🍓  

This project is licensed under the super-flexible MIT License. 🌟 So go ahead and spread the berry sweetness wherever you like! 💖🍒  