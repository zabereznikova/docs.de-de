---
title: Lastenausgleich
ms.date: 03/30/2017
helpviewer_keywords:
- load balancing [WCF]
ms.assetid: 148e0168-c08d-4886-8769-776d0953b80f
ms.openlocfilehash: a444df2b05803ec54c5bd9030ce12209cfe9bd07
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183993"
---
# <a name="load-balancing"></a><span data-ttu-id="e588b-102">Lastenausgleich</span><span class="sxs-lookup"><span data-stu-id="e588b-102">Load Balancing</span></span>
<span data-ttu-id="e588b-103">Eine Möglichkeit, die Kapazität von Windows Communication Foundation (WCF)-Anwendungen zu erhöhen, besteht darin, sie durch Bereitstellen in einer Serverfarm mit Lastenausgleich zu skalieren.</span><span class="sxs-lookup"><span data-stu-id="e588b-103">One way to increase the capacity of Windows Communication Foundation (WCF) applications is to scale them out by deploying them into a load-balanced server farm.</span></span> <span data-ttu-id="e588b-104">WCF-Anwendungen können mithilfe von Standard-Lastausgleichstechniken, einschließlich Software-Lastenausgleichswietoren wie Windows Network Load Balancing sowie hardwarebasierten Lastenausgleichsgeräten, lastenausgeglichen werden.</span><span class="sxs-lookup"><span data-stu-id="e588b-104">WCF applications can be load balanced using standard load balancing techniques, including software load balancers such as Windows Network Load Balancing as well as hardware-based load balancing appliances.</span></span>  
  
 <span data-ttu-id="e588b-105">In den folgenden Abschnitten werden Überlegungen zum Lastenausgleich von WCF-Anwendungen erläutert, die mit verschiedenen vom System bereitgestellten Bindungen erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="e588b-105">The following sections discuss considerations for load balancing WCF applications built using various system-provided bindings.</span></span>  
  
## <a name="load-balancing-with-the-basic-http-binding"></a><span data-ttu-id="e588b-106">Lastenausgleich mit der Basic-HTTP-Bindung</span><span class="sxs-lookup"><span data-stu-id="e588b-106">Load Balancing with the Basic HTTP Binding</span></span>  
 <span data-ttu-id="e588b-107">Aus der Perspektive des Lastenausgleichs unterscheiden <xref:System.ServiceModel.BasicHttpBinding> sich WCF-Anwendungen, die über die kommunizieren, nicht von anderen gängigen Typen von HTTP-Netzwerkverkehr (statischer HTML-Inhalt, ASP.NET Seiten oder ASMX-Webdienste).</span><span class="sxs-lookup"><span data-stu-id="e588b-107">From the perspective of load balancing, WCF applications that communicate using the <xref:System.ServiceModel.BasicHttpBinding> are no different than other common types of HTTP network traffic (static HTML content, ASP.NET pages, or ASMX Web Services).</span></span> <span data-ttu-id="e588b-108">WCF-Kanäle, die diese Bindung verwenden, sind von Natur aus zustandslos und beenden ihre Verbindungen, wenn der Kanal geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="e588b-108">WCF channels that use this binding are inherently stateless, and terminate their connections when the channel closes.</span></span> <span data-ttu-id="e588b-109">Daher funktioniert die <xref:System.ServiceModel.BasicHttpBinding> gut mit vorhandenen HTTP-Lastenausgleichstechniken.</span><span class="sxs-lookup"><span data-stu-id="e588b-109">As such, the <xref:System.ServiceModel.BasicHttpBinding> works well with existing HTTP load balancing techniques.</span></span>  
  
 <span data-ttu-id="e588b-110">Standardmäßig sendet die <xref:System.ServiceModel.BasicHttpBinding> einen HTTP-Verbindungsheader in Nachrichten mit einem `Keep-Alive`-Wert, der Clients ermöglicht, permanente Verbindungen zu den Diensten herzustellen, die sie unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e588b-110">By default, the <xref:System.ServiceModel.BasicHttpBinding> sends a connection HTTP header in messages with a `Keep-Alive` value, which enables clients to establish persistent connections to the services that support them.</span></span> <span data-ttu-id="e588b-111">Diese Konfiguration bietet einen höheren Durchsatz, da zuvor hergestellte Verbindungen erneut verwendet werden können, um nachfolgende Nachrichten an denselben Server zu senden.</span><span class="sxs-lookup"><span data-stu-id="e588b-111">This configuration offers enhanced throughput because previously established connections can be reused to send subsequent messages to the same server.</span></span> <span data-ttu-id="e588b-112">Die Wiederverwendung der Verbindung kann jedoch dazu führen, dass Clients eng mit einem bestimmten Server innerhalb der Serverfarm mit Lastenausgleich verbunden werden, was die Effektivität des Roundrobin-Lastenausgleichs reduziert.</span><span class="sxs-lookup"><span data-stu-id="e588b-112">However, connection reuse may cause clients to become strongly associated to a specific server within the load-balanced farm, which reduces the effectiveness of round-robin load balancing.</span></span> <span data-ttu-id="e588b-113">Wenn dieses Verhalten unerwünscht ist, kann HTTP `Keep-Alive` auf dem Server deaktiviert werden, indem die <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A>-Eigenschaft mit einer <xref:System.ServiceModel.Channels.CustomBinding> oder einer benutzerdefinierten <xref:System.ServiceModel.Channels.Binding> verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e588b-113">If this behavior is undesirable, HTTP `Keep-Alive` can be disabled on the server using the <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> property with a <xref:System.ServiceModel.Channels.CustomBinding> or user-defined <xref:System.ServiceModel.Channels.Binding>.</span></span> <span data-ttu-id="e588b-114">Im folgenden Beispiel wird gezeigt, wie dieser Vorgang unter Verwendung der Konfiguration ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e588b-114">The following example shows how to do this using configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  
 <system.serviceModel>  
  <services>  
   <service
     name="Microsoft.ServiceModel.Samples.CalculatorService"  
     behaviorConfiguration="CalculatorServiceBehavior">  
     <host>  
      <baseAddresses>  
       <add baseAddress="http://localhost:8000/servicemodelsamples/service"/>  
      </baseAddresses>  
     </host>  
    <!-- configure http endpoint, use base address provided by host  
         And the customBinding -->  
     <endpoint address=""  
           binding="customBinding"  
           bindingConfiguration="HttpBinding"
           contract="Microsoft.ServiceModel.Samples.ICalculator" />  
   </service>  
  </services>  
  
  <bindings>  
    <customBinding>  
  
    <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
      <binding name="HttpBinding" keepAliveEnabled="False"/>  
  
    </customBinding>  
  </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="e588b-115">Mit der vereinfachten Konfiguration, die in .NET Framework 4 eingeführt wurde, kann das gleiche Verhalten mit der folgenden vereinfachten Konfiguration erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="e588b-115">Using the simplified configuration introduced in .NET Framework 4, the same behavior can be accomplished using the following simplified configuration.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
 <system.serviceModel>  
    <protocolMapping>  
      <add scheme="http" binding="customBinding" />  
    </protocolMapping>  
    <bindings>  
      <customBinding>  
  
      <!-- Configure a CustomBinding that disables keepAliveEnabled-->  
        <binding keepAliveEnabled="False"/>  
  
      </customBinding>  
    </bindings>  
 </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="e588b-116">Weitere Informationen über Standardendpunkte, Bindungen und Verhalten finden Sie unter [Simplified Configuration (Vereinfachte Konfiguration)](simplified-configuration.md) und [Simplified Configuration for WCF Services (Vereinfachte Konfiguration für WCF-Dienste)](./samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="e588b-116">For more information about default endpoints, bindings, and behaviors, see [Simplified Configuration](simplified-configuration.md) and [Simplified Configuration for WCF Services](./samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
## <a name="load-balancing-with-the-wshttp-binding-and-the-wsdualhttp-binding"></a><span data-ttu-id="e588b-117">Lastenausgleich mit der WSHttp-Bindung und der WSDualHttp-Bindung</span><span class="sxs-lookup"><span data-stu-id="e588b-117">Load Balancing with the WSHttp Binding and the WSDualHttp Binding</span></span>  
 <span data-ttu-id="e588b-118">Sowohl die <xref:System.ServiceModel.WSHttpBinding> als auch die <xref:System.ServiceModel.WSDualHttpBinding> können mit HTTP-Lastenausgleichstechniken ausgeglichen werden, vorausgesetzt, an der Standardbindungskonfiguration werden einige Änderungen vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="e588b-118">Both the <xref:System.ServiceModel.WSHttpBinding> and the <xref:System.ServiceModel.WSDualHttpBinding> can be load balanced using HTTP load balancing techniques provided several modifications are made to the default binding configuration.</span></span>  
  
- <span data-ttu-id="e588b-119">Sicherheitskontexterstellung deaktivieren: Dies kann durch Festlegen der <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A>-Eigenschaft der <xref:System.ServiceModel.WSHttpBinding> auf `false` erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="e588b-119">Turn off Security Context Establishment: this can be accomplished by the setting the <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> property on the <xref:System.ServiceModel.WSHttpBinding> to `false`.</span></span> <span data-ttu-id="e588b-120">Wenn Sicherheitssitzungen erforderlich sind, ist es auch möglich, zustandsbehaftete Sicherheitssitzungen zu verwenden, wie im Thema ["Sichere Sitzungen"](./feature-details/secure-sessions.md) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e588b-120">Alternatively, if security sessions are required, it is possible to use stateful security sessions as described in the [Secure Sessions](./feature-details/secure-sessions.md) topic.</span></span> <span data-ttu-id="e588b-121">Zustandsbehaftete Sicherheitssitzungen ermöglichen dem Dienst, zustandslos zu bleiben, da der gesamte Zustand für die Sicherheitssitzung mit jeder Anforderung als Teil des Schutzsicherheitstokens übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="e588b-121">Stateful security sessions enable the service to remain stateless as all of the state for the security session is transmitted with each request as a part of the protection security token.</span></span> <span data-ttu-id="e588b-122">Zum Aktivieren einer zustandsbehafteten Sicherheitssitzung muss eine <xref:System.ServiceModel.Channels.CustomBinding> oder eine benutzerdefinierte <xref:System.ServiceModel.Channels.Binding> verwendet werden, da die erforderlichen Konfigurationseinstellungen nicht für die vom System bereitgestellte <xref:System.ServiceModel.WSHttpBinding> und <xref:System.ServiceModel.WSDualHttpBinding> verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="e588b-122">Note that to enable a stateful security session, it is necessary to use a <xref:System.ServiceModel.Channels.CustomBinding> or user-defined <xref:System.ServiceModel.Channels.Binding> as the necessary configuration settings are not exposed on <xref:System.ServiceModel.WSHttpBinding> and <xref:System.ServiceModel.WSDualHttpBinding> that are provided by the system.</span></span>  
  
- <span data-ttu-id="e588b-123">Verwenden Sie keine zuverlässigen Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="e588b-123">Do not use reliable sessions.</span></span> <span data-ttu-id="e588b-124">Diese Funktion ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e588b-124">This feature is off by default.</span></span>  
  
## <a name="load-balancing-the-nettcp-binding"></a><span data-ttu-id="e588b-125">Lastenausgleich der Net.TCP-Bindung</span><span class="sxs-lookup"><span data-stu-id="e588b-125">Load Balancing the Net.TCP Binding</span></span>  
 <span data-ttu-id="e588b-126">Für die <xref:System.ServiceModel.NetTcpBinding> kann mit Lastenausgleichstechniken der IP-Ebene ein Lastausgleich vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="e588b-126">The <xref:System.ServiceModel.NetTcpBinding> can be load balanced using IP-layer load balancing techniques.</span></span> <span data-ttu-id="e588b-127">Die <xref:System.ServiceModel.NetTcpBinding> legt jedoch TCP-Verbindungen standardmäßig zusammen, um die Verbindungswartezeit zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="e588b-127">However, the <xref:System.ServiceModel.NetTcpBinding> pools TCP connections by default to reduce connection latency.</span></span> <span data-ttu-id="e588b-128">Dies ist eine Optimierung, die den grundlegenden Mechanismus des Lastenausgleichs behindert.</span><span class="sxs-lookup"><span data-stu-id="e588b-128">This is an optimization that interferes with the basic mechanism of load balancing.</span></span> <span data-ttu-id="e588b-129">Der primäre Konfigurationswert zur Optimierung der <xref:System.ServiceModel.NetTcpBinding> ist der Leasetimeout, der zu den Verbindungspooleinstellungen gehört.</span><span class="sxs-lookup"><span data-stu-id="e588b-129">The primary configuration value for optimizing the <xref:System.ServiceModel.NetTcpBinding> is the lease timeout, which is part of the Connection Pool Settings.</span></span> <span data-ttu-id="e588b-130">Verbindungspooling bewirkt, dass Clientverbindungen bestimmten Servern innerhalb der Farm zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="e588b-130">Connection pooling causes client connections to become associated to specific servers within the farm.</span></span> <span data-ttu-id="e588b-131">Mit steigender Lebensdauer dieser Verbindung (ein Faktor, der von der Leasetimeout-Einstellung gesteuert wird) wird die Lastenverteilung über die verschiedenen Server auf der Farm zunehmend unausgeglichen.</span><span class="sxs-lookup"><span data-stu-id="e588b-131">As the lifetime of those connections increase (a factor controlled by the lease timeout setting), the load distribution across various servers in the farm becomes unbalanced.</span></span> <span data-ttu-id="e588b-132">Demzufolge steigt die durchschnittliche Aufrufzeit.</span><span class="sxs-lookup"><span data-stu-id="e588b-132">As a result the average call time increases.</span></span> <span data-ttu-id="e588b-133">Erwägen Sie daher bei der Verwendung der <xref:System.ServiceModel.NetTcpBinding> in Lastenausgleichsszenarien, den von der Bindung verwendeten Leasetimeout-Standardwert zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="e588b-133">So when using the <xref:System.ServiceModel.NetTcpBinding> in load-balanced scenarios, consider reducing the default lease timeout used by the binding.</span></span> <span data-ttu-id="e588b-134">Ein 30 Sekunden dauernder Leasetimeout ist ein angemessener Ausgangspunkt für Lastenausgleichsszenarien. Der optimale Wert richtet sich jedoch nach der jeweiligen Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e588b-134">A 30-second lease timeout is a reasonable starting point for load-balanced scenarios, although the optimal value is application-dependent.</span></span> <span data-ttu-id="e588b-135">Weitere Informationen zum Channelleasetimeout und anderen Transportkontingenten finden Sie unter [Transportkontingente](./feature-details/transport-quotas.md).</span><span class="sxs-lookup"><span data-stu-id="e588b-135">For more information about the channel lease timeout and other transport quotas, see [Transport Quotas](./feature-details/transport-quotas.md).</span></span>  
  
 <span data-ttu-id="e588b-136">Erwägen Sie, für die optimale Leistung in Lastenausgleichsszenarien <xref:System.ServiceModel.NetTcpSecurity> ( <xref:System.ServiceModel.SecurityMode.Transport> oder <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e588b-136">For best performance in load-balanced scenarios, consider using <xref:System.ServiceModel.NetTcpSecurity> (either <xref:System.ServiceModel.SecurityMode.Transport> or <xref:System.ServiceModel.SecurityMode.TransportWithMessageCredential>).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e588b-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e588b-137">See also</span></span>

- [<span data-ttu-id="e588b-138">Empfohlene Vorgehensweisen für das Hosten in Internetinformationsdiensten</span><span class="sxs-lookup"><span data-stu-id="e588b-138">Internet Information Services Hosting Best Practices</span></span>](./feature-details/internet-information-services-hosting-best-practices.md)
