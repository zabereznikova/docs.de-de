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
# <a name="netsdk1145-targeting-or-apphost-pack-missing"></a>NETSDK1145: Zielversionen oder AppHost-Paket fehlen

**Dieser Artikel gilt für:** ✔️ .NET 5.0.100 SDK und höhere Versionen

Wenn vom .NET SDK der Fehler NETSDK1145 zurückgegeben wird, sind die Zielversionen oder das AppHost-Paket nicht installiert, und die NuGet-Paketwiederherstellung wird nicht unterstützt. Dies kann in der Regel damit begründet werden, dass ein neueres SDK verwendet wird als das in Visual Studio für C++/CLI-Projekte eingeschlossene. Führen Sie ein Upgrade für Visual Studio durch, entfernen Sie _global.json_, wenn darin eine bestimmte SDK-Version angegeben wird, und deinstallieren Sie das neuere SDK. Alternativ können Sie die Zielversionen oder die AppHost-Version überschreiben. Suchen Sie nach der Version, die im Paketverzeichnis der Fehlermeldung enthalten ist und mit dem Zielframework des Projekts übereinstimmt. Fügen Sie dem Projekt Folgendes hinzu:

Für das AppHost-Paket:

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```

Für die Zielversionen:

```xml
<ItemGroup>
  <KnownAppHostPack Update="@(KnownAppHostPack)">
    <AppHostPackVersion Condition="'%(TargetFramework)' == 'TARGETFRAMEWORK'">EXISTINGVERSION</AppHostPackVersion>
  </KnownAppHostPack>
</ItemGroup>
```
