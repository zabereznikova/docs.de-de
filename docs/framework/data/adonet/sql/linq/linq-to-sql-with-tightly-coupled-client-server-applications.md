---
title: "LINQ to SQL mit eng verkn&#252;pften Client-Server-Anwendungen | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e083d805-dcf6-459d-b9af-9ef0563f2dd7
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# LINQ to SQL mit eng verkn&#252;pften Client-Server-Anwendungen
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] kann auf der mittleren Ebene zusammen mit eng verknüpften intelligenten Clients auf der Darstellungsebene verwendet werden.  Szenarien mit schreibgeschütztem Datenzugriff, ohne Überprüfungen auf vollständige Parallelität oder ohne vollständige Parallelität mit Timestamps sind nicht wesentlich komplexer als Szenarien ohne Remotezugriff.  Wenn für eine Datenbank jedoch eine Überprüfung auf vollständige Parallelität mit ursprünglichen Werten erforderlich ist, bietet [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht die erforderliche Unterstützung für Roundtrips durch die in DataSets enthaltenen Daten.  Eine mittlere [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Ebene kann Daten jedoch mit Clients auf beliebigen Plattformen austauschen.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] in [!INCLUDE[vs_orcas_long](../../../../../../includes/vs-orcas-long-md.md)] stellt keine Infrastruktur zum Nachverfolgen des Entitätszustands bereit, nachdem die Serialisierung in einen Client erfolgte.  [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] aktiviert dienstorientierte Architekturen, in denen es nur wenig und relativ atomare Interaktionen zwischen den Daten und den Darstellungsschichten gibt. Es werden jedoch keine Round\-Trips von ursprünglichen Werten ausgeführt.  Wenn Sie einen eng gekoppelten intelligenten Client mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] einsetzen möchten und eine Datenbank vollständige Parallelität mit ursprünglichen Werten verwendet, müssen Sie deshalb einen eigenen Mechanismus implementieren, um Änderungen zwischen Präsentationsebene und mittlerer Ebene zu kommunizieren.  Es liegt im Ermessen des System\-Designers, ob dieser geringe zusätzliche Arbeitsaufwand die Vorteile aufwiegt, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf der mittleren Ebene bereitstellt.  Wenn die Datenbank über Timestamps verfügt, besteht andererseits keine Notwendigkeit für eine benutzerdefinierte Logik zur Änderungsverfolgung.  
  
## Siehe auch  
 [N\-Tier\- und Remoteanwendungen mit LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)   
 [LINQ to SQL\-N\-Tier mit Webdiensten](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)   
 [Arbeiten mit Datasets in N\-Tier\-Anwendungen](../Topic/Work%20with%20datasets%20in%20n-tier%20applications.md)