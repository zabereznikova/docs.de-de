---
title: 'Breaking Change: TargetFramework-Änderung von „netcoreapp“ in „net“'
description: Hier erfahren Sie mehr über den Breaking Change für .NET 5.0, durch den der Wert der MSBuild-Eigenschaft „TargetFramework“ von „netcoreapp3.1“ in „net5.0“ geändert wurde.
ms.date: 10/17/2020
ms.openlocfilehash: c3b39a36548d58d6ed75fd8b1c84b0cccfc738f0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759398"
---
# <a name="targetframework-change-from-netcoreapp-to-net"></a>TargetFramework-Änderung von „netcoreapp“ in „net“

Der Wert der MSBuild-Eigenschaft `TargetFramework` wurde von `netcoreapp3.1` in `net5.0` geändert. Dadurch wird möglicherweise Code unterbrochen, der von der Verarbeitung des Werts von `TargetFramework` abhängig ist.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 1.0 bis 3.1 beginnt der Wert für die MSBuild-Eigenschaft `TargetFramework` mit `netcoreapp` (z. B. `netcoreapp3.1` für Apps, die auf .NET Core 3.1 abzielen). Ab NET 5.0 wird dieser Wert vereinfacht und beginnt nur mit `net` (z. B. `net5.0` für .NET 5.0).

Weitere Informationen finden Sie unter [Die Zukunft von .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) und [Zielframeworknamen in .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).

## <a name="reason-for-change"></a>Grund für die Änderung

- Dadurch wird der `TargetFramework`-Wert vereinfacht.
- Projekte können eine `TargetPlatform` in die `TargetFramework`-Eigenschaft einschließen.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie über Logik verfügen, die den Wert von `TargetFramework` analysiert, müssen Sie sie aktualisieren. Die folgende MSBuild-Bedingung basiert beispielsweise auf dem Wert von `TargetFramework`.

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

Für diese Anforderung können Sie den Code so aktualisieren, dass er stattdessen den Zielframeworkbezeichner vergleicht.

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

## <a name="affected-apis"></a>Betroffene APIs

Nicht zutreffend

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
