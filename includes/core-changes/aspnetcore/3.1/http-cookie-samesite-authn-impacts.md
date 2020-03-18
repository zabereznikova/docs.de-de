---
ms.openlocfilehash: 3cc07eef109b9096bc5a5fbcd1ea098a23b2155f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78968269"
---
### <a name="http-browser-samesite-changes-impact-authentication"></a>HTTP: Browser-SameSite-Änderungen mit Auswirkung auf die Authentifizierung

Bei einigen Browsern, z. B. Chrome und Firefox, gab es Breaking Changes bei deren Implementierungen von `SameSite` für Cookies. Die Änderungen wirken sich auf Remoteauthentifizierungsszenarien aus, z. B. OpenID Connect und WS-Verbund, die durch das Senden von `SameSite=None` deaktiviert werden müssen. `SameSite=None` funktioniert jedoch unter iOS 12 und einigen älteren Versionen anderer Browser nicht. Die App muss ermitteln, ob diese Versionen vorliegen, und `SameSite` weglassen.

Dieses Problem wird unter [dotnet/aspnetcore#14996](https://github.com/dotnet/aspnetcore/issues/14996) behandelt.

#### <a name="version-introduced"></a>Eingeführt in Version

3.1 Vorschauversion 1

#### <a name="old-behavior"></a>Altes Verhalten

`SameSite` ist eine Erweiterung des Normentwurfs von 2016 für HTTP-Cookies. Damit soll das Risiko einer websiteübergreifenden Anforderungsfälschung (Cross-Site Request Forgery, CSRF) minimiert werden. Es wurde ursprünglich als eine Funktion entwickelt, die die Server durch Hinzufügen der neuen Parameter aktivieren können. In ASP.NET Core 2.0 wurde die erstmalige Unterstützung für `SameSite` eingeführt.

#### <a name="new-behavior"></a>Neues Verhalten

Google hat einen neuen Normentwurf vorgeschlagen, der nicht abwärtskompatibel ist. In der Norm wird der Standardmodus in `Lax` geändert und der neue Eintrag `None` zur Deaktivierung eingeführt. `Lax` ist für die meisten App-Cookies ausreichend, allerdings funktionieren standardübergreifende Szenarien wie die Anmeldung mit OpenID Connect und WS-Verbund dann nicht mehr. Die meisten OAuth-Anmeldungen sind aufgrund von Unterschieden beim Ablauf der Anforderung nicht betroffen. Der neue Parameter `None` führt zu Kompatibilitätsproblemen mit Clients, die den früheren Normentwurf implementiert haben (z. B. iOS 12). Chrome 80 enthält die Änderungen. Weitere Informationen finden Sie unter [SameSite-Updates](https://www.chromium.org/updates/same-site) für den Chrome-Produkteinführungszeitplan.

ASP.NET Core 3.1 wurde aktualisiert, um das neue `SameSite`-Verhalten zu implementieren. Das Update definiert das Verhalten von `SameSiteMode.None` neu, um `SameSite=None` auszugeben, und ergänzt den neuen Wert `SameSiteMode.Unspecified`, um das `SameSite`-Attribut auszulassen. Der Standard für alle Cookie-APIs ist jetzt `Unspecified`, obwohl einige Komponenten, die Cookies verwenden, Werte festlegen, die sich eher auf die entsprechenden Szenarien beziehen, z. B. die OpenID Connect-Korrelation und Nonce-Cookies.

Weitere aktuelle Änderungen in diesem Bereich finden Sie unter [HTTP: Einige Standardeinstellungen für Cookie-SameSite wurden in None geändert](/dotnet/core/compatibility/2.2-3.0#http-some-cookie-samesite-defaults-changed-to-none). In ASP.NET Core 3.0 wurden die meisten Standardwerte von <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType> in <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType> geändert (der vorherige Standard wird jedoch weiterhin verwendet).

#### <a name="reason-for-change"></a>Grund für die Änderung

Änderungen bei Browsern und Spezifikationen, wie im vorangehenden Text erläutert.

#### <a name="recommended-action"></a>Empfohlene Aktion

Apps, die mit Remotestandorten interagieren, z. B. über die Anmeldung über Drittanbieter, müssen folgende Aktionen ausführen:

* Testen Sie diese Szenarien in mehreren Browsern.
* Wenden Sie die Maßnahmen zur Ermittlung der Cookierichtlinien im Browser an, die in [Unterstützung älterer Browser](#support-older-browsers) erläutert werden.

Informationen zu Tests und Browserermittlung finden Sie im folgenden Abschnitt.

##### <a name="determine-if-youre-affected"></a>Ermitteln, ob Sie betroffen sind

Testen Sie Ihre Web-App mit einer Clientversion, die das neue Verhalten aktivieren kann. Chrome, Firefox und Microsoft Edge Chromium verfügen über neue Featureflags, die für Tests verwendet werden können. Vergewissern Sie sich, dass Ihre App nach dem Anwenden der Patches mit älteren Clientversionen kompatibel ist, insbesondere mit Safari. Weitere Informationen finden Sie unter [Unterstützung älterer Browser](#support-older-browsers).

##### <a name="chrome"></a>Chrome

Chrome 78 und höher liefert irreführende Testergebnisse. Diese Versionen verfügen über eine vorübergehende Entschärfung und akzeptieren Cookies, die weniger als zwei Minuten alt sind. Wenn die entsprechenden Testflags aktiviert sind, liefern Chrome 76 und 77 genauere Ergebnisse. Um das neue Verhalten zu testen, legen Sie `chrome://flags/#same-site-by-default-cookies` auf aktiviert fest. Bei Chrome 75 und früheren Versionen wurde ein Fehlschlagen mit der neuen `None`-Einstellung gemeldet. Weitere Informationen finden Sie unter [Unterstützung älterer Browser](#support-older-browsers).

Google stellt keine älteren Chrome-Versionen zur Verfügung. Sie können jedoch ältere Versionen von Chromium herunterladen, die für Tests ausreichen. Befolgen Sie die Anweisungen unter [Herunterladen von Chromium](https://www.chromium.org/getting-involved/download-chromium).

* [Chromium 76 Win64](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/664998/)
* [Chromium 74 Win64](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/638880/)

##### <a name="safari"></a>Safari

In Safari 12 wurde der vorherige Entwurf streng implementiert, und der neue `None`-Wert in Cookies führt zu einem Fehler. Um dies zu vermeiden, muss der unter [Unterstützung älterer Browser](#support-older-browsers) aufgeführte Code zur Browserermittlung verwendet werden. Sie müssen Tests mit Safari 12 und 13 sowie auf WebKit-Basis, Betriebssystemanmeldungen mit Microsoft Authentication Library (MSAL), Active Directory Authentication Library (ADAL) oder einer sonstigen von Ihnen verwendeten Bibliothek durchführen. Das Problem hängt von der zugrunde liegenden Betriebssystemversion ab. Bei OSX Mojave 10.14 und iOS 12 sind Kompatibilitätsprobleme mit dem neuen Verhalten bekannt. Das Problem lässt sich mit einem Upgrade auf OSX Catalina 10.15 bzw. iOS 13 beheben. Safari verfügt derzeit über kein Aktivierungsflag zum Testen des neuen Spezifikationsverhaltens.

##### <a name="firefox"></a>Firefox

Die Firefox-Unterstützung für den neuen Standard kann in Version 68 und höher getestet werden, indem Sie sich auf der Seite `about:config` mit dem Featureflag `network.cookie.sameSite.laxByDefault`anmelden. Bei älteren Versionen von Firefox sind keine Kompatibilitätsprobleme bekannt.

##### <a name="microsoft-edge"></a>Microsoft Edge

Microsoft Edge unterstützt zwar den alten `SameSite`-Standard, ab Version 44 sind jedoch keine Kompatibilitätsprobleme mit dem neuen Standard aufgetreten.

##### <a name="microsoft-edge-chromium"></a>Microsoft Edge Chromium

Das Featureflag ist `edge://flags/#same-site-by-default-cookies`. Bei Tests mit Microsoft Edge Chromium 78 wurden keine Kompatibilitätsprobleme festgestellt.

##### <a name="electron"></a>Electron

Zu den Electron-Versionen zählen ältere Versionen von Chromium. Beispielsweise ist die von Microsoft Teams verwendete Electron-Version Chromium 66, das das ältere Verhalten aufweist. Führen Sie Ihre eigenen Kompatibilitätstests mit der Version von Electron aus, die in Ihrem Produkt verwendet wird. Weitere Informationen finden Sie unter [Unterstützung älterer Browser](#support-older-browsers).

##### <a name="support-older-browsers"></a>Unterstützung älterer Browser

Im `SameSite`-Standard von 2016 ist vorgeschrieben, dass unbekannte Werte als `SameSite=Strict`-Werte behandelt werden. Folglich kann es sein, dass bei älteren Browsern, die den ursprünglichen Standard unterstützen, Fehler auftreten, wenn eine `SameSite`-Eigenschaft mit dem Wert `None` erkannt wird. Web-Apps müssen eine Browserermittlung implementieren, wenn diese alten Browser unterstützt werden sollen. ASP.NET Core implementiert keine Browserermittlung für Sie, da die Werte des `User-Agent`-Anforderungsheaders sehr instabil sind und sich wöchentlich ändern. Stattdessen können Sie mithilfe eines Erweiterungspunkts in der Cookierichtlinie für `User-Agent`spezifische Logik hinzufügen.

Fügen Sie in *Startup.cs* folgenden Code hinzu:

```csharp
private void CheckSameSite(HttpContext httpContext, CookieOptions options)
{
    if (options.SameSite == SameSiteMode.None)
    {
        var userAgent = httpContext.Request.Headers["User-Agent"].ToString();
        // TODO: Use your User Agent library of choice here.
        if (/* UserAgent doesn't support new behavior */)
        {
            options.SameSite = SameSiteMode.Unspecified;
        }
    }
}

public void ConfigureServices(IServiceCollection services)
{
    services.Configure<CookiePolicyOptions>(options =>
    {
        options.MinimumSameSitePolicy = SameSiteMode.Unspecified;
        options.OnAppendCookie = cookieContext =>
            CheckSameSite(cookieContext.Context, cookieContext.CookieOptions);
        options.OnDeleteCookie = cookieContext =>
            CheckSameSite(cookieContext.Context, cookieContext.CookieOptions);
    });
}

public void Configure(IApplicationBuilder app)
{
    // Before UseAuthentication or anything else that writes cookies.
    app.UseCookiePolicy();

    app.UseAuthentication();
    // code omitted for brevity
}
```

##### <a name="opt-out-switches"></a>Deaktivierungsschalter

Mit dem Kompatibilitätsschalter `Microsoft.AspNetCore.SuppressSameSiteNone` können Sie das neue ASP.NET Core-Cookieverhalten vorübergehend deaktivieren. Fügen Sie folgenden JSON-Code einer *runtimeconfig.template.json*-Datei in Ihrem Projekt hinzu:

```json
{
  "configProperties": {
    "Microsoft.AspNetCore.SuppressSameSiteNone": "true"
  }
}
```

##### <a name="other-versions"></a>Andere Versionen

Entsprechende `SameSite`-Patches für folgende Versionen sind in Entwicklung:

* ASP.NET Core 2.1, 2.2 und 3.0
* `Microsoft.Owin` 4.1
* `System.Web` (für .NET Framework 4.7.2 und höher)

#### <a name="category"></a>Kategorie

ASP.NET

#### <a name="affected-apis"></a>Betroffene APIs

- <xref:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.CookieBuilder.SameSite%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.CookieOptions.SameSite%2A?displayProperty=fullName>
- <xref:Microsoft.AspNetCore.Http.SameSiteMode?displayProperty=fullName>
- <xref:Microsoft.Net.Http.Headers.SameSiteMode?displayProperty=fullName>
- <xref:Microsoft.Net.Http.Headers.SetCookieHeaderValue.SameSite%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:Microsoft.AspNetCore.Builder.CookiePolicyOptions.MinimumSameSitePolicy`
- `Overload:Microsoft.AspNetCore.Http.CookieBuilder.SameSite`
- `Overload:Microsoft.AspNetCore.Http.CookieOptions.SameSite`
- `T:Microsoft.AspNetCore.Http.SameSiteMode`
- `T:Microsoft.Net.Http.Headers.SameSiteMode`
- `Overload:Microsoft.Net.Http.Headers.SetCookieHeaderValue.SameSite`

-->
