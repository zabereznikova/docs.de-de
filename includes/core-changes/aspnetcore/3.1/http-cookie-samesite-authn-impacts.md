---
ms.openlocfilehash: b0d093cc30a09b3248cc57a521b386bf581b5451
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552162"
---
### <a name="http-browser-samesite-changes-impact-authentication"></a><span data-ttu-id="6f723-101">HTTP: Browser-SameSite-Änderungen mit Auswirkung auf die Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="6f723-101">HTTP: Browser SameSite changes impact authentication</span></span>

<span data-ttu-id="6f723-102">Bei einigen Browsern, z. B. Chrome und Firefox, gab es Breaking Changes bei deren Implementierungen von `SameSite` für Cookies.</span><span class="sxs-lookup"><span data-stu-id="6f723-102">Some browsers, such as Chrome and Firefox, made breaking changes to their implementations of `SameSite` for cookies.</span></span> <span data-ttu-id="6f723-103">Die Änderungen wirken sich auf Remoteauthentifizierungsszenarien aus, z. B. OpenID Connect und WS-Verbund, die durch das Senden von `SameSite=None` deaktiviert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6f723-103">The changes impact remote authentication scenarios, such as OpenID Connect and WS-Federation, which must opt out by sending `SameSite=None`.</span></span> <span data-ttu-id="6f723-104">`SameSite=None` funktioniert jedoch unter iOS 12 und einigen älteren Versionen anderer Browser nicht.</span><span class="sxs-lookup"><span data-stu-id="6f723-104">However, `SameSite=None` breaks on iOS 12 and some older versions of other browsers.</span></span> <span data-ttu-id="6f723-105">Die App muss ermitteln, ob diese Versionen vorliegen, und `SameSite` weglassen.</span><span class="sxs-lookup"><span data-stu-id="6f723-105">The app needs to sniff these versions and omit `SameSite`.</span></span>

<span data-ttu-id="6f723-106">Dieses Problem wird unter [aspnet/AspNetCore#14996](https://github.com/aspnet/AspNetCore/issues/14996) behandelt.</span><span class="sxs-lookup"><span data-stu-id="6f723-106">For discussion on this issue, see [aspnet/AspNetCore#14996](https://github.com/aspnet/AspNetCore/issues/14996).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="6f723-107">Eingeführt in Version</span><span class="sxs-lookup"><span data-stu-id="6f723-107">Version introduced</span></span>

<span data-ttu-id="6f723-108">3.1 Vorschauversion 1</span><span class="sxs-lookup"><span data-stu-id="6f723-108">3.1 Preview 1</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="6f723-109">Altes Verhalten</span><span class="sxs-lookup"><span data-stu-id="6f723-109">Old behavior</span></span>

<span data-ttu-id="6f723-110">`SameSite` ist eine Erweiterung des Normentwurfs von 2016 für HTTP-Cookies.</span><span class="sxs-lookup"><span data-stu-id="6f723-110">`SameSite` is a 2016 draft standard extension to HTTP cookies.</span></span> <span data-ttu-id="6f723-111">Damit soll das Risiko einer websiteübergreifenden Anforderungsfälschung (Cross-Site Request Forgery, CSRF) minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="6f723-111">It's intended to mitigate Cross-Site Request Forgery (CSRF).</span></span> <span data-ttu-id="6f723-112">Es wurde ursprünglich als eine Funktion entwickelt, die die Server durch Hinzufügen der neuen Parameter aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="6f723-112">This was originally designed as a feature the servers would opt into by adding the new parameters.</span></span> <span data-ttu-id="6f723-113">In ASP.NET Core 2.0 wurde die erstmalige Unterstützung für `SameSite` eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6f723-113">ASP.NET Core 2.0 added initial support for `SameSite`.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="6f723-114">Neues Verhalten</span><span class="sxs-lookup"><span data-stu-id="6f723-114">New behavior</span></span>

<span data-ttu-id="6f723-115">Google hat einen neuen Normentwurf vorgeschlagen, der nicht abwärtskompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="6f723-115">Google proposed a new draft standard that isn't backwards compatible.</span></span> <span data-ttu-id="6f723-116">In der Norm wird der Standardmodus in `Lax` geändert und der neue Eintrag `None` zur Deaktivierung eingeführt. `Lax` ist für die meisten App-Cookies ausreichend, allerdings funktionieren standardübergreifende Szenarien wie die Anmeldung mit OpenID Connect und WS-Verbund dann nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="6f723-116">The standard changes the default mode to `Lax` and adds a new entry `None` to opt out. `Lax` suffices for most app cookies; however, it breaks cross-site scenarios like OpenID Connect and WS-Federation login.</span></span> <span data-ttu-id="6f723-117">Die meisten OAuth-Anmeldungen sind aufgrund von Unterschieden beim Ablauf der Anforderung nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="6f723-117">Most OAuth logins aren't affected because of differences in how the request flows.</span></span> <span data-ttu-id="6f723-118">Der neue Parameter `None` führt zu Kompatibilitätsproblemen mit Clients, die den früheren Normentwurf implementiert haben (z. B. iOS 12).</span><span class="sxs-lookup"><span data-stu-id="6f723-118">The new `None` parameter causes compatibility problems with clients that implemented the prior draft standard (for example, iOS 12).</span></span> <span data-ttu-id="6f723-119">Chrome 80 enthält die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="6f723-119">Chrome 80 will include the changes.</span></span> <span data-ttu-id="6f723-120">Weitere Informationen finden Sie unter [SameSite-Updates](https://www.chromium.org/updates/same-site) für den Chrome-Produkteinführungszeitplan.</span><span class="sxs-lookup"><span data-stu-id="6f723-120">See [SameSite Updates](https://www.chromium.org/updates/same-site) for the Chrome product launch timeline.</span></span>

<span data-ttu-id="6f723-121">ASP.NET Core 3.1 wurde aktualisiert, um das neue `SameSite`-Verhalten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="6f723-121">ASP.NET Core 3.1 has been updated to implement the new `SameSite` behavior.</span></span> <span data-ttu-id="6f723-122">Das Update definiert das Verhalten von `SameSiteMode.None` neu, um `SameSite=None` auszugeben, und ergänzt den neuen Wert `SameSiteMode.Unspecified`, um das `SameSite`-Attribut auszulassen.</span><span class="sxs-lookup"><span data-stu-id="6f723-122">The update redefines the behavior of `SameSiteMode.None` to emit `SameSite=None` and adds a new value `SameSiteMode.Unspecified` to omit the `SameSite` attribute.</span></span> <span data-ttu-id="6f723-123">Der Standard für alle Cookie-APIs ist jetzt `Unspecified`, obwohl einige Komponenten, die Cookies verwenden, Werte festlegen, die sich eher auf die entsprechenden Szenarien beziehen, z. B. die OpenID Connect-Korrelation und Nonce-Cookies.</span><span class="sxs-lookup"><span data-stu-id="6f723-123">All cookie APIs now default to `Unspecified`, though some components that use cookies set values more specific to their scenarios such as the OpenID Connect correlation and nonce cookies.</span></span>

<span data-ttu-id="6f723-124">Weitere aktuelle Änderungen in diesem Bereich finden Sie unter [HTTP: Einige Standardeinstellungen für Cookie-SameSite wurden in None geändert](/dotnet/core/compatibility/2.2-3.0#http-some-cookie-samesite-defaults-changed-to-none).</span><span class="sxs-lookup"><span data-stu-id="6f723-124">For other recent changes in this area, see [HTTP: Some cookie SameSite defaults changed to None](/dotnet/core/compatibility/2.2-3.0#http-some-cookie-samesite-defaults-changed-to-none).</span></span> <span data-ttu-id="6f723-125">In ASP.NET Core 3.0 wurden die meisten Standardwerte von <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType> in <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType> geändert (der vorherige Standard wird jedoch weiterhin verwendet).</span><span class="sxs-lookup"><span data-stu-id="6f723-125">In ASP.NET Core 3.0, most defaults were changed from <xref:Microsoft.AspNetCore.Http.SameSiteMode.Lax?displayProperty=nameWithType> to <xref:Microsoft.AspNetCore.Http.SameSiteMode.None?displayProperty=nameWithType> (but still using the prior standard).</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="6f723-126">Grund für die Änderung</span><span class="sxs-lookup"><span data-stu-id="6f723-126">Reason for change</span></span>

<span data-ttu-id="6f723-127">Änderungen bei Browsern und Spezifikationen, wie im vorangehenden Text erläutert.</span><span class="sxs-lookup"><span data-stu-id="6f723-127">Browser and specification changes as outlined in the preceding text.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="6f723-128">Empfohlene Maßnahme</span><span class="sxs-lookup"><span data-stu-id="6f723-128">Recommended action</span></span>

<span data-ttu-id="6f723-129">Apps, die mit Remotestandorten interagieren, z. B. über die Anmeldung über Drittanbieter, müssen folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="6f723-129">Apps that interact with remote sites, such as through third-party login, need to:</span></span>

* <span data-ttu-id="6f723-130">Testen Sie diese Szenarien in mehreren Browsern.</span><span class="sxs-lookup"><span data-stu-id="6f723-130">Test those scenarios on multiple browsers.</span></span>
* <span data-ttu-id="6f723-131">Wenden Sie die Maßnahmen zur Ermittlung der Cookierichtlinien im Browser an, die in [Unterstützung älterer Browser](#support-older-browsers) erläutert werden.</span><span class="sxs-lookup"><span data-stu-id="6f723-131">Apply the cookie policy browser sniffing mitigation discussed in [Support older browsers](#support-older-browsers).</span></span>

<span data-ttu-id="6f723-132">Informationen zu Tests und Browserermittlung finden Sie im folgenden Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="6f723-132">For testing and browser sniffing instructions, see the following section.</span></span>

##### <a name="determine-if-youre-affected"></a><span data-ttu-id="6f723-133">Ermitteln, ob Sie betroffen sind</span><span class="sxs-lookup"><span data-stu-id="6f723-133">Determine if you're affected</span></span>

<span data-ttu-id="6f723-134">Testen Sie Ihre Web-App mit einer Clientversion, die das neue Verhalten aktivieren kann.</span><span class="sxs-lookup"><span data-stu-id="6f723-134">Test your web app using a client version that can opt into the new behavior.</span></span> <span data-ttu-id="6f723-135">Chrome, Firefox und Microsoft Edge Chromium verfügen über neue Featureflags, die für Tests verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="6f723-135">Chrome, Firefox, and Microsoft Edge Chromium all have new opt-in feature flags that can be used for testing.</span></span> <span data-ttu-id="6f723-136">Vergewissern Sie sich, dass Ihre App nach dem Anwenden der Patches mit älteren Clientversionen kompatibel ist, insbesondere mit Safari.</span><span class="sxs-lookup"><span data-stu-id="6f723-136">Verify that your app is compatible with older client versions after you've applied the patches, especially Safari.</span></span> <span data-ttu-id="6f723-137">Weitere Informationen finden Sie unter [Unterstützung älterer Browser](#support-older-browsers).</span><span class="sxs-lookup"><span data-stu-id="6f723-137">For more information, see [Support older browsers](#support-older-browsers).</span></span>

##### <a name="chrome"></a><span data-ttu-id="6f723-138">Chrome</span><span class="sxs-lookup"><span data-stu-id="6f723-138">Chrome</span></span>

<span data-ttu-id="6f723-139">Chrome 78 und höher liefert irreführende Testergebnisse.</span><span class="sxs-lookup"><span data-stu-id="6f723-139">Chrome 78 and later yield misleading test results.</span></span> <span data-ttu-id="6f723-140">Diese Versionen verfügen über eine vorübergehende Entschärfung und akzeptieren Cookies, die weniger als zwei Minuten alt sind.</span><span class="sxs-lookup"><span data-stu-id="6f723-140">Those versions have a temporary mitigation in place and allow cookies less than two minutes old.</span></span> <span data-ttu-id="6f723-141">Wenn die entsprechenden Testflags aktiviert sind, liefern Chrome 76 und 77 genauere Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="6f723-141">With the appropriate test flags enabled, Chrome 76 and 77 yield more accurate results.</span></span> <span data-ttu-id="6f723-142">Um das neue Verhalten zu testen, legen Sie `chrome://flags/#same-site-by-default-cookies` auf aktiviert fest.</span><span class="sxs-lookup"><span data-stu-id="6f723-142">To test the new behavior, toggle `chrome://flags/#same-site-by-default-cookies` to enabled.</span></span> <span data-ttu-id="6f723-143">Bei Chrome 75 und früheren Versionen wurde ein Fehlschlagen mit der neuen `None`-Einstellung gemeldet.</span><span class="sxs-lookup"><span data-stu-id="6f723-143">Chrome 75 and earlier are reported to fail with the new `None` setting.</span></span> <span data-ttu-id="6f723-144">Weitere Informationen finden Sie unter [Unterstützung älterer Browser](#support-older-browsers).</span><span class="sxs-lookup"><span data-stu-id="6f723-144">For more information, see [Support older browsers](#support-older-browsers).</span></span>

<span data-ttu-id="6f723-145">Google stellt keine älteren Chrome-Versionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6f723-145">Google doesn't make older Chrome versions available.</span></span> <span data-ttu-id="6f723-146">Sie können jedoch ältere Versionen von Chromium herunterladen, die für Tests ausreichen.</span><span class="sxs-lookup"><span data-stu-id="6f723-146">You can, however, download older versions of Chromium, which will suffice for testing.</span></span> <span data-ttu-id="6f723-147">Befolgen Sie die Anweisungen unter [Herunterladen von Chromium](https://www.chromium.org/getting-involved/download-chromium).</span><span class="sxs-lookup"><span data-stu-id="6f723-147">Follow the instructions at [Download Chromium](https://www.chromium.org/getting-involved/download-chromium).</span></span>

* [<span data-ttu-id="6f723-148">Chromium 76 Win64</span><span class="sxs-lookup"><span data-stu-id="6f723-148">Chromium 76 Win64</span></span>](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/664998/)
* [<span data-ttu-id="6f723-149">Chromium 74 Win64</span><span class="sxs-lookup"><span data-stu-id="6f723-149">Chromium 74 Win64</span></span>](https://commondatastorage.googleapis.com/chromium-browser-snapshots/index.html?prefix=Win_x64/638880/)

##### <a name="safari"></a><span data-ttu-id="6f723-150">Safari</span><span class="sxs-lookup"><span data-stu-id="6f723-150">Safari</span></span>

<span data-ttu-id="6f723-151">In Safari 12 wurde der vorherige Entwurf streng implementiert, und der neue `None`-Wert in Cookies führt zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="6f723-151">Safari 12 strictly implemented the prior draft and fails if it sees the new `None` value in cookies.</span></span> <span data-ttu-id="6f723-152">Um dies zu vermeiden, muss der unter [Unterstützung älterer Browser](#support-older-browsers) aufgeführte Code zur Browserermittlung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6f723-152">This must be avoided via the browser sniffing code shown in [Support older browsers](#support-older-browsers).</span></span> <span data-ttu-id="6f723-153">Sie müssen Tests mit Safari 12 und 13 sowie auf WebKit-Basis, Betriebssystemanmeldungen mit Microsoft Authentication Library (MSAL), Active Directory Authentication Library (ADAL) oder einer sonstigen von Ihnen verwendeten Bibliothek durchführen.</span><span class="sxs-lookup"><span data-stu-id="6f723-153">Ensure you test Safari 12 and 13 as well as WebKit-based, OS-style logins using Microsoft Authentication Library (MSAL), Active Directory Authentication Library (ADAL), or whichever library you're using.</span></span> <span data-ttu-id="6f723-154">Das Problem hängt von der zugrunde liegenden Betriebssystemversion ab.</span><span class="sxs-lookup"><span data-stu-id="6f723-154">The problem is dependent on the underlying OS version.</span></span> <span data-ttu-id="6f723-155">Bei OSX Mojave 10.14 und iOS 12 sind Kompatibilitätsprobleme mit dem neuen Verhalten bekannt.</span><span class="sxs-lookup"><span data-stu-id="6f723-155">OSX Mojave 10.14 and iOS 12 are known to have compatibility problems with the new behavior.</span></span> <span data-ttu-id="6f723-156">Das Problem lässt sich mit einem Upgrade auf OSX Catalina 10.15 bzw. iOS 13 beheben.</span><span class="sxs-lookup"><span data-stu-id="6f723-156">Upgrading to OSX Catalina 10.15 or iOS 13 fixes the problem.</span></span> <span data-ttu-id="6f723-157">Safari verfügt derzeit über kein Aktivierungsflag zum Testen des neuen Spezifikationsverhaltens.</span><span class="sxs-lookup"><span data-stu-id="6f723-157">Safari doesn't currently have an opt-in flag for testing the new specification behavior.</span></span>

##### <a name="firefox"></a><span data-ttu-id="6f723-158">Firefox</span><span class="sxs-lookup"><span data-stu-id="6f723-158">Firefox</span></span>

<span data-ttu-id="6f723-159">Die Firefox-Unterstützung für den neuen Standard kann in Version 68 und höher getestet werden, indem Sie sich auf der Seite `about:config` mit dem Featureflag `network.cookie.sameSite.laxByDefault`anmelden.</span><span class="sxs-lookup"><span data-stu-id="6f723-159">Firefox support for the new standard can be tested on version 68 and later by opting in on the `about:config` page with the feature flag `network.cookie.sameSite.laxByDefault`.</span></span> <span data-ttu-id="6f723-160">Bei älteren Versionen von Firefox sind keine Kompatibilitätsprobleme bekannt.</span><span class="sxs-lookup"><span data-stu-id="6f723-160">No compatibility issues have been reported on older versions of Firefox.</span></span>

##### <a name="microsoft-edge"></a><span data-ttu-id="6f723-161">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="6f723-161">Microsoft Edge</span></span>

<span data-ttu-id="6f723-162">Microsoft Edge unterstützt zwar den alten `SameSite`-Standard, ab Version 44 sind jedoch keine Kompatibilitätsprobleme mit dem neuen Standard aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6f723-162">While Microsoft Edge supports the old `SameSite` standard, as of version 44 it didn't have any compatibility problems with the new standard.</span></span>

##### <a name="microsoft-edge-chromium"></a><span data-ttu-id="6f723-163">Microsoft Edge Chromium</span><span class="sxs-lookup"><span data-stu-id="6f723-163">Microsoft Edge Chromium</span></span>

<span data-ttu-id="6f723-164">Das Featureflag ist `edge://flags/#same-site-by-default-cookies`.</span><span class="sxs-lookup"><span data-stu-id="6f723-164">The feature flag is `edge://flags/#same-site-by-default-cookies`.</span></span> <span data-ttu-id="6f723-165">Bei Tests mit Microsoft Edge Chromium 78 wurden keine Kompatibilitätsprobleme festgestellt.</span><span class="sxs-lookup"><span data-stu-id="6f723-165">No compatibility issues were observed when testing with Microsoft Edge Chromium 78.</span></span>

##### <a name="electron"></a><span data-ttu-id="6f723-166">Electron</span><span class="sxs-lookup"><span data-stu-id="6f723-166">Electron</span></span>

<span data-ttu-id="6f723-167">Zu den Electron-Versionen zählen ältere Versionen von Chromium.</span><span class="sxs-lookup"><span data-stu-id="6f723-167">Versions of Electron include older versions of Chromium.</span></span> <span data-ttu-id="6f723-168">Beispielsweise ist die von Microsoft Teams verwendete Electron-Version Chromium 66, das das ältere Verhalten aufweist.</span><span class="sxs-lookup"><span data-stu-id="6f723-168">For example, the version of Electron used by Microsoft Teams is Chromium 66, which exhibits the older behavior.</span></span> <span data-ttu-id="6f723-169">Führen Sie Ihre eigenen Kompatibilitätstests mit der Version von Electron aus, die in Ihrem Produkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6f723-169">Perform your own compatibility testing with the version of Electron your product uses.</span></span> <span data-ttu-id="6f723-170">Weitere Informationen finden Sie unter [Unterstützung älterer Browser](#support-older-browsers).</span><span class="sxs-lookup"><span data-stu-id="6f723-170">For more information, see [Support older browsers](#support-older-browsers).</span></span>

##### <a name="support-older-browsers"></a><span data-ttu-id="6f723-171">Unterstützung älterer Browser</span><span class="sxs-lookup"><span data-stu-id="6f723-171">Support older browsers</span></span>

<span data-ttu-id="6f723-172">Im `SameSite`-Standard von 2016 ist vorgeschrieben, dass unbekannte Werte als `SameSite=Strict`-Werte behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="6f723-172">The 2016 `SameSite` standard mandated that unknown values be treated as `SameSite=Strict` values.</span></span> <span data-ttu-id="6f723-173">Folglich kann es sein, dass bei älteren Browsern, die den ursprünglichen Standard unterstützen, Fehler auftreten, wenn eine `SameSite`-Eigenschaft mit dem Wert `None` erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="6f723-173">Consequently, any older browsers that support the original standard may break when they see a `SameSite` property with a value of `None`.</span></span> <span data-ttu-id="6f723-174">Web-Apps müssen eine Browserermittlung implementieren, wenn diese alten Browser unterstützt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6f723-174">Web apps must implement browser sniffing if they intend to support these old browsers.</span></span> <span data-ttu-id="6f723-175">ASP.NET Core implementiert keine Browserermittlung für Sie, da die Werte des `User-Agent`-Anforderungsheaders sehr instabil sind und sich wöchentlich ändern.</span><span class="sxs-lookup"><span data-stu-id="6f723-175">ASP.NET Core doesn't implement browser sniffing for you because `User-Agent` request header values are highly unstable and change on a weekly basis.</span></span> <span data-ttu-id="6f723-176">Stattdessen können Sie mithilfe eines Erweiterungspunkts in der Cookierichtlinie für `User-Agent`spezifische Logik hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6f723-176">Instead, an extension point in the cookie policy allows you to add `User-Agent`-specific logic.</span></span>

<span data-ttu-id="6f723-177">Fügen Sie in *Startup.cs* folgenden Code hinzu:</span><span class="sxs-lookup"><span data-stu-id="6f723-177">In *Startup.cs*, add the following code:</span></span>

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

##### <a name="opt-out-switches"></a><span data-ttu-id="6f723-178">Deaktivierungsschalter</span><span class="sxs-lookup"><span data-stu-id="6f723-178">Opt-out switches</span></span>

<span data-ttu-id="6f723-179">Mit dem Kompatibilitätsschalter `Microsoft.AspNetCore.SuppressSameSiteNone` können Sie das neue ASP.NET Core-Cookieverhalten vorübergehend deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6f723-179">The `Microsoft.AspNetCore.SuppressSameSiteNone` compatibility switch enables you to temporarily opt out of the new ASP.NET Core cookie behavior.</span></span> <span data-ttu-id="6f723-180">Fügen Sie folgenden JSON-Code einer *runtimeconfig.template.json*-Datei in Ihrem Projekt hinzu:</span><span class="sxs-lookup"><span data-stu-id="6f723-180">Add the following JSON to a *runtimeconfig.template.json* file in your project:</span></span>

```json
{ 
  "configProperties": { 
    "Microsoft.AspNetCore.SuppressSameSiteNone": "true" 
  } 
}
```

##### <a name="other-versions"></a><span data-ttu-id="6f723-181">Andere Versionen</span><span class="sxs-lookup"><span data-stu-id="6f723-181">Other Versions</span></span>

<span data-ttu-id="6f723-182">Entsprechende `SameSite`-Patches für folgende Versionen sind in Entwicklung:</span><span class="sxs-lookup"><span data-stu-id="6f723-182">Related `SameSite` patches are forthcoming for:</span></span>

* <span data-ttu-id="6f723-183">ASP.NET Core 2.1, 2.2 und 3.0</span><span class="sxs-lookup"><span data-stu-id="6f723-183">ASP.NET Core 2.1, 2.2, and 3.0</span></span>
* <span data-ttu-id="6f723-184">`Microsoft.Owin` 4.1</span><span class="sxs-lookup"><span data-stu-id="6f723-184">`Microsoft.Owin` 4.1</span></span>
* <span data-ttu-id="6f723-185">`System.Web` (für .NET Framework 4.7.2 und höher)</span><span class="sxs-lookup"><span data-stu-id="6f723-185">`System.Web` (for .NET Framework 4.7.2 and later)</span></span>

#### <a name="category"></a><span data-ttu-id="6f723-186">Kategorie</span><span class="sxs-lookup"><span data-stu-id="6f723-186">Category</span></span>

<span data-ttu-id="6f723-187">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6f723-187">ASP.NET</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="6f723-188">Betroffene APIs</span><span class="sxs-lookup"><span data-stu-id="6f723-188">Affected APIs</span></span>

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
