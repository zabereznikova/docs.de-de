---
title: 'Breaking Change: Erweiterungen: Paketverweisänderungen beeinträchtigen einige NuGet-Pakete'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Erweiterungen: Paketverweisänderungen beeinträchtigen einige NuGet-Pakete'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 4a525d9f7aad4409fd507fcf80c00968ff4b63d4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759422"
---
# <a name="extensions-package-reference-changes-affecting-some-nuget-packages"></a>Erweiterungen: Paketverweisänderungen beeinträchtigen einige NuGet-Pakete

Bei der Migration einiger `Microsoft.Extensions.*`-NuGet-Pakete vom Repository [dotnet/extensions](https://github.com/dotnet/extensions) zu [dotnet/runtime](https://github.com/dotnet/runtime) ([aspnet/Announcements#411](https://github.com/aspnet/Announcements/issues/411)) werden Paketänderungen auf einige der migrierten Pakete angewendet. Dieses Problem wird unter [dotnet/aspnetcore#21033](https://github.com/dotnet/aspnetcore/issues/21033) behandelt.

## <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 4

## <a name="old-behavior"></a>Altes Verhalten

Einige `Microsoft.Extensions.*`-Pakete enthielten Paketverweise für APIs, auf die Ihre App angewiesen war.

## <a name="new-behavior"></a>Neues Verhalten

Möglicherweise müssen Sie Ihrer App `Microsoft.Extensions.*`-Paketabhängigkeiten hinzufügen.

## <a name="reason-for-change"></a>Grund für die Änderung

Die Paketrichtlinien wurden besser auf das Repository *dotnet/runtime* abgestimmt. Unter der neuen Richtlinie werden nicht verwendete Paketverweise während der Paketerstellung aus *NUPKG*-Dateien entfernt.

## <a name="recommended-action"></a>Empfohlene Aktion

Benutzer der betroffenen Pakete sollten eine direkte Abhängigkeit von der entfernten Paketabhängigkeit zu ihrem Projekt hinzufügen, wenn APIs der entfernten Paketabhängigkeit verwendet werden. In der folgenden Tabelle werden die betroffenen Pakete und die zugehörigen Änderungen aufgelistet.

|Paketname|Änderungsbeschreibung|
|------------|------------------|
|[Microsoft.Extensions.Configuration.Binder](https://nuget.org/packages/Microsoft.Extensions.Configuration.Binder)|Verweis auf `Microsoft.Extensions.Configuration` entfernt|
|[Microsoft.Extensions.Configuration.Json](https://nuget.org/packages/Microsoft.Extensions.Configuration.Json)    |Verweis auf `System.Threading.Tasks.Extensions` entfernt|
|[Microsoft.Extensions.Hosting.Abstractions](https://nuget.org/packages/Microsoft.Extensions.Hosting.Abstractions)|Verweis auf `Microsoft.Extensions.Logging.Abstractions` entfernt|
|[Microsoft.Extensions.Logging](https://nuget.org/packages/Microsoft.Extensions.Logging)                          |Verweis auf `Microsoft.Extensions.Configuration.Binder` entfernt|
|[Microsoft.Extensions.Logging.Console](https://nuget.org/packages/Microsoft.Extensions.Logging.Console)          |Verweis auf `Microsoft.Extensions.Configuration.Abstractions` entfernt|
|[Microsoft.Extensions.Logging.EventLog](https://nuget.org/packages/Microsoft.Extensions.Logging.EventLog)        |Verweis auf `System.Diagnostics.EventLog` für den .NET Framework 4.6.1-Zielframeworkmoniker entfernt|
|[Microsoft.Extensions.Logging.EventSource](https://nuget.org/packages/Microsoft.Extensions.Logging.EventSource)  |Verweis auf `System.Threading.Tasks.Extensions` entfernt|
|[Microsoft.Extensions.Options](https://nuget.org/packages/Microsoft.Extensions.Options)                          |Verweis auf `System.ComponentModel.Annotations` entfernt|

Beispielsweise wurde der Paketverweis auf `Microsoft.Extensions.Configuration` aus `Microsoft.Extensions.Configuration.Binder`entfernt. Im Paket wurde keine API der Abhängigkeit verwendet. Benutzer von `Microsoft.Extensions.Configuration.Binder`, die von `Microsoft.Extensions.Configuration`-APIs abhängig sind, sollten Ihrem Projekt einen direkten Verweis auf diese hinzufügen.

## <a name="affected-apis"></a>Betroffene APIs

Keine

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
