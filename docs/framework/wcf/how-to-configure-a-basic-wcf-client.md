---
title: 'Gewusst wie: Konfigurieren eines grundlegenden Windows Communication Foundation-Clients'
ms.date: 03/30/2017
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: 2866cbd5862bf55286fc771823488cf913863de2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43466570"
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a>Gewusst wie: Konfigurieren eines grundlegenden Windows Communication Foundation-Clients
Dies ist die fünfte von sechs Aufgaben, die zum Erstellen einer grundlegenden Windows Communication Foundation (WCF)-Anwendung erforderlich sind. Eine Übersicht über alle sechs Aufgaben finden Sie im Artikel [Getting Started Tutorial (Tutorial: Erste Schritte)](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 In diesem Thema wird erläutert, die Clientkonfigurationsdatei, die generiert wurde, mithilfe der Funktion "Dienstverweis hinzufügen" von [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] oder [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md). Für die Konfiguration des Clients muss der Endpunkt angegeben werden, den der Client verwendet, um auf den Dienst zuzugreifen. Ein Endpunkt hat eine Adresse, eine Bindung und einen Vertrag. Bei der Konfiguration eines Clients muss jedes dieser Elemente angegeben werden.  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a>So konfigurieren Sie einen Windows Communication Foundation-Client  
  
1.  Öffnen Sie die generierte Konfigurationsdatei (App.config) aus dem GettingStartedClient-Projekt. Im folgenden Beispiel wird der Inhalt der generierten Konfiguration gezeigt. Unter den [ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Abschnitt, suchen Sie nach der [ \<Endpunkt >](https://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017) Element.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
          <!-- specifies the version of WCF to use-->  
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <!-- Uses wsHttpBinding-->  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <!-- specifies the endpoint to use when calling the service -->  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration>   
    ```  
  
     In diesem Beispiel wird den Endpunkt, den der Client verwendet, um den Zugriff auf den Dienst, der sich unter folgender Adresse befindet: http://localhost:8000/ServiceModelSamples/Service/CalculatorService  
  
     Das Endpunktelement gibt an, dass für die Kommunikation zwischen dem WCF-Client und dem Dienst der `ServiceReference1.ICalculator`-Dienstvertrag verwendet wird. Der WCF-Kanal wird mit der vom System bereitgestellten <xref:System.ServiceModel.WSHttpBinding> konfiguriert. Dieser Vertrag wurde mithilfe der Visual Studio-Funktion Dienstverweis hinzufügen generiert. Es handelt sich eigentlich um eine Kopie des Vertrags, der im GettingStartedLib-Projekt definiert wurde. Die <xref:System.ServiceModel.WSHttpBinding>-Bindung gibt HTTP als Transport, interoperable Sicherheit und weitere Einzelheiten der Konfiguration an.  
  
2.  Weitere Informationen zur Verwendung des generierten Clients mit dieser Konfiguration finden Sie unter [Vorgehensweise: Verwenden Sie einen Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [ServiceModel Metadata Utility-Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)
