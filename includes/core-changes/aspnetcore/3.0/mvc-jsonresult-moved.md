---
ms.openlocfilehash: f6fd75c5b49156f44d31c650ea452eb549f13b0e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75901637"
---
### <a name="mvc-jsonresult-moved-to-microsoftaspnetcoremvccore"></a>MVC: JsonResult verschoben in Microsoft.AspNetCore.Mvc.Core

`JsonResult` wurde in die `Microsoft.AspNetCore.Mvc.Core`-Assembly verschoben. Dieser Typ wurde bisher in [Microsoft.AspNetCore.Mvc.Formatters.Json](https://www.nuget.org/packages/Microsoft.AspNetCore.Mvc.Formatters.Json) definiert. Ein [[TypeForwardedTo]](xref:System.Runtime.CompilerServices.TypeForwardedToAttribute)-Attribut auf Assemblyebene wurde `Microsoft.AspNetCore.Mvc.Formatters.Json` hinzugefügt, um dieses Problem für die Mehrheit der Benutzer zu beheben. Bei Apps, die Bibliotheken von Drittanbietern verwenden, treten möglicherweise Probleme auf.

#### <a name="version-introduced"></a>Eingeführt in Version

3.0 Vorschau 6

#### <a name="old-behavior"></a>Altes Verhalten

Eine App, die eine auf Version 2.2 basierende Bibliothek verwendet, wird erfolgreich erstellt.

#### <a name="new-behavior"></a>Neues Verhalten

Für eine App, die eine auf Version 2.2 basierende Bibliothek verwendet, schlägt die Kompilierung fehl. Eine Fehlermeldung, die ähnlich wie der folgende Text lautet, wird bereitgestellt:

```
The type 'JsonResult' exists in both 'Microsoft.AspNetCore.Mvc.Core, Version=3.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60' and 'Microsoft.AspNetCore.Mvc.Formatters.Json, Version=2.0.0.0, Culture=neutral, PublicKeyToken=adb9793829ddae60'
```

Ein Beispiel für ein solches Problem finden Sie unter [dotnet/aspnetcore#7220](https://github.com/dotnet/aspnetcore/issues/7220).

#### <a name="reason-for-change"></a>Grund für die Änderung

Änderungen auf Plattformebene an der Zusammenstellung von ASP.NET Core wie unter [aspnet/Announcements#325](https://github.com/aspnet/Announcements/issues/325) beschrieben.

#### <a name="recommended-action"></a>Empfohlene Aktion

Bibliotheken, die anhand von Version 2.2 von `Microsoft.AspNetCore.Mvc.Formatters.Json` kompiliert wurden, müssen möglicherweise erneut kompiliert werden, um das Problem für alle Benutzer zu beheben. Wenden Sie sich an den Autor der Bibliothek, wenn Sie davon betroffen sind. Fordern Sie eine Neukompilierung der Bibliothek mit dem Ziel ASP.NET Core 3.0 an.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Mvc.JsonResult?displayProperty=nameWithType>

<!-- 

### Affected APIs

`T:Microsoft.AspNetCore.Mvc.JsonResult`

-->
