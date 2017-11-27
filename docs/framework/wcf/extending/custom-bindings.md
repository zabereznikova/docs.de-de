---
title: Benutzerdefinierte Bindungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation, endpoints
- Windows Communication Foundation, configuration
ms.assetid: 58532b6d-4eea-4a4f-854f-a1c8c842564d
caps.latest.revision: "33"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 07247573678d81bb45f8b4b7f07a453573326cbc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="custom-bindings"></a><span data-ttu-id="c64d7-102">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="c64d7-102">Custom Bindings</span></span>
<span data-ttu-id="c64d7-103">Verwenden Sie die <xref:System.ServiceModel.Channels.CustomBinding>-Klasse, wenn eine der vom System bereitgestellten Bindungen die Anforderungen für Ihren Dienst nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="c64d7-103">You can use the <xref:System.ServiceModel.Channels.CustomBinding> class when one of the system-provided bindings does not meet the requirements of your service.</span></span> <span data-ttu-id="c64d7-104">Alle Bindungen werden anhand einer geordneten Menge von Bindungselementen erstellt.</span><span class="sxs-lookup"><span data-stu-id="c64d7-104">All bindings are constructed from an ordered set of binding elements.</span></span> <span data-ttu-id="c64d7-105">Benutzerdefinierte Bindungen können alleine aus systemeigenen Bindungselementen erstellt werden oder auch benutzerspezifische Bindungselemente umfassen.</span><span class="sxs-lookup"><span data-stu-id="c64d7-105">Custom bindings can be built from a set of system-provided binding elements or can include user-defined custom binding elements.</span></span> <span data-ttu-id="c64d7-106">So können Sie mithilfe von benutzerdefinierten Bindungselementen beispielsweise die Verwendung neuer Transporte oder Encoder an einem Dienstendpunkt aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c64d7-106">You can use custom binding elements, for example, to enable the use of new transports or encoders at a service endpoint.</span></span> <span data-ttu-id="c64d7-107">Funktionierende Beispiele finden Sie in [Beispiele für die benutzerdefinierte Bindung](http://msdn.microsoft.com/en-us/657e8143-beb0-472d-9cfe-ed1a19c2ab08).</span><span class="sxs-lookup"><span data-stu-id="c64d7-107">For working examples, see [Custom Binding Samples](http://msdn.microsoft.com/en-us/657e8143-beb0-472d-9cfe-ed1a19c2ab08).</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="c64d7-108">[ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span><span class="sxs-lookup"><span data-stu-id="c64d7-108"> [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
## <a name="construction-of-a-custom-binding"></a><span data-ttu-id="c64d7-109">Aufbau einer benutzerdefinierten Bindung</span><span class="sxs-lookup"><span data-stu-id="c64d7-109">Construction of a Custom Binding</span></span>  
 <span data-ttu-id="c64d7-110">Eine benutzerdefinierte Bindung wird unter Verwendung des <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A>-Konstruktors aus einer Sammlung von Bindungselementen erstellt, die in einer spezifischen Reihenfolge "gestapelt" sind:</span><span class="sxs-lookup"><span data-stu-id="c64d7-110">A custom binding is constructed using the <xref:System.ServiceModel.Channels.CustomBinding.%23ctor%2A> constructor from a collection of binding elements that are "stacked" in a specific order:</span></span>  
  
-   <span data-ttu-id="c64d7-111">Am Anfang steht eine optionale <xref:System.ServiceModel.Channels.TransactionFlowBindingElement>-Klasse, die den Transaktionsfluss ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="c64d7-111">At the top is an optional <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> class that allows flowing transactions.</span></span>  
  
-   <span data-ttu-id="c64d7-112">Darauf folgt eine optionale <xref:System.ServiceModel.Channels.ReliableSessionBindingElement>-Klasse, die eine Sitzung und Sortiermechanismen wie in der WS-ReliableMessaging-Spezifikation definiert bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c64d7-112">Next is an optional <xref:System.ServiceModel.Channels.ReliableSessionBindingElement> class that provides a session and ordering mechanisms as defined in the WS-ReliableMessaging specification.</span></span> <span data-ttu-id="c64d7-113">Eine Sitzung kann SOAP- und Transportvermittler überqueren.</span><span class="sxs-lookup"><span data-stu-id="c64d7-113">A session can cross SOAP and transport intermediaries.</span></span>  
  
-   <span data-ttu-id="c64d7-114">Anschließend folgt eine <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse, die Sicherheitsfunktionen wie Autorisierung, Authentifizierung, Schutz und Vertraulichkeit bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c64d7-114">Next is an optional <xref:System.ServiceModel.Channels.SecurityBindingElement> class that provides security features such as authorization, authentication, protection, and confidentiality.</span></span>  
  
-   <span data-ttu-id="c64d7-115">Hierauf folgt eine optionale <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>-Klasse, die eine Duplexkommunikation mit einem Transportprotokoll ermöglicht, das selbst keine Duplexkommunikation unterstützt, z. B. HTTP.</span><span class="sxs-lookup"><span data-stu-id="c64d7-115">Next is an optional <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement> class that provides the ability to have two way duplex communication with a transport protocol that does not support duplex communication natively, such as HTTP.</span></span>  
  
-   <span data-ttu-id="c64d7-116">Danach folgt eine optionale <xref:System.ServiceModel.Channels.OneWayBindingElement>-Klasse, die eine unidirektionale Kommunikation bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c64d7-116">Next is an optional <xref:System.ServiceModel.Channels.OneWayBindingElement>) class that provides one-way communication.</span></span>  
  
-   <span data-ttu-id="c64d7-117">Dann folgt ein optionales Streamsicherheitsbindungselement, das einem der folgenden Elemente entsprechen kann.</span><span class="sxs-lookup"><span data-stu-id="c64d7-117">Next is an optional stream security binding element which can be one of the following.</span></span>  
  
    -   <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
  
-   <span data-ttu-id="c64d7-118">Darauf wiederum folgt ein erforderliches, Nachrichten codierendes Bindungselement.</span><span class="sxs-lookup"><span data-stu-id="c64d7-118">Next is a required message encoding binding element.</span></span> <span data-ttu-id="c64d7-119">Sie können Ihren eigenen Nachrichtenencoder oder eine von drei Nachrichten codierenden Bindungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="c64d7-119">You can use your own message encoder or one of the three message encoding bindings:</span></span>  
  
    -   <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>  
  
    -   <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>  
  
 <span data-ttu-id="c64d7-120">Am Ende befindet sich ein erforderliches Transportelement.</span><span class="sxs-lookup"><span data-stu-id="c64d7-120">At the bottom is a required transport element.</span></span> <span data-ttu-id="c64d7-121">Sie können Ihren eigenen Transport oder eines der folgenden, von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] bereitgestellten Transportbindungselemente verwenden:</span><span class="sxs-lookup"><span data-stu-id="c64d7-121">You can use your own transport or one of the following transport binding elements [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] provides:</span></span>  
  
-   <xref:System.ServiceModel.Channels.TcpTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.PeerTransportBindingElement>  
  
-   <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>  
  
-   <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>  
  
-   <xref:System.ServiceModel.Channels.ConnectionOrientedTransportBindingElement>  
  
 <span data-ttu-id="c64d7-122">In der folgenden Tabelle werden die Optionen für jede Ebene zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="c64d7-122">The following table summarizes the options for each layer.</span></span>  
  
|<span data-ttu-id="c64d7-123">Ebene</span><span class="sxs-lookup"><span data-stu-id="c64d7-123">Layer</span></span>|<span data-ttu-id="c64d7-124">Optionen</span><span class="sxs-lookup"><span data-stu-id="c64d7-124">Options</span></span>|<span data-ttu-id="c64d7-125">Erforderlich</span><span class="sxs-lookup"><span data-stu-id="c64d7-125">Required</span></span>|  
|-----------|-------------|--------------|  
|<span data-ttu-id="c64d7-126">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="c64d7-126">Transactions</span></span>|<xref:System.ServiceModel.Channels.TransactionFlowBindingElement>|<span data-ttu-id="c64d7-127">Nein</span><span class="sxs-lookup"><span data-stu-id="c64d7-127">No</span></span>|  
|<span data-ttu-id="c64d7-128">Zuverlässigkeit</span><span class="sxs-lookup"><span data-stu-id="c64d7-128">Reliability</span></span>|<xref:System.ServiceModel.Channels.ReliableSessionBindingElement>|<span data-ttu-id="c64d7-129">Nein</span><span class="sxs-lookup"><span data-stu-id="c64d7-129">No</span></span>|  
|<span data-ttu-id="c64d7-130">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c64d7-130">Security</span></span>|<xref:System.ServiceModel.Channels.SecurityBindingElement>|<span data-ttu-id="c64d7-131">Nein</span><span class="sxs-lookup"><span data-stu-id="c64d7-131">No</span></span>|  
|<span data-ttu-id="c64d7-132">Codierung</span><span class="sxs-lookup"><span data-stu-id="c64d7-132">Encoding</span></span>|<span data-ttu-id="c64d7-133">Text, binär, Message Transmission Optimization Mechanism (MTOM), benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="c64d7-133">Text, binary, Message Transmission Optimization Mechanism (MTOM), custom</span></span>|<span data-ttu-id="c64d7-134">Ja</span><span class="sxs-lookup"><span data-stu-id="c64d7-134">Yes</span></span>|  
|<span data-ttu-id="c64d7-135">Transport</span><span class="sxs-lookup"><span data-stu-id="c64d7-135">Transport</span></span>|<span data-ttu-id="c64d7-136">TCP, HTTP, HTTPS, benannte Pipes (Named Pipes, auch als IPC bekannt), Peer-to-Peer (P2P), Message Queuing (auch als MSMQ bekannt), benutzerdefiniert</span><span class="sxs-lookup"><span data-stu-id="c64d7-136">TCP, HTTP, HTTPS, named pipes (also known as IPC), Peer-to-Peer (P2P), Message Queuing (also known as MSMQ), Custom</span></span>|<span data-ttu-id="c64d7-137">Ja</span><span class="sxs-lookup"><span data-stu-id="c64d7-137">Yes</span></span>|  
  
 <span data-ttu-id="c64d7-138">Zusätzlich können Sie Ihre eigenen Bindungselemente definieren und diese zwischen den vorangehenden definierten Ebenen einsetzen.</span><span class="sxs-lookup"><span data-stu-id="c64d7-138">In addition, you can define your own binding elements and insert them between any of the preceding defined layers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c64d7-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c64d7-139">See Also</span></span>  
 [<span data-ttu-id="c64d7-140">Übersicht über die Endpunkterstellung</span><span class="sxs-lookup"><span data-stu-id="c64d7-140">Endpoint Creation Overview</span></span>](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [<span data-ttu-id="c64d7-141">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="c64d7-141">Using Bindings to Configure Services and Clients</span></span>](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="c64d7-142">Vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="c64d7-142">System-Provided Bindings</span></span>](../../../../docs/framework/wcf/system-provided-bindings.md)  
 [<span data-ttu-id="c64d7-143">Vorgehensweise: Anpassen einer vom System bereitgestellte Bindung</span><span class="sxs-lookup"><span data-stu-id="c64d7-143">How to: Customize a System-Provided Binding</span></span>](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)  
 [<span data-ttu-id="c64d7-144">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="c64d7-144">\<customBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="c64d7-145">Benutzerdefinierte Bindung</span><span class="sxs-lookup"><span data-stu-id="c64d7-145">Custom Binding</span></span>](../../../../docs/framework/wcf/samples/custom-binding.md)
