---
title: Xamarin-Einschränkungen
ms.date: 12/13/2019
description: Beschreibt einige der Einschränkungen, die bei der Verwendung von xamarin auftreten werden.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450405"
---
# <a name="xamarin-limitations"></a><span data-ttu-id="5ff3e-103">Xamarin-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5ff3e-103">Xamarin limitations</span></span>

<span data-ttu-id="5ff3e-104">"Microsoft. Data. sqlite" ist .NET Standard 2,0 und wird für xamarin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5ff3e-104">Microsoft.Data.Sqlite targets .NET Standard 2.0 and is supported on Xamarin.</span></span> <span data-ttu-id="5ff3e-105">In der folgenden Tabelle ist aufgeführt, für welche Plattformen das sqlitepclraw-Standardpaket Native SQLite-Binärdateien bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="5ff3e-105">The following table shows which platforms the default SQLitePCLRaw bundle provides native SQLite binaries for.</span></span> <span data-ttu-id="5ff3e-106">Weitere Informationen zur Verwendung eines anderen Pakets oder zum Bereitstellen eigener Binärdateien für SQLite finden Sie unter [benutzerdefinierte SQLite-Versionen](custom-versions.md) .</span><span class="sxs-lookup"><span data-stu-id="5ff3e-106">See [Custom SQLite versions](custom-versions.md) for details on using a different bundle or providing your own native SQLite binaries.</span></span>

| <span data-ttu-id="5ff3e-107">Platform</span><span class="sxs-lookup"><span data-stu-id="5ff3e-107">Platform</span></span> | <span data-ttu-id="5ff3e-108">SQLite-Binärdateien</span><span class="sxs-lookup"><span data-stu-id="5ff3e-108">SQLite binaries</span></span> |
| --- | --- |
| <span data-ttu-id="5ff3e-109">**Xamarin.Android**</span><span class="sxs-lookup"><span data-stu-id="5ff3e-109">**Xamarin.Android**</span></span> | <span data-ttu-id="5ff3e-110">—</span><span class="sxs-lookup"><span data-stu-id="5ff3e-110">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | <span data-ttu-id="5ff3e-111">✔</span><span class="sxs-lookup"><span data-stu-id="5ff3e-111">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | <span data-ttu-id="5ff3e-112">✔</span><span class="sxs-lookup"><span data-stu-id="5ff3e-112">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="5ff3e-113">✔</span><span class="sxs-lookup"><span data-stu-id="5ff3e-113">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | <span data-ttu-id="5ff3e-114">✔</span><span class="sxs-lookup"><span data-stu-id="5ff3e-114">✔</span></span> |
| <span data-ttu-id="5ff3e-115">**Xamarin.iOS**</span><span class="sxs-lookup"><span data-stu-id="5ff3e-115">**Xamarin.iOS**</span></span> | <span data-ttu-id="5ff3e-116">✔</span><span class="sxs-lookup"><span data-stu-id="5ff3e-116">✔</span></span> |
| <span data-ttu-id="5ff3e-117">**Xamarin.Mac**</span><span class="sxs-lookup"><span data-stu-id="5ff3e-117">**Xamarin.Mac**</span></span> | <span data-ttu-id="5ff3e-118">✔</span><span class="sxs-lookup"><span data-stu-id="5ff3e-118">✔</span></span> |
| <span data-ttu-id="5ff3e-119">**Xamarin. tvos**</span><span class="sxs-lookup"><span data-stu-id="5ff3e-119">**Xamarin.TVOS**</span></span> | <span data-ttu-id="5ff3e-120">✔</span><span class="sxs-lookup"><span data-stu-id="5ff3e-120">✔</span></span> |
| <span data-ttu-id="5ff3e-121">**UWP**</span><span class="sxs-lookup"><span data-stu-id="5ff3e-121">**UWP**</span></span> | <span data-ttu-id="5ff3e-122">—</span><span class="sxs-lookup"><span data-stu-id="5ff3e-122">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | <span data-ttu-id="5ff3e-123">✔</span><span class="sxs-lookup"><span data-stu-id="5ff3e-123">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | <span data-ttu-id="5ff3e-124">✔</span><span class="sxs-lookup"><span data-stu-id="5ff3e-124">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | <span data-ttu-id="5ff3e-125">✔</span><span class="sxs-lookup"><span data-stu-id="5ff3e-125">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="5ff3e-126">✔</span><span class="sxs-lookup"><span data-stu-id="5ff3e-126">✔</span></span> |

## <a name="ios"></a><span data-ttu-id="5ff3e-127">iOS</span><span class="sxs-lookup"><span data-stu-id="5ff3e-127">iOS</span></span>

<span data-ttu-id="5ff3e-128">Microsoft. Data. sqlite versucht, sqlitepclraw-Bündel automatisch zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="5ff3e-128">Microsoft.Data.Sqlite tries to automatically initialize SQLitePCLRaw bundles.</span></span> <span data-ttu-id="5ff3e-129">Aufgrund von Einschränkungen bei der Ahead-of-Time-Kompilierung (AOT) für xamarin. IOS schlägt der Versuch fehl, und Sie erhalten die folgende Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="5ff3e-129">Unfortunately, because of limitations in the ahead-of-time (AOT) compilation for Xamarin.iOS, the attempt fails and you get the following error.</span></span>

> <span data-ttu-id="5ff3e-130">Sie müssen `SQLitePCL.raw.SetProvider()`abrufen.</span><span class="sxs-lookup"><span data-stu-id="5ff3e-130">You need to call `SQLitePCL.raw.SetProvider()`.</span></span> <span data-ttu-id="5ff3e-131">Wenn Sie ein Paket Paket verwenden, erfolgt dies durch Aufrufen von `SQLitePCL.Batteries.Init()`.</span><span class="sxs-lookup"><span data-stu-id="5ff3e-131">If you're using a bundle package, this is done by calling `SQLitePCL.Batteries.Init()`.</span></span>

<span data-ttu-id="5ff3e-132">Fügen Sie der APP vor der Verwendung von "Microsoft. Data. sqlite" die folgende Codezeile hinzu, um das Paket zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="5ff3e-132">To initialize the bundle, add the following line of code to your app before using Microsoft.Data.Sqlite.</span></span>

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a><span data-ttu-id="5ff3e-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ff3e-133">See also</span></span>

* [<span data-ttu-id="5ff3e-134">Async-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="5ff3e-134">Async limitations</span></span>](async.md)
* [<span data-ttu-id="5ff3e-135">Benutzerdefinierte SQLite-Versionen</span><span class="sxs-lookup"><span data-stu-id="5ff3e-135">Custom SQLite versions</span></span>](custom-versions.md)
