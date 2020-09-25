---
title: 'Gewusst wie: Hinzufügen, Ändern und Löschen von Entitäten (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: a00f8933-b232-4445-95ba-adc634f055d8
ms.openlocfilehash: 3d147f05e2911cdaa05c5fc2374e14c539235fda
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172527"
---
# <a name="how-to-add-modify-and-delete-entities-wcf-data-services"></a>Gewusst wie: Hinzufügen, Ändern und Löschen von Entitäten (WCF Data Services)

Mit den WCF Data Services-Client Bibliotheken können Sie Entitäts Daten in einem Datendienst erstellen, aktualisieren und löschen, indem Sie entsprechende Aktionen für Objekte im Ausführen <xref:System.Data.Services.Client.DataServiceContext> . Weitere Informationen finden Sie unter [Aktualisieren des Daten Dienstanbieter](updating-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine neue Objektinstanz erstellt und dann die <xref:System.Data.Services.Client.DataServiceContext.AddObject%2A>-Methode im <xref:System.Data.Services.Client.DataServiceContext> aufgerufen, um das Element im Kontext zu erstellen. Eine HTTP POST-Nachricht wird an den Datendienst gesendet, wenn die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>-Methode aufgerufen wird.  
  
 [!code-csharp[Astoria Northwind Client#AddProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addproduct)]
 [!code-vb[Astoria Northwind Client#AddProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addproduct)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird ein vorhandenes Objekt abgerufen und geändert und anschließend die <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A>-Methode im <xref:System.Data.Services.Client.DataServiceContext> aufgerufen, um das Element im Kontext als aktualisiert zu markieren. Eine HTTP MERGE-Nachricht wird an den Datendienst gesendet, wenn die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>-Methode aufgerufen wird.  
  
 [!code-csharp[Astoria Northwind Client#ModifyCustomer](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#modifycustomer)]
 [!code-vb[Astoria Northwind Client#ModifyCustomer](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#modifycustomer)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird die <xref:System.Data.Services.Client.DataServiceContext.DeleteObject%2A>-Methode im <xref:System.Data.Services.Client.DataServiceContext> aufgerufen, um das Element im Kontext als gelöscht zu markieren. Eine HTTP DELETE-Nachricht wird an den Datendienst gesendet, wenn die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>-Methode aufgerufen wird.  
  
 [!code-csharp[Astoria Northwind Client#DeleteProduct](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#deleteproduct)]
 [!code-vb[Astoria Northwind Client#DeleteProduct](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#deleteproduct)]  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine neue Objektinstanz erstellt und dann die <xref:System.Data.Services.Client.DataServiceContext.AddRelatedObject%2A>-Methode im <xref:System.Data.Services.Client.DataServiceContext> aufgerufen, um das Element im Kontext zusammen mit dem Link zur damit verknüpften Bestellung (Order) zu erstellen. Eine HTTP POST-Nachricht wird an den Datendienst gesendet, wenn die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>-Methode aufgerufen wird.  
  
 [!code-csharp[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#addorderdetailtoorderauto)]
 [!code-vb[Astoria Northwind Client#AddOrderDetailToOrderAuto](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#addorderdetailtoorderauto)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
- [Vorgehensweise: Anfügen einer vorhandenen Entität an den DataServiceContext](attach-an-existing-entity-to-dc-wcf-data.md)
- [Vorgehensweise: Definieren von Entitätsbeziehungen](how-to-define-entity-relationships-wcf-data-services.md)
- [Batchvorgänge](batching-operations-wcf-data-services.md)
