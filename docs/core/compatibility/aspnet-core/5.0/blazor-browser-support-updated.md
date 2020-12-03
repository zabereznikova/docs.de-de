---
title: 'Breaking Change: Blazor: Aktualisierte Browserunterstützung'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Blazor: Aktualisierte Browserunterstützung'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 63b35aa8cb73bfb82c565007704375bac3737299
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759537"
---
# <a name="blazor-updated-browser-support"></a>Blazor: Aktualisierte Browserunterstützung

Mit ASP.NET Core 5.0 werden [neue Blazor-Features](https://github.com/dotnet/aspnetcore/issues/21514) eingeführt. Einige davon sind mit älteren Browsern nicht kompatibel. Die Liste der von Blazor in ASP.NET Core 5.0 unterstützten Browser wurde entsprechend aktualisiert.

Weitere Informationen finden Sie im GitHub-Issue [dotnet/aspnetcore#26475](https://github.com/dotnet/aspnetcore/issues/26475).

## <a name="version-introduced"></a>Eingeführt in Version

5.0

## <a name="old-behavior"></a>Altes Verhalten

Blazor Server unterstützt Microsoft Internet Explorer 11 mit erforderlichen Polyfills. Blazor Server und Blazor WebAssembly können auch mit der [Vorgängerversion von Microsoft Edge](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy) verwendet werden.

## <a name="new-behavior"></a>Neues Verhalten

Blazor Server in ASP.NET Core 5.0 wird mit Microsoft Internet Explorer 11 nicht unterstützt. Blazor Server und Blazor WebAssembly sind in der Vorgängerversion von Microsoft Edge nicht voll funktionsfähig.

## <a name="reason-for-change"></a>Grund für die Änderung

Neue Blazor-Features in ASP.NET Core 5.0 sind mit diesen älteren Browsern nicht kompatibel. Außerdem nimmt die Verwendung dieser älteren Browser immer mehr ab. Weitere Informationen finden Sie in den folgenden Ressourcen:

* [Was ist die Vorgängerversion von Microsoft Edge?](https://support.microsoft.com/help/4533505/what-is-microsoft-edge-legacy)
* [Microsoft 365-Apps und -Dienste beenden die Unterstützung für IE 11; Ende der Unterstützung für die Legacyversion von Microsoft Edge](/lifecycle/announcements/m365-ie11-microsoft-edge-legacy)

## <a name="recommended-action"></a>Empfohlene Maßnahme

Führen Sie ein Upgrade dieser älteren Browser auf den [neuen, Chromium-basierten Microsoft Edge-Browser](https://www.microsoft.com/edge) durch. Für Blazor-Apps, die auf die Unterstützung dieser alten Browser angewiesen sind, können Sie ASP.NET Core 3.1 verwenden. Die Liste unterstützter Browser für Blazor in ASP.NET Core 3.1 wurde nicht geändert und ist unter [Unterstützte Plattformen für ASP.NET Core Blazor](/aspnet/core/blazor/supported-platforms?view=aspnetcore-3.1) dokumentiert.

## <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
