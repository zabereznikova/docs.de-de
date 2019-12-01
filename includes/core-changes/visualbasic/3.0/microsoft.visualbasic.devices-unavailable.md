---
ms.openlocfilehash: 4c47b95e98aca727d9f0eda54a167a71fd53afb9
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567465"
---
### <a name="types-in-microsoftvisualbasicdevices-namespace-not-available"></a>Typen im Microsoft.VisualBasic.Devices-Namespace nicht verfügbar

Die Typen im <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>-Namespace sind nicht verfügbar.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET Core 3.0 Preview 8

#### <a name="change-description"></a>Änderungsbeschreibung

Die Typen im <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>-Namespace waren in einigen Versionen von .NET Core 3.0 Preview verfügbar. Ab .NET Core 3.0 Preview 9 sind sie nicht mehr verfügbar.

Die Typen wurden entfernt, um unnötige Assemblyabhängigkeiten oder Breaking Changes in nachfolgenden Releases zu vermeiden.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie für Ihren Code <xref:Microsoft.VisualBasic.Devices>-Typen und deren Member benötigen, können Sie möglicherweise einen entsprechenden Typ oder Member in der .NET-Klassenbibliothek verwenden. Beispielsweise werden die entsprechenden Funktionen für die <xref:Microsoft.VisualBasic.Devices.Clock?displayProperty=nameWithType>-Klasse von den Typen <xref:System.DateTime?displayProperty=nameWithType> und <xref:System.Environment?displayProperty=nameWithType> bereitgestellt, und die entsprechenden Funktionen für die <xref:Microsoft.VisualBasic.Devices.Ports?displayProperty=nameWithType>-Klasse wird von Typen im <xref:System.IO.Ports?displayProperty=nameWithType>-Namespace bereitgestellt.

#### <a name="category"></a>Kategorie

Visual Basic

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.VisualBasic.Devices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.Devices`

-- >

