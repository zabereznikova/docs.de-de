---
title: Xamarin-Einschränkungen
ms.date: 12/13/2019
description: In diesem Artikel werden einige Einschränkungen bei der Verwendung von Xamarin beschrieben.
ms.openlocfilehash: 192f25954726919dc66d706e755e0853404b4d85
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450405"
---
# <a name="xamarin-limitations"></a><span data-ttu-id="f0cf2-103">Xamarin-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f0cf2-103">Xamarin limitations</span></span>

<span data-ttu-id="f0cf2-104">Microsoft.Data.Sqlite bezieht sich auf .NET Standard 2.0 und wird unter Xamarin unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f0cf2-104">Microsoft.Data.Sqlite targets .NET Standard 2.0 and is supported on Xamarin.</span></span> <span data-ttu-id="f0cf2-105">In der folgenden Tabelle sehen Sie, für welche Plattformen das SQLitePCLRaw-Standardpaket native SQLite-Binärdateien bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="f0cf2-105">The following table shows which platforms the default SQLitePCLRaw bundle provides native SQLite binaries for.</span></span> <span data-ttu-id="f0cf2-106">Weitere Informationen zur Verwendung eines anderen Pakets oder zur Bereitstellung eigener nativer SQLite-Binärdateien finden Sie unter [Benutzerdefinierte SQLite-Versionen](custom-versions.md).</span><span class="sxs-lookup"><span data-stu-id="f0cf2-106">See [Custom SQLite versions](custom-versions.md) for details on using a different bundle or providing your own native SQLite binaries.</span></span>

| <span data-ttu-id="f0cf2-107">Plattform</span><span class="sxs-lookup"><span data-stu-id="f0cf2-107">Platform</span></span> | <span data-ttu-id="f0cf2-108">SQLite-Binärdateien</span><span class="sxs-lookup"><span data-stu-id="f0cf2-108">SQLite binaries</span></span> |
| --- | --- |
| <span data-ttu-id="f0cf2-109">**Xamarin.Android**</span><span class="sxs-lookup"><span data-stu-id="f0cf2-109">**Xamarin.Android**</span></span> | <span data-ttu-id="f0cf2-110">—</span><span class="sxs-lookup"><span data-stu-id="f0cf2-110">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64-v8a` | <span data-ttu-id="f0cf2-111">✔</span><span class="sxs-lookup"><span data-stu-id="f0cf2-111">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`armeabi-v7a` | <span data-ttu-id="f0cf2-112">✔</span><span class="sxs-lookup"><span data-stu-id="f0cf2-112">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="f0cf2-113">✔</span><span class="sxs-lookup"><span data-stu-id="f0cf2-113">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86_64` | <span data-ttu-id="f0cf2-114">✔</span><span class="sxs-lookup"><span data-stu-id="f0cf2-114">✔</span></span> |
| <span data-ttu-id="f0cf2-115">**Xamarin.iOS**</span><span class="sxs-lookup"><span data-stu-id="f0cf2-115">**Xamarin.iOS**</span></span> | <span data-ttu-id="f0cf2-116">✔</span><span class="sxs-lookup"><span data-stu-id="f0cf2-116">✔</span></span> |
| <span data-ttu-id="f0cf2-117">**Xamarin.Mac**</span><span class="sxs-lookup"><span data-stu-id="f0cf2-117">**Xamarin.Mac**</span></span> | <span data-ttu-id="f0cf2-118">✔</span><span class="sxs-lookup"><span data-stu-id="f0cf2-118">✔</span></span> |
| <span data-ttu-id="f0cf2-119">**Xamarin.TVOS**</span><span class="sxs-lookup"><span data-stu-id="f0cf2-119">**Xamarin.TVOS**</span></span> | <span data-ttu-id="f0cf2-120">✔</span><span class="sxs-lookup"><span data-stu-id="f0cf2-120">✔</span></span> |
| <span data-ttu-id="f0cf2-121">**UWP**</span><span class="sxs-lookup"><span data-stu-id="f0cf2-121">**UWP**</span></span> | <span data-ttu-id="f0cf2-122">—</span><span class="sxs-lookup"><span data-stu-id="f0cf2-122">—</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm` | <span data-ttu-id="f0cf2-123">✔</span><span class="sxs-lookup"><span data-stu-id="f0cf2-123">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`arm64` | <span data-ttu-id="f0cf2-124">✔</span><span class="sxs-lookup"><span data-stu-id="f0cf2-124">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x64` | <span data-ttu-id="f0cf2-125">✔</span><span class="sxs-lookup"><span data-stu-id="f0cf2-125">✔</span></span> |
| &nbsp;&nbsp;&nbsp;&nbsp;`x86` | <span data-ttu-id="f0cf2-126">✔</span><span class="sxs-lookup"><span data-stu-id="f0cf2-126">✔</span></span> |

## <a name="ios"></a><span data-ttu-id="f0cf2-127">iOS</span><span class="sxs-lookup"><span data-stu-id="f0cf2-127">iOS</span></span>

<span data-ttu-id="f0cf2-128">Microsoft.Data.Sqlite versucht automatisch, SQLitePCLRaw-Pakete zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="f0cf2-128">Microsoft.Data.Sqlite tries to automatically initialize SQLitePCLRaw bundles.</span></span> <span data-ttu-id="f0cf2-129">Aufgrund von Einschränkungen bei der AOT-Kompilierung (Ahead-of-Time) für Xamarin.iOS schlägt der Versuch fehl, und Sie erhalten die folgende Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="f0cf2-129">Unfortunately, because of limitations in the ahead-of-time (AOT) compilation for Xamarin.iOS, the attempt fails and you get the following error.</span></span>

> <span data-ttu-id="f0cf2-130">Rufen Sie `SQLitePCL.raw.SetProvider()` auf.</span><span class="sxs-lookup"><span data-stu-id="f0cf2-130">You need to call `SQLitePCL.raw.SetProvider()`.</span></span> <span data-ttu-id="f0cf2-131">Wenn Sie ein Bündelpaket verwenden, rufen Sie `SQLitePCL.Batteries.Init()` auf.</span><span class="sxs-lookup"><span data-stu-id="f0cf2-131">If you're using a bundle package, this is done by calling `SQLitePCL.Batteries.Init()`.</span></span>

<span data-ttu-id="f0cf2-132">Fügen Sie zur Initialisierung des Pakets Ihrer App die folgende Codezeile hinzu, bevor Sie Microsoft.Data.Sqlite verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0cf2-132">To initialize the bundle, add the following line of code to your app before using Microsoft.Data.Sqlite.</span></span>

```csharp
SQLitePCL.Batteries_V2.Init();
```

## <a name="see-also"></a><span data-ttu-id="f0cf2-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0cf2-133">See also</span></span>

* [<span data-ttu-id="f0cf2-134">Async-Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f0cf2-134">Async limitations</span></span>](async.md)
* [<span data-ttu-id="f0cf2-135">Benutzerdefinierte SQLite-Versionen</span><span class="sxs-lookup"><span data-stu-id="f0cf2-135">Custom SQLite versions</span></span>](custom-versions.md)
