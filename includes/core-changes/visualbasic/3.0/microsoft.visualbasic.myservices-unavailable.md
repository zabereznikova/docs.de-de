---
ms.openlocfilehash: 58e65bae1593f23945a971b896a1db4a929b4587
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74567415"
---
### <a name="types-in-microsoftvisualbasicmyservices-namespace-not-available"></a>Typen im Microsoft.VisualBasic.MyServices-Namespace nicht verfügbar

Die Typen im <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>-Namespace sind nicht verfügbar.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET Core 3.0 Preview 8

#### <a name="change-description"></a>Änderungsbeschreibung

Die Typen im <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>-Namespace waren in einigen Releases von .NET Core 3.0 Preview verfügbar. Ab .NET Core 3.0 Preview 9 sind sie nicht mehr verfügbar.

Die Typen wurden entfernt, um unnötige Assemblyabhängigkeiten oder Breaking Changes in nachfolgenden Releases zu vermeiden.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Wenn Sie für Ihren Code **Microsoft.VisualBasic.MyServices**-Typen und deren Member benötigen, finden Sie entsprechende Typen und Member in der .NET-Klassenbibliothek. Im Folgenden ist eine Zuordnung von **Microsoft.VisualBasic.MyServices**-Typen zu den entsprechenden .NET-Klassenbibliothekstypen dargestellt:

|Microsoft.VisualBasic.MyServices-Typ|.NET-Klassenbibliothekstyp|
|--|--|
|<xref:Microsoft.VisualBasic.MyServices.ClipboardProxy>|<xref:System.Windows.Clipboard?displayProperty=nameWithType> für WPF-Anwendungen, <xref:System.Windows.Forms.Clipboard?displayProperty=nameWithType> für Windows Forms-Anwendungen|
|<xref:Microsoft.VisualBasic.MyServices.FileSystemProxy>|Typen im <xref:System.IO>-Namespace|
|<xref:Microsoft.VisualBasic.MyServices.RegistryProxy>|Registrierungsbezogene Typen im <xref:Microsoft.Win32>-Namespace|
|<xref:Microsoft.VisualBasic.MyServices.SpecialDirectoriesProxy>|<xref:System.Environment.GetFolderPath%2A?displayProperty=nameWithType>|

#### <a name="category"></a>Kategorie

Visual Basic

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.VisualBasic.MyServices?displayProperty=fullName>

<!--

### Affected APIs

- `N:Microsoft.VisualBasic.MyServices`

-- >

