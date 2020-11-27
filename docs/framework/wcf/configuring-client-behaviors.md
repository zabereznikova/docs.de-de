---
title: Konfigurieren von Clientverhalten
description: 'Erfahren Sie mehr über die zwei Möglichkeiten, wie WCF das Verhalten konfiguriert: in der Anwendungs Konfigurationsdatei oder Programm gesteuert von der aufrufenden Anwendung.'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: df5b32fa-e73b-4e8e-b66f-357c748e0173
ms.openlocfilehash: 34cbb9e31933debb5120eb30956c3a5f0be065ed
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96266713"
---
# <a name="configuring-client-behaviors"></a><span data-ttu-id="9dacb-103">Konfigurieren von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="9dacb-103">Configuring Client Behaviors</span></span>

<span data-ttu-id="9dacb-104">Windows Communication Foundation (WCF) konfiguriert Verhalten auf zwei Arten: entweder durch den Verweis auf Verhaltens Konfigurationen, die im `<behavior>` Abschnitt einer Client Anwendungs Konfigurationsdatei definiert sind – oder Programm gesteuert in der aufrufenden Anwendung.</span><span class="sxs-lookup"><span data-stu-id="9dacb-104">Windows Communication Foundation (WCF) configures behaviors in two ways: either by referring to behavior configurations -- which are defined in the `<behavior>` section of a client application configuration file – or programmatically in the calling application.</span></span> <span data-ttu-id="9dacb-105">In diesem Abschnitt werden beide Ansätze beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9dacb-105">This topic describes both approaches.</span></span>  
  
 <span data-ttu-id="9dacb-106">Bei Verwendung einer Konfigurationsdatei ist die Verhaltenskonfiguration eine benannte Auflistung von Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9dacb-106">When using a configuration file, behavior configuration is a named collection of configuration settings.</span></span> <span data-ttu-id="9dacb-107">Der Name jeder Verhaltenskonfiguration muss eindeutig sein.</span><span class="sxs-lookup"><span data-stu-id="9dacb-107">The name of each behavior configuration must be unique.</span></span> <span data-ttu-id="9dacb-108">Diese Zeichenfolge wird im `behaviorConfiguration`-Attribut einer Endpunktkonfiguration zum Verknüpfen des Endpunkts mit dem Verhalten verwendet.</span><span class="sxs-lookup"><span data-stu-id="9dacb-108">This string is used in the `behaviorConfiguration` attribute of an endpoint configuration to link the endpoint to the behavior.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dacb-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dacb-109">Example</span></span>  

 <span data-ttu-id="9dacb-110">Der folgende Konfigurationscode definiert ein Verhalten mit der Bezeichnung `myBehavior`.</span><span class="sxs-lookup"><span data-stu-id="9dacb-110">The following configuration code defines a behavior called `myBehavior`.</span></span> <span data-ttu-id="9dacb-111">Der Clientendpunkt verweist im `behaviorConfiguration`-Attribut auf dieses Verhalten.</span><span class="sxs-lookup"><span data-stu-id="9dacb-111">The client endpoint references this behavior in the `behaviorConfiguration` attribute.</span></span>  
  
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
  
## <a name="using-behaviors-programmatically"></a><span data-ttu-id="9dacb-112">Programmgesteuertes Verwenden von Verhaltensweisen</span><span class="sxs-lookup"><span data-stu-id="9dacb-112">Using Behaviors Programmatically</span></span>  

 <span data-ttu-id="9dacb-113">Sie können Verhaltensweisen auch Programm gesteuert konfigurieren oder einfügen, indem Sie die entsprechende `Behaviors` Eigenschaft für das Windows Communication Foundation (WCF)-Client Objekt oder das clientkanalfactoryobjekt vor dem Öffnen des Clients suchen.</span><span class="sxs-lookup"><span data-stu-id="9dacb-113">You can also configure or insert behaviors programmatically by locating the appropriate `Behaviors` property on the Windows Communication Foundation (WCF) client object or on the client channel factory object prior to opening the client.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9dacb-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9dacb-114">Example</span></span>  

 <span data-ttu-id="9dacb-115">Im folgenden Codebeispiel wird das programmgesteuerte Einfügen eines Verhaltens durch Zugreifen auf die <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A>-Eigenschaft auf dem <xref:System.ServiceModel.Description.ServiceEndpoint> veranschaulicht, der vor der Erstellung des Kanalobjekts von der <xref:System.ServiceModel.ChannelFactory.Endpoint%2A>-Eigenschaft zurückgegeben wurde:</span><span class="sxs-lookup"><span data-stu-id="9dacb-115">The following code example shows how to programmatically insert a behavior by accessing the <xref:System.ServiceModel.Description.ServiceEndpoint.Behaviors%2A> property on the <xref:System.ServiceModel.Description.ServiceEndpoint> returned from the <xref:System.ServiceModel.ChannelFactory.Endpoint%2A> property prior to the creation of the channel object.</span></span>  
  
 [!code-csharp[ChannelFactoryBehaviors#10](../../../samples/snippets/csharp/VS_Snippets_CFX/channelfactorybehaviors/cs/client.cs#10)]
 [!code-vb[ChannelFactoryBehaviors#10](../../../samples/snippets/visualbasic/VS_Snippets_CFX/channelfactorybehaviors/vb/client.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="9dacb-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9dacb-116">See also</span></span>

- [\<behaviors>](../configure-apps/file-schema/wcf/behaviors.md)
