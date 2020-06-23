---
title: Konfigurieren von Clientverhalten
description: 'Erfahren Sie mehr über die zwei Möglichkeiten, wie WCF das Verhalten konfiguriert: in der Anwendungs Konfigurationsdatei oder Programm gesteuert von der aufrufenden Anwendung.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 4b83862221cf249455478c3ade159a3101062f3e
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245439"
---
# <a name="configuring-client-behaviors"></a>Konfigurieren von Clientverhalten
Windows Communication Foundation (WCF) konfiguriert Verhalten auf zwei Arten: entweder durch den Verweis auf Verhaltens Konfigurationen, die im `<behavior>` Abschnitt einer Client Anwendungs Konfigurationsdatei definiert sind – oder Programm gesteuert in der aufrufenden Anwendung. In diesem Abschnitt werden beide Ansätze beschrieben.  
  
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
 Sie können Verhaltensweisen auch Programm gesteuert konfigurieren oder einfügen, indem Sie die entsprechende `Behaviors` Eigenschaft für das Windows Communication Foundation (WCF)-Client Objekt oder das clientkanalfactoryobjekt vor dem Öffnen des Clients suchen.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird das programmgesteuerte Einfügen eines Verhaltens durch Zugreifen auf die <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>-Eigenschaft auf dem <xref:System.ServiceModel.Description.ServiceEndpoint> veranschaulicht, der vor der Erstellung des Kanalobjekts von der <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>-Eigenschaft zurückgegeben wurde:  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a>Weitere Informationen

- [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)
