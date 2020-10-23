---
title: Entwickeln für mehrere Plattformen mit .NET Framework
ms.date: 10/21/2020
ms.technology: dotnet-standard
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
ms.openlocfilehash: 75c33d2d2eb4bda0bcd86e19c5098af4a63863e9
ms.sourcegitcommit: 870bc4b4087510f6fba3c7b1c0d391f02bcc1f3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2020
ms.locfileid: "92471961"
---
# <a name="develop-for-multiple-platforms-with-net-framework"></a>Entwickeln für mehrere Plattformen mit .NET Framework

Sie können Apps für Microsoft-und nicht-Microsoft-Plattformen entwickeln, indem Sie .NET Framework und Visual Studio verwenden.

[!INCLUDE [net-framework-future](../../../includes/net-framework-future.md)]

## <a name="options-for-cross-platform-development"></a>Optionen für das plattformübergreifende Entwickeln

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

Um für mehrere Plattformen zu entwickeln, können Sie Quellcode oder Binärdateien freigeben und Aufrufe zwischen .NET Framework-Code und Windows Runtime-APIs ausführen.

|Zweck|Lösung|
|-----------------------|------------|
|Quellcode zwischen Windows Phone 8.1- und Windows 8.1-Apps freigeben|Frei **gegebene Projekte** (Universal apps-Vorlage in Visual Studio 2013, Update 2).<br /><br /> -Derzeit wird keine Visual Basic unterstützt.<br />-Sie können plattformspezifischen Code mithilfe von #- `if` Anweisungen trennen.<br /><br /> Details hierzu finden Sie in den folgenden Abschnitten:<br /><br /> -   [Codierung starten](/windows/uwp/get-started/create-uwp-apps)<br />-   [Verwenden von Visual Studio zum Erstellen universeller XAML-apps](https://devblogs.microsoft.com/visualstudio/using-visual-studio-to-build-universal-xaml-apps/) (Blogbeitrag)<br />-   [Verwenden von Visual Studio zum Erstellen von XAML-konvergierten apps](https://channel9.msdn.com/Events/Build/2014/3-591) (Video)|
|Binärdateien zwischen Apps freigeben, die verschiedene Plattformen als Ziel haben|**Projekte für Portable Klassenbibliotheken** für Code, der plattformunabhängig ist.<br /><br /> Diese Vorgehensweise wird in der Regel für Code verwendet, der die Geschäftslogik implementiert.<br />-Sie können Visual Basic oder c# verwenden.<br />-Die API-Unterstützung variiert je nach Plattform.<br />-Portable Klassen Bibliotheks Projekte, die auf Windows 8.1 abzielen und Windows Phone 8,1-Unterstützung Windows-Runtime APIs und XAML. Diese Funktionen sind in älteren Versionen der portablen Klassenbibliothek nicht verfügbar.<br />-Falls erforderlich, können Sie plattformspezifischen Code mithilfe von Schnittstellen oder abstrakten Klassen abstrahieren.<br /><br /> Details hierzu finden Sie in den folgenden Abschnitten:<br /><br /> -   [Portable Klassenbibliothek](cross-platform-development-with-the-portable-class-library.md)<br />-   [Arbeiten mit portablen Klassenbibliotheken](/archive/blogs/dsplaisted/how-to-make-portable-class-libraries-work-for-you) (Blogbeitrag)<br />-   [Verwenden der portablen Klassenbibliothek mit MVVM](using-portable-class-library-with-model-view-view-model.md) <br />-   [App-Ressourcen für Bibliotheken, die auf mehrere Plattformen abzielen](app-resources-for-libraries-that-target-multiple-platforms.md) <br />-   [.Net-Portabilitäts Analyse](https://marketplace.visualstudio.com/items?itemName=ConnieYau.NETPortabilityAnalyzer) (Visual Studio-Erweiterung)|
|Quellcode zwischen Apps für andere Plattformen als Windows 8.1 und Windows Phone 8.1 freigeben|Funktion **als Link hinzufügen** .<br /><br /> Diese Vorgehensweise eignet sich für App-Logik, die für beide apps gilt, aber aus irgendeinem Grund nicht portabel ist. Sie können diese Funktion für C#- oder Visual Basic-Code verwenden.<br />     Beispielsweise nutzen Windows Phone 8 und Windows 8 die Windows Runtime-APIs gemeinsam, aber die portablen Klassenbibliotheken unterstützen Windows Runtime für diese Plattformen nicht. Sie können `Add as link` verwenden, um gemeinsamen Windows Runtime-Code zwischen einer Windows Phone 8-App und einer Windows Store-App, die Windows 8 als Ziel hat, freizugeben.<br /><br /> Details hierzu finden Sie in den folgenden Abschnitten:<br /><br /> -   [Freigeben von Code mit Add as-Link](/previous-versions/windows/apps/jj714082(v=vs.105))<br />-   [Gewusst wie: Hinzufügen vorhandener Elemente zu einem Projekt](/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))|
|Windows Store-Apps mit .NET Framework schreiben oder Windows Runtime-APIs aus .NET Framework-Code aufrufen|**Windows-Runtime Sie APIs** aus Ihrem .NET Framework c#-oder Visual Basic-Code, und verwenden Sie die .NET Framework, um Windows Store-Apps zu erstellen. Beachten Sie die API-Unterschiede zwischen den zwei Plattformen. Es gibt jedoch Klassen, die Ihnen bei der Arbeit mit diesen Unterschieden helfen.<br /><br /> Details hierzu finden Sie in den folgenden Abschnitten:<br /><br /> -   [.NET Framework Unterstützung für Windows Store-Apps und Windows-Runtime](support-for-windows-store-apps-and-windows-runtime.md) <br />-   [Übergeben eines URI an den Windows-Runtime](passing-a-uri-to-the-windows-runtime.md) <br />-   <xref:System.IO.WindowsRuntimeStreamExtensions><br />-    <xref:System.WindowsRuntimeSystemExtensions>|
|.NET Framework-Apps für Plattformen anderer Anbieter erstellen|Verweisassemblys für die **portable Klassenbibliothek** im .NET Framework und eine Visual Studio-Erweiterung oder ein Drittanbieter Tool wie xamarin.<br /><br /> Details hierzu finden Sie in den folgenden Abschnitten:<br /><br /> -   [Die portable Klassenbibliothek ist jetzt auf allen Plattformen verfügbar.](https://devblogs.microsoft.com/dotnet/portable-class-library-pcl-now-available-on-all-platforms/) (Blogbeitrag)<br />-   [Xamarin-Dokumentation](/xamarin)|
|JavaScript und HTML für plattformübergreifende Entwicklung verwenden|**Universelle App-Vorlagen** in Visual Studio 2013, Update 2 für die Entwicklung mit Windows-Runtime-APIs für Windows 8.1 und Windows Phone 8,1. Derzeit können Sie JavaScript und HTML nicht mit .NET Framework-APIs verwenden, um plattformübergreifende apps zu entwickeln.<br /><br /> Details hierzu finden Sie in den folgenden Abschnitten:<br /><br /> -   [JavaScript-Projektvorlagen](/previous-versions/windows/apps/hh758331(v=win.10))<br />-   [Portieren einer Windows-Runtime-App mithilfe von JavaScript auf Windows Phone](/previous-versions/windows/apps/dn636144(v=win.10))|
