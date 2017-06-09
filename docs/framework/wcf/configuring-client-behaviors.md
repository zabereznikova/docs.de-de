---
title: "Konfigurieren von Clientverhalten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Konfigurieren von Clientverhalten
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] konfiguriert Verhaltensweisen auf zwei Arten: entweder durch Verweisen auf Verhaltenskonfigurationen &\#8211; definiert im `<behavior>`\-Abschnitt der Konfigurationsdatei einer Clientanwendung &\#8211; oder programmgesteuert in der aufrufenden Anwendung.  In diesem Abschnitt werden beide Ansätze beschrieben.  
  
 Bei Verwendung einer Konfigurationsdatei ist die Verhaltenskonfiguration eine benannte Auflistung von Konfigurationseinstellungen.  Der Name jeder Verhaltenskonfiguration muss eindeutig sein.  Diese Zeichenfolge wird im `behaviorConfiguration`\-Attribut einer Endpunktkonfiguration zum Verknüpfen des Endpunkts mit dem Verhalten verwendet.  
  
## Beispiel  
 Der folgende Konfigurationscode definiert ein Verhalten mit der Bezeichnung `myBehavior`.  Der Clientendpunkt verweist im `behaviorConfiguration`\-Attribut auf dieses Verhalten.  
  
```  
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
  
## Programmgesteuertes Verwenden von Verhaltensweisen  
 Verhaltensweisen können auch programmgesteuert konfiguriert oder eingefügt werden. Suchen Sie hierzu vor dem Öffnen des Clients im [!INCLUDE[indigo1](../../../includes/indigo1-md.md)]\-Clientobjekt oder im Clientkanalfactory\-Objekt nach der entsprechenden `Behaviors`\-Eigenschaft.  
  
## Beispiel  
 Im folgenden Codebeispiel wird das programmgesteuerte Einfügen eines Verhaltens durch Zugreifen auf die <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>\-Eigenschaft auf dem <xref:System.ServiceModel.Description.ServiceEndpoint> veranschaulicht, der vor der Erstellung des Kanalobjekts von der <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>\-Eigenschaft zurückgegeben wurde:  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## Siehe auch  
 [\<Verhalten\>](../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)