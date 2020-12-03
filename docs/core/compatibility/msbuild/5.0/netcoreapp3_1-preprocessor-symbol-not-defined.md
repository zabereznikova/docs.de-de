---
title: 'Breaking Change: Das NETCOREAPP3_1-Präprozessorsymbol ist nicht definiert, wenn .NET 5 als Zielversion verwendet wird'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den Projekte keine Präprozessorsymbole mehr für frühere Versionen definieren.
ms.date: 09/17/2020
ms.openlocfilehash: 61a5e4fce258d2be3d584318e154bb752b88ebe1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759401"
---
# <a name="netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5"></a>Das NETCOREAPP3_1-Präprozessorsymbol ist nicht definiert, wenn .NET 5 als Zielversion verwendet wird

In .NET 5.0 RC2 und höher definieren Projekte keine Präprozessorsymbole mehr für frühere Versionen, sondern nur für die Zielversion. Dieses Verhalten entspricht dem von .NET Core 1.0 bis .NET Core 3.1.

## <a name="version-introduced"></a>Eingeführt in Version

5.0 RC2

## <a name="change-description"></a>Änderungsbeschreibung

In .NET 5.0 Preview 7 bis .NET 5.0 RC1 definieren Projekte für `net5.0` die Präprozessorsymbole `NETCOREAPP3_1` und `NET5_0`. Durch diesen Behavior Change sind [Symbole für die bedingte Kompilierung ab .NET 5.0 kumulativ](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md#preprocessor-symbols).

Ab .NET 5.0 RC2 definieren Projekte nur Symbole für die Zielframeworkmoniker, nicht jedoch für frühere Versionen.

## <a name="reason-for-change"></a>Grund für die Änderung

Die Änderung aus Preview 7 wurde aufgrund von Kundenfeedback zurückgenommen. Kunden waren überrascht und verwirrt, dass sie Symbole für frühere Versionen definieren mussten, und einige hielten dies für einen Fehler im C#-Compiler.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Stellen Sie sicher, dass Ihre `#if`-Logik nicht von einer vorhandenen `NETCOREAPP3_1`-Definition ausgeht, wenn das Projekt auf `net5.0` oder höher ausgerichtet ist. Es sollte stattdessen davon ausgegangen werden, dass `NETCOREAPP3_1` nur definiert ist, wenn das Projekt explizit auf `netcoreapp3.1` ausgerichtet ist.

Wenn Ihr Projekt beispielsweise .NET Core 2.1 und .NET Core 3.1 als Zielversionen verwendet und Sie APIs aufrufen, die in .NET Core 3.1 eingeführt wurden, sollte Ihre `#if`-Logik folgendermaßen aussehen:

```csharp
#if NETCOREAPP2_1 || NETCOREAPP3_0
    // Fallback behavior for old versions.
#elif NETCOREAPP
    // Behavior for .NET Core 3.1 and later.
#endif
```

## <a name="affected-apis"></a>Betroffene APIs

Nicht zutreffend

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
