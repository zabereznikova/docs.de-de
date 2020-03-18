---
ms.openlocfilehash: c8f44ae1a500ed240dbff7d9a2c1479af368b7f1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "72394050"
---
### <a name="identity-default-bootstrap-version-of-ui-changed"></a><span data-ttu-id="97a87-101">Identität: Bootstrap-Standardversion der Benutzeroberfläche geändert</span><span class="sxs-lookup"><span data-stu-id="97a87-101">Identity: Default Bootstrap version of UI changed</span></span>

<span data-ttu-id="97a87-102">Ab ASP.NET Core 3.0 verwendet die Identitäts-Benutzeroberfläche standardmäßig Version 4 von Bootstrap.</span><span class="sxs-lookup"><span data-stu-id="97a87-102">Starting in ASP.NET Core 3.0, Identity UI defaults to using version 4 of Bootstrap.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="97a87-103">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="97a87-103">Version introduced</span></span>

<span data-ttu-id="97a87-104">3.0</span><span class="sxs-lookup"><span data-stu-id="97a87-104">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="97a87-105">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="97a87-105">Old behavior</span></span>

<span data-ttu-id="97a87-106">Der `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();`-Methodenaufruf war mit `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);` identisch.</span><span class="sxs-lookup"><span data-stu-id="97a87-106">The `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` method call was the same as `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);`</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="97a87-107">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="97a87-107">New behavior</span></span>

<span data-ttu-id="97a87-108">Der `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();`-Methodenaufruf ist mit `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);` identisch.</span><span class="sxs-lookup"><span data-stu-id="97a87-108">The `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();` method call is the same as `services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap4);`</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="97a87-109">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="97a87-109">Reason for change</span></span>

<span data-ttu-id="97a87-110">Bootstrap 4 wurde im Zeitrahmen von ASP.NET Core 3.0 veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="97a87-110">Bootstrap 4 was released during ASP.NET Core 3.0 timeframe.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="97a87-111">Empfohlene Aktion</span><span class="sxs-lookup"><span data-stu-id="97a87-111">Recommended action</span></span>

<span data-ttu-id="97a87-112">Diese Änderung hat Auswirkungen auf Ihre Arbeit, wenn Sie die Standardbenutzeroberfläche für Identitäten verwenden und diese in `Startup.ConfigureServices` hinzugefügt haben, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="97a87-112">You're impacted by this change if you use the default Identity UI and have added it in `Startup.ConfigureServices` as shown in the following example:</span></span>

```csharp
services.AddDefaultIdentity<IdentityUser>().AddDefaultUI();
```

<span data-ttu-id="97a87-113">Führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="97a87-113">Take one of the following actions:</span></span>

- <span data-ttu-id="97a87-114">Migrieren Sie Ihre App mithilfe der [Migrationsanleitung](https://getbootstrap.com/docs/4.0/migration) zur Verwendung von Bootstrap 4.</span><span class="sxs-lookup"><span data-stu-id="97a87-114">Migrate your app to use Bootstrap 4 using their [migration guide](https://getbootstrap.com/docs/4.0/migration).</span></span>
- <span data-ttu-id="97a87-115">Aktualisieren Sie `Startup.ConfigureServices`, um die Verwendung von Bootstrap 3 zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="97a87-115">Update `Startup.ConfigureServices` to enforce usage of Bootstrap 3.</span></span> <span data-ttu-id="97a87-116">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="97a87-116">For example:</span></span>

    ```csharp
    services.AddDefaultIdentity<IdentityUser>().AddDefaultUI(UIFramework.Bootstrap3);
    ```

#### <a name="category"></a><span data-ttu-id="97a87-117">Kategorie</span><span class="sxs-lookup"><span data-stu-id="97a87-117">Category</span></span>

<span data-ttu-id="97a87-118">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="97a87-118">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="97a87-119">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="97a87-119">Affected APIs</span></span>

<span data-ttu-id="97a87-120">Keine</span><span class="sxs-lookup"><span data-stu-id="97a87-120">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
