---
title: 'Vorgehensweise: Überprüfen oder Ändern von Nachrichten auf dem Client'
ms.date: 03/30/2017
ms.assetid: b8256335-f1c2-419f-b862-9f220ccad84c
ms.openlocfilehash: 67fa0e092e6494ff55d71e666b5137cfc9a3069e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343297"
---
# <a name="how-to-inspect-or-modify-messages-on-the-client"></a>Vorgehensweise: Überprüfen oder Ändern von Nachrichten auf dem Client
Sie können überprüfen, oder ändern Sie die eingehenden oder ausgehenden Nachrichten für einen WCF-Client, durch die Implementierung einer <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType> und in die Clientlaufzeit einfügen. Weitere Informationen finden Sie unter [Erweitern von Clients](../../../../docs/framework/wcf/extending/extending-clients.md). Die entsprechende Funktion für den Dienst ist der <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>. Ein vollständiges Codebeispiel finden Sie unter den [Nachrichteninspektoren](../../../../docs/framework/wcf/samples/message-inspectors.md) Beispiel.  
  
### <a name="to-inspect-or-modify-messages"></a>So überprüfen oder ändern Sie Nachrichten  
  
1. Implementieren Sie die <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>-Schnittstelle.  
  
2. Implementieren Sie ein <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> oder <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType>, je nach dem Bereich, in dem Sie den Clientnachrichteninspektor einfügen möchten. <xref:System.ServiceModel.Description.IEndpointBehavior?displayProperty=nameWithType> können Sie das Verhalten auf Endpunktebene ändern. <xref:System.ServiceModel.Description.IContractBehavior?displayProperty=nameWithType> können Sie das Verhalten auf Vertragsebene ändern.  
  
3. Fügen Sie das Verhalten ein, bevor Sie die <xref:System.ServiceModel.ClientBase%601.Open%2A?displayProperty=nameWithType>-Methode oder die <xref:System.ServiceModel.ICommunicationObject.Open%2A?displayProperty=nameWithType>-Methode für die <xref:System.ServiceModel.ChannelFactory%601?displayProperty=nameWithType> aufrufen. Weitere Informationen finden Sie unter [konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md).  
  
## <a name="example"></a>Beispiel  
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
  
## <a name="see-also"></a>Siehe auch

- <xref:System.ServiceModel.Dispatcher.IClientMessageInspector?displayProperty=nameWithType>
- <xref:System.ServiceModel.Dispatcher.IDispatchMessageInspector?displayProperty=nameWithType>
- [Konfigurieren und Erweitern der Laufzeit mit Verhalten](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)
