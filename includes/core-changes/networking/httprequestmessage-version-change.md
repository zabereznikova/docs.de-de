---
ms.openlocfilehash: ff156afb3da4b921517fd841c5de2295265a8d7b
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198434"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a>Standardwert von HttpRequestMessage.Version wurde in 1.1 geändert

Der Standardwert der Eigenschaft <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> wurde aus 2.0 in 1.1 geändert.

#### <a name="version-introduced"></a>Eingeführt in Version

.NET Core 3.0

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 1.0 bis 2.0 ist der Standardwert der Eigenschaft <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 1.1. Ab .NET Core 2.1 wurde er in 2.1 geändert.

Ab .NET Core 3.0 ist die Standardversionsnummer, die von der <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>-Eigenschaft zurückgegeben wird, erneut 1.1.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Aktualisieren Sie Ihren Code, wenn die <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>-Eigenschaft einen Standardwert von 2.0 zurückgeben muss.

#### <a name="category"></a>Kategorie

Netzwerk

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--
a def
### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-- >

