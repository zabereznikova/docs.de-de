---
title: 'Breaking Change: Lokalisierung: ResourceManagerWithCultureStringLocalizer-Klasse und WithCulture-Schnittstellenmember entfernt'
description: 'Hier erfahren Sie mehr über den Breaking Change in ASP.NET Core 5.0 mit dem Titel „Lokalisierung: ResourceManagerWithCultureStringLocalizer-Klasse und WithCulture-Schnittstellenmember entfernt'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: ac7723cd9b961b34b3f87a55119d421668c87417
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437859"
---
# <a name="localization-resourcemanagerwithculturestringlocalizer-class-and-withculture-interface-member-removed"></a>Lokalisierung: ResourceManagerWithCultureStringLocalizer-Klasse und WithCulture-Schnittstellenmember entfernt

Die [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)-Klasse und die [WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)-Methode wurden in .NET 5.0 Preview 1 entfernt.

Weitere Informationen finden Sie unter [aspnet/Announcements#346](https://github.com/aspnet/Announcements/issues/346) und [dotnet/aspnetcore#3324](https://github.com/dotnet/aspnetcore/issues/3324). Diese Änderung wird unter [dotnet/aspnetcore#7756](https://github.com/dotnet/aspnetcore/issues/7756) behandelt.

## <a name="version-introduced"></a>Eingeführt in Version

5.0 Preview 1

## <a name="old-behavior"></a>Altes Verhalten

Die `ResourceManagerWithCultureStringLocalizer`-Klasse und die `ResourceManagerStringLocalizer.WithCulture`-Methode gelten in [.NET Core 3.0 Preview 3 und höher](../../3.0.md#localization-resourcemanagerwithculturestringlocalizer-and-withculture-marked-obsolete) als veraltet.

## <a name="new-behavior"></a>Neues Verhalten

Die `ResourceManagerWithCultureStringLocalizer`-Klasse und die `ResourceManagerStringLocalizer.WithCulture`-Methode wurden in .NET 5.0 Preview 1 entfernt. Eine Übersicht über die vorgenommenen Änderungen finden Sie im Pull Request unter [dotnet/extensions#2562](https://github.com/dotnet/extensions/pull/2562/files).

## <a name="reason-for-change"></a>Grund für die Änderung

Die [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)-Klasse und die [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)-Methode sorgten bei Benutzern mit lokalisierten Versionen häufig für Verwirrung. Das galt insbesondere für die Erstellung einer benutzerdefinierten <xref:Microsoft.Extensions.Localization.IStringLocalizer>-Implementierung. Diese Klasse und Methode erwecken bei Benutzern den Eindruck, dass eine `IStringLocalizer`-Instanz pro Sprache und pro Ressource gilt. Tatsächlich sollte die Instanz nur pro Ressource gelten. Zur Laufzeit bestimmt die <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=nameWithType>-Eigenschaft die zu verwendende Sprache.

## <a name="recommended-action"></a>Empfohlene Aktion

Verwenden Sie die `ResourceManagerWithCultureStringLocalizer`-Klasse und die `ResourceManagerStringLocalizer.WithCulture`-Methode nicht mehr.

## <a name="affected-apis"></a>Betroffene APIs

- [ResourceManagerWithCultureStringLocalizer](/dotnet/api/microsoft.extensions.localization.resourcemanagerwithculturestringlocalizer?view=dotnet-plat-ext-3.1)
- [ResourceManagerStringLocalizer.WithCulture](/dotnet/api/microsoft.extensions.localization.resourcemanagerstringlocalizer.withculture?view=dotnet-plat-ext-3.1)

<!--

### Category

ASP.NET Core

### Affected APIs

- `T:Microsoft.Extensions.Localization.ResourceManagerWithCultureStringLocalizer`
- `Overload:Microsoft.Extensions.Localization.ResourceManagerStringLocalizer.WithCulture`

-->
