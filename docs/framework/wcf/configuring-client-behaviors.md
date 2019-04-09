---
title: Konfigurieren von Clientverhalten
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 83fdc77bd17115f9952f2ca6c494ed0eb873cd9c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59193654"
---
# <a name="configuring-client-behaviors"></a>Konfigurieren von Clientverhalten
Windows Communication Foundation (WCF) konfiguriert Verhaltensweisen auf zwei Arten: entweder durch das Verweisen auf verhaltenskonfigurationen – die definiert sind die `<behavior>` Abschnitt einer Konfigurationsdatei für den Client-Anwendung – oder programmgesteuert in der aufrufenden die Anwendung. In diesem Abschnitt werden beide Ansätze beschrieben.  
  
 Bei Verwendung einer Konfigurationsdatei ist die Verhaltenskonfiguration eine benannte Auflistung von Konfigurationseinstellungen. Der Name jeder Verhaltenskonfiguration muss eindeutig sein. Diese Zeichenfolge wird im `behaviorConfiguration`-Attribut einer Endpunktkonfiguration zum Verknüpfen des Endpunkts mit dem Verhalten verwendet.  
  
## <a name="example"></a>Beispiel  
 Der folgende Konfigurationscode definiert ein Verhalten mit der Bezeichnung `myBehavior`. Der Clientendpunkt verweist im `behaviorConfiguration`-Attribut auf dieses Verhalten.  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
            <endpointBehaviors>  
                <behavior name="myBehavior">  
                    <clientVia />  
                </behavior>  
            </endpointBehaviors>  
        </behaviors>  
        <bindings>  
            <basicHttpBinding>  
                <binding name="myBinding" maxReceivedMessageSize="10000" />  
            </basicHttpBinding>  
        </bindings>  
        <client>  
            <endpoint address="myAddress" binding="basicHttpBinding" bindingConfiguration="myBinding" behaviorConfiguration="myBehavior" contract="myContract" />  
        </client>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-behaviors-programmatically"></a>Programmgesteuertes Verwenden von Verhaltensweisen  
 Können Sie auch konfigurieren oder Programmgesteuertes Einfügen von Verhalten dazu sucht er die entsprechende `Behaviors` -Eigenschaft für das Windows Communication Foundation (WCF)-Clientobjekt oder auf die clientkanalfactory-Objekt vor dem Öffnen des Clients.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird das programmgesteuerte Einfügen eines Verhaltens durch Zugreifen auf die <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>-Eigenschaft auf dem <xref:System.ServiceModel.Description.ServiceEndpoint> veranschaulicht, der vor der Erstellung des Kanalobjekts von der <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>-Eigenschaft zurückgegeben wurde:  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a>Siehe auch

- [\<behaviors>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)
