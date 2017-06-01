---
title: "SQL Server Compact und LINQ to SQL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 59022359-a5a2-4c42-9a6a-5c0259c3ad17
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# SQL Server Compact und LINQ to SQL
SQL Server Compact ist die Standarddatenbank, die mit Visual Studio installiert wird. Weitere Informationen finden Sie unter [PAVE OVER Using SQL Server Compact \(Visual Studio\)](http://msdn.microsoft.com/de-de/13320dd1-94e5-4077-bf76-8df253695ccc).  
  
 Dieses Thema erläutert die Hauptunterschiede hinsichtlich der Verwendung, Konfiguration, Funktionsgruppen und des Umfangs der [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Unterstützung.  
  
## Eigenschaften von SQL Server Compact im Verhältnis zu LINQ to SQL  
 SQL Server Compact wird standardmäßig für alle [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)]\-Editionen installiert und steht daher auf dem Entwicklungscomputer zur Verwendung mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] zur Verfügung.  Die Bereitstellung einer Anwendung, die SQL Server Compact und [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwendet, unterscheidet sich jedoch von einer Bereitstellung, die eine [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)]\-Anwendung verwendet.  SQL Server Compact ist nicht Bestandteil von .NET Framework und muss daher in die Anwendung integriert werden oder separat von der Microsoft\-Website heruntergeladen werden.  
  
 Beachten Sie die folgenden Eigenschaften:  
  
-   SQL Server Compact wird als DLL verpackt, die für Datenbankdateien \(Erweiterung .sdf\) direkt verwendet werden kann.  
  
-   SQL Server Compact wird in demselben Prozess wie die Clientanwendung ausgeführt.  Die Effizienz der Kommunikation mit SQL Server Compact kann deshalb bedeutend höher als diejenige der Kommunikation mit [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)] sein.  Andererseits erfordert SQL Server Compact Interoperabilität zwischen verwaltetem und nicht verwaltetem Code \(was mit den entsprechenden Kosten verbunden ist\).  
  
-   Die SQL Server Compact\-DLL weist eine geringe Größe auf.  Diese Funktion verringert die Gesamtgröße der Anwendung.  
  
-   Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Laufzeit und das SQLMetal\-Befehlszeilentool unterstützen SQL Server Compact.  
  
-   Der [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] bietet keine Unterstützung für SQL Server Compact.  
  
## Funktionsgruppe  
 Die SQL Server Compact\-Funktionsgruppe ist erheblich einfacher als die Funktionsgruppe von [!INCLUDE[ssNoVersion](../../../../../../includes/ssnoversion-md.md)]. Dies kann [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Anwendungen wie folgt beeinflussen:  
  
-   SQL Server Compact unterstützt keine gespeicherten Prozeduren oder Ansichten.  
  
-   SQL Server Compact unterstützt nur eine Teilmenge von Datentypen und SQL\-Funktionen.  
  
-   SQL Server Compact unterstützt nur eine Teilmenge von SQL\-Konstrukten.  
  
-   SQL Server Compact bietet nur einen minimalen Optimierer.  Es ist möglich, dass es bei einigen Abfragen zu Zeitüberschreitungen kommt.  
  
-   SQL Server Compact unterstützt keine teilweise Vertrauenswürdigkeit.  
  
## Siehe auch  
 [Verweis](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)