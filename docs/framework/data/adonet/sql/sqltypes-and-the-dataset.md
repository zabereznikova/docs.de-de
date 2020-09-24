---
title: "\"SqlTypes\" und \"DataSet\""
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9172c20a-9876-4b3b-9c97-1963c02b1993
ms.openlocfilehash: 04f95cd7d3f6e52f644f23dd8a32c77d56a5ddda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147507"
---
# <a name="sqltypes-and-the-dataset"></a>"SqlTypes" und "DataSet"

Mit ADO.NET 2.0 wurde durch den Namespace <xref:System.Data.SqlTypes> erweiterte Typunterstützung für das `DataSet` eingeführt. Die Typen in <xref:System.Data.SqlTypes> stellen Datentypen mit derselben Semantik und Präzision wie die Datentypen in einer SQL Server-Datenbank bereit. Für jeden Datentyp in <xref:System.Data.SqlTypes> gibt es einen äquivalenten Datentyp in SQL Server mit derselben zugrunde liegenden Datendarstellung.  
  
 Wenn Sie <xref:System.Data.SqlTypes> direkt in einem <xref:System.Data.DataSet> verwenden, profitieren Sie von einigen Vorteilen bei der Arbeit mit SQL Server-Datentypen. <xref:System.Data.SqlTypes> unterstützt die gleiche Semantik wie native SQL Server-Datentypen. Wenn Sie einen <xref:System.Data.SqlTypes>-Namespace in der Definition einer <xref:System.Data.DataColumn>-Klasse angeben, ist dies präziser als die Konvertierung von dezimalen oder numerische Datentypen in einen CLR-Datentyp (Common Language Runtime).  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird ein <xref:System.Data.DataTable>-Objekt erstellt. Dabei werden explizit die <xref:System.Data.DataColumn>-Datentypen definiert, wobei anstelle von CLR-Typen <xref:System.Data.SqlTypes> verwendet werden. Der Code füllt die <xref:System.Data.DataTable> mit Daten aus der Sales.SalesOrderDetail-Tabelle in der SQL Server-AdventureWorks-Datenbank. Die im Konsolenfenster angezeigte Ausgabe enthält die Datentypen der einzelnen Spalten und die von SQL Server abgerufenen Werte.  
  
 [!code-csharp[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/CS/source.cs#1)]
 [!code-vb[DataWorks SqlTypes.GetTypeAW#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlTypes.GetTypeAW/VB/source.vb#1)]  
  
## <a name="see-also"></a>Weitere Informationen

- [SQL Server-Datentypzuordnungen](../sql-server-data-type-mappings.md)
- [Konfigurieren von Parametern und Parameterdatentypen](../configuring-parameters-and-parameter-data-types.md)
- [Übersicht über ADO.NET](../ado-net-overview.md)
