---
title: 'Vorgehensweise: Verwenden von MetadataResolver, um Bindungsmetadaten dynamisch zu erhalten'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 56ffcb99-fff0-4479-aca0-e3909009f605
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 640d053e0186766e5acdbef692f4e7fae59337b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a>Vorgehensweise: Verwenden von MetadataResolver, um Bindungsmetadaten dynamisch zu erhalten
Dieses Thema zeigt Ihnen, wie man die Klasse <xref:System.ServiceModel.Description.MetadataResolver> einsetzt, um Bindungsmetadaten dynamisch zu erhalten.  
  
### <a name="to-dynamically-obtain-binding-metadata"></a>So erhalten Sie dynamisch Bindungsmetadaten  
  
1.  Erstellen Sie ein <xref:System.ServiceModel.EndpointAddress>-Objekt mit der Adresse des Metadatenendpunkts.  
  
    ```  
    EndpointAddress metaAddress  
      = new EndpointAddress(new   Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2.  Rufen Sie <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29> auf, der im Diensttyp und der Metadatenendpunktadresse übergibt. Es gibt eine Auflistung von Endpunkten zurück, die den angegebenen Vertrag implementieren. Die Metadaten implementieren nur Bindungsinformationen; Vertragsinformationen werden nicht importiert. Stattdessen wird der angegebene Vertrag verwendet.  
  
    ```  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3.  Sie können dann die Auflistung von Dienstendpunkten durchlaufen, um die Bindungsinformationen zu extrahieren, die Sie benötigen. Der folgende Code durchläuft die Endpunkte, erstellt ein Dienstclientobjekt, das in der Bindung und der Adresse übergeben wird, die mit dem aktuellen Endpunkt verbunden sind, und ruft dann im Dienst eine Methode auf.  
  
    ```  
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
  
## <a name="see-also"></a>Siehe auch  
 [Metadaten](../../../../docs/framework/wcf/feature-details/metadata.md)
