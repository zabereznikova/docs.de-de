---
title: "Erste Schritte mit .NET Framework | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework, Erste Schritte"
  - "Erste Schritte [.NET Framework]"
ms.assetid: c693fd34-88fe-4d90-b332-19eeadf3b7e7
caps.latest.revision: 35
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 29
---
# Erste Schritte mit .NET Framework
.NET Framework ist eine Ausführungsumgebung für die Laufzeit, die Anwendungen für .NET Framework verwaltet. Sie besteht aus der Common Language Runtime, die Speicherverwaltung und andere Systemdienste bereitstellt, und einer umfangreichen Klassenbibliothek, die Programmierern stabilen, zuverlässigen Code für alle wesentlichen Bereiche der Anwendungsentwicklung zur Verfügung stellt.  
  
<a name="Introducing"></a>   
## Was ist .NET Framework?  
 .NET Framework ist eine verwaltete Ausführungsumgebung, die eine Vielzahl von Diensten für die darin ausgeführten Anwendungen bereitstellt. Sie besteht aus zwei Hauptkomponenten: der CLR \(Common Language Runtime\), die als Ausführungsmodul die ausgeführten Anwendungen behandelt, und der .NET Framework\-Klassenbibliothek, einer Bibliothek mit getestetem, wiederverwendbarem Code, den Entwickler in ihren eigenen Anwendungen aufrufen können. Zu den Diensten, die .NET Framework für ausgeführte Anwendungen bereitstellt, gehören:  
  
-   Speicherverwaltung. Bei vielen Programmiersprachen sind die Programmierer für das Zuordnen und Freigeben von Arbeitsspeicher und das Behandeln der Objektlebensdauer zuständig. In .NET Framework\-Anwendungen stellt die CLR diese Dienste für die Anwendung zur Verfügung.  
  
-   Ein allgemeines Typsystem. In herkömmlichen Programmiersprachen werden grundlegende Typen durch den Compiler definiert. Dies erschwert die sprachübergreifende Interoperabilität. In .NET Framework werden grundlegende Typen durch das .NET Framework\-Typsystem definiert und werden von allen von .NET Framework unterstützten Sprachen verwendet.  
  
-   Eine umfangreiche Klassenbibliothek. Statt große Mengen von Code schreiben zu müssen, um allgemeine Programmiervorgänge auf niedriger Ebene zu behandeln, können Programmierer in der .NET Framework\-Klassenbibliothek auf eine sofort verfügbare Bibliothek von Typen und deren Member zugreifen.  
  
-   Entwicklungsframeworks und \-Technologien. .NET Framework enthält Bibliotheken für bestimmte Bereiche der Anwendungsentwicklung, beispielsweise ASP.NET für Webanwendungen, ADO.NET für den Datenzugriff und Windows Communication Foundation für dienstorientierte Anwendungen.  
  
-   Sprachinteroperabilität. Sprachcompiler für .NET Framework geben einen temporären Code namens CIL \(Common Intermediate Language\) aus, der zur Laufzeit wiederum von der Common Language Runtime kompiliert wird. Mit dieser Funktion sind die Routinen, die in einer Sprache geschrieben werden, für andere Sprachen verfügbar, und Programmierer können sich auf das Erstellen von Anwendungen in ihren bevorzugten Sprachen konzentrieren.  
  
-   Versionskompatibilität. Mit wenigen Ausnahmen können Anwendungen, die mit einer bestimmten Version von .NET Framework entwickelt wurden, ohne Änderungen unter einer höheren Version ausgeführt werden.  
  
-   Parallele Ausführung. .NET Framework unterstützt das Lösen von Versionskonflikten, da mehrere Versionen der Common Language Runtime gleichzeitig auf dem gleichen Computer vorhanden sein können. Dies bedeutet, dass mehrere Versionen von Anwendungen gleichzeitig vorhanden sein können, und dass eine Anwendung unter der Version von .NET Framework ausgeführt werden kann, mit der sie erstellt wurde.  
  
-   Festlegung von Zielversionen. Die portable Klassenbibliothek von .NET Framework ermöglicht es Entwicklern, Assemblys zu erstellen, die auf mehreren .NET Framework\-Plattformen verwendet werden können, beispielsweise Windows 7, Windows 8, Windows 8.1, Windows 10, Windows Phone und Xbox 360.  
  
<a name="ForUsers"></a>   
## .NET Framework für Benutzer  
 Wenn Sie .NET Framework\-Anwendungen nicht entwickeln, sondern sie nur verwenden, müssen Sie sich nicht mit .NET Framework oder der Arbeitsweise von .NET Framework auskennen. Der größte Teil von .NET Framework ist für Benutzer vollständig transparent.  
  
 Wenn Sie Windows als Betriebssystem verwenden, ist .NET Framework möglicherweise bereits auf dem Computer installiert. Wenn Sie eine Anwendung installieren, die .NET Framework erfordert, installiert das Setupprogramm der Anwendung möglicherweise eine bestimmte Version von .NET Framework auf dem Computer. In einigen Fällen wird möglicherweise ein Dialogfeld angezeigt, in dem Sie aufgefordert werden, .NET Framework zu installieren. Wenn Sie gerade versucht haben, eine Anwendung auszuführen, und dieses Dialogfeld angezeigt wird, können Sie, sofern Sie über Internetzugang verfügen, zu einer Webseite wechseln, über die Sie die fehlende .NET Framework\-Version installieren können.  
  
 Im Allgemeinen sollten Sie keine der .NET Framework\-Versionen deinstallieren, die auf Ihrem Computer installiert sind. Hierfür gibt es zwei Gründe:  
  
-   Wenn eine Anwendung, die Sie verwenden, von einer bestimmten Version von .NET Framework abhängt, können Fehler in dieser Anwendung entstehen, wenn diese Version entfernt wird.  
  
-   Einige Versionen von .NET Framework sind direkte Updates früherer Versionen. So ist z. B. [!INCLUDE[net_v35_short](../../../includes/net-v35-short-md.md)] ein direktes Update zu Version 2.0 und .NET Framework 4.6 ein direktes Update zu Version 4, 4.5, 4.5.1 und 4.5.2. Weitere Informationen finden Sie unter [.NET Framework\-Versionen und \-Abhängigkeiten](../../../docs/framework/migration-guide/versions-and-dependencies.md).  
  
 Wenn Sie das .NET Framework entfernen möchten, verwenden Sie immer **Programme und Funktionen** in der Systemsteuerung, um es zu deinstallieren. Entfernen Sie .NET Framework\-Versionen nie manuell.  
  
 Beachten Sie, dass mehrere Versionen von .NET Framework gleichzeitig auf einem Computer vorhanden sein können. Dies bedeutet, dass Sie ältere Versionen nicht deinstallieren müssen, um eine höhere Version zu installieren.  
  
<a name="ForDevelopers"></a>   
## .NET Framework für Entwickler  
 Wenn Sie ein Entwickler sind, können Sie Anwendungen in jeder beliebigen Programmiersprache erstellen, die .NET Framework unterstützt. Da .NET Framework Sprachenunabhängigkeit und Sprachinteroperabilität bietet, ist die Interaktion mit allen anderen .NET Framework\-Anwendungen und \-Komponenten möglich, unabhängig davon, in welcher Sprache sie entwickelt wurden.  
  
 Gehen Sie beim Entwickeln von .NET Framework\-Anwendungen oder Komponenten folgendermaßen vor:  
  
1.  Installieren Sie die für die Anwendung erforderliche Version von .NET Framework. Die neueste Produktionsversion ist [.NET Framework 4.6.1](http://go.microsoft.com/fwlink/?LinkId=671729). Es gibt zusätzliche .NET Framework\-Pakete, die out\-of\-band veröffentlicht werden. Informationen zu diesen Paketen finden Sie unter [.NET Framework und Out\-of\-Band\-Versionen](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md).  
  
2.  Wählen Sie die .NET Framework\-Sprachen aus, die Sie bei der Entwicklung von Anwendungen verwenden möchten. Es stehen eine Anzahl von Sprachen zur Verfügung, darunter Visual Basic, C\#, Visual F\# und C\+\+ von Microsoft \(Programmiersprachen, die Ihnen ermöglichen, Anwendungen für .NET Framework zu entwickeln, erfüllen die [CLI\-Spezifikation](http://go.microsoft.com/fwlink/?LinkId=199862).\) Eine Liste der verfügbaren Programmiersprachen finden Sie unter [Visual Studio\-Sprachen](http://go.microsoft.com/fwlink/?LinkId=199863).  
  
3.  Wählen Sie die Entwicklungsumgebung aus, die Sie zum Erstellen der Anwendungen verwenden möchten und welche die von Ihnen gewählten Programmiersprachen unterstützt, und installieren Sie sie. Die integrierte Microsoft\-Entwicklungsumgebung für .NET Framework\-Anwendungen ist [Visual Studio](http://go.microsoft.com/fwlink/?LinkId=325532). Es stehen verschiedene verkäufliche und kostenlose Editionen zur Verfügung.  
  
 Weitere Informationen zum Entwickeln von Apps, die auf .NET Framework ausgerichtet sind, finden Sie unter [Entwicklungshandbuch](../../../docs/framework/development-guide.md).  
  
## Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|------------------|  
|[Übersicht](../../../docs/framework/get-started/overview.md)|Enthält ausführliche Informationen für Entwickler, die Anwendungen für .NET Framework erstellen.|  
|[.NET Framework und Out\-of\-Band\-Versionen](../../../docs/framework/get-started/the-net-framework-and-out-of-band-releases.md)|Beschreibt die Out\-of\-Band\-Versionen von .NET Framework und ihre Verwendung in der App.|  
|[Systemanforderungen](../../../docs/framework/get-started/system-requirements.md)|Führt die Hardware\- und Softwareanforderungen für das Ausführen von .NET Framework auf.|  
|[.NET Core und Open\-Source](../../../docs/framework/get-started/net-core-and-open-source.md)|Beschreibt, was .NET Core in Bezug auf .NET Framework ist und wie Sie auf die Open\-Source\-Projekte von .NET Core zugreifen können.|  
|[Installationshandbuch](../../../docs/framework/install/guide-for-developers.md)|Stellt Informationen zum Installieren von .NET Framework bereit.|  
  
## Siehe auch  
 [.NET Framework 4.6 und 4.5](../Topic/.NET%20Framework%204.6%20and%204.5.md)   
 [Neues](../../../docs/framework/whats-new/index.md)   
 [.NET Framework\-Klassenbibliothek](http://go.microsoft.com/fwlink/?LinkId=227195)   
 [Entwicklungshandbuch](../../../docs/framework/development-guide.md)