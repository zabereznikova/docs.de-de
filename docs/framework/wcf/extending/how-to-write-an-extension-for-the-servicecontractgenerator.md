---
title: "Vorgehensweise: Schreiben einer Erweiterung für den ServiceContractGenerator"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 876ca823-bd16-4bdf-9e0f-02092df90e51
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e40ea594c7743dfec06876515a1165da1a16d4e5
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-write-an-extension-for-the-servicecontractgenerator"></a>Vorgehensweise: Schreiben einer Erweiterung für den ServiceContractGenerator
In diesem Thema wird beschrieben, wie Sie eine Erweiterung für den <xref:System.ServiceModel.Description.ServiceContractGenerator> schreiben können. Dies kann durch Implementieren der <xref:System.ServiceModel.Description.IOperationContractGenerationExtension>-Schnittstelle für ein Vorgangsverhalten oder Implementieren der <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>-Schnittstelle für ein Vertragsverhalten geschehen. In diesem Thema wird gezeigt, wie die <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>-Schnittstelle in einem Vertragsverhalten implementiert wird.  
  
 Der <xref:System.ServiceModel.Description.ServiceContractGenerator> erstellt aus <xref:System.ServiceModel.Description.ServiceEndpoint>-Instanzen, <xref:System.ServiceModel.Description.ContractDescription>-Instanzen und <xref:System.ServiceModel.Channels.Binding>-Instanzen Dienstverträge, Clienttypen und Clientkonfigurationen. Normalerweise importieren Sie <xref:System.ServiceModel.Description.ServiceEndpoint>-Instanzen, <xref:System.ServiceModel.Description.ContractDescription>-Instanzen und <xref:System.ServiceModel.Channels.Binding>-Instanzen aus Dienstmetadaten und verwenden dann diese Instanzen, um den Code zum Aufrufen des Dienstes zu schreiben. In diesem Beispiel wird eine <xref:System.ServiceModel.Description.IWsdlImportExtension>-Implementierung zur Verarbeitung von WSDL-Anmerkungen verwendet. Dann werden Codegenerierungserweiterungen in die importierten Verträge eingefügt, um Kommentare zu dem generierten Code zu erstellen.  
  
### <a name="to-write-an-extension-for-the-servicecontractgenerator"></a>So schreiben Sie eine Erweiterung für den ServiceContractGenerator  
  
1.  Implementieren Sie <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>. Verwenden Sie zum Bearbeiten des generierten Dienstvertrags die <xref:System.ServiceModel.Description.ServiceContractGenerationContext>-Instanz, die an die <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29>-Methode weitergegeben wurde.  
  
    ```  
    public void GenerateContract(ServiceContractGenerationContext context)  
    {  
        Console.WriteLine("In generate contract.");  
    context.ContractType.Comments.AddRange(Formatter.FormatComments(commentText));  
    }  
    ```  
  
2.  Implementieren Sie <xref:System.ServiceModel.Description.IWsdlImportExtension> für die gleiche Klasse. Mit der <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>-Methode kann eine bestimmte WSDL-Erweiterung (in diesem Fall WSDL-Anmerkungen) verarbeitet werden, indem eine Codegenerierungserweiterung der importierten <xref:System.ServiceModel.Description.ContractDescription>-Instanz hinzugefügt wird.  
  
    ```  
    public void ImportContract(WsdlImporter importer, WsdlContractConversionContext context)  
       {  
                // Contract documentation  
             if (context.WsdlPortType.Documentation != null)  
             {  
                    context.Contract.Behaviors.Add(new WsdlDocumentationImporter(context.WsdlPortType.Documentation));  
             }  
             // Operation documentation  
             foreach (Operation operation in context.WsdlPortType.Operations)  
             {  
                if (operation.Documentation != null)  
                {  
                   OperationDescription operationDescription = context.Contract.Operations.Find(operation.Name);  
                   if (operationDescription != null)  
                   {  
                            operationDescription.Behaviors.Add(new WsdlDocumentationImporter(operation.Documentation));  
                   }  
                }  
             }  
          }  
          public void BeforeImport(ServiceDescriptionCollection wsdlDocuments, XmlSchemaSet xmlSchemas, ICollection<XmlElement> policy)   
            {  
                Console.WriteLine("BeforeImport called.");  
            }  
  
          public void ImportEndpoint(WsdlImporter importer, WsdlEndpointConversionContext context)   
            {  
                Console.WriteLine("ImportEndpoint called.");  
            }  
    ```  
  
3.  Fügen Sie den WSDL-Importer in Ihre Clientkonfiguration ein.  
  
    ```xml  
    <metadata>  
      <wsdlImporters>  
        <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
      </wsdlImporters>  
    </metadata>  
    ```  
  
4.  Erstellen Sie im Clientcode einen `MetadataExchangeClient`, und rufen Sie `GetMetadata` auf.  
  
    ```  
    MetadataExchangeClient mexClient = new MetadataExchangeClient(metadataAddress);  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet metaDocs = mexClient.GetMetadata();  
    ```  
  
5.  Erstellen Sie einen `WsdlImporter`, und rufen Sie `ImportAllContracts` auf.  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);            System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
6.  Erstellen Sie einen `ServiceContractGenerator`, und rufen Sie den `GenerateServiceContractType` für jeden Vertrag auf.  
  
    ```  
    ServiceContractGenerator generator = new ServiceContractGenerator();  
    foreach (ContractDescription contract in contracts)  
    {  
       generator.GenerateServiceContractType(contract);  
    }  
    if (generator.Errors.Count != 0)  
       throw new Exception("There were errors during code compilation.");  
    ```  
  
7.  <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> wird automatisch für jedes Vertragsverhalten für einen bestimmten Vertrag, der <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> implementiert, aufgerufen. Diese Methode kann dann den übergebenen <xref:System.ServiceModel.Description.ServiceContractGenerationContext> ändern. In diesem Beispiel werden Kommentare hinzugefügt.  
  
## <a name="see-also"></a>Siehe auch  
 [Metadaten](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [Vorgehensweise: Importieren von benutzerdefinierter WSDL](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)
