---
title: 'Vorgehensweise: Importieren von Metadaten in Dienstendpunkte'
ms.date: 03/30/2017
ms.assetid: b69dbe20-92a1-4911-89d8-ffbc3dad4663
ms.openlocfilehash: 1de316b8e91739d5e3e24ff960e2cdfb33cc7fab
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84597058"
---
# <a name="how-to-import-metadata-into-service-endpoints"></a><span data-ttu-id="95d8e-102">Vorgehensweise: Importieren von Metadaten in Dienstendpunkte</span><span class="sxs-lookup"><span data-stu-id="95d8e-102">How to: Import Metadata into Service Endpoints</span></span>
<span data-ttu-id="95d8e-103">In diesem Thema wird erläutert, wie Sie Metadaten in eine Auflistung von Dienst Endpunkten importieren und den Dienst verwenden [, der in den ersten](../samples/getting-started-sample.md)Schritten definiert ist.</span><span class="sxs-lookup"><span data-stu-id="95d8e-103">This topic explains how to import metadata into a collection of service endpoints and use the service defined in the [Getting Started](../samples/getting-started-sample.md).</span></span> <span data-ttu-id="95d8e-104">Im Thema wird gezeigt, wie Sie eine Clientanwendung erstellen, die Metadaten aus dem Dienst importiert und anschließend die`Add`-Methode für den Dienst aufruft.</span><span class="sxs-lookup"><span data-stu-id="95d8e-104">This topic show how to create a client application that imports metadata from the service and then calls the `Add` method on the service.</span></span>  
  
### <a name="to-import-metadata-into-service-endpoints"></a><span data-ttu-id="95d8e-105">So importieren Sie Metadaten in Dienstendpunkte</span><span class="sxs-lookup"><span data-stu-id="95d8e-105">To import metadata into service endpoints</span></span>  
  
1. <span data-ttu-id="95d8e-106">Deklarieren Sie ein <xref:System.ServiceModel.EndpointAddress>-Objekt, und initialisieren Sie es mit dem Uniform Resource Identifier (URI) für die Metadatenaustausch-Adresse (MEX) des Dienstes.</span><span class="sxs-lookup"><span data-stu-id="95d8e-106">Declare an <xref:System.ServiceModel.EndpointAddress> object and initialize it with the Uniform Resource Identifier (URI) for the metadata exchange (MEX) address of the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#0)]  
  
2. <span data-ttu-id="95d8e-107">Erstellen Sie einen <xref:System.ServiceModel.Description.MetadataExchangeClient>, der die MEX-Adresse übergibt, und rufen Sie <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> auf.</span><span class="sxs-lookup"><span data-stu-id="95d8e-107">Create a <xref:System.ServiceModel.Description.MetadataExchangeClient>, passing in the MEX address, and call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>.</span></span> <span data-ttu-id="95d8e-108">Auf diese Weise werden die Metadaten aus dem Dienst abgerufen.</span><span class="sxs-lookup"><span data-stu-id="95d8e-108">This retrieves the metadata from the service.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#1)]  
  
3. <span data-ttu-id="95d8e-109">Erstellen Sie einen <xref:System.ServiceModel.Description.WsdlImporter>, der die vorher abgerufenen Metadaten übergibt, und rufen Sie <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A> auf.</span><span class="sxs-lookup"><span data-stu-id="95d8e-109">Create a <xref:System.ServiceModel.Description.WsdlImporter>, passing in the metadata previously retrieved, and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>.</span></span> <span data-ttu-id="95d8e-110">Dadurch wird eine Auflistung der <xref:System.ServiceModel.Description.ContractDescription>-Objekte erzeugt.</span><span class="sxs-lookup"><span data-stu-id="95d8e-110">This generates a collection of <xref:System.ServiceModel.Description.ContractDescription> objects.</span></span> <span data-ttu-id="95d8e-111">Sie können je nach Ihren Anforderungen auch <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> oder <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A> aufrufen.</span><span class="sxs-lookup"><span data-stu-id="95d8e-111">You could also call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllEndpoints%2A> or <xref:System.ServiceModel.Description.WsdlImporter.ImportAllBindings%2A>, depending upon your needs.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#2)]  
  
    > [!NOTE]
    > <span data-ttu-id="95d8e-112">Nachdem Sie die Metadaten importiert haben, können Sie keinen Clientkanal mehr erstellen oder die Metadaten exportieren.</span><span class="sxs-lookup"><span data-stu-id="95d8e-112">After you have imported the metadata, you will not be able to create a client channel or export the metadata.</span></span> <span data-ttu-id="95d8e-113">Dies liegt daran, dass an diesem Punkt keine Typinformationen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="95d8e-113">This is because no type information is available at this point.</span></span> <span data-ttu-id="95d8e-114">Typinformationen sind erforderlich, um direkt mit dem Dienst zu interagieren oder Metadaten zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="95d8e-114">Type information is required to actually interact with the service or export metadata.</span></span> <span data-ttu-id="95d8e-115">Um die Typinformationen zu erzeugen, müssen Sie den in den Schritten 4 und 5 gezeigten Code generieren.</span><span class="sxs-lookup"><span data-stu-id="95d8e-115">To generate the type information, you need to generate code, shown in steps 4 and 5.</span></span> <span data-ttu-id="95d8e-116">Alternativ dazu können Sie auch die <xref:System.ServiceModel.Description.MetadataResolver>-Hilfsklasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="95d8e-116">Alternatively, you could use the <xref:System.ServiceModel.Description.MetadataResolver> helper class.</span></span> <span data-ttu-id="95d8e-117">Weitere Informationen finden Sie unter Gewusst [wie: Verwenden von von MetadataResolver zum dynamischen Abrufen von Bindungs Metadaten](how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span><span class="sxs-lookup"><span data-stu-id="95d8e-117">For more information, see [How to: Use MetadataResolver to Obtain Binding Metadata Dynamically](how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically.md).</span></span>  
  
4. <span data-ttu-id="95d8e-118">Generieren Sie Typinformationen für jeden Vertrag.</span><span class="sxs-lookup"><span data-stu-id="95d8e-118">Generate type information for each contract.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#3)]  
  
5. <span data-ttu-id="95d8e-119">Jetzt können Sie diese Informationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="95d8e-119">Now you can use this information.</span></span> <span data-ttu-id="95d8e-120">Im folgenden Beispiel wird C#-Quellcode generiert.</span><span class="sxs-lookup"><span data-stu-id="95d8e-120">The following sample generates C# source code.</span></span>  
  
     [!code-csharp[UE_ImportMetadata#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/ue_importmetadata/cs/client.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="95d8e-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="95d8e-121">See also</span></span>

- [<span data-ttu-id="95d8e-122">Metadaten</span><span class="sxs-lookup"><span data-stu-id="95d8e-122">Metadata</span></span>](metadata.md)
- [<span data-ttu-id="95d8e-123">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="95d8e-123">Getting Started</span></span>](../samples/getting-started-sample.md)
