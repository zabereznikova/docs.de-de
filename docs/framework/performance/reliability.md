---
title: "Reliability | Microsoft Docs"
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
  - "SQL Server [.NET Framework]"
  - "managed code, reliability"
  - "reliability [.NET Framework]"
  - "writing reliable code"
  - "code, reliability"
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
caps.latest.revision: 9
author: "mairaw"
ms.author: "mairaw"
manager: "wpickett"
caps.handback.revision: 9
---
# Reliability
Code, der in Serverumgebungen wie SQL Server ausführt wird, muss unbedingt vor asynchronen Ausnahmen geschützt werden.  Die in diesem Thema erörterte Zuverlässigkeit bezieht sich nicht alleine auf SQL Server, sondern gilt allgemein für das Schreiben von zuverlässigem Code für jeden Host, der in einer Umgebung mit .NET Framework, Version 2.0, ausgeführt wird.  SQL Server ist jedoch der erste Dienst, der die neuen Zuverlässigkeitsfeatures der Version 2.0 ausgiebig nutzt, und wird daher als Beispiel verwendet.  
  
 Code, der in SQL Server ausgeführt wird, unterliegt strengeren Zuverlässigkeitsrichtlinien als in anderen Serverumgebungen.  Dies ist aufgrund SQL Servers stabilen Vorgangs am Rand des Ressourcenverbrauchs. Ausnahmen sind <xref:System.OutOfMemoryException> und <xref:System.Threading.ThreadAbortException> nicht in einer SQL Server\-Umgebung immer wieder auf.  Diese Richtlinien sind weniger auf Zuverlässigkeit ausgerichtet, sondern sollen dafür sorgen, dass vollständig vertrauenswürdiger, verwalteter Code bei Wiederverwendung auf <xref:System.AppDomain>\-Ebene keinen Absturz verursacht. Dies ist das wichtigste Verfahren, mit dem der Server die Konsistenz und Verfügbarkeit aufrecht erhält.  
  
## In diesem Abschnitt  
 [SQL Server Programming and Host Protection Attributes](../../../docs/framework/performance/sql-server-programming-and-host-protection-attributes.md)  
 Beschreibt, wie die Ausführung von verwaltetem Code von SQL Server mithilfe des <xref:System.Security.Permissions.HostProtectionAttribute>\-Attribut eingeschränkt wird.  
  
 [Reliability Best Practices](../../../docs/framework/performance/reliability-best-practices.md)  
 Gibt Richtlinien zum Schreiben von Code an, die die Anforderungen hinsichtlich der Zuverlässigkeit erfüllt.  
  
 [Constrained Execution Regions](../../../docs/framework/performance/constrained-execution-regions.md)  
 Beschreibt die Funktion und das Verhalten eingeschränkter Ausführungsbereiche \(Constrained Execution Region, CER\).  
  
## Referenz  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>