---
ms.openlocfilehash: 26e521a86b504824f035ad5d40e4a04d2ea26abc
ms.sourcegitcommit: 6d4ee46871deb9ea1e45bb5f3784474e240bbc26
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/11/2020
ms.locfileid: "90022965"
---
### <a name="middleware-exception-handler-middleware-throws-original-exception-if-handler-not-found"></a>Middleware: Ausnahmehandlermiddleware löst ursprüngliche Ausnahme aus, wenn der Handler nicht gefunden wurde

Vor ASP.NET Core 5.0 führt die [Ausnahmehandlermiddleware](xref:Microsoft.AspNetCore.Builder.ExceptionHandlerExtensions.UseExceptionHandler%2A) im Falle einer Ausnahme den konfigurierten Ausnahmehandler aus. Wenn der Ausnahmehandler, der über <xref:Microsoft.AspNetCore.Builder.ExceptionHandlerOptions.ExceptionHandlingPath> konfiguriert wurde, nicht gefunden werden kann, wird eine HTTP 404-Antwort erstellt. Die Antwort ist aus den folgenden Gründen irreführend:

* Anscheinend handelt es sich um einen Benutzerfehler.
* Die Tatsache wird verschleiert, dass auf dem Server eine Ausnahme aufgetreten ist.

Wenn der Ausnahmehandler nicht gefunden werden kann, löst die `ExceptionHandlerMiddleware`-Klasse die ursprüngliche Ausnahme aus, um den irreführenden Fehler in ASP.NET Core 5.0 zu beheben. Folglich wird eine HTTP 500-Antwort vom Server erzeugt. Beim Debuggen des aufgetretenen Fehlers kann die Antwort in den Serverprotokollen leichter untersucht werden.

Weitere Informationen finden Sie unter GitHub-Issue [dotnet/aspnetcore#25288](https://github.com/dotnet/aspnetcore/issues/25288).

#### <a name="version-introduced"></a>Eingeführt in Version

5.0 RC 1

#### <a name="old-behavior"></a>Altes Verhalten

Die Ausnahmehandlermiddleware erzeugt eine HTTP 404-Antwort, wenn der konfigurierte Ausnahmehandler nicht gefunden werden kann.

#### <a name="new-behavior"></a>Neues Verhalten

Die Ausnahmehandlermiddleware löst die ursprüngliche Ausnahme aus, wenn der konfigurierte Ausnahmehandler nicht gefunden werden kann.

#### <a name="reason-for-change"></a>Grund für die Änderung

Der HTTP 404-Fehler macht nicht deutlich, dass auf dem Server eine Ausnahme aufgetreten ist. Durch diese Änderung wird ein HTTP 500-Fehler erzeugt, um Folgendes zu verdeutlichen:

* Das Problem wird nicht durch einen Benutzerfehler verursacht.
* Auf dem Server ist eine Ausnahme aufgetreten.

#### <a name="recommended-action"></a>Empfohlene Maßnahme

Es sind keine API-Änderungen verfügbar. Alle vorhandenen Apps werden weiterhin kompiliert und ausgeführt. Die ausgelöste Ausnahme wird vom Server verarbeitet. Die Ausnahme wird beispielsweise in eine HTTP 500-Fehlerantwort von [Kestrel](/aspnet/core/fundamentals/servers/kestrel) oder [HTTP.sys](/aspnet/core/fundamentals/servers/httpsys) konvertiert.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

#### Affected APIs

Not detectable via API analysis

-->
