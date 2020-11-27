---
title: 'Vorgehensweise: Schreiben einer Erweiterung für die ServiceContractGenerator-Klasse'
ms.date: 03/30/2017
ms.assetid: 876ca823-bd16-4bdf-9e0f-02092df90e51
ms.openlocfilehash: 3a81204ca470b9b94d9e8f048ecccbade74b2e10
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254635"
---
# <a name="how-to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="0b97a-102">Vorgehensweise: Schreiben einer Erweiterung für die ServiceContractGenerator-Klasse</span><span class="sxs-lookup"><span data-stu-id="0b97a-102">How to: Write an Extension for the ServiceContractGenerator</span></span>

<span data-ttu-id="0b97a-103">In diesem Thema wird beschrieben, wie Sie eine Erweiterung für den <xref:System.ServiceModel.Description.ServiceContractGenerator> schreiben können.</span><span class="sxs-lookup"><span data-stu-id="0b97a-103">This topic describes how to write an extension for the <xref:System.ServiceModel.Description.ServiceContractGenerator>.</span></span> <span data-ttu-id="0b97a-104">Dies kann durch Implementieren der <xref:System.ServiceModel.Description.IOperationContractGenerationExtension>-Schnittstelle für ein Vorgangsverhalten oder Implementieren der <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>-Schnittstelle für ein Vertragsverhalten geschehen.</span><span class="sxs-lookup"><span data-stu-id="0b97a-104">This can be done by implementing the <xref:System.ServiceModel.Description.IOperationContractGenerationExtension> interface on an operation behavior or implementing the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span> <span data-ttu-id="0b97a-105">In diesem Thema wird gezeigt, wie die <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>-Schnittstelle in einem Vertragsverhalten implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="0b97a-105">This topic shows how to implement the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> interface on a contract behavior.</span></span>  
  
 <span data-ttu-id="0b97a-106">Der <xref:System.ServiceModel.Description.ServiceContractGenerator> erstellt aus <xref:System.ServiceModel.Description.ServiceEndpoint>-Instanzen, <xref:System.ServiceModel.Description.ContractDescription>-Instanzen und <xref:System.ServiceModel.Channels.Binding>-Instanzen Dienstverträge, Clienttypen und Clientkonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="0b97a-106">The <xref:System.ServiceModel.Description.ServiceContractGenerator> generates service contracts, client types, and client configurations from <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances.</span></span> <span data-ttu-id="0b97a-107">Normalerweise importieren Sie <xref:System.ServiceModel.Description.ServiceEndpoint>-Instanzen, <xref:System.ServiceModel.Description.ContractDescription>-Instanzen und <xref:System.ServiceModel.Channels.Binding>-Instanzen aus Dienstmetadaten und verwenden dann diese Instanzen, um den Code zum Aufrufen des Dienstes zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="0b97a-107">Typically, you import <xref:System.ServiceModel.Description.ServiceEndpoint>, <xref:System.ServiceModel.Description.ContractDescription>, and <xref:System.ServiceModel.Channels.Binding> instances from service metadata and then use these instances to generate code to call the service.</span></span> <span data-ttu-id="0b97a-108">In diesem Beispiel wird eine <xref:System.ServiceModel.Description.IWsdlImportExtension>-Implementierung zur Verarbeitung von WSDL-Anmerkungen verwendet. Dann werden Codegenerierungserweiterungen in die importierten Verträge eingefügt, um Kommentare zu dem generierten Code zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0b97a-108">In this example, an <xref:System.ServiceModel.Description.IWsdlImportExtension> implementation is used to process WSDL annotations and then add code generation extensions to the imported contracts to generate comments on the generated code.</span></span>  
  
### <a name="to-write-an-extension-for-the-servicecontractgenerator"></a><span data-ttu-id="0b97a-109">So schreiben Sie eine Erweiterung für den ServiceContractGenerator</span><span class="sxs-lookup"><span data-stu-id="0b97a-109">To write an extension for the ServiceContractGenerator</span></span>  
  
1. <span data-ttu-id="0b97a-110">Implementieren Sie <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span><span class="sxs-lookup"><span data-stu-id="0b97a-110">Implement <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="0b97a-111">Verwenden Sie zum Bearbeiten des generierten Dienstvertrags die <xref:System.ServiceModel.Description.ServiceContractGenerationContext>-Instanz, die an die <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29>-Methode weitergegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="0b97a-111">To modify the generated service contract, use the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> instance passed into the <xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> method.</span></span>  
  
    ```csharp
    public void GenerateContract(ServiceContractGenerationContext context)  
    {  
        Console.WriteLine("In generate contract.");  
        context.ContractType.Comments.AddRange(Formatter.FormatComments(commentText));  
    }  
    ```  
  
2. <span data-ttu-id="0b97a-112">Implementieren Sie <xref:System.ServiceModel.Description.IWsdlImportExtension> für die gleiche Klasse.</span><span class="sxs-lookup"><span data-stu-id="0b97a-112">Implement <xref:System.ServiceModel.Description.IWsdlImportExtension> on the same class.</span></span> <span data-ttu-id="0b97a-113">Mit der <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>-Methode kann eine bestimmte WSDL-Erweiterung (in diesem Fall WSDL-Anmerkungen) verarbeitet werden, indem eine Codegenerierungserweiterung der importierten <xref:System.ServiceModel.Description.ContractDescription>-Instanz hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="0b97a-113">The <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29> method can process a specific WSDL extension (WSDL annotations in this case) by adding a code generation extension to the imported <xref:System.ServiceModel.Description.ContractDescription> instance.</span></span>  
  
    ```csharp
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
  
3. <span data-ttu-id="0b97a-114">Fügen Sie den WSDL-Importer in Ihre Clientkonfiguration ein.</span><span class="sxs-lookup"><span data-stu-id="0b97a-114">Add the WSDL importer to your client configuration.</span></span>  
  
    ```xml  
    <metadata>  
      <wsdlImporters>  
        <extension type="Microsoft.WCF.Documentation.WsdlDocumentationImporter, WsdlDocumentation" />  
      </wsdlImporters>  
    </metadata>  
    ```  
  
4. <span data-ttu-id="0b97a-115">Erstellen Sie im Clientcode einen `MetadataExchangeClient`, und rufen Sie `GetMetadata` auf.</span><span class="sxs-lookup"><span data-stu-id="0b97a-115">In the client code, create a `MetadataExchangeClient` and call `GetMetadata`.</span></span>  
  
    ```csharp
    var mexClient = new MetadataExchangeClient(metadataAddress);  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet metaDocs = mexClient.GetMetadata();  
    ```  
  
5. <span data-ttu-id="0b97a-116">Erstellen Sie einen `WsdlImporter`, und rufen Sie `ImportAllContracts` auf.</span><span class="sxs-lookup"><span data-stu-id="0b97a-116">Create a `WsdlImporter` and call `ImportAllContracts`.</span></span>  
  
    ```csharp
    var importer = new WsdlImporter(metaDocs);
    System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
6. <span data-ttu-id="0b97a-117">Erstellen Sie einen `ServiceContractGenerator`, und rufen Sie den `GenerateServiceContractType` für jeden Vertrag auf.</span><span class="sxs-lookup"><span data-stu-id="0b97a-117">Create a `ServiceContractGenerator` and call `GenerateServiceContractType` for each contract.</span></span>  
  
    ```csharp
    var generator = new ServiceContractGenerator();  
    foreach (ContractDescription contract in contracts)  
    {  
       generator.GenerateServiceContractType(contract);  
    }  
    if (generator.Errors.Count != 0)  
       throw new Exception("There were errors during code compilation.");  
    ```  
  
7. <span data-ttu-id="0b97a-118"><xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> wird automatisch für jedes Vertragsverhalten für einen bestimmten Vertrag, der <xref:System.ServiceModel.Description.IServiceContractGenerationExtension> implementiert, aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="0b97a-118"><xref:System.ServiceModel.Description.IServiceContractGenerationExtension.GenerateContract%28System.ServiceModel.Description.ServiceContractGenerationContext%29> is called automatically for each contract behavior on a given contract that implements <xref:System.ServiceModel.Description.IServiceContractGenerationExtension>.</span></span> <span data-ttu-id="0b97a-119">Diese Methode kann dann den übergebenen <xref:System.ServiceModel.Description.ServiceContractGenerationContext> ändern.</span><span class="sxs-lookup"><span data-stu-id="0b97a-119">This method can then modify the <xref:System.ServiceModel.Description.ServiceContractGenerationContext> passed in.</span></span> <span data-ttu-id="0b97a-120">In diesem Beispiel werden Kommentare hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0b97a-120">In this example comments are added.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b97a-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b97a-121">See also</span></span>

- [<span data-ttu-id="0b97a-122">Metadaten</span><span class="sxs-lookup"><span data-stu-id="0b97a-122">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="0b97a-123">Vorgehensweise: Importieren von benutzerdefinierten WSDL-Informationen</span><span class="sxs-lookup"><span data-stu-id="0b97a-123">How to: Import Custom WSDL</span></span>](how-to-import-custom-wsdl.md)
