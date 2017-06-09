---
title: "Modellieren und Zuordnen | Microsoft Docs"
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
  - "ESQL"
  - "jsharp"
ms.assetid: ec8a9515-3708-4cde-a688-4d8e6975f150
caps.latest.revision: 7
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 7
---
# Modellieren und Zuordnen
In [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] können Sie das konzeptionelle Modell, das Speichermodell und die Zuordnung zwischen beiden auf die Weise definieren, die der Anwendung am besten entspricht.  Mit den Entity Data Model\-Tools in [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] können Sie eine [EDMX\-Datei](http://msdn.microsoft.com/de-de/f4c8e7ce-1db6-417e-9759-15f8b55155d4) aus einer Datenbank oder einem grafischen Modell erstellen und die Datei dann aktualisieren, wenn sich entweder die Datenbank oder das Modell ändert.  
  
 Ab Entity Framework 4.1 können Sie ein Modell anhand der Code First\-Entwicklung auch programmgesteuert erstellen.  Es gibt zwei verschiedene Szenarien für die Code First\-Entwicklung.  In beiden Fällen definiert der Entwickler ein Modell, indem er .NET Framework\-Klassendefinitionen codiert und dann optional zusätzliche Zuordnungen oder Konfigurationen mithilfe von Datenanmerkungen oder der Fluent\-API angibt.  
  
 Weitere Informationen finden Sie unter [Erstellen und Zuordnen eines konzeptionellen Modells](http://go.microsoft.com/fwlink/?LinkId=235016).  
  
 Sie können auch den EDM\-Generator verwenden, der in [!INCLUDE[dnprdnshort](../../../../../includes/dnprdnshort-md.md)] enthalten ist.  EdmGen.exe generiert die CSDL\-, SSDL\- und MSL\-Dateien aus einer vorhandenen Datenquelle.  Sie können Modell\- und Zuordnungsinhalte auch manuell erstellen.  Weitere Informationen finden Sie unter [EDM\-Generator \(EdmGen.exe\)](../../../../../docs/framework/data/adonet/ef/edm-generator-edmgen-exe.md).