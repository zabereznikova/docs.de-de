---
title: 'Breaking Change: TextFormatFlags.ModifyString ist veraltet'
description: Hier erfahren Sie mehr über den Breaking Change in .NET 5.0, durch den das Feld „TextFormatFlags.ModifyString“ als Warnung als veraltet gilt.
ms.date: 11/05/2020
ms.openlocfilehash: 83dca65a770ccdcd5ce48bb669f5122dc2d5ad77
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759377"
---
# <a name="textformatflagsmodifystring-is-obsolete"></a>TextFormatFlags.ModifyString ist veraltet

Das Feld <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> ist als Warnung veraltet und kann in einer zukünftigen .NET-Version entfernt werden.

## <a name="change-description"></a>Änderungsbeschreibung

In früheren .NET-Versionen ist das Enumerationsfeld <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> nicht als veraltet gekennzeichnet. In .NET 5.0 oder höher ist es als Warnung als veraltet gekennzeichnet. Dieses Feld kann in einer zukünftigen .NET-Version entfernt werden.

## <a name="reason-for-change"></a>Grund für die Änderung

Durch die Übergabe einer Zeichenfolge an <xref:System.Windows.Forms.TextRenderer.MeasureText%2A?displayProperty=nameWithType> mit <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> wird die Zeichenfolge in einigen Situationen geändert. Dieses Verhalten unterbricht die Unveränderlichkeitszusage der Zeichenfolge und kann zu einer schwerwiegenden Beschädigung des Runtimestatus von .NET führen.

## <a name="version-introduced"></a>Eingeführt in Version

.NET 5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Aktualisieren Sie Code, der auf <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=nameWithType> basiert.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Windows.Forms.TextFormatFlags.ModifyString?displayProperty=fullName>

<!--

### Affected APIs

- `F:System.Windows.Forms.TextFormatFlags.ModifyString`

### Category

Windows Forms

-->
