---
title: 'Vorgehensweise: Importieren von benutzerdefinierter WSDL'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 00a845fe5c8321d521fb7baa3b16bd009fc3e660
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-import-custom-wsdl"></a><span data-ttu-id="a11b2-102">Vorgehensweise: Importieren von benutzerdefinierter WSDL</span><span class="sxs-lookup"><span data-stu-id="a11b2-102">How to: Import Custom WSDL</span></span>
<span data-ttu-id="a11b2-103">In diesem Thema wird beschrieben, wie Sie benutzerdefinierte WSDL importieren.</span><span class="sxs-lookup"><span data-stu-id="a11b2-103">This topic describes how to import custom WSDL.</span></span> <span data-ttu-id="a11b2-104">Zum Behandeln der benutzerdefinierten WSDL müssen Sie die <xref:System.ServiceModel.Description.IWsdlImportExtension>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="a11b2-104">To handle the custom WSDL, you must implement the <xref:System.ServiceModel.Description.IWsdlImportExtension> interface.</span></span>  
  
### <a name="to-import-custom-wsdl"></a><span data-ttu-id="a11b2-105">So importieren Sie benutzerdefinierte WSDL</span><span class="sxs-lookup"><span data-stu-id="a11b2-105">To import custom WSDL</span></span>  
  
1.  <span data-ttu-id="a11b2-106">Implementieren Sie <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span><span class="sxs-lookup"><span data-stu-id="a11b2-106">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span></span> <span data-ttu-id="a11b2-107">Implementieren Sie die <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29>-Methode, um die Metadaten vor dem Import zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a11b2-107">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> method to modify the metadata before it is imported.</span></span> <span data-ttu-id="a11b2-108">Implementieren Sie die <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29>-Methode und die <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>-Methode, um aus den Metadaten importierte Verträge und Endpunkte zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a11b2-108">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> and <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> methods to modify contracts and endpoints imported from the metadata.</span></span> <span data-ttu-id="a11b2-109">Verwenden Sie zum Zugriff auf den importierten Vertrag oder Endpunkt das entsprechende Kontextobjekt (<xref:System.ServiceModel.Description.WsdlContractConversionContext> oder <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span><span class="sxs-lookup"><span data-stu-id="a11b2-109">To access the imported contract or endpoint, use the corresponding context object (<xref:System.ServiceModel.Description.WsdlContractConversionContext> or <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span></span>  
  
    ```  
    public class WsdlDocumentationImporter : IWsdlImportExtension  
       {  
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
       }  
    ```  
  
2.  <span data-ttu-id="a11b2-110">Konfigurieren Sie die Clientanwendung für die Verwendung des benutzerdefinierten WSDL-Importers.</span><span class="sxs-lookup"><span data-stu-id="a11b2-110">Configure the client application to use the custom WSDL importer.</span></span> <span data-ttu-id="a11b2-111">Wenn Sie Svcutil.exe verwenden, sollten Sie diese Konfiguration der Konfigurationsdatei für Svcutil.exe (Svcutil.exe.config) hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="a11b2-111">Note that if you are using Svcutil.exe, you should add this configuration to the configuration file for Svcutil.exe (Svcutil.exe.config):</span></span>  
  
    ```xml  
    <system.serviceModel>  
          <client>  
            <endpoint   
              address="http://localhost:8000/Fibonacci"   
              binding="wsHttpBinding"  
              contract="IFibonacci"  
            />  
            <metadata>  
              <wsdlImporters>  
                <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
              </wsdlImporters>  
            </metadata>  
          </client>  
        </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="a11b2-112">Erstellen Sie eine neue <xref:System.ServiceModel.Description.WsdlImporter>-Instanz (die dabei <xref:System.ServiceModel.Description.MetadataSet>-Instanz übergibt, die die zu importierenden WSDL-Dokumente enthält), und rufen Sie <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A> auf:</span><span class="sxs-lookup"><span data-stu-id="a11b2-112">Create a new <xref:System.ServiceModel.Description.WsdlImporter> instance (passing in the <xref:System.ServiceModel.Description.MetadataSet> instance that contains the WSDL documents that you want to import), and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span></span>  
  
    ```  
    WsdlImporter importer = new WsdlImporter(metaDocs);          System.Collections.ObjectModel.Collection<ContractDescription> contracts  = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a11b2-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a11b2-113">See Also</span></span>  
 [<span data-ttu-id="a11b2-114">Metadaten</span><span class="sxs-lookup"><span data-stu-id="a11b2-114">Metadata</span></span>](../../../../docs/framework/wcf/feature-details/metadata.md)  
 [<span data-ttu-id="a11b2-115">Exportieren und Importieren von Metadaten</span><span class="sxs-lookup"><span data-stu-id="a11b2-115">Exporting and Importing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)  
 [<span data-ttu-id="a11b2-116">Benutzerdefinierte WSDL-Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="a11b2-116">Custom WSDL Publication</span></span>](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)
