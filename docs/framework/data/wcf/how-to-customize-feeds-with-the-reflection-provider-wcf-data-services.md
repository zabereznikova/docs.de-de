---
title: 'Vorgehensweise: Anpassen von Feeds mit dem Reflektionsanbieter (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: fe6e65a0030ca016f280e6b2c1106b4aa302d26e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54637702"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a>Vorgehensweise: Anpassen von Feeds mit dem Reflektionsanbieter (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es Ihnen, die Atom-Serialisierung in einer Datendienstantwort anzupassen, damit Eigenschaften einer Entität nicht verwendeten Elementen zugeordnet werden können, die im AtomPub-Protokoll definiert werden. In diesem Thema wird erläutert, wie Zuordnungsattribute für die Entitätstypen in einem Datenmodell definiert werden, das mit dem Reflektionsanbieter definiert wird. Weitere Informationen finden Sie unter [Feed Anpassung](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md).  
  
 Das Datenmodell für dieses Beispiel ist im Thema definiert [Vorgehensweise: Erstellen eines Datendiensts mit dem Reflektionsanbieter](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel werden vorhandenen Atom-Elementen beide Eigenschaften des `Order`-Typs zugeordnet. Einem benutzerdefinierten Feedattribut wird in einem separaten Namespace die `Product`-Eigenschaft des `Item`-Typs zugeordnet.  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria custom feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria custom feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a>Beispiel  
 Das vorherige Beispiel gibt das folgende Ergebnis für den URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items` zurück.  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria custom feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a>Siehe auch
- [Reflektionsanbieter](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
