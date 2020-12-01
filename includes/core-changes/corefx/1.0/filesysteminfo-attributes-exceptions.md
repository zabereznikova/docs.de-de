---
ms.openlocfilehash: 2ea9abca7578c2ddf92712a1c597f8f1ff4a5c0c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032001"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a>UnauthorizedAccessException, ausgelöst von FileSystemInfo.Attributes

In .NET Core wird eine <xref:System.UnauthorizedAccessException> ausgelöst, wenn der Aufrufer versucht, den Wert eines Dateiattributs festzulegen, aber nicht über die Schreibberechtigung verfügt.

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Framework wird eine <xref:System.ArgumentException> ausgelöst, wenn der Aufrufer versucht, in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> den Wert eines Dateiattributs festzulegen, aber nicht über die Schreibberechtigung verfügt. In .NET Core wird stattdessen eine <xref:System.UnauthorizedAccessException> ausgelöst. (In .NET Core wird eine <xref:System.ArgumentException> weiterhin ausgelöst, wenn der Aufrufer versucht, ein ungültiges Dateiattribut festzulegen.)

#### <a name="version-introduced"></a>Eingeführt in Version

1.0

#### <a name="recommended-action"></a>Empfohlene Aktion

Ändern Sie beliebige `catch`-Anweisungen so, dass sie nach Bedarf <xref:System.UnauthorizedAccessException> anstelle von oder zusätzlich zu <xref:System.ArgumentException> abfangen.

#### <a name="category"></a>Kategorie

Core .NET-Bibliotheken

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
