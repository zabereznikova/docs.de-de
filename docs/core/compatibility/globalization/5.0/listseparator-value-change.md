---
title: 'Breaking Change: Änderung des TextInfo.ListSeparator-Werts'
description: Hier efahren Sie mehr über die Breaking Change bei .NET 5.0, bei der der Standardwert von TextInfo.ListSeparator zwischen den Versionen 5.0 und 5.0.1 geändert wurde.
ms.date: 12/10/2020
ms.openlocfilehash: 720d46c1908bcd70812f575a90f580470dbc7f32
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596330"
---
# <a name="textinfolistseparator-values-changed"></a>Änderung der TextInfo.ListSeparator-Werte

Die <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Standardwerte für verschiedene Kulturen haben sich bei allen Betriebssystemen geändert.

## <a name="change-description"></a>Änderungsbeschreibung

Im Rahmen der [Umstellung von NLS- auf ICU-Bibliotheken](icu-globalization-api.md) wurden in .NET 5.0.0 die Standardwerte für <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> für verschiedene Kulturen unter Windows geändert. Dezimaltrennzeichenwerte, die von International Components for Unicode (ICU) abgerufen wurden, wurden als <xref:System.Globalization.TextInfo.ListSeparator>-Werte verwendet. Unter Linux und macOS wurden keine Änderungen an <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Werten vorgenommen, d. h. sie verwenden weiterhin Dezimaltrennzeichenwerte.

Für alle Betriebssysteme in .NET 5.0.1 und höheren Versionen entsprechen die Werte für <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType> den Werten, die von NLS abgerufen werden. Für Windows bedeutet dies, dass die Werte den Werten in .NET Framework und .NET Core 1.0–3.1 entsprechen. Für Linux und macOS stimmen die <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Werte nun mit den <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Werten für Windows überein.

Die folgende Tabelle enthält die Änderungen für <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Werte.

| | .NET Framework<br/>.NET Core 1.0–3.1 | .NET 5.0 | .NET 5.0.1 |
-|-|-|-
| **Windows** | Aus NLS abrufen | Dezimaltrennzeichen aus ICU<br/>Kann zurück zu NLS wechseln | Entspricht NLS |
| **Linux und macOS** | Dezimaltrennzeichen aus ICU | Dezimaltrennzeichen aus ICU | Entspricht NLS |

## <a name="version-introduced"></a>Eingeführt in Version

5.0.1

## <a name="reason-for-change"></a>Grund für die Änderung

Entwickler haben gemeldet, dass sie die <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Eigenschaft beim Parsen von durch Trennzeichen getrennte Dateien (CSV) verwenden und die neuen <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Werte diesen Parservorgang unterbrechen.

## <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Ihr Code auf den vorherigen Dezimaltrennzeichen basiert, können Sie die gewünschten <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=nameWithType>-Werte hartkodieren.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Globalization.TextInfo.ListSeparator?displayProperty=fullName>

<!--

#### Category

- Globalization

### Affected APIs

- `P:System.Globalization.TextInfo.ListSeparator`

-->
