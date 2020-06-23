---
title: 'Vorgehensweise: Verwenden der ChannelFactory'
description: Erfahren Sie, wie Sie eine Kanalfactory erstellen, um mehr als einen Kanal zum Zugreifen auf Dienste mit einem WCF-Client zu erstellen.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
ms.openlocfilehash: 7c87026ca4cf7c739f4615da9bc7f0272a382392
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85246661"
---
# <a name="how-to-use-the-channelfactory"></a><span data-ttu-id="f57f0-103">Vorgehensweise: Verwenden der ChannelFactory</span><span class="sxs-lookup"><span data-stu-id="f57f0-103">How to: Use the ChannelFactory</span></span>
<span data-ttu-id="f57f0-104">Die generische <xref:System.ServiceModel.ChannelFactory%601>-Klasse wird in komplexen Szenarien verwendet, in denen eine Kanalfactory erstellt werden muss, die zum Erstellen mehrerer Kanäle eingesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f57f0-104">The generic <xref:System.ServiceModel.ChannelFactory%601> class is used in advanced scenarios that require the creation of a channel factory that can be used to create more than one channel.</span></span>  
  
### <a name="to-create-and-use-the-channelfactory-class"></a><span data-ttu-id="f57f0-105">So erstellen und verwenden Sie die ChannelFactory-Klasse</span><span class="sxs-lookup"><span data-stu-id="f57f0-105">To create and use the ChannelFactory class</span></span>  
  
1. <span data-ttu-id="f57f0-106">Erstellen und Ausführen eines Windows Communication Foundation (WCF)-Dienstanbieter.</span><span class="sxs-lookup"><span data-stu-id="f57f0-106">Build and run an Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="f57f0-107">Weitere Informationen finden Sie unter [Entwerfen und Implementieren von Diensten](../designing-and-implementing-services.md), [Konfigurieren von Diensten](../configuring-services.md)und [Hostingdiensten](../hosting-services.md).</span><span class="sxs-lookup"><span data-stu-id="f57f0-107">For more information, see [Designing and Implementing Services](../designing-and-implementing-services.md), [Configuring Services](../configuring-services.md), and [Hosting Services](../hosting-services.md).</span></span>  
  
2. <span data-ttu-id="f57f0-108">Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) , um den Vertrag (Schnittstelle) für den Client zu generieren.</span><span class="sxs-lookup"><span data-stu-id="f57f0-108">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) to generate the contract (interface) for the client.</span></span>  
  
3. <span data-ttu-id="f57f0-109">Verwenden Sie im Clientcode die <xref:System.ServiceModel.ChannelFactory%601>-Klasse, um mehrere Endpunktlistener zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f57f0-109">In the client code, use the <xref:System.ServiceModel.ChannelFactory%601> class to create multiple endpoint listeners.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f57f0-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f57f0-110">Example</span></span>  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
