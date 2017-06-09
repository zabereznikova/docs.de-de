---
title: "Namespaces (Entity SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Namespaces (Entity SQL)
[!INCLUDE[esql](../../../../../../includes/esql-md.md)] vermeidet Namenskonflikte bei globalen Bezeichnern wie Typnamen, Entitätenmengen, Funktionen usw. mithilfe von Namespaces.  Die Unterstützung von Namespaces in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] entspricht der Unterstützung von Namespaces in [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellt, wie in folgendem Beispiel veranschaulicht, zwei Arten der **USING**\-Klausel zur Verfügung: qualifizierte Namespaces \(wobei ein kürzerer Alias für den Namespace bereitgestellt wird\) und unqualifizierte Namespaces:  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## Regeln zur Namensauflösung  
 Wenn ein Bezeichner nicht in den lokalen Bereichen aufgelöst werden kann, sucht [!INCLUDE[esql](../../../../../../includes/esql-md.md)] den Namen in den globalen Bereichen \(den Namespaces\).  [!INCLUDE[esql](../../../../../../includes/esql-md.md)] vergleicht zunächst den Bezeichner \(Präfix\) mit einem der qualifizierten Namespaces.  Wenn eine Übereinstimmung festgestellt wird, versucht [!INCLUDE[esql](../../../../../../includes/esql-md.md)] den Rest des Bezeichners im angegebenen Namespace aufzulösen.  Wenn keine Übereinstimmung festgestellt werden kann, wird eine Ausnahme ausgelöst.  
  
 Anschließend sucht [!INCLUDE[esql](../../../../../../includes/esql-md.md)] nach allen unqualifizierten Namespaces \(die im Prolog angegeben sind\) für den Bezeichner.  Wird der Bezeichner in genau einem Namespace gefunden, wird dieser Bereich zurückgegeben.  Wenn dem Bezeichner mehrere Namespaces entsprechen, wird eine Ausnahme ausgelöst.  Wenn für den Bezeichner kein Namespace gefunden werden kann, übergibt [!INCLUDE[esql](../../../../../../includes/esql-md.md)] den Namen an den nächsten äußeren Bereich \(das <xref:System.Data.Common.DbCommand>\- oder <xref:System.Data.Common.DbConnection>\-Objekt\), wie in folgendem Beispiel dargestellt:  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## Unterschiede zum .NET Framework  
 In [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] können teilweise qualifizierte Namespaces verwendet werden.  Mit [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist dies nicht zulässig.  
  
## Verwendung von ADO.NET  
 Abfragen werden mit ADO.NET\-<xref:System.Data.Common.DbCommand>\-Objekten ausgedrückt.  <xref:System.Data.Common.DbCommand>\-Objekte werden über <xref:System.Data.Common.DbConnection>\-Objekte erstellt.  Namespaces können außerdem als Teil der <xref:System.Data.Common.DbCommand>\- und <xref:System.Data.Common.DbConnection>\-Objekte spezifiziert werden.  Wenn [!INCLUDE[esql](../../../../../../includes/esql-md.md)] einen Bezeichner nicht in der Abfrage selbst auflösen kann, werden die externen Namespaces \(nach ähnlichen Regeln\) untersucht.  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)