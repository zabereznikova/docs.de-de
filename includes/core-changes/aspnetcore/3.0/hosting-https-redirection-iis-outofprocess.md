---
ms.openlocfilehash: eb3fa768a491f6c0ff4b15479beabd71b0670338
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75937295"
---
### <a name="hosting-https-redirection-enabled-for-iis-out-of-process-apps"></a>Hosting: HTTPS-Umleitung für IIS-Out-of-Process-Apps aktiviert

In der Version 13.0.19218.0 des [ASP.NET Core-Moduls (ANCM)](/aspnet/core/host-and-deploy/aspnet-core-module) für das Hosten über IIS-Out-of-Process wurde ein vorhandenes HTTPS-Umleitungsfeature für ASP.NET Core 3.0- und ASP.NET Core 2.2.-Apps aktiviert.

Weitere Informationen finden Sie unter [dotnet/AspNetCore#15243](https://github.com/dotnet/AspNetCore/issues/15243).

#### <a name="version-introduced"></a>Eingeführt in Version

3.0

#### <a name="old-behavior"></a>Altes Verhalten

Bei der ASP.NET Core 2.1-Projektvorlage wurde zuerst Unterstützung für HTTPS-Middlewaremethoden wie <xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection%2A> und <xref:Microsoft.AspNetCore.Builder.HstsBuilderExtensions.UseHsts%2A> eingeführt. Es musste eine Konfiguration hinzugefügt werden, um die HTTPS-Umleitung zu aktivieren, da Apps in der Entwicklung nicht den Standardport 443 verwenden. [HTTP Strict Transport Security (HSTS)](https://cheatsheetseries.owasp.org/cheatsheets/HTTP_Strict_Transport_Security_Cheat_Sheet.html) ist nur aktiv, wenn die Anforderung bereits HTTPS verwendet. Der Localhost wird standardmäßig übersprungen.

#### <a name="new-behavior"></a>Neues Verhalten

In ASP.NET Core 3.0 wurde das IIS-HTTPS-Szenario [verbessert](https://github.com/dotnet/AspNetCore/pull/4685). Dank dieser Optimierung kann eine App nun die HTTPS-Ports eines Servers ermitteln, und `UseHttpsRedirection` funktioniert standardmäßig. Die In-Process-Komponente hat das Ermitteln von Ports mithilfe des `IServerAddresses`-Features möglich gemacht. Das betrifft nur ASP.NET Core 3.0-Apps, da die In-Process-Bibliothek mit dem Framework versioniert ist. Die Out-of-Process-Komponente wurde so geändert, dass die `ASPNETCORE_HTTPS_PORT`-Umgebungsvariable automatisch hinzugefügt wird. Diese Änderung wirkt sich sowohl auf ASP.NET Core 2.2- als auch ASP.NET Core 3.0-Apps aus, da die Out-of-Process-Komponente global geteilt wird. ASP.NET Core 2.1-Apps sind nicht betroffen, da sie standardmäßig eine ältere ANCM-Version verwenden.

Das hier beschriebene Verhalten wurde in ASP.NET Core 3.0.1 und ASP.NET Core 3.1.0 Preview 3 so geändert, dass die Behavior Changes in ASP.NET Core 2.x umgekehrt werden. Diese Änderungen betreffen nur IIS-Out-of-Process-Apps.

Wie oben beschrieben hatte das Installieren von ASP.NET Core 3.0.0 die Begleiterscheinung, dass auch die `UseHttpsRedirection`-Middleware in ASP.NET Core 2.x-Apps aktiviert wurde. Deshalb wurde das ANCM in ASP.NET Core 3.0.1 und in ASP.NET Core 3.1.0 Preview 3 so geändert, dass eine Installation des Frameworks nicht mehr diese Begleiterscheinung für ASP.NET Core 2.x-Apps hat. Die `ASPNETCORE_HTTPS_PORT`-Umgebungsvariable, die in ASP.NET Core 3.0.0 vom ANCM aufgefüllt wurde, wurde in ASP.NET Core 3.0.1 und ASP.NET Core 3.1.0 Preview 3 in `ASPNETCORE_ANCM_HTTPS_PORT` geändert. `UseHttpsRedirection` wurde in diesen Releases ebenfalls aktualisiert, sodass die neuen und die alten Variablen verstanden werden können. ASP.NET Core 2.x wird nicht aktualisiert. Das führt dazu, dass das vorherige Verhalten (standardmäßig deaktiviert) wiederhergestellt wird.

#### <a name="reason-for-change"></a>Grund für die Änderung

Verbesserung der ASP.NET Core 3.0-Funktionen.

#### <a name="recommended-action"></a>Empfohlene Aktion

Es ist keine Aktion erforderlich, wenn Sie möchten, dass alle Clients HTTPS verwenden. Wenn Sie zulassen möchten, dass einige Clients HTTP verwenden, führen Sie einen der folgenden Schritte aus:

* Entfernen Sie die Aufrufe von `UseHttpsRedirection` und `UseHsts` aus der `Startup.Configure`-Methode Ihres Projekts, und stellen Sie die App neu bereit.
* Legen Sie in der Datei *web.config* die `ASPNETCORE_HTTPS_PORT`-Umgebungsvariable auf eine leere Zeichenfolge fest. Diese Änderung kann direkt auf dem Server ausgeführt werden, ohne dass die App dafür neu bereitgestellt werden muss. Zum Beispiel:

    ```xml
    <aspNetCore processPath="dotnet" arguments=".\WebApplication3.dll" stdoutLogEnabled="false" stdoutLogFile="\\?\%home%\LogFiles\stdout" >
        <environmentVariables>
        <environmentVariable name="ASPNETCORE_HTTPS_PORT" value="" />
        </environmentVariables>
    </aspNetCore>
    ```

Folgende Aktionen sind für `UseHttpsRedirection` weiterhin möglich:

* Manuelles Aktivieren in ASP.NET Core 2.x, indem die `ASPNETCORE_HTTPS_PORT`-Umgebungsvariable auf die entsprechende Portnummer festgelegt wird. In den meisten Produktionsszenarios ist das 443.
* Deaktivieren in ASP.NET Core 3.x, indem `ASPNETCORE_ANCM_HTTPS_PORT` mit einem leeren Zeichenfolgenwert definiert wird. Dieser Wert wird auf dieselbe Art und Weise festgelegt, wie im vorherigen `ASPNETCORE_HTTPS_PORT`-Beispiel.

Auf Computern, auf denen ASP.NET Core 3.0.0-Apps ausgeführt werden, sollte die ASP.NET Core 3.0.1-Runtime installiert werden, bevor das ANCM von ASP.NET Core 3.1.0 Preview 3 installiert wird. Dadurch kann sichergestellt werden, dass `UseHttpsRedirection` für ASP.NET Core 3.0-Apps weiterhin erwartungsgemäß ausgeführt wird.

In Azure App Service wird das ANCM aufgrund seiner globalen Natur gemäß eines von der Runtime unabhängigen Plans bereitgestellt. Das ANCM wurde in Azure nach den Bereitstellungen von ASP.NET Core 3.0.1 und ASP.NET Core 3.1.0 mit diesen Änderungen bereitgestellt.

#### <a name="category"></a>Kategorie

ASP.NET Core

#### <a name="affected-apis"></a>Betroffene APIs

<xref:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)?displayProperty=nameWithType>

<!-- 

#### Affected APIs

`M:Microsoft.AspNetCore.Builder.HttpsPolicyBuilderExtensions.UseHttpsRedirection(Microsoft.AspNetCore.Builder.IApplicationBuilder)`

-->
