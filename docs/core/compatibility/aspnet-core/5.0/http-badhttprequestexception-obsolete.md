---
title: 'Breaking Change: HTTP: BadHttpRequestException-Typen von Kestrel und IIS werden als veraltet markiert und ersetzt'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „HTTP: BadHttpRequestException-Typen von Kestrel und IIS werden als veraltet markiert und ersetzt'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: c51b1dd9d708c04bc1bbcfb65ea2e9daea5330b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759421"
---
# <a name="http-kestrel-and-iis-badhttprequestexception-types-marked-obsolete-and-replaced"></a>HTTP: BadHttpRequestException-Typen von Kestrel und IIS werden als veraltet markiert und ersetzt

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` wurden als veraltet markiert und so geändert, dass sie von `Microsoft.AspNetCore.Http.BadHttpRequestException` abgeleitet werden. Die Kestrel- und IIS-Server lösen die alten Ausnahmetypen aus Gründen der Abwärtskompatibilität weiterhin aus. Die veralteten Typen werden in einem zukünftigen Release entfernt.

Weitere Informationen finden Sie unter [dotnet/aspnetcore#20614](https://github.com/dotnet/aspnetcore/issues/20614).

## <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 4

## <a name="old-behavior"></a>Altes Verhalten

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` werden von <xref:System.IO.IOException?displayProperty=nameWithType> abgeleitet.

## <a name="new-behavior"></a>Neues Verhalten

`Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` sind veraltet. Werttypen werden von der `Microsoft.AspNetCore.Http.BadHttpRequestException`-Klasse abgeleitet, die wiederum von `System.IO.IOException` abgeleitet wird.

## <a name="reason-for-change"></a>Grund für die Änderung

Die Änderung wurde aus folgenden Gründen vorgenommen:

* zur Konsolidierung duplizierter Typen
* zur Vereinheitlichen des Verhaltens von Serverimplementierungen

damit Apps die Standardausnahme `Microsoft.AspNetCore.Http.BadHttpRequestException` abfangen können, wenn Kestrel oder IIS verwendet werden

## <a name="recommended-action"></a>Empfohlene Aktion

Ersetzen Sie die Instanzen von `Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException` und `Microsoft.AspNetCore.Server.IIS.BadHttpRequestException` durch `Microsoft.AspNetCore.Http.BadHttpRequestException`.

## <a name="affected-apis"></a>Betroffene APIs

- [Microsoft.AspNetCore.Server.IIS.BadHttpRequestException](/dotnet/api/microsoft.aspnetcore.server.iis.badhttprequestexception?view=aspnetcore-3.1)
- [Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException](/dotnet/api/microsoft.aspnetcore.server.kestrel.badhttprequestexception?view=aspnetcore-1.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.AspNetCore.Server.IIS.BadHttpRequestException`
- `T:Microsoft.AspNetCore.Server.Kestrel.BadHttpRequestException`

-->
