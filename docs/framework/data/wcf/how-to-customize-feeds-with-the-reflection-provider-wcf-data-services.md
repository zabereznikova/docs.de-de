---
title: 'Gewusst wie: Anpassen von Feeds mit dem Reflektionsanbieter (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, customizing
- WCF Data Services, customizing feeds
ms.assetid: 00c23dcf-9bb8-459a-a012-6c4d9bcad7e9
ms.openlocfilehash: fb22e87569a8e243813b3186232b6989abeb2a5e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161307"
---
# <a name="how-to-customize-feeds-with-the-reflection-provider-wcf-data-services"></a><span data-ttu-id="0ca83-102">Gewusst wie: Anpassen von Feeds mit dem Reflektionsanbieter (WCF Data Services)</span><span class="sxs-lookup"><span data-stu-id="0ca83-102">How to: Customize Feeds with the Reflection Provider (WCF Data Services)</span></span>

<span data-ttu-id="0ca83-103">Mit WCF Data Services können Sie die Atom-Serialisierung in einer Datendienst Antwort anpassen, sodass Eigenschaften einer Entität nicht verwendeten Elementen zugeordnet werden können, die im AtomPub-Protokoll definiert sind.</span><span class="sxs-lookup"><span data-stu-id="0ca83-103">WCF Data Services enables you to customize the Atom serialization in a data service response so that properties of an entity may be mapped to unused elements that are defined in the AtomPub protocol.</span></span> <span data-ttu-id="0ca83-104">In diesem Thema wird erläutert, wie Zuordnungsattribute für die Entitätstypen in einem Datenmodell definiert werden, das mit dem Reflektionsanbieter definiert wird.</span><span class="sxs-lookup"><span data-stu-id="0ca83-104">This topic shows how to define mapping attributes for the entity types in a data model that is defined by using the reflection provider.</span></span> <span data-ttu-id="0ca83-105">Weitere Informationen finden Sie unter [Feed-Anpassung](feed-customization-wcf-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="0ca83-105">For more information, see [Feed Customization](feed-customization-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="0ca83-106">Das Datenmodell für dieses Beispiel wird im Thema Gewusst [wie: Erstellen eines Daten Dienstanbieters mithilfe des reflektionsanbieters](create-a-data-service-using-rp-wcf-data-services.md) definiert.</span><span class="sxs-lookup"><span data-stu-id="0ca83-106">The data model for this example is defined in the topic [How to: Create a Data Service Using the Reflection Provider](create-a-data-service-using-rp-wcf-data-services.md)</span></span>  
  
## <a name="example"></a><span data-ttu-id="0ca83-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ca83-107">Example</span></span>  

 <span data-ttu-id="0ca83-108">Im folgenden Beispiel werden vorhandenen Atom-Elementen beide Eigenschaften des `Order`-Typs zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0ca83-108">In the following example, both properties of the `Order` type are mapped to existing Atom elements.</span></span> <span data-ttu-id="0ca83-109">Einem benutzerdefinierten Feedattribut wird in einem separaten Namespace die `Product`-Eigenschaft des `Item`-Typs zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="0ca83-109">The `Product` property of the `Item` type is mapped to a custom feed attribute in a separate namespace.</span></span>  
  
 [!code-csharp[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_custom_feeds/cs/orderitems.svc.cs#customiqueryablefeeds)]
 [!code-vb[Astoria Custom Feeds#CustomIQueryableFeeds](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_custom_feeds/vb/orderitems.svc.vb#customiqueryablefeeds)]  
  
## <a name="example"></a><span data-ttu-id="0ca83-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0ca83-110">Example</span></span>  

 <span data-ttu-id="0ca83-111">Das vorherige Beispiel gibt das folgende Ergebnis für den URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items` zurück.</span><span class="sxs-lookup"><span data-stu-id="0ca83-111">The previous example returns the following result for the URI `http://myservice/OrderItems.svc/Orders(0)?$expand=Items`.</span></span>  
  
 [!code-xml[Astoria Custom Feeds#IQueryableFeedResultInline](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_custom_feeds/xml/iqueryablefeedresultinline.xml#iqueryablefeedresultinline)]  
  
## <a name="see-also"></a><span data-ttu-id="0ca83-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0ca83-112">See also</span></span>

- [<span data-ttu-id="0ca83-113">Reflektionsanbieter</span><span class="sxs-lookup"><span data-stu-id="0ca83-113">Reflection Provider</span></span>](reflection-provider-wcf-data-services.md)
