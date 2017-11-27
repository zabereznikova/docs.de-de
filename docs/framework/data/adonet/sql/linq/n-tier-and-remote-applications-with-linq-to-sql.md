---
title: N-schichtige Anwendungen und Remoteanwendungen mit LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 854a1cdd-53cb-45f5-83ca-63962a9b3598
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f44b6da8ecc8d036a9550856f71b2981770e9478
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="n-tier-and-remote-applications-with-linq-to-sql"></a>N-schichtige Anwendungen und Remoteanwendungen mit LINQ to SQL
Sie können N-Tier-Anwendungen bzw. Anwendungen mit mehreren Ebenen erstellen, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwenden. In der Regel die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Datenkontext, Entitätsklassen und Abfrageerstellungslogik befinden sich auf der mittleren Ebene als der Datenzugriffsebene (DAL). Geschäftslogik und nicht dauerhafte Daten können vollständig in partiellen Klassen und Methoden von Entitäten und Datenkontext implementiert werden, oder sie können in separaten Klassen implementiert werden.  
  
 Die Client- oder Präsentationsebene ruft Methoden für die Remoteschnittstelle der mittleren Ebene auf, und die Datenzugriffsebene auf dieser Ebene führt Abfragen oder gespeicherte Prozeduren aus, die <xref:System.Data.Linq.DataContext>-Methoden zugeordnet sind. Die mittlere Ebene gibt die Daten normalerweise als XML-Darstellungen von Entitäten oder Proxyobjekten an Clients zurück.  
  
 Auf der mittleren Ebene werden Entitäten vom Datenkontext erstellt, der deren Zustand nachverfolgt und das verzögerte Laden von Änderungen aus der Datenbank und das Übergeben von Änderungen an die Datenbank verwaltet. Diese Entitäten werden an den `DataContext` "angefügt". Nachdem die Entitäten jedoch mittels Serialisierung an eine andere Ebene gesendet wurden, werden sie getrennt, was dazu führt, dass ihr Zustand nicht mehr vom `DataContext` nachverfolgt wird. Entitäten, die vom Client zum Update zurückgesendet werden, müssen erneut an den Datenkontext angefügt werden, bevor die Änderungen von [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] an die Datenbank übergeben werden können. Der Client ist dafür zuständig, ursprüngliche Werte und/oder Timestamps wieder für die mittlere Ebene bereitzustellen, wenn diese für Überprüfungen auf vollständige Parallelität benötigt werden.  
  
 In ASP.NET-Anwendungen wird diese Komplexität größtenteils von <xref:System.Web.UI.WebControls.LinqDataSource> verwaltet. Weitere Informationen finden Sie unter [NIB: Übersicht über das LinqDataSource-Steuerelement](http://msdn.microsoft.com/en-us/104cfc3f-7385-47d3-8a51-830dfa791136).  
  
## <a name="additional-resources"></a>Zusätzliche Ressourcen  
 Weitere Informationen zur Implementierung von N-Tier-Anwendungen, die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] verwenden, finden Sie unter den folgenden Themen:  
  
-   [LINQ to SQL-N-Schicht mit ASP.NET](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-aspnet.md)  
  
-   [LINQ to SQL-N-Tier mit Webdiensten](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-n-tier-with-web-services.md)  
  
-   [LINQ to SQL mit eng verknüpften Client-Server-Anwendungen](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-with-tightly-coupled-client-server-applications.md)  
  
-   [Implementieren von N-Schichtiger Geschäftslogik](../../../../../../docs/framework/data/adonet/sql/linq/implementing-business-logic-linq-to-sql.md)  
  
-   [Datenabruf und CUD-Operationen in N-Tier-Anwendungen (LINQ to SQL)](../../../../../../docs/framework/data/adonet/sql/linq/data-retrieval-and-cud-operations-in-n-tier-applications.md)  
  
 Weitere Informationen zu n-Tier-Anwendungen, die ADO.NET-Datasets verwenden, finden Sie unter [arbeiten mit Datasets in n-Tier-Anwendungen](http://msdn.microsoft.com/library/f6ae2ee0-ea5f-4a79-8f4b-e21c115afb20).  
  
## <a name="see-also"></a>Siehe auch  
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
