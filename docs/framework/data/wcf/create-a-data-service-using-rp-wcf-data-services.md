---
title: 'Gewusst wie: Erstellen eines Datendiensts mit dem Reflektionsanbieter (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 7315c6d8-f452-4fb2-a0c1-76ab0593c146
ms.openlocfilehash: 44ba47deaf803f8a911b5a76d7e93f09b47e677a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-data-service-using-the-reflection-provider-wcf-data-services"></a>Gewusst wie: Erstellen eines Datendiensts mit dem Reflektionsanbieter (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es Ihnen, ein auf beliebigen Klassen basierendes Datenmodell zu definieren, solange die Klassen als Objekte verfügbar gemacht werden, die die <xref:System.Linq.IQueryable%601>-Schnittstelle implementieren. Weitere Informationen finden Sie unter [Datendiensteanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Datenmodell definiert, das `Orders` und `Items` enthält. Die Entitätscontainerklasse `OrderItemData` enthält zwei öffentliche Methoden, die <xref:System.Linq.IQueryable%601>-Schnittstellen zurückgeben. Diese Schnittstellen sind die Entitätenmengen der Entitätstypen `Orders` und `Items`. Eine `Order` kann mehrere `Items` enthalten, daher verfügt der `Orders`-Entitätstyp über eine `Items`-Navigationseigenschaft, die eine Auflistung von `Items`-Objekten zurückgibt. Die `OrderItemData`-Entitätscontainerklasse ist der generische Typ der <xref:System.Data.Services.DataService%601>-Klasse, von der der `OrderItems`-Datendienst abgeleitet ist.  
  
> [!NOTE]
>  Da in diesem Beispiel ein Datenanbieter im Arbeitsspeicher veranschaulicht wird und Änderungen außerhalb der aktuellen Objektinstanzen nicht beibehalten werden, leitet sich aus der Implementierung der <xref:System.Data.Services.IUpdatable>-Schnittstelle kein Vorteil ab. Ein Beispiel für die implementiert die <xref:System.Data.Services.IUpdatable> -Schnittstelle, finden Sie unter [Vorgehensweise: Erstellen eines Daten mithilfe einer LINQ to SQL-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md).  
  
 [!code-csharp[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria reflection provider/cs/orderitems.svc.cs#customiqueryable)]
 [!code-vb[Astoria Reflection Provider#CustomIQueryable](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria reflection provider/vb/orderitems.svc.vb#customiqueryable)]  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Erstellen eines Datendiensts mit einer LINQ to SQL-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-linq-to-sql-wcf.md)  
 [Datendienstanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Vorgehensweise: Erstellen eines Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)
