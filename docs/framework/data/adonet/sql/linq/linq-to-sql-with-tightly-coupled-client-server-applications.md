---
title: "LINQ to SQL mit eng verknüpften Client-Server-Anwendungen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e083d805-dcf6-459d-b9af-9ef0563f2dd7
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 6ff0ee9019f8c61ad2fc18c5d22240abb2dc6b9b
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="linq-to-sql-with-tightly-coupled-client-server-applications"></a>LINQ to SQL mit eng verknüpften Client-Server-Anwendungen
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]kann auf der mittleren Ebene mit eng verknüpften intelligenten Clients auf der Darstellungsebene verwendet werden. Szenarien mit schreibgeschütztem Datenzugriff, ohne Überprüfungen auf vollständige Parallelität oder ohne vollständige Parallelität mit Timestamps sind nicht wesentlich komplexer als Szenarien ohne Remotezugriff. Wenn für eine Datenbank jedoch eine Überprüfung auf vollständige Parallelität mit ursprünglichen Werten erforderlich ist, bietet [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] nicht die erforderliche Unterstützung für Roundtrips durch die in DataSets enthaltenen Daten. Eine mittlere [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Ebene kann Daten jedoch mit Clients auf beliebigen Plattformen austauschen.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]in [!INCLUDE[vs_orcas_long](../../../../../../includes/vs-orcas-long-md.md)] stellt keine Infrastruktur zum Nachverfolgen des nach der Serialisierung an einen Client. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]aktiviert dienstorientierte Architekturen, in denen Interaktionen zwischen den Daten und den Darstellungsschichten wenig und relativ atomare sind, aber wird nicht Trips von ursprünglichen Werten. Wenn Sie einen eng gekoppelten intelligenten Client mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] einsetzen möchten und eine Datenbank vollständige Parallelität mit ursprünglichen Werten verwendet, müssen Sie deshalb einen eigenen Mechanismus implementieren, um Änderungen zwischen Präsentationsebene und mittlerer Ebene zu kommunizieren. Es liegt im Ermessen des System-Designers, ob dieser geringe zusätzliche Arbeitsaufwand die Vorteile aufwiegt, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] auf der mittleren Ebene bereitstellt. Wenn die Datenbank über Timestamps verfügt, besteht andererseits keine Notwendigkeit für eine benutzerdefinierte Logik zur Änderungsverfolgung.  
  
## <a name="see-also"></a>Siehe auch  
 [N-schichtige Anwendungen und Remoteanwendungen mit LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql.md)  
 [N-Schicht-LINQ to SQL mit Webdiensten](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
 [Arbeiten mit Datasets in N-Tier-Anwendungen](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20)
