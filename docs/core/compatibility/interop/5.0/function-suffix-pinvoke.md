---
title: 'Breaking Change: Keine A/W-Überprüfung des Suffixes auf anderen Plattformen als Windows'
description: Hier erfahren Sie mehr über den Breaking Change für den Interopbereich in .NET 5.0, durch den bei der Suche nach „P/Invokes“ auf Nicht-Windows-Plattformen keine Suffixe mehr zu den Namen von Funktionsexporten hinzugefügt werden.
ms.date: 08/13/2020
ms.openlocfilehash: a4c612a81796faf80fa257df21232a54f7b95431
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759481"
---
# <a name="no-aw-suffix-probing-on-non-windows-platforms"></a>Keine A/W-Überprüfung des Suffixes auf anderen Plattformen als Windows

Die .NET-Runtimes fügen kein `A`- oder `W`-Suffix zu Funktionsexportnamen während der Stichprobenentnahme für P/Invokes auf anderen Plattformen als Windows hinzu.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="change-description"></a>Änderungsbeschreibung

[Windows umfasst eine Konvention](/windows/win32/intl/conventions-for-function-prototypes), laut der ein `A`- oder `W`-Suffix zu Funktionsnamen des Windows SDKs hinzugefügt werden, die jeweils der Windows-Codeseite und den Unicode-Versionen entsprechen.

In vorherigen Versionen von .NET haben die CoreCLR- und Mono-Runtimes während der Exportermittlung *auf allen Plattformen* ein `A`- oder `W`-Suffix zum Exportnamen für P/Invokes hinzugefügt.

In .NET 5.0 und höheren Versionen wird ein `A`- oder `W`-Suffix *nur unter Windows* während der Exportermittlung zum Exportnamen hinzugefügt. Auf UNIX-Plattformen wird das Suffix nicht hinzugefügt. Die Semantik beider Runtimes bleiben auf der Windows-Plattform unverändert.

## <a name="reason-for-change"></a>Grund für die Änderung

Diese Änderung wurde zur Vereinfachung der plattformübergreifenden Überprüfung implementiert. Dabei handelt es sich um einen Mehraufwand, der nicht hätte auftreten sollen, da andere Plattformen als Windows diese Semantik nicht aufweisen.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Sie können das gewünschte Suffix auf anderen Plattformen als Windows manuell hinzufügen, um diese Änderung zu umgehen. Zum Beispiel:

```csharp
[DllImport(...)]
extern static void SetWindowTextW();
```

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Runtime.InteropServices.DllImportAttribute?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.Runtime.InteropServices.DllImportAttribute`

### Category

Interop

-->
