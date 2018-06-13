---
title: 'Gewusst wie: Anfügen einer vorhandenen Entität an "DataServiceContext" (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, changing data
ms.assetid: e3f2d71d-434c-4e98-91c3-95adae4702b6
ms.openlocfilehash: 30a0c0eb618dc7cedc8be2be4a327d9b1f73a51b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33357208"
---
# <a name="how-to-attach-an-existing-entity-to-the-dataservicecontext-wcf-data-services"></a>Gewusst wie: Anfügen einer vorhandenen Entität an "DataServiceContext" (WCF Data Services)
Wenn eine Entität in einem Datendienst bereits die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] -Clientbibliothek ermöglicht es Ihnen, ein Objekt anzufügen, die die Entität darstellt, die direkt an die <xref:System.Data.Services.Client.DataServiceContext> ohne zuerst eine Abfrage ausführt. Weitere Informationen finden Sie unter [Aktualisieren des Datendiensts](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema werden der Northwind-Beispieldatendienst und automatisch generierte Client-Datendienstklassen verwendet. Dieser Dienst und die clientdatenklassen werden erstellt, wenn Sie die [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie ein vorhandenes `Customer`-Objekt erstellt wird, das im Datendienst zu speichernde Änderungen enthält. Das Objekt wird an den Kontext angefügt, und die <xref:System.Data.Services.Client.DataServiceContext.UpdateObject%2A>-Methode wird aufgerufen, um das angefügte Objekt als <xref:System.Data.Services.Client.EntityStates.Modified> zu markieren, bevor die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>-Methode aufgerufen wird.  
  
 [!code-csharp[Astoria Northwind Client#AttachObject](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/source.cs#attachobject)]
 [!code-vb[Astoria Northwind Client#AttachObject](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/source.vb#attachobject)]  
  
## <a name="see-also"></a>Siehe auch  
 [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
