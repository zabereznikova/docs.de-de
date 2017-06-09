---
title: "Sicherheit bei der CLR-Integration in SQL Server | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Sicherheit bei der CLR-Integration in SQL Server
Die CLR \(Common Language Runtime\)\-Komponente von .NET Framework ist in Microsoft SQL Server integriert.  Dank CLR\-Integration können Sie gespeicherte Prozeduren, Trigger, benutzerdefinierte Datentypen, Funktionen und Aggregate sowie Tabellenwertfunktionen mit kontinuierlichem Datenstream \(Streaming Table\-Valued Function, STVF\) in jeder beliebigen .NET Framework\-Sprache \(wie Microsoft Visual Basic .NET oder Microsoft Visual C\#\) schreiben.  
  
 Die CLR unterstützt das Sicherheitsmodell der Codezugriffssicherheit \(Code Access Security, CAS\) für verwalteten Code.  In diesem Modell werden Assemblys Berechtigungen auf der Basis des Codes in Metadaten gewährt.  SQL Server sorgt für eine enge Zusammenarbeit zwischen dem SQL Server\-Modell der benutzerbasierten Sicherheit und dem CLR\-Modell der Codezugriffssicherheit.  
  
## Externe Ressourcen  
 Weitere Informationen zur CLR\-Integration mit SQL Server finden Sie in den folgenden Ressourcen.  
  
|Ressource|Beschreibung|  
|---------------|------------------|  
|[Code Access Security](http://msdn.microsoft.com/de-de/23a20143-241d-4fe5-9d9f-3933fd594c03)|Enthält Themen, in denen die CAS in .NET Framework beschrieben wird.|  
|[Sicherheit bei der CLR\-Integration](http://go.microsoft.com/fwlink/?LinkId=59998)|Beschreibt das Sicherheitsmodell für verwalteten Code, der innerhalb von SQL Server ausgeführt wird.|  
  
## Siehe auch  
 [Sichern von ADO.NET\-Anwendungen](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)   
 [Anwendungssicherheitsszenarios in SQL Server](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)   
 [CLR\-Integration in SQL Server](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)