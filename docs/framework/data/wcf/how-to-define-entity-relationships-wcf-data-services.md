---
title: "Gewusst wie: Definieren von Entitätsbeziehungen (WCF Data Services)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: WCF Data Services, changing data
ms.assetid: cc255524-1534-4fae-b83c-250933d5a72b
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0e043f15adb510f2c5d563dc5d7e8c23978c89b5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-define-entity-relationships-wcf-data-services"></a>Gewusst wie: Definieren von Entitätsbeziehungen (WCF Data Services)
Wenn Sie eine neue Entität in [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] hinzufügen, werden Beziehungen zwischen der neuen Entität und verknüpften Entitäten nicht automatisch definiert. Sie können Beziehungen zwischen Entitätsinstanzen erstellen und ändern und die Clientbibliothek diese Änderungen im Datendienst widerspiegeln lassen. Weitere Informationen finden Sie unter [Aktualisieren des Datendiensts](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine neue Objektinstanz erstellt und dann die <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A>-Methode im <xref:System.Data.Services.Client.DataServiceContext> aufgerufen, um das Element im Kontext zusammen mit dem Link zur damit verknüpften Bestellung (Order) zu erstellen. Eine HTTP POST-Nachricht wird an den Datendienst gesendet, wenn die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>-Methode aufgerufen wird.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addorderdetailtoorderauto)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addorderdetailtoorderauto)]  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A>-Methode verwendet wird, um einem verknüpften `Order_Details`-Objekt mit einem Verweis auf ein bestimmtes `Orders`-Objekt ein `Products`-Objekt hinzuzufügen. Die Methoden <xref:System.Data.Services.Client.DataServiceContext.AddLink%2A> und <xref:System.Data.Services.Client.DataServiceContext.SetLink%2A> definieren die Beziehungen. In diesem Beispiel werden die Navigationseigenschaften für das `Order_Details`-Objekt auch explizit festgelegt.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#addorderdetailtoorder)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrder](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#addorderdetailtoorder)]  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [Vorgehensweise: hinzufügen, ändern und Löschen von Entitäten](../../../../docs/framework/data/wcf/how-to-add-modify-and-delete-entities-wcf-data-services.md)
