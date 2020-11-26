---
title: 'Vorgehensweise: Importieren von benutzerdefinierten WSDL-Informationen'
ms.date: 03/30/2017
ms.assetid: ddc3718d-ce60-44f6-92af-a5c67477dd99
ms.openlocfilehash: c5aa554394743314a91afd6a5cdf86f9974e81f8
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249084"
---
# <a name="how-to-import-custom-wsdl"></a><span data-ttu-id="ebbae-102">Vorgehensweise: Importieren von benutzerdefinierten WSDL-Informationen</span><span class="sxs-lookup"><span data-stu-id="ebbae-102">How to: Import Custom WSDL</span></span>

<span data-ttu-id="ebbae-103">In diesem Thema wird beschrieben, wie Sie benutzerdefinierte WSDL importieren.</span><span class="sxs-lookup"><span data-stu-id="ebbae-103">This topic describes how to import custom WSDL.</span></span> <span data-ttu-id="ebbae-104">Zum Behandeln der benutzerdefinierten WSDL müssen Sie die <xref:System.ServiceModel.Description.IWsdlImportExtension>-Schnittstelle implementieren.</span><span class="sxs-lookup"><span data-stu-id="ebbae-104">To handle the custom WSDL, you must implement the <xref:System.ServiceModel.Description.IWsdlImportExtension> interface.</span></span>  
  
### <a name="to-import-custom-wsdl"></a><span data-ttu-id="ebbae-105">So importieren Sie benutzerdefinierte WSDL</span><span class="sxs-lookup"><span data-stu-id="ebbae-105">To import custom WSDL</span></span>  
  
1. <span data-ttu-id="ebbae-106">Implementieren Sie <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span><span class="sxs-lookup"><span data-stu-id="ebbae-106">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension>.</span></span> <span data-ttu-id="ebbae-107">Implementieren Sie die <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29>-Methode, um die Metadaten vor dem Import zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ebbae-107">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29> method to modify the metadata before it is imported.</span></span> <span data-ttu-id="ebbae-108">Implementieren Sie die <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29>-Methode und die <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>-Methode, um aus den Metadaten importierte Verträge und Endpunkte zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ebbae-108">Implement the <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29> and <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> methods to modify contracts and endpoints imported from the metadata.</span></span> <span data-ttu-id="ebbae-109">Verwenden Sie zum Zugriff auf den importierten Vertrag oder Endpunkt das entsprechende Kontextobjekt (<xref:System.ServiceModel.Description.WsdlContractConversionContext> oder <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span><span class="sxs-lookup"><span data-stu-id="ebbae-109">To access the imported contract or endpoint, use the corresponding context object (<xref:System.ServiceModel.Description.WsdlContractConversionContext> or <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):</span></span>  
  
    ```csharp
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
  
2. <span data-ttu-id="ebbae-110">Konfigurieren Sie die Clientanwendung für die Verwendung des benutzerdefinierten WSDL-Importers.</span><span class="sxs-lookup"><span data-stu-id="ebbae-110">Configure the client application to use the custom WSDL importer.</span></span> <span data-ttu-id="ebbae-111">Wenn Sie Svcutil.exe verwenden, sollten Sie diese Konfiguration der Konfigurationsdatei für Svcutil.exe (Svcutil.exe.config) hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="ebbae-111">Note that if you are using Svcutil.exe, you should add this configuration to the configuration file for Svcutil.exe (Svcutil.exe.config):</span></span>  
  
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
  
3. <span data-ttu-id="ebbae-112">Erstellen Sie eine neue <xref:System.ServiceModel.Description.WsdlImporter>-Instanz (die dabei <xref:System.ServiceModel.Description.MetadataSet>-Instanz übergibt, die die zu importierenden WSDL-Dokumente enthält), und rufen Sie <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A> auf:</span><span class="sxs-lookup"><span data-stu-id="ebbae-112">Create a new <xref:System.ServiceModel.Description.WsdlImporter> instance (passing in the <xref:System.ServiceModel.Description.MetadataSet> instance that contains the WSDL documents that you want to import), and call <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A>:</span></span>  
  
    ```csharp
    WsdlImporter importer = new WsdlImporter(metaDocs);
    System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ebbae-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ebbae-113">See also</span></span>

- [<span data-ttu-id="ebbae-114">Metadaten</span><span class="sxs-lookup"><span data-stu-id="ebbae-114">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="ebbae-115">Exportieren und Importieren von Metadaten</span><span class="sxs-lookup"><span data-stu-id="ebbae-115">Exporting and Importing Metadata</span></span>](../feature-details/exporting-and-importing-metadata.md)
- [<span data-ttu-id="ebbae-116">Benutzerdefinierte WSDL-Veröffentlichung</span><span class="sxs-lookup"><span data-stu-id="ebbae-116">Custom WSDL Publication</span></span>](../samples/custom-wsdl-publication.md)
