---
ms.openlocfilehash: 5ad9c494fd02059e05cc744aad3b06cfc9399995
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77451885"
---
### <a name="default-value-of-httprequestmessageversion-changed-to-11"></a>Standardwert von HttpRequestMessage.Version wurde in 1.1 geändert

Der Standardwert der Eigenschaft <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> wurde aus 2.0 in 1.1 geändert.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="change-description"></a>Änderungsbeschreibung

In .NET Core 1.0 bis 2.0 ist der Standardwert der Eigenschaft <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName> 1.1. Ab .NET Core 2.1 wurde er in 2.1 geändert.

Ab .NET Core 3.0 ist die Standardversionsnummer, die von der <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>-Eigenschaft zurückgegeben wird, erneut 1.1.

#### <a name="recommended-action"></a>Empfohlene Aktion

Aktualisieren Sie Ihren Code, wenn die <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>-Eigenschaft einen Standardwert von 2.0 zurückgeben muss.

#### <a name="category"></a>Kategorie

Netzwerk

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:System.Net.Http.HttpRequestMessage.Version?displayProperty=fullName>

<!--

#### Affected APIs

- `P:System.Net.Http.HttpRequestMessage.Version`

-->
