---
title: "Übersicht über .NET Framework | Microsoft-Dokumentation"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application development [.NET Framework]
- common language runtime
- common language runtime, about
- common language runtime, overview
ms.assetid: 29848c96-fc36-462d-8072-ba223a40b697
caps.latest.revision: 34
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: fe9ab371ab8d3eee3778412e446b7aa30b42476b
ms.openlocfilehash: f7af2ff5db3d6d06383906fc271ae60d68f43731
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
<a id="overview-of-the-net-framework" class="xliff"></a>

# Übersicht über .NET Framework
Beim .NET Framework handelt es sich um eine Technologie, mit der die Entwicklung und Ausführung von Anwendungen und XML-Webdiensten der nächsten Generation unterstützt wird. .NET Framework wurde im Hinblick auf folgende Zielsetzungen entwickelt:  
  
-   Bereitstellung einer konsistenten, objektorientierten Programmierumgebung, in der Objektcode gespeichert wird. Die Ausführung erfolgt dann entweder lokal oder über Remotezugriff bzw. lokal mit Verteilung über das Internet.  
  
-   Bereitstellung einer Codeausführungsumgebung, mit der Konflikte bei der Softwarebereitstellung und Versionskonflikte auf ein Minimum beschränkt werden.  
  
-   Bereitstellung einer Codeausführungsumgebung, die eine sichere Ausführung ermöglicht, und zwar auch von Code, der von unbekannten oder nur halb-vertrauenswürdigen Dritten erstellt wurde.  
  
-   Bereitstellung einer Codeausführungsumgebung, die nicht mehr die bei interpretations- oder skriptbasierten Umgebungen auftretenden Leistungsprobleme aufweist.  
  
-   Schaffung einer konsistenten Entwicklungsumgebung für die verschiedensten Anwendungsarten, wie beispielsweise Windows- und webbasierte Anwendungen.  
  
-   Aufbau der gesamten Kommunikation auf Industriestandards, um die Integration von Code, der auf .NET Framework basiert, in jeden anderen Code zu gewährleisten.  
  
> [!NOTE]
>  Eine allgemeine Einführung in .NET Framework für Benutzer und Entwickler erhalten Sie unter [Erste Schritte](../../../docs/framework/get-started/index.md).  
  
 Das .NET Framework besteht aus der Common Language Runtime und der .NET Framework-Klassenbibliothek. .NET Framework setzt auf der Common Language Runtime auf. Sie können sich die Common Language Runtime als Agenten vorstellen, der zum Ausführungszeitpunkt Code verwaltet sowie Basisdienste wie Speicherverwaltung, Threadverwaltung und Remoting bereitstellt. Er erzwingt gleichzeitig strikte Typsicherheit und andere Formen der Codegenauigkeit, mit denen Sicherheit und Zuverlässigkeit unterstützt werden. Das Konzept der Codeverwaltung ist ein fundamentales Prinzip der Laufzeitumgebung. Code, der die Laufzeit zum Ziel hat, wird als verwalteter Code bezeichnet, während Code, der nicht auf die Laufzeit abzielt, als nicht verwalteter Code gilt. Die Klassenbibliothek, ist eine umfassende, objektorientierte Auflistung wiederverwendbarer Typen für die Entwicklung vielfältiger Anwendungen, z. B. solcher mit herkömmlicher Befehlszeile oder grafischer Benutzeroberfläche (GUI), bis hin zu Anwendungen, die auf den neuesten Innovationen von ASP.NET, wie beispielsweise Web Forms und XML-Webdiensten, basieren.  
  
 .NET Framework kann von nicht verwalteten Komponenten gehostet werden, durch die die Common Language Runtime in die Prozesse geladen und die Ausführung verwalteten Codes initiiert wird. So entsteht eine Softwareumgebung, in der sowohl verwaltete als auch nicht verwaltete Features genutzt werden können. .NET Framework stellt nicht nur mehrere Laufzeithosts bereit, sondern unterstützt auch die Entwicklung von Laufzeithosts von Drittanbietern.  
  
 So dient beispielsweise ASP.NET als Laufzeithost und stellt eine skalierbare, serverseitige Umgebung für verwalteten Code bereit. ASP.NET arbeitet direkt mit der Common Language Runtime und aktiviert ASP.NET-Anwendungen sowie XML-Webdienste, die weiter unten in diesem Thema behandelt werden.  
  
 Internet Explorer ist ein Beispiel für eine nicht verwaltete Anwendung, die die Laufzeit (als MIME-Typerweiterung) hostet. Mit Internet Explorer als Laufzeithost können Sie verwaltete Komponenten oder Steuerelemente für Windows Forms in HTML-Dokumente einbetten. Ein derartiges Hosten der Laufzeit ermöglicht verwalteten mobilen Code, aber mit erheblichen Verbesserungen, wie sie nur verwalteter Code bietet, beispielsweise die Ausführung von halb-vertrauenswürdigem Code sowie isolierter Dateispeicher.  
  
 In der folgenden Abbildung ist die Beziehung der Common Language Runtime und der Klassenbibliothek zu den Anwendungen und dem Gesamtsystem dargestellt. Außerdem geht aus der Abbildung hervor, wie verwalteter Code innerhalb einer größeren Architektur operiert.  
  
 ![Verwalteter Code innerhalb einer größeren Architektur](../../../docs/framework/get-started/media/circle.gif "circle")  
.NET Framework im Kontext  
  
 In den folgenden Abschnitten werden die Hauptfunktionen von .NET Framework genauer beschrieben.  
  
<a id="features-of-the-common-language-runtime" class="xliff"></a>

## Features der Common Language Runtime  
 Die Common Language Runtime verwaltet Speicher, Thread- und Codeausführung, Überprüfung der Codesicherheit, Kompilierung und andere Systemdienste. Diese Features sind in den verwalteten Code integriert, der durch die Common Language Runtime ausgeführt wird.  
  
 Aus Sicherheitsgründen werden verwalteten Komponenten unterschiedliche Vertrauensstufen zugewiesen, die von mehreren Faktoren abhängen, zu denen auch der Ursprung (z. B. das Internet, ein Intranet oder ein lokaler Computer) zählt. Das bedeutet, dass eine verwaltete Komponente je nachdem auf Dateien und die Registrierung zugreifen bzw. andere sensible Funktionen ausführen kann oder ihr der Zugriff untersagt ist, selbst wenn sie in derselben aktiven Anwendung verwendet wird.  
  
 Die Common Language Runtime erzwingt die Codezugriffssicherheit. So kann sich der Benutzer beispielsweise darauf verlassen, dass durch eine in einer Webseite eingebettete ausführbare Datei zwar eine Animation auf dem Bildschirm wiedergegeben oder ein Musiktitel abgespielt werden, jedoch kein Zugriff auf persönliche Daten, das Dateisystem oder das Netzwerk erfolgen kann. Durch die Sicherheitsfunktionen der Common Language Runtime kann daher legitim über das Internet bereitgestellte Software mit einer besonders großen Funktionsvielfalt ausgestattet werden.  
  
 Durch die Implementierung des allgemeinen Typsystems (Common Type System; CTS), einer Infrastruktur mit strikter Typ- und Codeüberprüfung, erzwingt die Common Language Runtime außerdem die Coderobustheit. Durch das CTS wird sichergestellt, dass der gesamte verwaltete Code sich selbst beschreibt. Die verschieden Sprachcompiler von Microsoft und von Drittanbietern generieren verwalteten Code, der dem CTS entspricht. Dies bedeutet, dass verwalteter Code andere verwaltete Typen und Instanzen nutzen und gleichzeitig streng Typtreue und Typsicherheit erzwingen kann.  
  
 Außerdem werden durch eine verwaltete Laufzeitumgebung viele bekannte Softwareprobleme beseitigt. So verarbeitet die Common Language Runtime beispielsweise automatisch das Objektlayout, verwaltet Objektreferenzen und gibt diese wieder frei, wenn sie nicht mehr verwendet werden. Durch diese automatische Speicherverwaltung werden Speicherverluste und ungültige Speicherreferenzen, die beiden häufigsten Anwendungsfehler, beseitigt.  
  
 Die Produktivität der Entwickler wird außerdem durch die Common Language Runtime erhöht. So können Programmierer beispielsweise Anwendungen in der von ihnen bevorzugten Programmiersprache schreiben und trotzdem die Common Language Runtime, die Klassenbibliothek und die in anderen Sprachen von anderen Entwicklern geschriebenen Komponenten in vollem Umfang nutzen. Jeder Compileranbieter, der die Laufzeit zum Ziel hat, kann entsprechend vorgehen. Sprachcompiler, die .NET Framework zum Ziel haben, stellen die .NET Framework-Features bereits bestehendem Code in der jeweiligen Sprache zur Verfügung und erleichtern damit nicht unerheblich den Migrationsprozess für bestehende Anwendungen.  
  
 Die Common Language Runtime wurde zwar für die Software von morgen entwickelt, unterstützt aber auch aktuelle und ältere Anwendungen. Durch die Interoperabilität zwischen verwaltetem und nicht verwaltetem Code können Entwickler weiterhin benötigte COM-Komponenten und DLLs verwenden.  
  
 Bei der Common Language Runtime wurde auch die Leistungssteigerung berücksichtigt. Obwohl die Common Language Runtime viele Standardlaufzeitdienste bereitstellt, wird verwalteter Code nicht interpretiert. Durch die JIT-Kompilierung, ein Feature für das Just-in-Time-Kompilieren (JIT), kann der gesamte verwaltete Code in der systemeigenen Maschinensprache des jeweiligen Systems ausgeführt werden. Währenddessen verhindert die Speicherverwaltung die Speicherfragmentierung und erhöht zur weiteren Leistungssteigerung die lokalen Speicherverweise.  
  
 Schließlich kann die Common Language Runtime auch von hochleistungsfähigen, serverseitigen Anwendungen wie Microsoft SQL Server und Internetinformationsdiensten (IIS) gehostet werden. Diese Infrastruktur bietet die Möglichkeit, Geschäftslogik mit verwaltetem Code zu schreiben und gleichzeitig die überlegene Leistungsfähigkeit der branchenweit besten Organisationsserver zu nutzen, die Laufzeithosting unterstützen.  
  
<a id="net-framework-class-library" class="xliff"></a>

## .NET Framework-Klassenbibliothek  
 Die .NET Framework-Klassenbibliothek ist eine Auflistung wiederverwendbarer Typen, die eng in die Common Language Runtime integriert sind. Die Klassenbibliothek ist objektorientiert und stellt Typen bereit, von denen eigener verwalteter Code Funktionen ableiten kann. Dadurch können Sie die .NET Framework-Typen problemlos verwenden und sich schneller mit den neuen Features von .NET Framework vertraut machen. Außerdem können Sie Komponenten von Drittanbietern nahtlos in .NET Framework integrieren.  
  
 So wird beispielsweise durch die Auflistungsklassen in .NET Framework ein Schnittstellensatz implementiert, der zur Entwicklung eigener Auflistungsklassen verwendet werden kann, die sich nahtlos in die .NET Framework-Klassen einfügen.  
  
 Wie von einer objektorientierten Klassenbibliothek zu erwarten, lassen sich mit den .NET Framework-Typen viele gängige Programmieraufgaben erledigen, darunter auch Zeichenfolgenverwaltung, Datenerfassung, Datenbankkonnektivität und Dateizugriff. Neben diesen Typen für normale Aufgaben beinhaltet die Klassenbibliothek auch Typen, die verschiedene spezielle Entwicklungsszenarien unterstützen. So kann .NET Framework beispielsweise zur Entwicklung der folgenden Anwendungs- und Diensttypen verwendet werden:  
  
-   Konsolenanwendungen Siehe [Erstellen von Konsolenanwendungen](../../../docs/standard/building-console-apps.md).  
  
-   GUI-Anwendungen für Windows (Windows Forms) Siehe [Windows Forms](../../../docs/framework/winforms/index.md).  
  
-   Windows Presentation Foundation (WPF)-Anwendungen Siehe [Windows Presentation Foundation](../../../docs/framework/wpf/index.md).  
  
-   ASP.NET-Anwendungen Siehe [Webanwendungen mit ASP.NET](../../../docs/framework/develop-web-apps-with-aspnet.md).  
  
-   Windows-Dienste Siehe [Einführung in Windows-Dienstanwendungen](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md).  
  
-   Dienstorientierte Anwendungen mit Windows Communication Foundation (WCF) Siehe [Dienstorientierte Anwendungen mit WCF](../../../docs/framework/wcf/index.md).  
  
-   Workflowfähige Anwendungen mit Windows Workflow Foundation (WF) Siehe [Erstellen von Workflows in .NET Framework](http://msdn.microsoft.com/en-us/cbf3880f-dc7b-466d-b808-1109b1223f4a).  
  
 So bestehen beispielsweise die Klassen für Windows Forms aus einem umfangreichen Satz wiederverwendbarer Typen, die die Entwicklung für Windows-GUIs erheblich vereinfachen. Beim Schreiben einer ASP.NET Web Form-Anwendung können diese Web Forms-Klassen verwendet werden.  
  
<a id="see-also" class="xliff"></a>

## Siehe auch  
 [Systemanforderungen](../../../docs/framework/get-started/system-requirements.md)   
 [Installationshandbuch](../../../docs/framework/install/index.md)   
 [Entwicklungshandbuch](../../../docs/framework/development-guide.md)   
 [Tools](../../../docs/framework/tools/index.md)   
 [.NET Framework-Beispiele](http://msdn.microsoft.com/en-us/177055f8-4a1f-43e7-aee6-995c196079b1)   
 [.NET Framework-Klassenbibliothek](http://go.microsoft.com/fwlink/?LinkID=227195)
