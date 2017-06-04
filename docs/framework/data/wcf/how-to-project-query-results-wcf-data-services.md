---
title: "Gewusst wie: Projizieren von Abfrageergebnissen (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Projektion [WCF Data Services]"
  - "Abfrageprojektionen [WCF Data Services]"
  - "WCF Data Services, Projektion"
  - "WCF Data Services, Abfragen"
ms.assetid: 474ac625-8770-43ba-8320-d3315ea9530f
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Gewusst wie: Projizieren von Abfrageergebnissen (WCF Data Services)
Die Projektion stellt einen Mechanismus bereit, mit dem sich die von einer Abfrage zurückgegebene Datenmenge reduzieren lässt, indem angegeben wird, dass nur bestimmte Eigenschaften einer Entität in der Antwort zurückgegeben werden sollen.  Sie können entweder Projektionen auf den Ergebnissen einer [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Abfrage ausführen, indem Sie entweder die `$select`\-Abfrageoption oder die [select](../Topic/select%20clause%20\(C%23%20Reference\).md)\-Klausel \([Select](../Topic/Select%20Clause%20\(Visual%20Basic\).md) in Visual Basic\) in einer LINQ\-Abfrage angeben.  Weitere Informationen finden Sie unter [Abfragen des Datendiensts](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind\-Beispieldatendienst und automatisch generierte Client\-Datendienstklassen verwendet.  Dieser Dienst und die Clientdatenklassen werden erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
## Beispiel  
 Im folgenden Beispiel wird eine LINQ\-Abfrage gezeigt, die Customers\-Entitäten in den neuen CustomerAddress\-Typ projiziert, der nur adressenspezifische Eigenschaften und die IDENTITY\-Eigenschaft enthält.  Diese `CustomerAddress`\-Klasse wird auf dem Client definiert und so zugeordnet, dass die Clientbibliothek ihn als Entitätstyp erkennen kann.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddress)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddress](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddress)]  
  
## Beispiel  
 Im folgenden Beispiel wird eine LINQ\-Abfrage gezeigt, die zurückgegebene Customers\-Entitäten in einen neuen CustomerAddressNonEntity\-Typ projiziert, der nur adressenspezifische Eigenschaften und keine IDENTITY\-Eigenschaft enthält.  Diese `CustomerAddressNonEntity`\-Klasse wird auf dem Client definiert und nicht als Entitätstyp ausgezeichnet.  
  
 [!code-csharp[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#selectcustomeraddressnonentity)]
 [!code-vb[Astoria Northwind Client#SelectCustomerAddressNonEntity](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#selectcustomeraddressnonentity)]  
  
## Beispiel  
 Das folgende Beispiel veranschaulicht die Definitionen der `CustomerAddress` `CustomerAddressNonEntity`\-Typen, die in den vorherigen Beispielen verwendet wurden.  
  
 [!code-csharp[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customeraddress.cs#customeraddressdefinition)]
 [!code-vb[Astoria Northwind Client#CustomerAddressDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customeraddress.vb#customeraddressdefinition)]