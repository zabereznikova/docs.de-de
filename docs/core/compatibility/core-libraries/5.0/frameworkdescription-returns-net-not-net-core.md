---
title: 'Breaking Change: Der Wert von FrameworkDescription entspricht „.NET“ anstelle von „.NET Core“'
description: Hier erfahren Sie mehr über den Breaking Change an den .NET-Kernbibliotheken in .NET 5.0, durch den RuntimeInformation.FrameworkDescription jetzt „.NET“ anstelle von „NET Core“ zurückgibt.
ms.date: 11/01/2020
ms.openlocfilehash: 3925fb092135c26291e1e60b99f359974d21553c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759485"
---
# <a name="frameworkdescriptions-value-is-net-instead-of-net-core"></a>Der Wert von FrameworkDescription entspricht „.NET“ anstelle von „.NET Core“

<xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> gibt jetzt „.NET“ anstelle von „.NET Core“ zurück.

## <a name="change-description"></a>Änderungsbeschreibung

In früheren Versionen von .NET gibt <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> „.NET Core“ als Teil der Beschreibungszeichenfolge zurück, z. B. `.NET Core 3.1.1`.

Ab .NET 5.0 gibt <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> „.NET“ als Teil der Beschreibungszeichenfolge zurück, z. B. `.NET 5.0.0`.

## <a name="reason-for-change"></a>Grund für die Änderung

Mit .NET 5 wird `netcoreapp` durch `net` als Zielframeworkmoniker ersetzt. Aus Konsistenzgründen wurde die Beschreibung des Frameworks ebenfalls aktualisiert. Die Änderung ist rein kosmetischer Natur, da der `FrameworkName` nur in der Eigenschaft <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=nameWithType> codiert wird.

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="recommended-action"></a>Empfohlene Maßnahme

Aktualisieren Sie jeglichen Code, mit dem in der von <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription> zurückgegebenen Zeichenfolge nach „.NET Core“ gesucht wird.

## <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `P:System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription`

-->
