---
title: 'Gewusst wie: Projizieren von Abfrageergebnissen (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- projection [WCF Data Services]
- WCF Data Services, projection
- query projection [WCF Data Services]
- WCF Data Services, querying
ms.assetid: 474ac625-8770-43ba-8320-d3315ea9530f
ms.openlocfilehash: 1e94b5f65229887b2d310f15499a2b14ef7c0536
ms.sourcegitcommit: 79a2d6a07ba4ed08979819666a0ee6927bbf1b01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2019
ms.locfileid: "74569003"
---
# <a name="how-to-project-query-results-wcf-data-services"></a>Gewusst wie: Projizieren von Abfrageergebnissen (WCF Data Services)
Die Projektion stellt einen Mechanismus bereit, mit dem sich die von einer Abfrage zurückgegebene Datenmenge reduzieren lässt, indem angegeben wird, dass nur bestimmte Eigenschaften einer Entität in der Antwort zurückgegeben werden sollen. Sie können Projektionen auf die Ergebnisse einer WCF Data Services Abfrage ausführen, indem Sie entweder die `$select` Query-Option oder die [Select](../../../csharp/language-reference/keywords/select-clause.md) -Klausel ([Select](../../../visual-basic/language-reference/queries/select-clause.md) in Visual Basic) in einer LINQ-Abfrage verwenden. Weitere Informationen finden Sie unter [Abfragen des Daten Dienstanbieter](querying-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine LINQ-Abfrage veranschaulicht, die Customers-Entitäten in den neuen CustomerAddress-Typ projiziert, der nur adressenspezifische Eigenschaften und die IDENTITY-Eigenschaft enthält. Diese `CustomerAddress`-Klasse wird auf dem Client definiert und so zugeordnet, dass die Clientbibliothek ihn als Entitätstyp erkennen kann.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddress)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine LINQ-Abfrage gezeigt, die zurückgegebene Customers-Entitäten in einen neuen CustomerAddressNonEntity-Typ projiziert, der nur adressenspezifische Eigenschaften und keine IDENTITY-Eigenschaft enthält. Diese `CustomerAddressNonEntity`-Klasse wird auf dem Client definiert und nicht als Entitätstyp ausgezeichnet.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Definitionen der `CustomerAddress` und `CustomerAddressNonEntity` Typen, die in den vorherigen Beispielen verwendet werden.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/customeraddress.vb#customeraddressdefinition)]
