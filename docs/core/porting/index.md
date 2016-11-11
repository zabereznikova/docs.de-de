---
title: Portieren von .NET Framework auf .NET Core
description: Portieren von .NET Framework auf .NET Core
keywords: .NET, .NET Core
author: cartermp
manager: wpickett
ms.date: 06/20/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 00d00d38-99af-44f4-a75f-defcd9729dc5
translationtype: Human Translation
ms.sourcegitcommit: ba6907f0054c3f4cdbaa687277ad70554670f0bb
ms.openlocfilehash: 677fe36a17b56aae0198140d82a2bfdd0d6e8224

---

# <a name="porting-to-net-core-from-net-framework"></a>Portieren von .NET Framework auf .NET Core

Wenn Code auf .NET Framework ausgeführt wird, sind Sie vielleicht interessiert daran, Ihren Code auf .NET Core 1.0 auszuführen.  Dieser Artikel enthält eine Übersicht über den Portiervorgang und eine Liste der Tools, die während des Portierens auf .NET Core hilfreich sein können.

## <a name="overview-of-the-porting-process"></a>Übersicht über den Portiervorgang

Die empfohlene Vorgehensweise für das Portieren ist in den folgenden Schritten dargestellt.  Jeder Teil dieses Vorgangs wird in weiteren Artikeln genauer erläutert.

1. Identifizieren Sie sich und weisen Sie sich für Ihre Drittanbieter-Abhängigkeiten aus.

   Sie müssen verstehen, was Ihre Drittanbieter-Abhängigkeiten sind, wie Sie von diesen abhängig sind, wie Sie überprüfen können, ob sie ebenso auf .NET Core ausgeführt werden, und welche Schritte Sie durchführen können, falls sie es nicht tun.
   
2. Legen Sie .NET Framework 4.6.2 als neues Ziel für alle Projekte fest, die Sie portieren möchten.

   Dadurch wird sichergestellt, dass Sie API-Alternativen für bestimmte .NET Framework-Ziele in Fällen verwenden können, in denen .NET Core eine bestimmte API nicht unterstützen kann.
   
3. Verwenden Sie das [Tool zum Analysieren der API-Portabilität](https://github.com/Microsoft/dotnet-apiport/), um Ihre Assemblys zu analysieren, und um einen Plan zum Portieren auf Grundlage der Ergebnisse zu entwickeln.

   Das Tool zum Analysieren der API-Portabilität analysiert Ihre kompilierten Assemblys und generiert einen Bericht, der eine allgemeine Zusammenfassung über die Portabilität sowie einen Strukturplan jeder API anzeigt, die Sie verwenden, und die nicht auf .NET Core verfügbar ist.  Sie können diesen Bericht zusammen mit einer Analyse Ihrer Codebase verwenden, um einen Plan zum Portieren Ihres Codes zu entwickeln.
   
4. Portieren Sie Ihre Testcodes.

   Da das Portieren auf .NET Core solch eine große Änderung für Ihre Codebase darstellt, wird empfohlen, Ihre Tests zu portieren, damit Sie Tests ausführen können, wenn Sie Code portieren.  MSTest, xUnit und NUnit unterstützen derzeit alle .NET Core 1.0.
   
6. Führen Sie Ihren Plan zum Portieren aus!

## <a name="tools-to-help"></a>Hilfetools

Nachstehend finden Sie eine Liste der Tools, die hilfreich sein können:

* NuGet – [Nuget Client](https://dist.nuget.org/index.html) oder [NuGet Package Explorer](https://github.com/NuGetPackageExplorer/NuGetPackageExplorer) sind die Paket-Manager von Microsoft für die .NET-Plattform.
* API Portability Analyzer – [Befehlszeilentool ](https://github.com/Microsoft/dotnet-apiport/releases) oder [Visual Studio-Erweiterung](https://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b); eine Toolkette, die einen Bericht generieren kann, der aussagt, wie portierbar Ihr Code zwischen .NET Framework und .NET Core ist, mithilfe einem Assembly-zu-Assymbly-Strukturplan der Fehler.  Weitere Informationen finden Sie unter [Tooling to help you on the process (Tools für den Vorgang)](https://github.com/Microsoft/dotnet-apiport/blob/master/docs/HowTo/).
* Reverse Package Search – ein [nützlicher Webdienst](https://packagesearch.azurewebsites.net), mit dem Sie einen Typ suchen können und Pakete finden können, die diesen Typ enthalten.

## <a name="next-steps"></a>Nächste Schritte

[Porting to .NET Core - Analyzing your Third-Party Dependencies (Portieren auf.NET Core – Analysieren Ihrer Drittanbieter-Abhängigkeiten)](third-party-deps.md)
   



<!--HONumber=Nov16_HO1-->


