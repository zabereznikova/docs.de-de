---
title: 'Vorgehensweise: Verwenden von MetadataResolver, um Bindungsmetadaten dynamisch zu erhalten'
ms.date: 03/30/2017
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
ms.openlocfilehash: fc64e11271c6901a8d4598c0efa563a06a92decf
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96280714"
---
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a><span data-ttu-id="ed660-102">Vorgehensweise: Verwenden von MetadataResolver, um Bindungsmetadaten dynamisch zu erhalten</span><span class="sxs-lookup"><span data-stu-id="ed660-102">How to: Use MetadataResolver to Obtain Binding Metadata Dynamically</span></span>

<span data-ttu-id="ed660-103">Dieses Thema zeigt Ihnen, wie man die Klasse <xref:System.ServiceModel.Description.MetadataResolver> einsetzt, um Bindungsmetadaten dynamisch zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ed660-103">This topic shows you how to use the <xref:System.ServiceModel.Description.MetadataResolver> class to dynamically obtain binding metadata.</span></span>  
  
### <a name="to-dynamically-obtain-binding-metadata"></a><span data-ttu-id="ed660-104">So erhalten Sie dynamisch Bindungsmetadaten</span><span class="sxs-lookup"><span data-stu-id="ed660-104">To dynamically obtain binding metadata</span></span>  
  
1. <span data-ttu-id="ed660-105">Erstellen Sie ein <xref:System.ServiceModel.EndpointAddress>-Objekt mit der Adresse des Metadatenendpunkts.</span><span class="sxs-lookup"><span data-stu-id="ed660-105">Create an <xref:System.ServiceModel.EndpointAddress> object with the address of the metadata endpoint.</span></span>  
  
    ```csharp
    EndpointAddress metaAddress  
      = new EndpointAddress(new Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2. <span data-ttu-id="ed660-106">Rufen Sie <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29> auf, der im Diensttyp und der Metadatenendpunktadresse übergibt.</span><span class="sxs-lookup"><span data-stu-id="ed660-106">Call <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29>, which passes in the service type and the metadata endpoint address.</span></span> <span data-ttu-id="ed660-107">Es gibt eine Auflistung von Endpunkten zurück, die den angegebenen Vertrag implementieren.</span><span class="sxs-lookup"><span data-stu-id="ed660-107">This returns a collection of endpoints that implement the specified contract.</span></span> <span data-ttu-id="ed660-108">Die Metadaten implementieren nur Bindungsinformationen; Vertragsinformationen werden nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="ed660-108">Only binding information is imported from the metadata; contract information is not imported.</span></span> <span data-ttu-id="ed660-109">Stattdessen wird der angegebene Vertrag verwendet.</span><span class="sxs-lookup"><span data-stu-id="ed660-109">The supplied contract is used instead.</span></span>  
  
    ```csharp  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3. <span data-ttu-id="ed660-110">Sie können dann die Auflistung von Dienstendpunkten durchlaufen, um die Bindungsinformationen zu extrahieren, die Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="ed660-110">You can then iterate through the collection of service endpoints to extract the binding information you need.</span></span> <span data-ttu-id="ed660-111">Der folgende Code durchläuft die Endpunkte, erstellt ein Dienstclientobjekt, das in der Bindung und der Adresse, die mit dem aktuellen Endpunkt verbunden ist, übergeben wird, und ruft dann im Dienst eine Methode auf.</span><span class="sxs-lookup"><span data-stu-id="ed660-111">The following code iterates through the endpoints, creates a service client object that passes in the binding and address associated with the current endpoint, and then calls a method on the service.</span></span>  
  
    ```csharp  
    foreach (ServiceEndpoint point in endpoints)  
    {  
       if (point != null)  
       {  
          // Create a new wcfClient using retrieved endpoints.  
          using (wcfClient = new SampleServiceClient(point.Binding, point.Address))  
          {  
             Console.WriteLine(  
               wcfClient.SampleMethod("Client used the "  
               + point.Address.ToString() + " address."));  
          }  
      }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ed660-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed660-112">See also</span></span>

- [<span data-ttu-id="ed660-113">Metadaten</span><span class="sxs-lookup"><span data-stu-id="ed660-113">Metadata</span></span>](metadata.md)
