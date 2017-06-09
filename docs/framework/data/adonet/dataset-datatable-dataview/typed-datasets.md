---
title: "Typisierte &#39;DataSets&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 033d2548-cf24-4c05-8179-67d8b009c048
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Typisierte &#39;DataSets&#39;
Neben dem späten Bindungszugriff auf Werte mithilfe von schwach typisierten Variablen bietet das <xref:System.Data.DataSet> über eine stark typisierte Metapher Zugriff auf Daten.  Auf Tabellen und Spalten, die Teil des **DataSet** sind, kann mithilfe von benutzerfreundlichen Namen und stark typisierten Variablen zugegriffen werden.  
  
 Ein typisiertes **DataSet** ist eine Klasse, die von einem **DataSet** abgeleitet ist.  Damit erbt sie alle Methoden, Ereignisse und Eigenschaften eines **DataSet**.  Darüber hinaus stellt ein typisiertes **DataSet** stark typisierte Methoden, Ereignisse und Eigenschaften bereit.  Das heißt, dass Sie auf Tabellen und Spalten anhand ihres Namens zugreifen können und keine auflistungsbasierten Methoden verwenden müssen.  Neben der verbesserten Lesbarkeit des Codes ermöglicht ein typisiertes **DataSet** auch, dass der Code\-Editor von Visual Studio .NET Zeilen bei der Eingabe automatisch vervollständigt.  
  
 Außerdem bietet ein stark typisiertes **DataSet** zur Kompilierzeit auch Zugriff auf Werte, die den korrekten Typ darstellen.  Mit einem stark typisierten **DataSet** werden Typenkonfliktfehler zur Kompilierzeit und nicht zur Laufzeit abgefangen.  
  
## In diesem Abschnitt  
 [Erstellen stark typisierter 'DataSets'](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/generating-strongly-typed-datasets.md)  
 Beschreibt das Erstellen und Verwenden eines stark typisierten **DataSet**.  
  
 [Hinzufügen von Anmerkungen zu typisierten DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/annotating-typed-datasets.md)  
 Beschreibt, wie das XSD\-Schema \(XML Schema Definition Language\) zum Erstellen eines stark typisierten **DataSet** mit Anmerkungen versehen wird, um **DataSet**\-Elementen lange Namen zuzuweisen, ohne dass das zugrunde liegende Schema geändert wird.  
  
## Siehe auch  
 [DataSets, DataTables und DataViews](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)