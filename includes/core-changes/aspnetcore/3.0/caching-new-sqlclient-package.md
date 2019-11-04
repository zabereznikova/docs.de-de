---
ms.openlocfilehash: 771238c53dc97f4cf4068968f3c68500ba9f87da
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "73198446"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a>Caching: Microsoft.Extensions.Caching.SqlServer verwendet neues Paket SqlClient.

Das Paket `Microsoft.Extensions.Caching.SqlServer` verwendet anstelle des Pakets `System.Data.SqlClient` das neue Paket `Microsoft.Data.SqlClient`. Diese Änderung kann zu geringfügigen Breaking Changes beim Verhalten führen. Weitere Informationen finden Sie unter [Introducing the new Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/) (Vorstellung des neuen Microsoft.Data.SqlClient).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Das Paket `Microsoft.Extensions.Caching.SqlServer` hat das Paket `System.Data.SqlClient` verwendet.

#### <a name="new-behavior"></a>Neues Verhalten

`Microsoft.Extensions.Caching.SqlServer` verwendet jetzt das Paket `Microsoft.Data.SqlClient`.

#### <a name="reason-for-change"></a>Grund für die Änderung

`Microsoft.Data.SqlClient` ist ein neues Paket, das aus `System.Data.SqlClient` erstellt wurde. Es enthält ab sofort alle neuen Funktionen.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Kunden müssen sich um diesen Breaking Change nur kümmern, wenn sie die vom Paket `Microsoft.Extensions.Caching.SqlServer` zurückgegebenen Typen verwendet und in `System.Data.SqlClient`-Typen umgewandelt haben. Wenn z. B. eine `DbConnection` in den [alten SqlConnection-Typ](xref:System.Data.SqlClient.SqlConnection) umgewandelt wurde, muss die Umwandlung in den neuen `Microsoft.Data.SqlClient.SqlConnection`-Typ geändert werden.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
