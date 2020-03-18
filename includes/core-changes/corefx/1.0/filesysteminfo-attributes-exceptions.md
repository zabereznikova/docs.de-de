---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449398"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a>UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes

In .NET Core wird eine <xref:System.UnauthorizedAccessException> ausgelöst, wenn der Aufrufer versucht, den Wert eines Dateiattributs festzulegen, aber nicht über die Schreibberechtigung verfügt.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework wird eine <xref:System.ArgumentException> ausgelöst, wenn der Aufrufer versucht, in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> den Wert eines Dateiattributs festzulegen, aber nicht über die Schreibberechtigung verfügt. In .NET Core wird stattdessen eine <xref:System.UnauthorizedAccessException> ausgelöst. (In .NET Core wird eine <xref:System.ArgumentException> weiterhin ausgelöst, wenn der Aufrufer versucht, ein ungültiges Dateiattribut festzulegen.)

#### <a name="version-introduced"></a>Eingeführt in Version

1,0

#### <a name="recommended-action"></a>Empfohlene Aktion

Ändern Sie beliebige `catch`-Anweisungen so, dass sie nach Bedarf <xref:System.UnauthorizedAccessException> anstelle von oder zusätzlich zu <xref:System.ArgumentException> abfangen.

#### <a name="category"></a>Kategorie

CoreFx

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
