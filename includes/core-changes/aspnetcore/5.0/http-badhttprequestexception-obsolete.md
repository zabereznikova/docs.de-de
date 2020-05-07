---
ms.openlocfilehash: c4e7864262a11aafa4b7f1f4bdf632fbf084c560
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "82507082"
---
### <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a>HTTP: BadHttpRequestException-Typen von Kestrel und IIS werden als veraltet markiert und ersetzt

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` wurden als veraltet markiert und so geändert, dass sie von `Microsoft.AspNetCore.Http.BadHttpRequestException` abgeleitet werden. Die Kestrel- und IIS-Server lösen die alten Ausnahmetypen aus Gründen der Abwärtskompatibilität weiterhin aus. Die veralteten Typen werden in einem zukünftigen Release entfernt.

Weitere Informationen finden Sie unter [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 4

#### <a name="old-behavior"></a>Altes Verhalten

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` werden von <xref:System.IO.IOException?displayProperty=nameWithType> abgeleitet.

#### <a name="new-behavior"></a>Neues Verhalten

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` sind veraltet. Werttypen werden von der `Microsoft.AspNetCore.Http.BadHttpRequestException`-Klasse abgeleitet, die wiederum von `System.IO.IOException` abgeleitet wird.

#### <a name="reason-for-change"></a>Grund für die Änderung

Die Änderung wurde aus folgenden Gründen vorgenommen:

* zur Konsolidierung duplizierter Typen
* zur Vereinheitlichen des Verhaltens von Serverimplementierungen

damit Apps die Standardausnahme `Microsoft.AspNetCore.Http.BadHttpRequestException` abfangen können, wenn Kestrel oder IIS verwendet werden

#### <a name="recommended-action"></a>Empfohlene Aktion

Ersetzen Sie die Instanzen von `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` durch `Microsoft.AspNetCore.Http.BadHttpRequestException`.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

- [Microsoft.AspNetCore.Server.IIS.BadHttpRequestException](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

#### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
