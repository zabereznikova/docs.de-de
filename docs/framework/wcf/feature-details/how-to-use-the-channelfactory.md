---
title: 'Vorgehensweise: Verwenden der ChannelFactory'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7d542a3dcae514e75194b49c23a8dec5dd7e8c3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62047255"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="a7fea-102">Vorgehensweise: Verwenden der ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="a7fea-102">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="a7fea-103">Die generische <xref:System.ServiceModel.ChannelFactory%601>-Klasse wird in komplexen Szenarien verwendet, in denen eine Kanalfactory erstellt werden muss, die zum Erstellen mehrerer Kanäle eingesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="a7fea-103">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="a7fea-104">So erstellen und verwenden Sie die ChannelFactory-Klasse</span><span class="sxs-lookup"><span data-stu-id="a7fea-104">To create and use the ChannelFactory class</span></span>  
  
1. <span data-ttu-id="a7fea-105">Erstellen und Ausführen eines Windows Communication Foundation (WCF)-Diensts.</span><span class="sxs-lookup"><span data-stu-id="a7fea-105">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="a7fea-106">Weitere Informationen finden Sie unter [entwerfen und Implementieren von Diensten](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Configuring Services](../../../../docs/framework/wcf/configuring-services.md), und [Hostingdienste](../../../../docs/framework/wcf/hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="a7fea-106">For more information, see [Designing and Implementing Services](../../../../docs/framework/wcf/designing-and-implementing-services.md), [Configuring Services](../../../../docs/framework/wcf/configuring-services.md), and [Hosting Services](../../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
2. <span data-ttu-id="a7fea-107">Verwenden der [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) um den Vertrag (Schnittstelle) für den Client zu generieren.</span><span class="sxs-lookup"><span data-stu-id="a7fea-107">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3. <span data-ttu-id="a7fea-108">Verwenden Sie im Clientcode die <xref:System.ServiceModel.ChannelFactory%601>-Klasse, um mehrere Endpunktlistener zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a7fea-108">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7fea-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a7fea-109">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
