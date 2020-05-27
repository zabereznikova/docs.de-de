---
ms.openlocfilehash: 09027863ff2f0009a14578db35db870c27369726
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721099"
---
### <a name="types-in-microsoftvisualbasicapplicationservices-namespace-not-available"></a>Typen im Microsoft.VisualBasic.ApplicationServices-Namespace nicht verfügbar

Die Typen im <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>-Namespace sind nicht verfügbar.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET Core 3.0 Preview 8

#### <a name="change-description"></a>Änderungsbeschreibung

Die Typen im <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>-Namespace waren in einigen Releases von .NET Core 3.0 Preview verfügbar. Ab .NET Core 3.0 Preview 9 sind sie nicht mehr verfügbar.

Die Typen wurden entfernt, um unnötige Assemblyabhängigkeiten oder Breaking Changes in nachfolgenden Releases zu vermeiden.

#### <a name="recommended-action"></a>Empfohlene Aktion

Wenn Sie für Ihren Code <xref:Microsoft.VisualBasic.ApplicationServices>-Typen und deren Member benötigen, können Sie möglicherweise einen entsprechenden Typ oder Member in der .NET-Klassenbibliothek verwenden. So stellen beispielsweise einige <xref:System.Environment?displayProperty=nameWithType>- und <xref:System.Security.Principal.WindowsIdentity?displayProperty=nameWithType>-Member entsprechende Funktionen für die Eigenschaften der <xref:Microsoft.VisualBasic.ApplicationServices.User?displayProperty=nameWithType>-Klasse bereit.

#### <a name="category"></a>Kategorie

Visual Basic

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.VisualBasic.ApplicationServices?displayProperty=fullName>

<!--

#### Affected APIs

- `N:Microsoft.VisualBasic.ApplicationServices`

-->
