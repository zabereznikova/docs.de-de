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
ms.openlocfilehash: c1eb2618e14f0e02aa5e1a2e91aa93fe0831c7c7
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/26/2018
ms.locfileid: "42932976"
---
# <a name="how-to-project-query-results-wcf-data-services"></a>Gewusst wie: Projizieren von Abfrageergebnissen (WCF Data Services)
Die Projektion stellt einen Mechanismus bereit, mit dem sich die von einer Abfrage zurückgegebene Datenmenge reduzieren lässt, indem angegeben wird, dass nur bestimmte Eigenschaften einer Entität in der Antwort zurückgegeben werden sollen. Durchführen können Projektionen auf den Ergebnissen der ein [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] Abfragen, indem Sie entweder die `$select` -Abfrageoption oder mithilfe der [auswählen](~/docs/csharp/language-reference/keywords/select-clause.md) Klausel ([auswählen](~/docs/visual-basic/language-reference/queries/select-clause.md) in Visual Basic) in einer LINQ-Abfrage. Weitere Informationen finden Sie unter [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine LINQ-Abfrage gezeigt, die Customers-Entitäten in den neuen CustomerAddress-Typ projiziert, der nur adressenspezifische Eigenschaften und die IDENTITY-Eigenschaft enthält. Diese `CustomerAddress`-Klasse wird auf dem Client definiert und so zugeordnet, dass die Clientbibliothek ihn als Entitätstyp erkennen kann.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddress)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine LINQ-Abfrage gezeigt, die zurückgegebene Customers-Entitäten in einen neuen CustomerAddressNonEntity-Typ projiziert, der nur adressenspezifische Eigenschaften und keine IDENTITY-Eigenschaft enthält. Diese `CustomerAddressNonEntity`-Klasse wird auf dem Client definiert und nicht als Entitätstyp ausgezeichnet.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt die Definitionen der `CustomerAddress` und `CustomerAddressNonEntity` Typen, die in den vorherigen Beispielen verwendet werden.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customeraddress.vb#customeraddressdefinition)]
