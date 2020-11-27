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
# <a name="how-to-use-metadataresolver-to-obtain-binding-metadata-dynamically"></a>Vorgehensweise: Verwenden von MetadataResolver, um Bindungsmetadaten dynamisch zu erhalten

Dieses Thema zeigt Ihnen, wie man die Klasse <xref:System.ServiceModel.Description.MetadataResolver> einsetzt, um Bindungsmetadaten dynamisch zu erhalten.  
  
### <a name="to-dynamically-obtain-binding-metadata"></a>So erhalten Sie dynamisch Bindungsmetadaten  
  
1. Erstellen Sie ein <xref:System.ServiceModel.EndpointAddress>-Objekt mit der Adresse des Metadatenendpunkts.  
  
    ```csharp
    EndpointAddress metaAddress  
      = new EndpointAddress(new Uri("http://localhost:8080/SampleService/mex"));  
    ```  
  
2. Rufen Sie <xref:System.ServiceModel.Description.MetadataResolver.Resolve%28System.Type%2CSystem.ServiceModel.EndpointAddress%29> auf, der im Diensttyp und der Metadatenendpunktadresse übergibt. Es gibt eine Auflistung von Endpunkten zurück, die den angegebenen Vertrag implementieren. Die Metadaten implementieren nur Bindungsinformationen; Vertragsinformationen werden nicht importiert. Stattdessen wird der angegebene Vertrag verwendet.  
  
    ```csharp  
    ServiceEndpointCollection endpoints = MetadataResolver.Resolve(typeof(SampleServiceClient),metaAddress);  
    ```  
  
3. Sie können dann die Auflistung von Dienstendpunkten durchlaufen, um die Bindungsinformationen zu extrahieren, die Sie benötigen. Der folgende Code durchläuft die Endpunkte, erstellt ein Dienstclientobjekt, das in der Bindung und der Adresse, die mit dem aktuellen Endpunkt verbunden ist, übergeben wird, und ruft dann im Dienst eine Methode auf.  
  
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
  
## <a name="see-also"></a>Weitere Informationen

- [Metadaten](metadata.md)
