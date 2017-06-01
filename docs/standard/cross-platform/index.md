---
title: "Entwickeln f&#252;r mehrere Plattformen mit dem .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
caps.latest.revision: 13
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 13
---
# Entwickeln f&#252;r mehrere Plattformen mit dem .NET Framework
Mit .NET Framework und Visual Studio können Sie Apps sowohl für Microsoft\-Plattformen als auch für Plattformen anderer Anbieter entwickeln.  
  
## Optionen für das plattformübergreifende Entwickeln  
 Um für mehrere Plattformen zu entwickeln, können Sie Quellcode oder Binärdateien freigeben und Aufrufe zwischen .NET Framework\-Code und Windows Runtime\-APIs ausführen.  
  
|Zweck|Lösung|  
|-----------|------------|  
|Quellcode zwischen Windows Phone 8.1\- und Windows 8.1\-Apps freigeben|**Freigegebene Projekte** \(Universal Apps\-Vorlage in Visual Studio 2013 Update 2\).<br /><br /> -   Derzeit keine Unterstützung von Visual Basic.<br />-   Plattformspezifischen Code können Sie mit \#`if`\-Anweisungen separieren.<br /><br /> Ausführliche Informationen finden Sie unter:<br /><br /> -   [Erstellen universeller Windows\-Apps für Windows und Windows Phone](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx) \(MSDN\-Artikel\)<br />-   [Using Visual Studio to build Universal XAML Apps](http://blogs.msdn.com/b/visualstudio/archive/2014/04/14/using-visual-studio-to-build-universal-xaml-apps.aspx) \(Blogbeitrag\)<br />-   [Using Visual Studio to Build XAML Converged Apps](http://channel9.msdn.com/Events/Build/2014/3-591) \(Video\)|  
|Binärdateien zwischen Apps freigeben, die verschiedene Plattformen als Ziel haben|**Projekte für portable Klassenbibliotheken** für plattformagnostischen Code.<br /><br /> -   Dieser Ansatz wird normalerweise für Code verwendet, der eine Geschäftslogik implementiert.<br />-   Sie können Visual Basic oder C\# verwenden.<br />-   API\-Unterstützung ist von der Plattform abhängig.<br />-   Projekte für portable Klassenbibliotheken, die Windows 8.1 und Windows Phone 8.1 als Ziel haben, unterstützen Windows Runtime\-APIs und XAML.  Diese Funktionen sind in älteren Versionen der portablen Klassenbibliothek nicht verfügbar.<br />-   Falls nötig, können Sie plattformspezifischen Code mit Schnittstellen oder abstrakten Klassen abstrahieren.<br /><br /> Ausführliche Informationen finden Sie unter:<br /><br /> -   [Portable Klassenbibliothek](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) \(MSDN\-Artikel\)<br />-   [How to Make Portable Class Libraries Work for You](http://blogs.msdn.com/b/dsplaisted/archive/2012/08/27/how-to-make-portable-class-libraries-work-for-you.aspx) \(Blogbeitrag\)<br />-   [Verwenden der portablen Klassenbibliothek mit MVVM](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md) \(MSDN\-Artikel\)<br />-   [App\-Ressourcen für Bibliotheken, die für mehrere Zielplattformen konfiguriert sind](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md) \(MSDN\-Artikel\)<br />-   [.NET\-Portabilitätsanalyse](http://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b) \(Visual Studio\-Erweiterung, möglicherweise nur in englischer Sprache\)|  
|Quellcode zwischen Apps für andere Plattformen als Windows 8.1 und Windows Phone 8.1 freigeben|Funktion **Als Link hinzufügen**.<br /><br /> -   Dieser Ansatz ist geeignet für App\-Logik, die beide Apps gemeinsam haben, die aber aus bestimmten Gründen nicht portabel ist.  Sie können diese Funktion für C\#\- oder Visual Basic\-Code verwenden.<br />     Beispielsweise nutzen Windows Phone 8 und Windows 8 die Windows Runtime\-APIs gemeinsam, aber die portablen Klassenbibliotheken unterstützen Windows Runtime für diese Plattformen nicht.  Sie können `Add as link` verwenden, um gemeinsamen Windows Runtime\-Code zwischen einer Windows Phone 8\-App und einer Windows Store\-App, die Windows 8 als Ziel hat, freizugeben.<br /><br /> Ausführliche Informationen finden Sie unter:<br /><br /> -   [Freigeben von Code mit "Als Link hinzufügen"](http://msdn.microsoft.com/library/windowsphone/develop/jj714082\(v=vs.105\).aspx) \(MSDN\-Artikel, möglicherweise nur in englischer Sprache\)<br />-   [Gewusst wie: Hinzufügen von vorhandenen Elementen zu einem Projekt](http://msdn.microsoft.com/library/vstudio/9f4t9t92\(v=vs.100\).aspx) \(MSDN\-Artikel, möglicherweise nur in englischer Sprache\)|  
|Windows Store\-Apps mit .NET Framework schreiben oder Windows Runtime\-APIs aus .NET Framework\-Code aufrufen|**Windows Runtime\-APIs** aus Ihrem .NET Framework\-Code in C\# oder Visual Basic. Verwenden Sie .NET Framework, um Windows Store\-Apps zu erstellen.  Beachten Sie die API\-Unterschiede zwischen den zwei Plattformen.  Es gibt jedoch Klassen, die Ihnen bei der Arbeit mit diesen Unterschieden helfen.<br /><br /> Ausführliche Informationen finden Sie unter:<br /><br /> -   [.NET Framework\-Unterstützung für Windows Store\-Apps und Windows\-Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) \(MSDN\-Artikel\)<br />-   [Übergeben eines URI an die Windows\-Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md) \(MSDN\-Artikel\)<br />-   <xref:System.IO.WindowsRuntimeStreamExtensions> \(MSDN API\-Referenzseite\)<br />-   <xref:System.WindowsRuntimeSystemExtensions> \(MSDN API\-Referenzseite\)|  
|.NET Framework\-Apps für Plattformen anderer Anbieter erstellen|**Verweisassemblys für portable Klassenbibliotheken** in .NET Framework und eine Visual Studio\-Erweiterung oder ein Drittanbietertool wie Xamarin.<br /><br /> Ausführliche Informationen finden Sie unter:<br /><br /> -   [Portable Class Library now available on all platforms.](http://blogs.msdn.com/b/dotnet/archive/2013/10/14/portable-class-library-pcl-now-available-on-all-platforms.aspx) \(Blogbeitrag\)<br />-   [Xamarin](http://xamarin.com/visual-studio) \(Website von Xamarin\)|  
|JavaScript und HTML für plattformübergreifende Entwicklung verwenden|**Universal App\-Vorlagen** in Visual Studio 2013 Update 2 zum Entwickeln für Windows Runtime\-APIs für Windows 8.1 und Windows Phone 8.1.  Derzeit können JavaScript und HTML nicht mit .NET Framework\-APIs zum Entwickeln plattformübergreifender Apps verwendet werden.<br /><br /> Ausführliche Informationen finden Sie unter:<br /><br /> -   [JavaScript\-Projektvorlagen für Store\-Apps](http://msdn.microsoft.com/library/windows/apps/hh758331.aspx)<br />-   [Gewusst wie: Portieren einer Windows\-Runtime\-App mit JavaScript auf Windows Phone](http://msdn.microsoft.com/library/windows/apps/dn636144.aspx)|