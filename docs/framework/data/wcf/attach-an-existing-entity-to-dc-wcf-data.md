---
title: 'Gewusst wie: Anfügen einer vorhandenen Entität an "DataServiceContext" (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 69ca64f4ab3470c1a4f58c582b31c06aed9cadd5
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166130"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>Gewusst wie: Anfügen einer vorhandenen Entität an "DataServiceContext" (WCF Data Services)

Wenn eine Entität bereits in einem Datendienst vorhanden ist, können Sie mit der WCF Data Services-Client Bibliothek ein Objekt, das die Entität darstellt, direkt an das Anfügen, <xref:System.Data.Services.Client.DataServiceContext> ohne zuerst eine Abfrage auszuführen. Weitere Informationen finden Sie unter [Aktualisieren des Daten Dienstanbieter](updating-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die Client Daten Klassen werden erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird gezeigt, wie ein vorhandenes `Customer`-Objekt erstellt wird, das im Datendienst zu speichernde Änderungen enthält. Das Objekt wird an den Kontext angefügt, und die <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A>-Methode wird aufgerufen, um das angefügte Objekt als <xref:System.Data.Services.Client.EntityStates.Modified> zu markieren, bevor die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>-Methode aufgerufen wird.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>Weitere Informationen

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
