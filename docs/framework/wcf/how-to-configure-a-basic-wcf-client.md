---
title: "Gewusst wie: Konfigurieren eines grundlegenden Windows Communication Foundation-Clients | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "WCF-Clients [WCF], Konfigurieren"
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
caps.latest.revision: 47
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 47
---
# Gewusst wie: Konfigurieren eines grundlegenden Windows Communication Foundation-Clients
Dies ist die fünfte von sechs Aufgaben, die zum Erstellen einer grundlegenden [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Anwendung erforderlich sind.  Eine Übersicht über alle sechs Aufgaben finden Sie im Thema [Lernprogramm 'Erste Schritte'](../../../docs/framework/wcf/getting-started-tutorial.md).  
  
 In diesem Thema wird die Clientkonfigurationsdatei erläutert, die mithilfe der [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]\-Funktion **Dienstverweis hinzufügen** oder mit dem [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) generiert wurde.  Für die Konfiguration des Clients muss der Endpunkt angegeben werden, den der Client verwendet, um auf den Dienst zuzugreifen.  Ein Endpunkt hat eine Adresse, eine Bindung und einen Vertrag. Bei der Konfiguration eines Clients muss jedes dieser Elemente angegeben werden.  
  
### So konfigurieren Sie einen Windows Communication Foundation\-Client  
  
1.  Öffnen Sie die generierte Konfigurationsdatei \(**App.config**\) aus dem GettingStartedClient\-Projekt.  Im folgenden Beispiel wird der Inhalt der generierten Konfiguration gezeigt.  Unter dem [\<system.serviceModel\>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)\-Abschnitt sehen Sie das [\<endpoint\>](http://msdn.microsoft.com/de-de/13aa23b7-2f08-4add-8dbf-a99f8127c017)\-Element.  
  
    ```  
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
    </configuration><?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
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
  
     In diesem Beispiel wird der Endpunkt konfiguriert, den der Client verwendet, um auf den unter der Adresse **http:\/\/localhost:8000\/ServiceModelSamples\/Service\/CalculatorService** zu findenden Dienst zuzugreifen.  
  
     Das Endpunktelement gibt an, dass für die Kommunikation zwischen dem WCF\-Client und dem Dienst der `ServiceReference1.ICalculator`\-Dienstvertrag verwendet wird.  Der WCF\-Kanal wird mit der vom System bereitgestellten <xref:System.ServiceModel.WsHttpBinding> konfiguriert.  Dieser Vertrag wurde mithilfe der Visual Studio\-Funktion **Dienstverweis hinzufügen** generiert.  Es handelt sich eigentlich um eine Kopie des Vertrags, der im GettingStartedLib\-Projekt definiert wurde.  Die <xref:System.ServiceModel.WsHttpBinding>\-Bindung gibt HTTP als Transport, interoperable Sicherheit und weitere Einzelheiten der Konfiguration an.  
  
2.  [!INCLUDE[crabout](../../../includes/crabout-md.md)] dazu, wie der generierte Client mit dieser Konfiguration verwendet wird, finden Sie unter [Gewusst wie: Verwenden eines Clients](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).  
  
## Siehe auch  
 [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [ServiceModel Metadata Utility\-Tool \(Svcutil.exe\)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)   
 [Vorgehensweise: Erstellen eines Clients](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)   
 [Erste Schritte](../../../docs/framework/wcf/samples/getting-started-sample.md)   
 [Selbst gehostete Dienste](../../../docs/framework/wcf/samples/self-host.md)