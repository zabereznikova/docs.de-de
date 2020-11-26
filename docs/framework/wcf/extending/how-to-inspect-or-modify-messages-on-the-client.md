---
title: 'Vorgehensweise: Überprüfen oder Ändern von Nachrichten auf dem Client'
description: Erfahren Sie, wie Sie eingehende oder ausgehende Nachrichten über einen WCF-Client oder-Dienst überprüfen oder ändern, indem Sie die entsprechende Schnittstelle implementieren
ms.date: 03/30/2017
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
ms.openlocfilehash: 1f8b75001754739b48d10ee577ae26a175e72860
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249045"
---
# <a name="how-to-inspect-or-modify-messages-on-the-client"></a>Vorgehensweise: Überprüfen oder Ändern von Nachrichten auf dem Client

Sie können die eingehenden oder ausgehenden Nachrichten über einen WCF-Client überprüfen oder ändern, indem Sie einen implementieren <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> und ihn in die Client Laufzeit einfügen. Weitere Informationen finden Sie unter [Erweitern von Clients](extending-clients.md). Die entsprechende Funktion für den Dienst ist der <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>. Ein umfassendes Codebeispiel finden Sie im Beispiel für [Nachrichten Inspektoren](../samples/message-inspectors.md) .  
  
### <a name="to-inspect-or-modify-messages"></a>So überprüfen oder ändern Sie Nachrichten  
  
1. Implementieren Sie die <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>-Schnittstelle.  
  
2. Implementieren Sie ein <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> oder <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>, je nach dem Bereich, in dem Sie den Clientnachrichteninspektor einfügen möchten. <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> ermöglicht das Ändern des Verhaltens auf Endpunkt Ebene. <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> ermöglicht es Ihnen, das Verhalten auf Vertrags Ebene zu ändern.  
  
3. Fügen Sie das Verhalten ein, bevor Sie die <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>-Methode oder die <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType>-Methode für die <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> aufrufen. Weitere Informationen finden Sie unter [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Beispiel  

 Die unten aufgeführten Codebeispiele zeigen der Reihe nach Folgendes:  
  
- Eine Clientinspektorimplementierung.  
  
- Ein Endpunktverhalten, das den Inspektor einfügt.  
  
- Eine von <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> abgeleitete Klasse, mit der Sie das Verhalten einer Konfigurationsdatei hinzufügen können.  
  
- Eine Konfigurationsdatei, die das Endpunktverhalten hinzufügt, das den Clientnachrichteninspektor in die Clientlaufzeit einfügt.  
  
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
  
```xml
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
    <system.serviceModel>  
        <client>  
            <endpoint address="http://localhost:8080/SimpleService/"
                      binding="wsHttpBinding"
                      behaviorConfiguration="clientInspectorsAdded"
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
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [Konfigurieren und Erweitern der Laufzeit mit Verhalten](configuring-and-extending-the-runtime-with-behaviors.md)
