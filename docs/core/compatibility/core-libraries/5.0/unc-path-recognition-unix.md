---
title: 'Breaking Change: URI-Erkennung von UNC-Pfaden unter UNIX'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den die Uri-Klasse jetzt Zeichenfolgen, die mit zwei Schrägstrichen beginnen, unter UNIX als UNC-Pfade erkennt.
ms.date: 11/01/2020
ms.openlocfilehash: 0d5d9cd8dd869f24e94d15724e5e16eaddf6ed47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759221"
---
# <a name="uri-recognition-of-unc-paths-on-unix"></a>URI-Erkennung von UNC-Pfaden unter UNIX

Die <xref:System.Uri>-Klasse erkennt jetzt unter UNIX-Betriebssystemen Zeichenfolgen, die mit zwei Schrägstrichen (`//`) beginnen, als UNC-Pfade (Universal Naming Convention). Diese Änderung hat zur Folge, dass das Verhalten für solche Zeichenfolgen auf allen Plattformen konsistent ist.

## <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen erkennt die <xref:System.Uri>-Klasse unter UNIX-Betriebssystemen Zeichenfolgen, die mit zwei Schrägstrichen beginnen (z. B. `//contoso`), als absolute Dateipfade. Unter Windows werden solche Zeichenfolgen jedoch als UNC-Pfade erkannt.

Ab .NET 5.0 erkennt die <xref:System.Uri>-Klasse Zeichenfolgen, die mit zwei Schrägstrichen beginnen, auf allen Plattformen einschließlich UNIX als UNC-Pfade. Außerdem verhalten sich Eigenschaften entsprechend der UNC-Semantik:

- <xref:System.Uri.IsUnc?displayProperty=nameWithType> gibt `true` zurück.
- Umgekehrte Schrägstriche im Pfad werden durch Schrägstriche ersetzt. `//first\second` wird beispielsweise zu `//first/second`.
- Bei <xref:System.Uri.LocalPath?displayProperty=nameWithType> werden keine Prozentzeichen in Zeichenfolgen eingefügt. `//first/\uFFF0` wird beispielsweise *nicht* in `//first/%EF%BF%B0` konvertiert.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Auf der Seite des Entwicklers ist keine Aktion erforderlich.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
