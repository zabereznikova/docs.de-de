---
ms.openlocfilehash: f7dcf9c4c3dc7ea536ddc847769a1a30f1298bb2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617215"
---
### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a>Die Methode System.Uri.IsWellFormedUriString gibt für relative URIs mit einem Doppelpunktzeichen im ersten Segment FALSE zurück

#### <a name="details"></a>Details

Ab .NET Framework 4.5 zeigt <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> für relative URIs mit einem `:` im ersten Segment an, dass es sich nicht um einen wohlgeformten relativen URI handelt. Dies ist eine Änderung des <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName>-Verhaltens in .NET Framework 4.0, die vorgenommen wurde, um eine Übereinstimmung mit RFC3986 sicherzustellen.

#### <a name="suggestion"></a>Vorschlag

Diese Änderung wirkt sich (wie viele andere URI-Änderungen auch) nur auf Anwendungen aus, die auf .NET Framework 4.5 (oder höher) ausgerichtet sind. Damit Sie weiterhin das alte Verhalten verwenden können, müssen Sie als Zielplattform für die App NET Framework 4.0 verwenden. Überprüfen Sie alternativ die URIs, bevor Sie <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> aufrufen, und suchen Sie nach `:`-Zeichen, die Sie für die Überprüfung entfernen sollten, wenn das alte Verhalten bevorzugt wird.

| name    | Wert       |
|:--------|:------------|
| Bereich   | Gering       |
| Version | 4.5         |
| Typ    | Neuzuweisung |

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType>
