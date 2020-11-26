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
# <a name="how-to-import-custom-wsdl"></a>Vorgehensweise: Importieren von benutzerdefinierten WSDL-Informationen

In diesem Thema wird beschrieben, wie Sie benutzerdefinierte WSDL importieren. Zum Behandeln der benutzerdefinierten WSDL müssen Sie die <xref:System.ServiceModel.Description.IWsdlImportExtension>-Schnittstelle implementieren.  
  
### <a name="to-import-custom-wsdl"></a>So importieren Sie benutzerdefinierte WSDL  
  
1. Implementieren Sie <xref:System.ServiceModel.Description.IWsdlImportExtension>. Implementieren Sie die <xref:System.ServiceModel.Description.IWsdlImportExtension.BeforeImport%28System.Web.Services.Description.ServiceDescriptionCollection%2CSystem.Xml.Schema.XmlSchemaSet%2CSystem.Collections.Generic.ICollection%7BSystem.Xml.XmlElement%7D%29>-Methode, um die Metadaten vor dem Import zu ändern. Implementieren Sie die <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportEndpoint%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlEndpointConversionContext%29>-Methode und die <xref:System.ServiceModel.Description.IWsdlImportExtension.ImportContract%28System.ServiceModel.Description.WsdlImporter%2CSystem.ServiceModel.Description.WsdlContractConversionContext%29>-Methode, um aus den Metadaten importierte Verträge und Endpunkte zu ändern. Verwenden Sie zum Zugriff auf den importierten Vertrag oder Endpunkt das entsprechende Kontextobjekt (<xref:System.ServiceModel.Description.WsdlContractConversionContext> oder <xref:System.ServiceModel.Description.WsdlEndpointConversionContext>):  
  
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
  
2. Konfigurieren Sie die Clientanwendung für die Verwendung des benutzerdefinierten WSDL-Importers. Wenn Sie Svcutil.exe verwenden, sollten Sie diese Konfiguration der Konfigurationsdatei für Svcutil.exe (Svcutil.exe.config) hinzufügen:  
  
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
  
3. Erstellen Sie eine neue <xref:System.ServiceModel.Description.WsdlImporter>-Instanz (die dabei <xref:System.ServiceModel.Description.MetadataSet>-Instanz übergibt, die die zu importierenden WSDL-Dokumente enthält), und rufen Sie <xref:System.ServiceModel.Description.WsdlImporter.ImportAllContracts%2A> auf:  
  
    ```csharp
    WsdlImporter importer = new WsdlImporter(metaDocs);
    System.Collections.ObjectModel.Collection<ContractDescription> contracts = importer.ImportAllContracts();  
    ```  
  
## <a name="see-also"></a>Weitere Informationen

- [Metadaten](../feature-details/metadata.md)
- [Exportieren und Importieren von Metadaten](../feature-details/exporting-and-importing-metadata.md)
- [Benutzerdefinierte WSDL-Veröffentlichung](../samples/custom-wsdl-publication.md)
