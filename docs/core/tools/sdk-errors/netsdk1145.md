---
title: 'NETSDK1145: Zielversionen oder AppHost-Paket fehlen'
description: Hier erfahren Sie, wie Sie das Problem fehlender Zielversionen beheben, wenn Wiederherstellungen für NuGet-Pakete nicht unterstützt werden.
author: wli3
ms.topic: error-reference
ms.date: 09/14/2020
f1_keywords:
- NETSDK1145
ms.openlocfilehash: c343952582cafb63eae388fd216769e6c67d4741
ms.sourcegitcommit: 636af37170ae75a11c4f7d1ecd770820e7dfe7bd
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "91805307"
---
# <a name="netsdk1145-targeting-or-apphost-pack-missing"></a><span data-ttu-id="e2a18-103">NETSDK1145: Zielversionen oder AppHost-Paket fehlen</span><span class="sxs-lookup"><span data-stu-id="e2a18-103">NETSDK1145: Targeting or apphost pack missing</span></span>

<span data-ttu-id="e2a18-104">**Dieser Artikel gilt für:** ✔️ .NET 5.0.100 SDK und höhere Versionen</span><span class="sxs-lookup"><span data-stu-id="e2a18-104">**This article applies to:** ✔️ .NET 5.0.100 SDK and later versions</span></span>

<span data-ttu-id="e2a18-105">Wenn vom .NET SDK der Fehler NETSDK1145 zurückgegeben wird, sind die Zielversionen oder das AppHost-Paket nicht installiert, und die NuGet-Paketwiederherstellung wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e2a18-105">When the .NET SDK issues error NETSDK1145, the targeting or apphost pack is not installed and NuGet package restore is not supported.</span></span> <span data-ttu-id="e2a18-106">Dies kann in der Regel damit begründet werden, dass ein neueres SDK verwendet wird als das in Visual Studio für C++/CLI-Projekte eingeschlossene.</span><span class="sxs-lookup"><span data-stu-id="e2a18-106">This is typically caused by having a newer SDK than the one included in Visual Studio for C++/CLI projects.</span></span> <span data-ttu-id="e2a18-107">Führen Sie ein Upgrade für Visual Studio durch, entfernen Sie _global.json_, wenn darin eine bestimmte SDK-Version angegeben wird, und deinstallieren Sie das neuere SDK.</span><span class="sxs-lookup"><span data-stu-id="e2a18-107">Upgrade Visual Studio, remove _global.json_ if it specifies a certain SDK version, and uninstall the newer SDK.</span></span> <span data-ttu-id="e2a18-108">Alternativ können Sie die Zielversionen oder die AppHost-Version überschreiben.</span><span class="sxs-lookup"><span data-stu-id="e2a18-108">Alternatively, you could override the targeting or apphost version.</span></span> <span data-ttu-id="e2a18-109">Suchen Sie nach der Version, die im Paketverzeichnis der Fehlermeldung enthalten ist und mit dem Zielframework des Projekts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="e2a18-109">Find the version that exists under the pack directory from the error message and matches the target framework of the project.</span></span> <span data-ttu-id="e2a18-110">Fügen Sie dem Projekt Folgendes hinzu:</span><span class="sxs-lookup"><span data-stu-id="e2a18-110">Add the following to the project:</span></span>

<span data-ttu-id="e2a18-111">Für das AppHost-Paket:</span><span class="sxs-lookup"><span data-stu-id="e2a18-111">For apphost pack</span></span>

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```

<span data-ttu-id="e2a18-112">Für die Zielversionen:</span><span class="sxs-lookup"><span data-stu-id="e2a18-112">For targeting pack</span></span>

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```
