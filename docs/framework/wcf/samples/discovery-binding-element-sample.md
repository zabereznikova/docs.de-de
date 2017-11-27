---
title: "Beispiel für Ermittlungsbindungselement"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af513015-85bf-417b-8729-1bdff77ff6d6
caps.latest.revision: "12"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 821f629a7f39869975af19c793fe26188a40d7d6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="discovery-binding-element-sample"></a>Beispiel für Ermittlungsbindungselement
In diesem Beispiel wird gezeigt, wie das Ermittlungsclient-Bindungselement verwendet wird, um einen Dienst zu ermitteln. Diese Funktion ermöglicht es Entwicklern, ihrem vorhandenen Clientkanalstapel einen Ermittlungsclientkanal hinzuzufügen. Dadurch wird das Programmiermodell sehr intuitiv. Wenn der zugeordnete Kanal geöffnet wird, wird die Adresse des Diensts mit der Ermittlung aufgelöst. Dieses Beispiel besteht aus den folgenden Projekten:  
  
-   **CalculatorService**: ein ermittelbarer [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Dienst.  
  
-   **CalculatorClient**: ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Clientanwendung, den Discovery Clientchannel zu suchen, und rufen Sie den CalculatorService verwendet.  
  
-   **DynamicCalculatorClient**: ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Clientanwendung, die mit einem dynamischen Endpunkt gesucht und den CalculatorService aufrufen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryBindingElement`  
  
## <a name="calculatorservice"></a>CalculatorService  
 Dieses Projekt enthält einen einfachen Rechnerdienst, der den `ICalculatorService`-Vertrag implementiert.  
  
 Die folgende APP.CONFIG-Datei wird verwendet, um ein `<serviceDiscovery>`-Verhalten zum Dienstverhalten und zum Ermittlungsendpunkt hinzuzufügen.  
  
```xml  
<system.serviceModel>  
    <services>  
      <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">  
        <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <!--Enable discovery through configuration.-->  
      <serviceBehaviors>  
        <behavior name="CalculatorBehavior">  
          <serviceDiscovery>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 Dadurch werden der Dienst und seine Endpunkte ermittelbar. Der CalculatorService ist ein selbst gehosteter Dienst, der mit der NetTcpBinding-Bindung einen Endpunkt hinzufügt. Zudem wird dem Endpunkt ein `EndpointDiscoveryBehavior` hinzugefügt und ein Bereich angegeben, wie im folgenden Code gezeigt.  
  
```  
// Add a NET.TCP endpoint and add a scope to that endpoint.  
ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new NetTcpBinding(), netTcpAddress);  
EndpointDiscoveryBehavior netTctEndpointBehavior = new EndpointDiscoveryBehavior();  
netTctEndpointBehavior.Scopes.Add(new Uri("ldap:///ou=engineering,o=exampleorg,c=us"));  
netTcpEndpoint.Behaviors.Add(netTctEndpointBehavior);  
serviceHost.Open();  
```  
  
## <a name="calculatorclient"></a>CalculatorClient  
 Dieses Projekt enthält eine Clientimplementierung, mit der Meldungen an den CalculatorService gesendet werden. Das Programm erstellt mithilfe der `CreateCustomBindingWithDiscoveryElement()`-Methode eine benutzerdefinierte Bindung, die den Ermittlungsclientkanal verwendet.  
  
```  
static CustomBinding CreateCustomBindingWithDiscoveryElement()  
 {  
      DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
            // Provide the search criteria and the endpoint over which the probe is sent  
            discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
            discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
            CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
            // Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
            // An exception is thrown if this binding element is not at the top  
            customBinding.Elements.Insert(0, discoveryBindingElement);  
  
            return customBinding; }  
```  
  
 Nachdem das <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> instanziiert wurde, gibt der Entwickler die Kriterien an, die bei der Suche nach einem Dienst verwendet werden sollen. In diesem Fall ist das Ermittlungssuchkriterium der `ICalculatorService`-Typ. Darüber hinaus gibt der Entwickler einen <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> an, der einen <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> zurückgibt, mit dem angegeben wird, wo nach den Diensten gesucht werden soll. Der <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> gibt eine neue <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>-Instanz zurück. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Mit einer benutzerdefinierten Bindung mit der Discovery-Clientchannel](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md).  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
    // to the DiscoveryClientBindingElement. The Discovery ClientChannel   
    // uses this endpoint to send Probe message.  
    public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
    {  
        public override DiscoveryEndpoint GetDiscoveryEndpoint()  
        {  
            return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
        }  
    }  
```  
  
 In diesem Fall verwendet der Client den UDP-Multicastmechanismus, der im Discovery-Protokoll definiert wird, um nach Diensten im lokalen Subnetz zu suchen. Mit dem Rest der Methode wird eine benutzerdefinierte Bindung erstellt und das Discovery-Bindungselement zu Beginn des Stapels eingefügt.  
  
> [!NOTE]
>  Das <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> muss zu Beginn des Bindungsstapels eingefügt werden. Für jedes <xref:System.ServiceModel.Channels.BindingElement> vor dem <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> muss sichergestellt werden, dass die erstellte Kanalfactory oder der erstellte Kanal nicht die `EndpointAddress`-Eigenschaft oder die `Via`-Eigenschaft verwendet, da die tatsächliche Adresse nur im Discovery-Clientkanal gefunden werden kann.  
  
 Als Nächstes kann der `CalculatorClient` instanziiert werden, indem diese benutzerdefinierte Bindung sowie eine Endpunktadresse übergeben werden.  
  
```  
CalculatorServiceClient client = new CalculatorServiceClient(CreateCustomBindingWithDiscoveryElement(), DiscoveryClientBindingElement.DiscoveryEndpointAddress);  
```  
  
 Wenn Sie den Ermittlungsclientkanal verwenden, wird die zuvor angegebene konstante Endpunktadresse übergeben. Zur Laufzeit findet der Ermittlungsclientkanal den angegebenen Dienst mithilfe der Suchkriterien und stellt eine Verbindung mit ihm her. Damit der Dienst und der Client eine Verbindung herstellen können, müssen sie außerdem über denselben zugrunde liegenden Bindungsstapel verfügen.  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Öffnen Sie die Projektmappe in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
2.  Erstellen Sie die Projektmappe.  
  
3.  Führen Sie die Dienstanwendung und alle Clientanwendungen aus.  
  
4.  Beachten Sie, dass der Client den Dienst ermitteln konnte, ohne seine Adresse zu kennen.  
  
## <a name="see-also"></a>Siehe auch
