---
title: "Vorgehensweise: &#220;berpr&#252;fen oder &#196;ndern von Nachrichten auf dem Client | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
caps.latest.revision: 6
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 6
---
# Vorgehensweise: &#220;berpr&#252;fen oder &#196;ndern von Nachrichten auf dem Client
Sie können die eingehenden oder ausgehenden Nachrichten für einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Client überprüfen oder ändern, indem Sie einen <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName> implementieren und in die Clientlaufzeit einfügen.  Weitere Informationen finden Sie unter [Erweitern von Clients](../../../../docs/framework/wcf/extending/extending-clients.md).  Die entsprechende Funktion für den Dienst ist der <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName>.  Ein vollständiges Codebeispiel finden Sie im Beispiel für [Nachrichteninspektoren](../../../../docs/framework/wcf/samples/message-inspectors.md).  
  
### So überprüfen oder ändern Sie Nachrichten  
  
1.  Implementieren Sie die <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>\-Schnittstelle.  
  
2.  Implementieren Sie ein <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName> oder <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName>, je nach dem Bereich, in dem Sie den Clientnachrichteninspektor einfügen möchten.  Mit <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=fullName> können Sie das Verhalten auf Endpunktebene ändern.  Mit <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=fullName> können Sie das Verhalten auf Vertragsebene ändern.  
  
3.  Fügen Sie das Verhalten ein, bevor Sie die <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=fullName>\-Methode oder die <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=fullName>\-Methode für die <xref:System.ServiceModel.ChannelFactory%601?displayProperty=fullName> aufrufen.  Ausführliche Informationen finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## Beispiel  
 Die unten aufgeführten Codebeispiele zeigen der Reihe nach Folgendes:  
  
-   Eine Clientinspektorimplementierung.  
  
-   Ein Endpunktverhalten, das den Inspektor einfügt.  
  
-   Eine von <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> abgeleitete Klasse, mit der Sie das Verhalten einer Konfigurationsdatei hinzufügen können.  
  
-   Eine Konfigurationsdatei, die das Endpunktverhalten hinzufügt, das den Clientnachrichteninspektor in die Clientlaufzeit einfügt.  
  
```csharp  
// Client message inspector  
public class SimpleMessageInspector : IClientMessageInspector  
{  
    public void AfterReceiveReply(ref System.ServiceModel.Channels.Message reply, object correlationState)  
    {  
        // Implement this method to inspect/modify messages after a message  
        // is received but prior to passing it back to the client   
        Console.WriteLine("AfterReceiveReply called");  
    }  
  
    public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, IClientChannel channel)  
    {  
        // Implement this method to inspect/modify messages before they   
        // are sent to the service  
        Console.WriteLine("BeforeSendRequest called");  
        return null;  
    }  
}  
  
```  
  
```csharp  
// Endpoint behavior  
public class SimpleEndpointBehavior : IEndpointBehavior  
{  
    public void AddBindingParameters(ServiceEndpoint endpoint, System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
    {  
         // No implementation necessary  
    }  
  
    public void ApplyClientBehavior(ServiceEndpoint endpoint, ClientRuntime clientRuntime)  
    {  
        clientRuntime.MessageInspectors.Add(new SimpleMessageInspector());  
    }  
  
    public void ApplyDispatchBehavior(ServiceEndpoint endpoint, EndpointDispatcher endpointDispatcher)  
    {  
         // No implementation necessary  
    }  
  
    public void Validate(ServiceEndpoint endpoint)  
    {  
         // No implementation necessary  
    }  
}  
```  
  
```csharp  
// Configuration element   
public class SimpleBehaviorExtensionElement : BehaviorExtensionElement  
{  
    public override Type BehaviorType  
    {  
        get { return typeof(SimpleEndpointBehavior); }  
    }  
  
    protected override object CreateBehavior()  
    {  
         // Create the  endpoint behavior that will insert the message  
         // inspector into the client runtime  
        return new SimpleEndpointBehavior();  
    }  
}  
  
```  
  
```vb  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <system.serviceModel>  
        <client>  
            <endpoint address="http://localhost:8080/SimpleService/"   
                      binding="wsHttpBinding"  
                      contract="ServiceReference1.IService1"  
                      name="WSHttpBinding_IService1"/>  
        </client>  
  
      <behaviors>  
        <endpointBehaviors>  
          <behavior name="clientInspectorsAdded">  
            <simpleBehaviorExtension />  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <extensions>  
        <behaviorExtensions>  
          <add  
            name="simpleBehaviorExtension"  
            type="SimpleServiceLib.SimpleBehaviorExtensionElement, Host, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null"/>  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
</configuration>  
  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=fullName>   
 <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=fullName>   
 [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)