---
title: Benutzerdefinierte Bindungen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
ms.openlocfilehash: e3954e90ed091d03656f25ce1a9b1ff35ffaa9ea
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260724"
---
# <a name="custom-bindings"></a><span data-ttu-id="32844-102">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="32844-102">Custom Bindings</span></span>
<span data-ttu-id="32844-103">Verwenden Sie die <xref:System.ServiceModel.Channels.CustomBinding>-Klasse, wenn eine der vom System bereitgestellten Bindungen die Anforderungen für Ihren Dienst nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="32844-103">You can use the <xref:System.ServiceModel.Channels.CustomBinding> class when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="32844-104">Alle Bindungen werden anhand einer geordneten Menge von Bindungselementen erstellt.</span><span class="sxs-lookup"><span data-stu-id="32844-104">All bindings are constructed from an ordered set of binding elements.</span></span> <span data-ttu-id="32844-105">Benutzerdefinierte Bindungen können alleine aus systemeigenen Bindungselementen erstellt werden oder auch benutzerspezifische Bindungselemente umfassen.</span><span class="sxs-lookup"><span data-stu-id="32844-105">Custom bindings can be built from a set of system-provided binding elements or can include user-defined custom binding elements.</span></span> <span data-ttu-id="32844-106">So können Sie mithilfe von benutzerdefinierten Bindungselementen beispielsweise die Verwendung neuer Transporte oder Encoder an einem Dienstendpunkt aktivieren.</span><span class="sxs-lookup"><span data-stu-id="32844-106">You can use custom binding elements, for example, to enable the use of new transports or encoders at a service endpoint.</span></span> <span data-ttu-id="32844-107">Arbeitsbeispiele finden Sie unter [Beispiele für die benutzerdefinierte Bindung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="32844-107">For working examples, see [Custom Binding Samples](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751479(v=vs.90)).</span></span> <span data-ttu-id="32844-108">Weitere Informationen finden Sie unter [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="32844-108">For more information, see [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
## <a name="construction-of-a-custom-binding"></a><span data-ttu-id="32844-109">Aufbau einer benutzerdefinierten Bindung</span><span class="sxs-lookup"><span data-stu-id="32844-109">Construction of a Custom Binding</span></span>  
 <span data-ttu-id="32844-110">Eine benutzerdefinierte Bindung wird unter Verwendung des <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A>-Konstruktors aus einer Sammlung von Bindungselementen erstellt, die in einer spezifischen Reihenfolge „gestapelt“ sind:</span><span class="sxs-lookup"><span data-stu-id="32844-110">A custom binding is constructed using the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> constructor from a collection of binding elements that are "stacked" in a specific order:</span></span>  
  
-   <span data-ttu-id="32844-111">Am Anfang steht eine optionale <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>-Klasse, die den Transaktionsfluss ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="32844-111">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> class that allows flowing transactions.</span></span>  
  
-   <span data-ttu-id="32844-112">Darauf folgt eine optionale <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>-Klasse, die eine Sitzung und Sortiermechanismen wie in der WS-ReliableMessaging-Spezifikation definiert bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="32844-112">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> class that provides a session and ordering mechanisms as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="32844-113">Eine Sitzung kann SOAP- und Transportvermittler überqueren.</span><span class="sxs-lookup"><span data-stu-id="32844-113">A session can cross SOAP and transport intermediaries.</span></span>  
  
-   <span data-ttu-id="32844-114">Anschließend folgt eine <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse, die Sicherheitsfunktionen wie Autorisierung, Authentifizierung, Schutz und Vertraulichkeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="32844-114">Next is an optional <xref:System.ServiceModel.Channels.SecurityBindingElement> class that provides security features such as authorization, authentication, protection, and confidentiality.</span></span>  
  
-   <span data-ttu-id="32844-115">Hierauf folgt eine optionale <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>-Klasse, die eine Duplexkommunikation mit einem Transportprotokoll ermöglicht, das selbst keine Duplexkommunikation unterstützt, z. B. HTTP.</span><span class="sxs-lookup"><span data-stu-id="32844-115">Next is an optional <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> class that provides the ability to have two way duplex communication with a transport protocol that does not support duplex communication natively, such as HTTP.</span></span>  
  
-   <span data-ttu-id="32844-116">Danach folgt eine optionale <xref:System.ServiceModel.Channels.OneWayBindingElement>-Klasse, die eine unidirektionale Kommunikation bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="32844-116">Next is an optional <xref:System.ServiceModel.Channels.OneWayBindingElement>) class that provides one-way communication.</span></span>  
  
-   <span data-ttu-id="32844-117">Dann folgt ein optionales Streamsicherheitsbindungselement, das einem der folgenden Elemente entsprechen kann.</span><span class="sxs-lookup"><span data-stu-id="32844-117">Next is an optional stream security binding element which can be one of the following.</span></span>  
  
    -   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
-   <span data-ttu-id="32844-118">Darauf wiederum folgt ein erforderliches, Nachrichten codierendes Bindungselement.</span><span class="sxs-lookup"><span data-stu-id="32844-118">Next is a required message encoding binding element.</span></span> <span data-ttu-id="32844-119">Sie können Ihren eigenen Nachrichtenencoder oder eine von drei Nachrichten codierenden Bindungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="32844-119">You can use your own message encoder or one of the three message encoding bindings:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
  
 <span data-ttu-id="32844-120">Am Ende befindet sich ein erforderliches Transportelement.</span><span class="sxs-lookup"><span data-stu-id="32844-120">At the bottom is a required transport element.</span></span> <span data-ttu-id="32844-121">Sie können Ihren eigenen Transport oder eines der folgenden transportbindungselemente, die Windows Communication Foundation (WCF) bietet:</span><span class="sxs-lookup"><span data-stu-id="32844-121">You can use your own transport or one of the following transport binding elements Windows Communication Foundation (WCF) provides:</span></span>  
  
-   <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>  
  
-   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>  
  
-   <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
 <span data-ttu-id="32844-122">In der folgenden Tabelle werden die Optionen für jede Ebene zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="32844-122">The following table summarizes the options for each layer.</span></span>  
  
|<span data-ttu-id="32844-123">Ebene</span><span class="sxs-lookup"><span data-stu-id="32844-123">Layer</span></span>|<span data-ttu-id="32844-124">Optionen</span><span class="sxs-lookup"><span data-stu-id="32844-124">Options</span></span>|<span data-ttu-id="32844-125">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="32844-125">Required</span></span>|  
|-----------|-------------|--------------|  
|<span data-ttu-id="32844-126">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="32844-126">Transactions</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="32844-127">Nein</span><span class="sxs-lookup"><span data-stu-id="32844-127">No</span></span>|  
|<span data-ttu-id="32844-128">Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="32844-128">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="32844-129">Nein</span><span class="sxs-lookup"><span data-stu-id="32844-129">No</span></span>|  
|<span data-ttu-id="32844-130">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="32844-130">Security</span></span>|<xref:System.ServiceModel.Channels.SecurityBindingElement>|<span data-ttu-id="32844-131">Nein</span><span class="sxs-lookup"><span data-stu-id="32844-131">No</span></span>|  
|<span data-ttu-id="32844-132">Codierung</span><span class="sxs-lookup"><span data-stu-id="32844-132">Encoding</span></span>|<span data-ttu-id="32844-133">Text, binär, Message Transmission Optimization Mechanism (MTOM), benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="32844-133">Text, binary, Message Transmission Optimization Mechanism (MTOM), custom</span></span>|<span data-ttu-id="32844-134">Ja</span><span class="sxs-lookup"><span data-stu-id="32844-134">Yes</span></span>|  
|<span data-ttu-id="32844-135">Transport</span><span class="sxs-lookup"><span data-stu-id="32844-135">Transport</span></span>|<span data-ttu-id="32844-136">TCP, HTTP, HTTPS, benannte Pipes (Named Pipes, auch als IPC bekannt), Peer-to-Peer (P2P), Message Queuing (auch als MSMQ bekannt), benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="32844-136">TCP, HTTP, HTTPS, named pipes (also known as IPC), Peer-to-Peer (P2P), Message Queuing (also known as MSMQ), Custom</span></span>|<span data-ttu-id="32844-137">Ja</span><span class="sxs-lookup"><span data-stu-id="32844-137">Yes</span></span>|  
  
 <span data-ttu-id="32844-138">Zusätzlich können Sie Ihre eigenen Bindungselemente definieren und diese zwischen den vorangehenden definierten Ebenen einsetzen.</span><span class="sxs-lookup"><span data-stu-id="32844-138">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32844-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32844-139">See also</span></span>
- [<span data-ttu-id="32844-140">Übersicht über die Endpunkterstellung</span><span class="sxs-lookup"><span data-stu-id="32844-140">Endpoint Creation Overview</span></span>](../../../../docs/framework/wcf/endpoint-creation-overview.md)
- [<span data-ttu-id="32844-141">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="32844-141">Using Bindings to Configure Services and Clients</span></span>](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="32844-142">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="32844-142">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)
- [<span data-ttu-id="32844-143">Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung</span><span class="sxs-lookup"><span data-stu-id="32844-143">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
- [<span data-ttu-id="32844-144">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="32844-144">\<customBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="32844-145">Benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="32844-145">Custom Binding</span></span>](../../../../docs/framework/wcf/samples/custom-binding.md)
