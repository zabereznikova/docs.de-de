---
title: Messagingprotokolle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 600a1bd57015c6a64a51bf99f3ded35a375e62fe
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="messaging-protocols"></a><span data-ttu-id="cd0bd-102">Messagingprotokolle</span><span class="sxs-lookup"><span data-stu-id="cd0bd-102">Messaging Protocols</span></span>
<span data-ttu-id="cd0bd-103">Der [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Kanalstapel wendet Codierungs- und Transportkanäle an, um eine interne Nachrichtendarstellung in ihr Kabelformat umzuwandeln und sie über einen bestimmten Transport zu versenden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-103">The [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] channel stack employs encoding and transport channels to transform internal message representation into its wire format and send it by using a particular transport.</span></span> <span data-ttu-id="cd0bd-104">Der am häufigsten verwendete Transport, der für die Interoperabilität bei Webdiensten verwendet wird, ist HTTP, und die am häufigsten von Webdiensten verwendeten Codierungen sind das XML-basierte SOAP 1.1, SOAP 1.2 und der Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="cd0bd-104">The most common transport used for Web services interoperability is HTTP, and the most common encodings used by Web services are XML-based SOAP 1.1, SOAP 1.2, and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="cd0bd-105">Dieses Thema behandelt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Implementierungsdetails für die folgenden, von <xref:System.ServiceModel.Channels.HttpTransportBindingElement> eingesetzten Protokolle.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-105">This topic covers [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation details for the following protocols employed by <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span>  
  
|<span data-ttu-id="cd0bd-106">Spezifikation/Dokument</span><span class="sxs-lookup"><span data-stu-id="cd0bd-106">Specification/document</span></span>|<span data-ttu-id="cd0bd-107">Link</span><span class="sxs-lookup"><span data-stu-id="cd0bd-107">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="cd0bd-108">HTTP 1.1</span><span class="sxs-lookup"><span data-stu-id="cd0bd-108">HTTP 1.1</span></span>|<span data-ttu-id="cd0bd-109">http://www.ietf.org/rfc/rfc2616.txt (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-109">http://www.ietf.org/rfc/rfc2616.txt</span></span>|  
|<span data-ttu-id="cd0bd-110">SOAP 1.1 HTTP-Bindung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-110">SOAP 1.1 HTTP Binding</span></span>|<span data-ttu-id="cd0bd-111">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, Abschnitt 7 (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-111">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, Section 7</span></span>|  
|<span data-ttu-id="cd0bd-112">SOAP 1,2 HTTP-Bindung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-112">SOAP 1.2 HTTP Binding</span></span>|<span data-ttu-id="cd0bd-113">http://www.w3.org/TR/soap12-part2/, Abschnitt 7 (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-113">http://www.w3.org/TR/soap12-part2/, Section 7</span></span>|  
  
 <span data-ttu-id="cd0bd-114">Dieses Thema behandelt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Implementierungsdetails für die folgenden Protokolle, die von <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> und <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-114">This topic covers [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation details for the following protocols  that <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employ.</span></span>  
  
|<span data-ttu-id="cd0bd-115">Spezifikation/Dokument</span><span class="sxs-lookup"><span data-stu-id="cd0bd-115">Specification/Document</span></span>|<span data-ttu-id="cd0bd-116">Link</span><span class="sxs-lookup"><span data-stu-id="cd0bd-116">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="cd0bd-117">XML</span><span class="sxs-lookup"><span data-stu-id="cd0bd-117">XML</span></span>|<span data-ttu-id="cd0bd-118">http://www.w3.org/TR/REC-xml (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-118">http://www.w3.org/TR/REC-xml</span></span>|  
|<span data-ttu-id="cd0bd-119">SOAP 1,1</span><span class="sxs-lookup"><span data-stu-id="cd0bd-119">SOAP 1.1</span></span>|<span data-ttu-id="cd0bd-120">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/ (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-120">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/</span></span>|  
|<span data-ttu-id="cd0bd-121">SOAP 1.2 Core</span><span class="sxs-lookup"><span data-stu-id="cd0bd-121">SOAP 1.2 Core</span></span>|<span data-ttu-id="cd0bd-122">http://www.w3.org/TR/soap12-part1/ (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-122">http://www.w3.org/TR/soap12-part1/</span></span>|  
|<span data-ttu-id="cd0bd-123">WS-Adressierung 2004/08</span><span class="sxs-lookup"><span data-stu-id="cd0bd-123">WS-Addressing 2004/08</span></span>|<span data-ttu-id="cd0bd-124">http://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/ (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-124">http://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/</span></span>|  
|<span data-ttu-id="cd0bd-125">W3C Web Services Addressing 1.0 - Core</span><span class="sxs-lookup"><span data-stu-id="cd0bd-125">W3C Web Services Addressing 1.0 - Core</span></span>|<span data-ttu-id="cd0bd-126">http://www.w3.org/TR/2006/REC-ws-addr-core-20060509 (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-126">http://www.w3.org/TR/2006/REC-ws-addr-core-20060509</span></span>|  
|<span data-ttu-id="cd0bd-127">W3C Web Services Addressing 1.0 - SOAP-Bindung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-127">W3C Web Services Addressing 1.0 - SOAP Binding</span></span>|<span data-ttu-id="cd0bd-128">http://www.w3.org/TR/2006/REC-ws-addr-soap-20060509 (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-128">http://www.w3.org/TR/2006/REC-ws-addr-soap-20060509</span></span>|  
|<span data-ttu-id="cd0bd-129">W3C Web Services Addressing 1.0 - WSDL-Bindung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-129">W3C Web Services Addressing 1.0 - WSDL Binding</span></span>|<span data-ttu-id="cd0bd-130">http://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/ (in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-130">http://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/</span></span>|  
<span data-ttu-id="cd0bd-131">W3C Web Services Addressing 1.0 - Metadaten</span><span class="sxs-lookup"><span data-stu-id="cd0bd-131">W3C Web Services Addressing 1.0 - Metadata</span></span>|<span data-ttu-id="cd0bd-132">http://www.w3.org/TR/ws-addr-metadata/</span><span class="sxs-lookup"><span data-stu-id="cd0bd-132">http://www.w3.org/TR/ws-addr-metadata/</span></span>|  
|<span data-ttu-id="cd0bd-133">WSDL SOAP1.1-Bindung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-133">WSDL SOAP1.1 Binding</span></span>|<span data-ttu-id="cd0bd-134">http://www.w3.org/TR/wsdl/ (in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-134">http://www.w3.org/TR/wsdl/</span></span>|  
|<span data-ttu-id="cd0bd-135">WSDL SOAP1.2-Bindung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-135">WSDL SOAP1.2 Binding</span></span>|<span data-ttu-id="cd0bd-136">http://www.w3.org/Submission/wsdl11soap12/ (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-136">http://www.w3.org/Submission/wsdl11soap12/</span></span>|  
  
 <span data-ttu-id="cd0bd-137">Dieses Thema behandelt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Implementierungsdetails für die folgenden Protokolle, die von <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-137">This topic covers [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation details for the following protocols that <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employs.</span></span>  
  
|<span data-ttu-id="cd0bd-138">Spezifikation/Dokument</span><span class="sxs-lookup"><span data-stu-id="cd0bd-138">Specification/document</span></span>|<span data-ttu-id="cd0bd-139">Link</span><span class="sxs-lookup"><span data-stu-id="cd0bd-139">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="cd0bd-140">XOP</span><span class="sxs-lookup"><span data-stu-id="cd0bd-140">XOP</span></span>|<span data-ttu-id="cd0bd-141">http://www.w3.org/TR/xop10/ (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-141">http://www.w3.org/TR/xop10/</span></span>|  
|<span data-ttu-id="cd0bd-142">MTOM + SOAP 1.2-Bindung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-142">MTOM + SOAP 1.2 Binding</span></span>|<span data-ttu-id="cd0bd-143">http://www.w3.org/TR/soap12-mtom/ (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-143">http://www.w3.org/TR/soap12-mtom/</span></span>|  
|<span data-ttu-id="cd0bd-144">MTOM SOAP 1.1-Bindung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-144">MTOM SOAP 1.1 Binding</span></span>|<span data-ttu-id="cd0bd-145">http://www.w3.org/Submission/soap11mtom10/ (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-145">http://www.w3.org/Submission/soap11mtom10/</span></span>|  
|<span data-ttu-id="cd0bd-146">MTOM WS-Richtlinienassertion</span><span class="sxs-lookup"><span data-stu-id="cd0bd-146">MTOM WS-Policy Assertion</span></span>|<span data-ttu-id="cd0bd-147">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/ (möglicherweise in englischer Sprache).</span><span class="sxs-lookup"><span data-stu-id="cd0bd-147">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/.</span></span>|  
  
 <span data-ttu-id="cd0bd-148">Die folgenden XML-Namespaces und zugeordneten Präfixe werden überall in diesem Thema verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-148">The following XML namespaces and associated prefixes are used throughout this topic.</span></span>  
  
|<span data-ttu-id="cd0bd-149">Präfix</span><span class="sxs-lookup"><span data-stu-id="cd0bd-149">Prefix</span></span>|<span data-ttu-id="cd0bd-150">Namespace Uniform Resource Identifier (URI)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-150">Namespace Uniform Resource Identifier (URI)</span></span>|  
|------------|---------------------------------------------------|  
|<span data-ttu-id="cd0bd-151">s11</span><span class="sxs-lookup"><span data-stu-id="cd0bd-151">s11</span></span>|<span data-ttu-id="cd0bd-152">http://schemas.xmlsoap.org/soap/envelope (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-152">http://schemas.xmlsoap.org/soap/envelope</span></span>|  
|<span data-ttu-id="cd0bd-153">s12</span><span class="sxs-lookup"><span data-stu-id="cd0bd-153">s12</span></span>|<span data-ttu-id="cd0bd-154">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="cd0bd-154">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="cd0bd-155">wsa</span><span class="sxs-lookup"><span data-stu-id="cd0bd-155">wsa</span></span>|<span data-ttu-id="cd0bd-156">http://www.w3.org/2004/08/Addressing</span><span class="sxs-lookup"><span data-stu-id="cd0bd-156">http://www.w3.org/2004/08/addressing</span></span>|  
|<span data-ttu-id="cd0bd-157">wsam</span><span class="sxs-lookup"><span data-stu-id="cd0bd-157">wsam</span></span>|<span data-ttu-id="cd0bd-158">http://www.w3.org/2007/05/addressing/metadata</span><span class="sxs-lookup"><span data-stu-id="cd0bd-158">http://www.w3.org/2007/05/addressing/metadata</span></span>|  
|<span data-ttu-id="cd0bd-159">wsap</span><span class="sxs-lookup"><span data-stu-id="cd0bd-159">wsap</span></span>|<span data-ttu-id="cd0bd-160">http://schemas.xmlsoap.org/ws/2004/09/policy/addressing (in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-160">http://schemas.xmlsoap.org/ws/2004/09/policy/addressing</span></span>|  
|<span data-ttu-id="cd0bd-161">wsa10</span><span class="sxs-lookup"><span data-stu-id="cd0bd-161">wsa10</span></span>|<span data-ttu-id="cd0bd-162">http://www.w3.org/2005/08/addressing (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-162">http://www.w3.org/2005/08/addressing</span></span>|  
|<span data-ttu-id="cd0bd-163">wsaw10</span><span class="sxs-lookup"><span data-stu-id="cd0bd-163">wsaw10</span></span>|<span data-ttu-id="cd0bd-164">http://www.w3.org/2006/05/addressing/wsdl (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-164">http://www.w3.org/2006/05/addressing/wsdl</span></span>|  
|<span data-ttu-id="cd0bd-165">xop</span><span class="sxs-lookup"><span data-stu-id="cd0bd-165">xop</span></span>|<span data-ttu-id="cd0bd-166">http://www.w3.org/2004/08/xop/include (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-166">http://www.w3.org/2004/08/xop/include</span></span>|  
|<span data-ttu-id="cd0bd-167">xmime</span><span class="sxs-lookup"><span data-stu-id="cd0bd-167">xmime</span></span>|<span data-ttu-id="cd0bd-168">http://www.w3.org/2004/06/xmlmime (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-168">http://www.w3.org/2004/06/xmlmime</span></span><br /><br /> <span data-ttu-id="cd0bd-169">http://www.w3.org/2005/05/xmlmime (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-169">http://www.w3.org/2005/05/xmlmime</span></span>|  
<span data-ttu-id="cd0bd-170">dp</span><span class="sxs-lookup"><span data-stu-id="cd0bd-170">dp</span></span>|<span data-ttu-id="cd0bd-171">http://schemas.microsoft.com/net/2006/06/duplex</span><span class="sxs-lookup"><span data-stu-id="cd0bd-171">http://schemas.microsoft.com/net/2006/06/duplex</span></span>|  
  
## <a name="soap-11-and-soap-12"></a><span data-ttu-id="cd0bd-172">SOAP 1.1 und SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="cd0bd-172">SOAP 1.1 and SOAP 1.2</span></span>  
  
### <a name="envelope-and-processing-model"></a><span data-ttu-id="cd0bd-173">Umschlag und Verarbeitungsmodell</span><span class="sxs-lookup"><span data-stu-id="cd0bd-173">Envelope and Processing Model</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-174"> implementiert SOAP 1.1-Umschlagsverarbeitung, unter Befolgung von Basic Profile 1.1 (BP11) und Basic Profile 1.0 (SSBP10).</span><span class="sxs-lookup"><span data-stu-id="cd0bd-174"> implements SOAP 1.1 envelope processing following Basic Profile 1.1 (BP11) and Basic Profile 1.0 (SSBP10).</span></span> <span data-ttu-id="cd0bd-175">SOAP 1.2-Umschlagsverarbeitung wird unter Befolgung von SOAP12-Part1 implementiert.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-175">SOAP 1.2 Envelope processing is implemented following SOAP12-Part1.</span></span>  
  
 <span data-ttu-id="cd0bd-176">Dieser Abschnitt erklärt bestimmte, in Hinsicht auf BP11 und SOAP12-Part1 von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] getroffene Implementierungsentscheidungen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-176">This section explains certain implementation choices taken by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] with regard to BP11 and SOAP12-Part1.</span></span>  
  
#### <a name="mandatory-header-processing"></a><span data-ttu-id="cd0bd-177">Erforderliche Headerverarbeitung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-177">Mandatory Header Processing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-178"> befolgt bei der Headerverarbeitung Regeln, die als `mustUnderstand` gekennzeichnet und in den SOAP 1.1- und SOAP 1.2-Spezifikationen beschrieben sind, mit den folgenden Variationen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-178"> follows rules for processing headers marked `mustUnderstand` described in the SOAP 1.1 and SOAP 1.2 specifications, with the following variations.</span></span>  
  
 <span data-ttu-id="cd0bd-179">Eine Nachricht, die in den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Kanalstapel übergeht, wird von einzelnen Kanälen verarbeitet, die durch zugeordnete Bindungselemente konfiguriert werden, u. a. Textnachrichtencodierung, Sicherheit, zuverlässiges Messaging und Transaktionen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-179">A message that enters the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] channel stack is processed by individual channels configured by associated binding elements, for example, Text Message Encoding, Security, Reliable Messaging, and Transactions.</span></span> <span data-ttu-id="cd0bd-180">Jeder Kanal erkennt Header des zugeordneten Namespace, und kennzeichnet sie als verstanden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-180">Each channel recognizes headers from the associated namespace and marks them as understood.</span></span> <span data-ttu-id="cd0bd-181">Sobald eine Nachricht in den Verteiler eingeht, liest der Vorgangsformatierer Header, die vom entsprechenden Nachrichten-/Vorgangsvertrag erwartet werden, und kennzeichnet sie als verstanden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-181">Once a message enters the dispatcher, the operation formatter reads headers expected by the corresponding message/operation contract and marks them understood.</span></span> <span data-ttu-id="cd0bd-182">Der Verteiler überprüft, ob einige der verbleibenden Header nicht verstanden, aber als `mustUnderstand` gekennzeichnet sind, und löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-182">Then the dispatcher verifies whether any remaining headers are not understood but marked as `mustUnderstand` and throws an exception.</span></span> <span data-ttu-id="cd0bd-183">Nachrichten, die an den Empfänger gerichtete `mustUnderstand`-Header enthalten, werden nicht vom Empfängeranwendungscode verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-183">Messages that contain `mustUnderstand` headers that are targeted at the recipient are not processed by recipient application code.</span></span>  
  
 <span data-ttu-id="cd0bd-184">Eine derartige schichtweise Verarbeitung lässt eine Trennung zwischen den Infrastrukturschichten und Anwendungsschichten auf dem SOAP-Knoten zu:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-184">Such layered processing allows for separation between infrastructure layers and application layers of the SOAP node:</span></span>  
  
-   <span data-ttu-id="cd0bd-185">B1111: Header, die nicht verstanden werden, werden nach der Verarbeitung der Nachricht durch den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Infrastrukturkanalstapel, aber vor der Verarbeitung durch die Anwendung erkannt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-185">B1111: Headers that are not understood are detected after the message is processed by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure channel stack, but before it is processed by application</span></span>  
  
     <span data-ttu-id="cd0bd-186">Der `mustUnderstand` Headerwert variiert zwischen SOAP 1.1 und SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-186">The `mustUnderstand` header value differs between SOAP 1.1 and SOAP 1.2.</span></span> <span data-ttu-id="cd0bd-187">Basic Profile 1.1 erfordert, dass der `mustUnderstand`-Wert für SOAP 1.1-Nachrichten "0" (null) oder "1" sein muss.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-187">Basic Profile 1.1 requires that the `mustUnderstand` value be 0 or 1 for SOAP 1.1 messages.</span></span> <span data-ttu-id="cd0bd-188">SOAP 1.2 lässt 0 (null), 1 `false` und `true` als Werte zu, empfiehlt aber die Ausgabe einer standardisierten Darstellung der `xs:boolean`-Werte (`false`, `true`).</span><span class="sxs-lookup"><span data-stu-id="cd0bd-188">SOAP 1.2 allows 0, 1, `false`, and `true` as values, but recommends emitting a canonical representation of `xs:boolean` values (`false`, `true`).</span></span>  
  
-   <span data-ttu-id="cd0bd-189">B1112: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gibt die `mustUnderstand`-Werte 0 und 1 sowohl für die SOAP 1.1- als auch für die SOAP 1.2-Version des SOAP-Umschlags aus.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-189">B1112: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] emits `mustUnderstand` values 0 and 1 for both SOAP 1.1 and SOAP 1.2 versions of the SOAP envelope.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-190"> akzeptiert den gesamten Wertebereich von `xs:boolean` für den `mustUnderstand`-Header (0, 1, `false`, `true`).</span><span class="sxs-lookup"><span data-stu-id="cd0bd-190"> accepts the entire value space of `xs:boolean` for the `mustUnderstand` header (0, 1, `false`, `true`)</span></span>  
  
#### <a name="soap-faults"></a><span data-ttu-id="cd0bd-191">SOAP-Fehler</span><span class="sxs-lookup"><span data-stu-id="cd0bd-191">SOAP Faults</span></span>  
 <span data-ttu-id="cd0bd-192">Die folgende Liste führt spezifische [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-SOAP-Fehler-Implementierungen auf.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-192">The following is a list of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-specific SOAP fault implementations.</span></span>  
  
-   <span data-ttu-id="cd0bd-193">B2121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gibt die folgenden SOAP 1.1-Fehlercodes: `s11:mustUnderstand`, `s11:Client`, und `s11:Server`.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-193">B2121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] returns the following SOAP 1.1 Fault Codes: `s11:mustUnderstand`, `s11:Client`, and `s11:Server`.</span></span>  
  
-   <span data-ttu-id="cd0bd-194">B2122: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gibt die folgenden SOAP 1.2-Fehlercodes zurück: `s12:MustUnderstand`, `s12:Sender` und `s12:Receiver`.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-194">B2122: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] returns the following SOAP 1.2 Fault Codes: `s12:MustUnderstand`, `s12:Sender`, and `s12:Receiver`.</span></span>  
  
### <a name="http-binding"></a><span data-ttu-id="cd0bd-195">HTTP-Bindung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-195">HTTP Binding</span></span>  
  
#### <a name="soap-11-http-binding"></a><span data-ttu-id="cd0bd-196">SOAP 1.1 HTTP-Bindung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-196">SOAP 1.1 HTTP Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-197"> implementiert die SOAP1.1 HTTP-Bindung gemäß Abschnitt 3.4 der Basic Profile 1.1-Spezifikation, mit den folgenden Erklärungen:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-197"> implements SOAP1.1 HTTP binding following the Basic Profile 1.1 specification section 3.4 with the following clarifications:</span></span>  
  
-   <span data-ttu-id="cd0bd-198">B2211: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst implementiert keine Umleitung von HTTP-POST-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-198">B2211: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service does not implement redirection of HTTP POST requests.</span></span>  
  
-   <span data-ttu-id="cd0bd-199">B2212: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Clients unterstützen HTTP-Cookies in Übereinstimmung mit 3.4.8.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-199">B2212: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients support HTTP Cookies in accordance with 3.4.8.</span></span>  
  
#### <a name="soap-12-http-binding"></a><span data-ttu-id="cd0bd-200">SOAP 1,2 HTTP-Bindung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-200">SOAP 1.2 HTTP Binding</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-201"> implementiert die SOAP1.2 HTTP-Bindung gemäß der Beschreibung in der SOAP 1.2-Teil 2 (SOAP12Part2)-Spezifikation, mit den folgenden Erklärungen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-201"> implements SOAP 1.2 HTTP binding as described in the SOAP 1.2-part 2 (SOAP12Part2) specification with the following clarifications.</span></span>  
  
 <span data-ttu-id="cd0bd-202">SOAP 1.2 hat einen optionalen Aktionsparameter für den `application/soap+xml`-Medientyp eingeführt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-202">SOAP 1.2 introduced an optional action parameter for the `application/soap+xml` media type.</span></span> <span data-ttu-id="cd0bd-203">Dieser Parameter ist nützlich bei der Optimierung des Sendens von Nachrichten, ohne dass der Text der SOAP-Nachricht analysiert werden muss, wenn die WS-Adressierung nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-203">This parameter is useful to optimize message dispatch without requiring that the body of the SOAP message be parsed when WS-Addressing is not used.</span></span>  
  
-   <span data-ttu-id="cd0bd-204">R2221: Der `application/soap+xml`-Aktionsparameter muss, wenn er in einer SOAP 1.2-Anforderung vorliegt, dem Attribut `soapAction` auf dem Element `wsoap12:operation` in der dazugehörigen WSDL-Bindung entsprechen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-204">R2221: The `application/soap+xml` action parameter, when present on a SOAP 1.2 request, must match the `soapAction` attribute on the `wsoap12:operation` element inside the corresponding WSDL binding.</span></span>  
  
-   <span data-ttu-id="cd0bd-205">R2222: Der `application/soap+xml`-Anwendungsparameter muss, wenn er in einer SOAP 1.2-Nachricht vorliegt, `wsa:Action` entsprechen, wenn die WS-Adressierung 2004/08 oder die WS-Adressierung 1.0 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-205">R2222: The `application/soap+xml` action parameter, when present on a SOAP 1.2 message, must match `wsa:Action` when WS-Addressing 2004/08 or WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="cd0bd-206">Wenn die WS-Adressierung deaktiviert ist und eine eingehende Anforderung keinen Aktionsparameter enthält, gilt die Nachrichten-`Action` als nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-206">When WS-Addressing is disabled and an incoming request does not contain an action parameter, message `Action` is considered not specified.</span></span>  
  
## <a name="ws-addressing"></a><span data-ttu-id="cd0bd-207">WS-Adressierung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-207">WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-208"> implementiert drei Versionen der WS-Adressierung:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-208"> implements 3 versions of WS-Addressing:</span></span>  
  
-   <span data-ttu-id="cd0bd-209">WS-Adressierung 2004/08</span><span class="sxs-lookup"><span data-stu-id="cd0bd-209">WS-Addressing 2004/08</span></span>  
  
-   <span data-ttu-id="cd0bd-210">W3C Web Services Addressing 1.0 Core (ADDR10-KERN) und SOAP-Bindung (ADDR10-SOAP)</span><span class="sxs-lookup"><span data-stu-id="cd0bd-210">W3C Web Services Addressing 1.0 Core  (ADDR10-CORE) and SOAP Binding (ADDR10-SOAP)</span></span>  
  
-   <span data-ttu-id="cd0bd-211">WS-Addressing 1.0 - Metadata</span><span class="sxs-lookup"><span data-stu-id="cd0bd-211">WS-Addressing 1.0 - Metadata</span></span>  
  
### <a name="endpoint-references"></a><span data-ttu-id="cd0bd-212">Endpunktverweise</span><span class="sxs-lookup"><span data-stu-id="cd0bd-212">Endpoint References</span></span>  
 <span data-ttu-id="cd0bd-213">Alle Versionen der WS-Adressierung, die von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementiert werden, verwenden zur Beschreibung von Endpunkten Endpunktverweise.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-213">All versions of WS-Addressing that [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implements use endpoint references to describe endpoints.</span></span>  
  
#### <a name="endpoint-references-and-ws-addressing-versions"></a><span data-ttu-id="cd0bd-214">Endpunktverweise und WS-Adressierungsversionen</span><span class="sxs-lookup"><span data-stu-id="cd0bd-214">Endpoint References and WS-Addressing Versions</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-215"> implementiert eine Reihe von Infrastrukturprotokollen, die WS-Adressierung und insbesondere das `EndpointReference`-Element und die `W3C.WsAddressing.EndpointReferenceType`-Klasse verwenden (z. B. WS-ReliableMessaging, WS-SecureConversation und WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="cd0bd-215"> implements a number of the infrastructure protocols that use WS-Addressing and in particular the `EndpointReference` element and `W3C.WsAddressing.EndpointReferenceType` class (for example, WS-ReliableMessaging, WS-SecureConversation, and WS-Trust).</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-216"> unterstützt die Verwendung beider Versionen der WS-Adressierung mit anderen Infrastrukturprotokollen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-216"> supports the use of either version of WS-Addressing with other infrastructure protocols.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-217">-Endpunkte unterstützen eine Version der WS-Adressierung pro Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-217"> endpoints support one version of WS-Addressing per endpoint.</span></span>  
  
 <span data-ttu-id="cd0bd-218">Für R3111 muss der Namespace des `EndpointReference`-Elements oder -Typs, das/der in über einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkt ausgetauschten Nachrichten verwendet wird, der Version der WS-Adressierung entsprechen, die von diesem Endpunkt implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-218">For R3111, the namespace for the `EndpointReference` element or type used in messages exchanged with a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint must match the version of WS-Addressing implemented by this endpoint.</span></span>  
  
 <span data-ttu-id="cd0bd-219">Wenn beispielsweise ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkt WS-ReliableMessaging implementiert, verwendet der Header `AcksTo`, der von einem derartigen Endpunkt in `CreateSequenceResponse` zurückgegeben wird, die WS-Adressierungsversion, die das `EncodingBinding`-Element für diesen Endpunkt angibt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-219">For example, if a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint implements WS-ReliableMessaging, the `AcksTo` header returned by such an endpoint inside `CreateSequenceResponse` uses the WS-Addressing version that the `EncodingBinding` element specifies for this endpoint.</span></span>  
  
#### <a name="endpoint-references-and-metadata"></a><span data-ttu-id="cd0bd-220">Endpunktverweise und Metadaten</span><span class="sxs-lookup"><span data-stu-id="cd0bd-220">Endpoint References and Metadata</span></span>  
 <span data-ttu-id="cd0bd-221">Eine Anzahl von Szenarien erfordert kommunizierende Metadaten oder einen Verweis auf Metadaten für einen bestimmten Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-221">A number of scenarios require communicating metadata or a reference to metadata for a given endpoint.</span></span>  
  
 <span data-ttu-id="cd0bd-222">B3121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wendet Mechanismen an, die im Abschnitt 6 der WS-MetadataExchange (MEX)-Spezifikation beschrieben werden, um Metadaten für Endpunktverweise nach Wert oder Verweis aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-222">B3121: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] employs mechanisms described in the WS-MetadataExchange (MEX) specification Section 6 to include metadata for endpoint references by value or by reference.</span></span>  
  
 <span data-ttu-id="cd0bd-223">Stellen Sie sich ein Szenario vor, in dem ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst Authentifizierung über ein Security Assertions Markup Language (SAML)-Token erfordert, das vom Tokenaussteller unter http://sts.fabrikam123.com ausgestellt wurde. Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkt beschreibt diese Authentifizierungsanforderung, indem er die `sp:IssuedToken`-Assertion zusammen mit einer verschachtelten `sp:Issuer`-Assertion verwendet, die auf den Tokenaussteller hinweist.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-223">Consider a scenario where a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service requires authentication using a Security Assertions Markup Language (SAML) token issued by the token issuer at http://sts.fabrikam123.com. The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint describes this authentication requirement by using `sp:IssuedToken` assertion with a nested `sp:Issuer` assertion pointing to the token issuer.</span></span> <span data-ttu-id="cd0bd-224">Clientanwendungen, die auf die `sp:Issuer`-Assertion zugreifen, müssen mit dem Tokenausstellerendpunkt kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-224">Client applications that access the `sp:Issuer` assertion need to know how to communicate with the token issuer endpoint.</span></span> <span data-ttu-id="cd0bd-225">Der Client muss Metadaten über den Tokenaussteller kennen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-225">The client needs to know metadata about the token issuer.</span></span> <span data-ttu-id="cd0bd-226">Durch die Nutzung der Erweiterungen für Endpunktverweismetadaten, die in MEX definiert sind, bietet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] einen Verweis auf die Tokenausstellermetadaten.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-226">Using the endpoint reference metadata extensions defined in MEX, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides a reference to the token issuer metadata.</span></span>  
  
```xml  
<sp:IssuedToken>  
  <sp:Issuer>  
    <wsa10:Address>  
      http://sts.fabrikam123.com  
    </wsa10:Address>  
    <wsa10:Metadata>  
      <mex:Metadata>  
        <mex:MetadataSection>  
          <mex:MetadataReference>  
            <wsa10:Address>  
              http://sts.fabrikam123.com/mex  
            </wsa10:Address>  
          </mex:MetadataReference>  
        </mex:MetadataSection>  
      </mex:Metadata>  
    </wsa10:Metadata>  
  </sp:Issuer>  
</sp:IssuedToken>  
```  
  
### <a name="message-addressing-headers"></a><span data-ttu-id="cd0bd-227">Nachrichtenadressierungsheader</span><span class="sxs-lookup"><span data-stu-id="cd0bd-227">Message Addressing Headers</span></span>  
  
#### <a name="message-headers"></a><span data-ttu-id="cd0bd-228">Nachrichtenheader</span><span class="sxs-lookup"><span data-stu-id="cd0bd-228">Message Headers</span></span>  
 <span data-ttu-id="cd0bd-229">Für beide Versionen der WS-Adressierung [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet die folgenden Nachrichtenheader gemäß den Spezifikationen `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`, und `wsa:RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-229">For both WS-Addressing versions, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the following message headers as prescribed by the specifications `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`,and `wsa:RelatesTo`.</span></span>  
  
 <span data-ttu-id="cd0bd-230">B3211: Für beide WS-Adressierungsversionen akzeptiert [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] die WS-Adressierungs-Nachrichtenheader `wsa:FaultTo` und `wsa:From`, erstellt sie aber nicht selbst.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-230">B3211: For all WS-Addressing versions, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] honors, but does not produce out of the box, WS-Addressing message headers `wsa:FaultTo` and `wsa:From`.</span></span>  
  
 <span data-ttu-id="cd0bd-231">Anwendungen, die mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Anwendungen interagieren, können diese Nachrichtenheader hinzufügen und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verarbeitet sie dementsprechend.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-231">Applications that interact with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications can add these message headers and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] will process them accordingly.</span></span>  
  
#### <a name="reference-parameters-and-properties"></a><span data-ttu-id="cd0bd-232">Verweisparameter und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="cd0bd-232">Reference Parameters and Properties</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-233"> implementiert die Verarbeitung von Endpunktverweisparametern und</span><span class="sxs-lookup"><span data-stu-id="cd0bd-233"> implements processing of endpoint reference parameters and reference p</span></span>  
  
 <span data-ttu-id="cd0bd-234">Verweiseigenschaften in Übereinstimmung mit den jeweiligen Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-234">roperties in accordance with respective specifications.</span></span>  
  
 <span data-ttu-id="cd0bd-235">B3221: Wenn die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkte für eine Verwendung von WS-Addressing 2004/08 konfiguriert sind, machen sie keinen Unterschied zwischen der Verarbeitung von Verweiseigenschaften und Verweisparametern.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-235">B3221: When configured to use WS-Addressing 2004/08, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoints do not differentiate between processing Reference Properties and Reference Parameters.</span></span>  
  
### <a name="message-exchange-patterns"></a><span data-ttu-id="cd0bd-236">Nachrichtenaustauschmuster</span><span class="sxs-lookup"><span data-stu-id="cd0bd-236">Message Exchange Patterns</span></span>  
 <span data-ttu-id="cd0bd-237">Die Abfolge von Meldungen Beteiligten die Webdienstvorgangs wird als bezeichnet den *Nachrichtenaustauschmuster*.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-237">The sequence of messages involved in the Web service operation invocation is referred to as the *message exchange pattern*.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-238"> unterstützt unidirektionale, Anfrage-Antwort- und Duplexnachrichten-Austauschmuster.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-238"> supports one-way, request-reply, and duplex message exchange patterns.</span></span> <span data-ttu-id="cd0bd-239">Dieser Abschnitt klärt die WS-Adressierungsanforderungen während der Nachrichtenverarbeitung, die vom verwendeten Nachrichtenaustauschmuster abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-239">This section clarifies WS-Addressing requirements on message processing depending on the message exchange pattern being used.</span></span>  
  
 <span data-ttu-id="cd0bd-240">Überall in diesem Abschnitt sendet der Anforderungsdienst die erste Nachricht, und der Antwortdienst empfängt die erste Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-240">Throughout this section, the requester sends the first message and the responder receives the first message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="cd0bd-241">Unidirektionale Nachricht</span><span class="sxs-lookup"><span data-stu-id="cd0bd-241">One-Way Message</span></span>  
 <span data-ttu-id="cd0bd-242">Wenn ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkt so konfiguriert ist, dass er Nachrichten mit einer angegebenen `Action` unterstützt, sodass sie ein unidirektionales Muster befolgen, befolgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkt die folgenden Verhalten und Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-242">When a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint is configured to support messages with a given `Action` to follow a one-way pattern, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint follows the following behaviors and requirements.</span></span> <span data-ttu-id="cd0bd-243">Sofern nicht anders angegeben, gelten die Verhalten und Regeln für beide Versionen der WS-Adressierung, die in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-243">Unless otherwise specified, behaviors and rules apply for both versions of WS-Addressing supported in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="cd0bd-244">R3311: Der Anforderungsdienst muss `wsa:To`, `wsa:Action` und Header für alle Verweisparameter, die vom Endpunktverweis angegeben werden, enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-244">R3311: The requester must include `wsa:To`, `wsa:Action`, and headers for all reference parameters specified by the endpoint reference.</span></span> <span data-ttu-id="cd0bd-245">Wenn die WS-Adressierung 2004/08 verwendet wird und [Verweiseigenschaften] vom Endpunktverweis angegeben werden, müssen auch die entsprechenden Header der Nachricht hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-245">When WS-Addressing 2004/08 is used and [reference properties] are specified by the endpoint reference, the corresponding headers must be added to the message too.</span></span>  
  
-   <span data-ttu-id="cd0bd-246">B3312: Der Anforderungsdienst kann `MessageID`-, `ReplyTo`- und `FaultTo`-Header enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-246">B3312: The requester may include `MessageID`, `ReplyTo`, and `FaultTo` headers.</span></span> <span data-ttu-id="cd0bd-247">Die Empfängerinfrastruktur ignoriert sie, und sie werden an die Anwendung übergeben.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-247">The receiver infrastructure will ignore them, and they will be passed to the application.</span></span>  
  
-   <span data-ttu-id="cd0bd-248">R3313: Wenn HTTP verwendet wird und keine Nachricht an den HTTP-Antwortzweig gesendet wird, muss der Antwortdienst eine HTTP-Antwort ohne Text und mit einem HTTP 202-Statuscode senden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-248">R3313: When HTTP is used and no message is being sent on the HTTP response leg, the responder must send an HTTP response with an empty body and an HTTP 202 status code.</span></span>  
  
     <span data-ttu-id="cd0bd-249">Wenn die HTTP-Transportmethode verwendet wird und der Vorgangsvertrag eine Nachricht als unidirektional ausweist, kann die HTTP-Antwort immer noch zum Senden von Infrastrukturnachrichten verwendet werden – Reliable Messaging kann beispielsweise eine `SequenceAcknowledgement`-Nachricht in einer HTTP-Antwort senden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-249">When the HTTP transport is in use and the operation contract declares a message one-way, the HTTP response can still be used for sending infrastructure messages—for example, reliable messaging can send a `SequenceAcknowledgement` message on an HTTP response.</span></span>  
  
-   <span data-ttu-id="cd0bd-250">B3314: Der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Antwortdienst sendet keine Fehlermeldung als Antwort auf eine unidirektionale Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-250">B3314: The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] responder does not send a fault message in response to a one-way message.</span></span>  
  
#### <a name="request-reply"></a><span data-ttu-id="cd0bd-251">Anforderung-Antwort</span><span class="sxs-lookup"><span data-stu-id="cd0bd-251">Request-Reply</span></span>  
 <span data-ttu-id="cd0bd-252">Wenn ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkt für eine Nachricht mit einer bestimmten `Action` so konfiguriert ist, dass er das Anforderung-Antwort-Muster befolgt, befolgt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkt die unten stehenden Verhalten und Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-252">When a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint is configured for a message with a given `Action` to follow the request-reply pattern, the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint follows the behaviors and requirements below.</span></span> <span data-ttu-id="cd0bd-253">Sofern nicht anders angegeben, gelten die Verhalten und Regeln für beide Versionen der WS-Adressierung, die in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-253">Unless specified otherwise, behaviors and rules apply for both versions of WS-Addressing supported in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]:</span></span>  
  
-   <span data-ttu-id="cd0bd-254">R3321: Der anforderungsdienst muss in der Anforderung enthalten `wsa:To`, `wsa:Action`, `wsa:MessageID`, und der Header für alle Verweisparameter oder Verweis Eigenschaften (oder beides) vom Endpunktverweis angegeben.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-254">R3321: The requester must include in the request `wsa:To`, `wsa:Action`, `wsa:MessageID`, and headers for all reference parameters or reference properties (or both) specified by the endpoint reference.</span></span>  
  
-   <span data-ttu-id="cd0bd-255">R3322: Wenn die WS-Adressierung 2004/08 verwendet wird, muss `ReplyTo` auch in der Anforderung enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-255">R3322: When WS-Addressing 2004/08 is used, `ReplyTo` must also be included in the request.</span></span>  
  
-   <span data-ttu-id="cd0bd-256">R3323: Wenn die WS-Adressierung 1.0 verwendet wird und `ReplyTo` nicht in der Anforderung enthalten ist, wird ein Standardendpunktverweis, dessen [Adresse]-Eigenschaft "http://www.w3.org/2005/08/addressing/anonymous" entspricht, verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-256">R3323: When WS-Addressing 1.0 is used and `ReplyTo` is not present in the request, a default endpoint reference with the [address] property equal to "http://www.w3.org/2005/08/addressing/anonymous" is used.</span></span>  
  
-   <span data-ttu-id="cd0bd-257">R3324: Der anforderungsdienst muss enthalten `wsa:To`, `wsa:Action`, und `wsa:RelatesTo` Header in der Antwortnachricht als auch Header für alle Verweisparameter oder Verweis Eigenschaften (oder beides) gemäß der `ReplyTo` -Endpunktverweis in der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-257">R3324: The requester must include `wsa:To`, `wsa:Action`, and `wsa:RelatesTo` headers in the reply message, as well as headers for all reference parameters or reference properties (or both) specified by the `ReplyTo` endpoint reference in the request.</span></span>  
  
### <a name="web-services-addressing-faults"></a><span data-ttu-id="cd0bd-258">Fehler bei Web Services Addressing</span><span class="sxs-lookup"><span data-stu-id="cd0bd-258">Web Services Addressing Faults</span></span>  
 <span data-ttu-id="cd0bd-259">R3411: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erzeugt die folgenden, von der WS-Adressierung 2004/08 definierten Fehler.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-259">R3411: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produces the following faults defined by WS-Addressing 2004/08.</span></span>  
  
|<span data-ttu-id="cd0bd-260">Code</span><span class="sxs-lookup"><span data-stu-id="cd0bd-260">Code</span></span>|<span data-ttu-id="cd0bd-261">Ursache</span><span class="sxs-lookup"><span data-stu-id="cd0bd-261">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="cd0bd-262">wsa:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="cd0bd-262">wsa:DestinationUnreachable</span></span>|<span data-ttu-id="cd0bd-263">Die Nachricht ist mit `ReplyTo` angekommen, das sich von der Antwortadresse, die für diesen Kanal festgelegt ist, unterscheidet; für die in der To-Headerzeile angegebene Adresse gibt es kein Endpunkt-Listening.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-263">The message arrived with a `ReplyTo` that is different from the reply address established for this channel; there is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="cd0bd-264">wsa:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="cd0bd-264">wsa:ActionNotSupported</span></span>|<span data-ttu-id="cd0bd-265">Die Infrastrukturkanäle und -verteiler, die mit dem Endpunkt verbunden sind, erkennen die Aktion, die in der Headerzeile `Action` angegeben ist, nicht.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-265">the infrastructure channels or dispatcher associated with the endpoint do not recognize the action specified in the `Action` header.</span></span>|  
  
 <span data-ttu-id="cd0bd-266">R3412: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] erzeugt die folgenden, von der WS-Adressierung 1.0 definierten Fehler.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-266">R3412: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] produces the following faults defined by WS-Addressing 1.0.</span></span>  
  
|<span data-ttu-id="cd0bd-267">Code</span><span class="sxs-lookup"><span data-stu-id="cd0bd-267">Code</span></span>|<span data-ttu-id="cd0bd-268">Ursache</span><span class="sxs-lookup"><span data-stu-id="cd0bd-268">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="cd0bd-269">wsa10:InvalidAddressingHeader</span><span class="sxs-lookup"><span data-stu-id="cd0bd-269">wsa10:InvalidAddressingHeader</span></span>|<span data-ttu-id="cd0bd-270">Doppelte `wsa:To`, `wsa:ReplyTo`, `wsa:From` oder `wsa:MessageID`.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-270">Duplicate `wsa:To`, `wsa:ReplyTo`, `wsa:From` or `wsa:MessageID`.</span></span> <span data-ttu-id="cd0bd-271">Doppelte `wsa:RelatesTo` mit dem gleichen `RelationshipType`.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-271">Duplicate `wsa:RelatesTo` with the same `RelationshipType`.</span></span>|  
|<span data-ttu-id="cd0bd-272">wsa10:MessageAddressingHeaderRequired</span><span class="sxs-lookup"><span data-stu-id="cd0bd-272">wsa10:MessageAddressingHeaderRequired</span></span>|<span data-ttu-id="cd0bd-273">Der erforderliche Adressierungsheader fehlt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-273">The required Addressing header is missing.</span></span>|  
|<span data-ttu-id="cd0bd-274">wsa10:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="cd0bd-274">wsa10:DestinationUnreachable</span></span>|<span data-ttu-id="cd0bd-275">Die Nachricht ist mit `ReplyTo` angekommen, das sich von der Antwortadresse, die für diesen Kanal eingeführt wurde, unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-275">The message arrived with a `ReplyTo` that is different from the reply address established for this channel.</span></span> <span data-ttu-id="cd0bd-276">An der Adresse, die im To-Header angegeben ist, gibt es kein Endpunkt-Listening.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-276">There is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="cd0bd-277">wsa10:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="cd0bd-277">wsa10:ActionNotSupported</span></span>|<span data-ttu-id="cd0bd-278">Eine Aktion, die im `Action`-Header angegeben ist, wird von den Infrastrukturkanälen oder dem Verteiler, die/der mit dem Endpunkt verbunden sind/ist, nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-278">An action specified in the `Action` header is not recognized by the infrastructure channels or dispatcher associated with the endpoint.</span></span>|  
|<span data-ttu-id="cd0bd-279">wsa10:EndpointUnavailable</span><span class="sxs-lookup"><span data-stu-id="cd0bd-279">wsa10:EndpointUnavailable</span></span>|<span data-ttu-id="cd0bd-280">Der RM-Kanal schickt diesen Fehler zurück und gibt an, dass der Endpunkt die Sequenz basierend auf einer Untersuchung der Adressheader der Nachricht `CreateSequence` nicht verarbeiten wird.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-280">The RM channel sends this fault back, indicating the endpoint will not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>|  
  
 <span data-ttu-id="cd0bd-281">Code in den vorangehenden Tabellen wird auf `FaultCode` in SOAP 1.1 und `SubCode` (mit Code=Sender) in SOAP 1.2 abgebildet.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-281">Code in the preceding tables maps to `FaultCode` in SOAP 1.1 and `SubCode` (with Code=Sender) in SOAP 1.2.</span></span>  
  
### <a name="wsdl-11-binding-and-ws-policy-assertions"></a><span data-ttu-id="cd0bd-282">WSDL 1.1-Bindung und WS-Richtlinienassertionen</span><span class="sxs-lookup"><span data-stu-id="cd0bd-282">WSDL 1.1 Binding and WS-Policy Assertions</span></span>  
  
#### <a name="indicating-use-of-ws-addressing"></a><span data-ttu-id="cd0bd-283">Angeben der Verwendung von WS-Adressierung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-283">Indicating Use of WS-Addressing</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-284"> verwendet Richtlinienassertionen, um Endpunktunterstützung für eine bestimmte WS-Adressierungsversion anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-284"> uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span></span>  
  
 <span data-ttu-id="cd0bd-285">Die folgende Richtlinienassertion verfügt über das Endpoint Policy Subject [WS-PA] und gibt an, dass von diesem Endpunkt gesendete und empfangene Nachrichten WS-Adressierung 2004/08 verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-285">The following policy assertion has Endpoint Policy Subject [WS-PA] and indicates messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsap:UsingAddressing />  
```  
  
 <span data-ttu-id="cd0bd-286">Diese Richtlinienassertion erweitert die Spezifikation zur WS-Adressierung 2004/08.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-286">This policy assertion augments the WS-Addressing 2004/08 specification.</span></span>  
  
 <span data-ttu-id="cd0bd-287">Die folgende Richtlinienassertion gibt an, dass gesendete/empfangene Nachrichten die WS-Adressierung 1.0 verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-287">The following policy assertion this indicates that messages sent/received must use WS-Addressing 1.0.</span></span>  
  
```xml
<wsam:Addressing/>   
```  
  
 <span data-ttu-id="cd0bd-288">Die folgende Richtlinienassertion verfügt über ein Endpoint Policy Subject [WS-PA] und gibt an, dass von diesem Endpunkt gesendete und empfangene Nachrichten WS-Adressierung 2004/08 verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-288">The following policy assertion has an Endpoint Policy Subject [WS-PA] and indicates that messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsaw10:UsingAddressing />  
```  
  
 <span data-ttu-id="cd0bd-289">Das Element `wsaw10:UsingAddressing` wird aus der [WS-Addressing-WSDL] ausgeliehen und im Kontext von WS-Policy entsprechend der Spezifikation, Abschnitt 3.1.2, verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-289">The `wsaw10:UsingAddressing` element is borrowed from [WS-Addressing-WSDL] and is used in the context of WS-Policy in compliance with that specification, section 3.1.2.</span></span>  
  
 <span data-ttu-id="cd0bd-290">Die Nutzung von Adressing verwendet nicht die Semantik von WSDL 1.1-, SOAP 1.1- und SOAP 1.2 HTTP-Bindungen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-290">Use of Addressing does not alter the semantics of WSDL 1.1, SOAP 1.1, and SOAP 1.2 HTTP Bindings.</span></span> <span data-ttu-id="cd0bd-291">Wenn beispielsweise eine Antwort auf eine Anfrage erwartet wird, die an einen Endpunkt gesendet wird, der Addressing und WSDL SOAP 1.x HTTP-Bindung verwendet, muss die Antwort unter Verwendung der HTTP-Antwort gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-291">For example, if a reply is expected to a request that is sent to an endpoint that uses Addressing and WSDL SOAP 1.x HTTP binding, the reply must be sent by using the HTTP response.</span></span>  
  
 <span data-ttu-id="cd0bd-292">Die WS-AM-Assertion von Antworten, die über die HTTP-Antwort gesendet werden, ist Folgende:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-292">For replies sent over the http response, the WS-AM assertion is:</span></span>  
  
```xml  
<wsam:AnonymousResponses/>  
```  
  
 <span data-ttu-id="cd0bd-293">Die vollständige Richtlinienassertion kann wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-293">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
        <wsam:AnonymousResponses />   
    </wsp:Policy>  
</wsam:Addressing>  
```  
  
 <span data-ttu-id="cd0bd-294">Es gibt aber Nachrichtenaustauschmuster, die davon profitieren, zwei unabhängige, entgegengesetzte HTTP-Verbindungen zwischen dem Anforderungsdienst und dem Antwortdienst etabliert zu haben, z. B. unaufgeforderte unidirektionale Nachrichten, die vom Antwortdienst gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-294">However, there are message exchange patterns that benefit from having two independent converse HTTP connections established between the requester and the responder, for example, unsolicited one-way messages sent by the responder.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-295"> bietet eine Funktion,über die zwei zugrunde liegende Transportkanäle einen Composite Duplex-Kanal bilden können, bei dem ein Kanal für eingehende Nachrichten und der andere für ausgehende Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-295"> offers a feature by which two underlying transport channels can form a Composite Duplex channel, where one channel is used for input messages and the other is used for output messages.</span></span> <span data-ttu-id="cd0bd-296">Im Fall des HTTP-Transports stellt Composite Duplex zwei umgekehrte HTTP-Verbindungen bereit.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-296">In the case of the HTTP Transport, Composite Duplex provides two converse HTTP connections.</span></span> <span data-ttu-id="cd0bd-297">Der Anforderungsdienst verwendet eine Verbindung, um Nachrichten an den Antwortdienst zu senden, und der Antwortdienst verwendet die andere, um Nachrichten zurück an den Anforderungsdienst zu senden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-297">The requester uses one connection to send messages to the responder, and the responder uses the other to send messages back to the requester.</span></span>  
  
 <span data-ttu-id="cd0bd-298">Die WS-AM-Assertion von Antworten, die über separate HTTP-Anforderungen gesendet werden, ist Folgende:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-298">For replies sent over separate http requests, the ws-am assertion is</span></span>  
  
```xml  
<wsam:NonAnonymousResponses/>  
```  
  
 <span data-ttu-id="cd0bd-299">Die vollständige Richtlinienassertion kann wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-299">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
      <wsam:NonAnonymousResponses />   
   </wsp:Policy>  
  </wsam:Addressing>  
```  
  
 <span data-ttu-id="cd0bd-300">Die Verwendung der folgenden Assertion, die über Endpoint Policy Subject [WS-PA] an Endpunkten verfügt, die WSDL 1.1 SOAP 1.x HTTP-Bindungen verwenden, erfordert zwei einzelne entgegengesetzte HTTP-Verbindungen, die jeweils für den Nachrichtenfluss vom Anforderungsdienst an den Antwortdienst bzw. vom Antwortdienst an den Anforderungsdienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-300">Use of the following assertion that has Endpoint Policy Subject [WS-PA] on endpoints that use WSDL 1.1 SOAP 1.x HTTP bindings requires two separate converse HTTP connections to be used for messages flowing from requester to responder and responder to requester, respectively.</span></span>  
  
```xml  
<cdp:CompositeDuplex/>  
```  
  
 <span data-ttu-id="cd0bd-301">Die vorherige Anweisung führt bei Anforderungsnachrichten zu den folgenden Anforderungen an den `wsa:ReplyTo`-Header:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-301">The previous statement leads to the following requirements on the `wsa:ReplyTo` header for request messages:</span></span>  
  
-   <span data-ttu-id="cd0bd-302">R3514: Die an einen Endpunkt gesendeten Anforderungsnachrichten müssen über einen `ReplyTo`-Header verfügen, dessen Eigenschaft `[address]` nicht "http://www.w3.org/2005/08/addressing/anonymous" entspricht, wenn der Endpunkt eine WSDL 1.1 SOAP 1.x HTTP-Bindung verwendet und über eine Richtlinienalternative verfügt, der eine `wsap10:UsingAddressing`- oder eine `wsap:UsingAddressing`-Assertion, die mit `cdp:CompositeDuplex` verbunden ist, angehängt ist.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-302">R3514: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property not equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with a `wsap10:UsingAddressing` or `wsap:UsingAddressing` assertion coupled with `cdp:CompositeDuplex` attached.</span></span>  
  
-   <span data-ttu-id="cd0bd-303">R3515: Die an einen Endpunkt gesendeten Anforderungsnachrichten müssen über einen `ReplyTo`-Header verfügen, dessen Eigenschaft `[address]` "http://www.w3.org/2005/08/addressing/anonymous" entspricht, oder gar keinen `ReplyTo` -Header besitzen, wenn der Endpunkt eine WSDL 1.1 SOAP 1.x HTTP-Bindung verwendet und über eine Richtlinienalternative mit `wsap10:UsingAddressing`-Assertion und keiner verbundenen `cdp:CompositeDuplex`-Assertion verfügt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-303">R3515: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous", or not have a `ReplyTo` header at all, if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap10:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
-   <span data-ttu-id="cd0bd-304">R3516: Die an einen Endpunkt gesendeten Anforderungsnachrichten müssen über einen `ReplyTo`-Header verfügen, dessen Eigenschaft `[address]` nicht "http://www.w3.org/2005/08/addressing/anonymous" entspricht, wenn der Endpunkt eine WSDL 1.1 SOAP 1.x HTTP-Bindung verwendet und über eine Richtlinienalternative verfügt, der eine `wsap:UsingAddressing`- und keine `cdp:CompositeDuplex`-Assertion angehängt ist.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-304">R3516: Request messages sent to an endpoint must have a `ReplyTo` header with an `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
 <span data-ttu-id="cd0bd-305">Die WS-Adressierung-WSDL-Spezifikation versucht, ähnliche Protokollbindungen zu beschreiben, indem sie ein `<wsaw:Anonymous/>`-Element mit drei Textwerten (erforderlich, optional und verboten) einführt, um die Anforderungen im `wsa:ReplyTo`-Header (Abschnitt 3.2) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-305">The WS-addressing WSDL specification attempts to describe similar protocol bindings by introducing an element `<wsaw:Anonymous/>` with three textual values (required, optional, and prohibited) to indicate requirements on the `wsa:ReplyTo` header (section 3.2).</span></span> <span data-ttu-id="cd0bd-306">Leider ist eine derartige Elementdefinition im Kontext einer WS-Richtlinie als Assertion nicht besonders nützlich, da sie domänenspezifische Erweiterungen benötigt, um den Knotenpunkt von Alternativen zu unterstützen, die ein derartiges Element als Assertion verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-306">Unfortunately, such element definition is not particularly usable as an assertion in the context of WS-Policy, because it requires domain-specific extensions to support the intersection of alternatives using such an element as an assertion.</span></span> <span data-ttu-id="cd0bd-307">Eine derartige Elementdefinition gibt außerdem den Wert des `ReplyTo`-Headers als Gegenstück zum Endpunktverhalten auf dem Kabel an und macht ihn somit spezifisch für den HTTP-Transport.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-307">Such element definition also indicates the value of the `ReplyTo` header as opposed to the endpoint behavior on the wire, which makes it specific to HTTP transport.</span></span>  
  
#### <a name="action-definition"></a><span data-ttu-id="cd0bd-308">Aktionsdefinition</span><span class="sxs-lookup"><span data-stu-id="cd0bd-308">Action Definition</span></span>  
 <span data-ttu-id="cd0bd-309">WS-Adressierung 2004/08 definiert ein `wsa:Action`-Attribut für die `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`-Elemente.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-309">WS-Addressing 2004/08 defines a `wsa:Action` attribute for the `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements.</span></span> <span data-ttu-id="cd0bd-310">WS-Adressierung 1.0 WSDL-Bindung (WS-ADDR10-WSDL) definiert ein ähnliches Attribut, `wsaw10:Action`.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-310">WS-Addressing 1.0 WSDL Binding (WS-ADDR10-WSDL) defines a similar attribute, `wsaw10:Action`.</span></span>  
  
 <span data-ttu-id="cd0bd-311">Der einzige Unterschied zwischen den beiden ist die Standardaktionsmustersemantik, die in Abschnitt 3.3.2 von WS-ADDR bzw. Abschnitt 4.4.4 der 4.4.4 von WS-ADDR10-WSDL beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-311">The only difference between the two is the default Action pattern semantics described in section 3.3.2 of WS-ADDR and section 4.4.4 of WS-ADDR10-WSDL, respectively.</span></span>  
  
 <span data-ttu-id="cd0bd-312">Es ist sinnvoll, zwei Endpunkte zu haben, die sich den gleichen `portType` (oder "Vertrag", in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Terminologie) teilen, aber verschiedene Versionen der WS-Adressierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-312">It is a reasonable to have two endpoints that share the same `portType` (or contract, in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] terminology) but using different versions of WS-Addressing.</span></span> <span data-ttu-id="cd0bd-313">Da aber "Aktion" durch den `portType` definiert wird und sich nicht zwischen den Endpunkten, die den `portType` implementieren, ändern sollte, ist es unmöglich, beide Standardaktionsmuster zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-313">But given that Action is defined by the `portType` and should not change across the endpoints that implement the `portType`, it becomes impossible to support both default action patterns.</span></span>  
  
 <span data-ttu-id="cd0bd-314">Um diese Kontroverse aufzulösen, unterstützt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eine einzelne Version des `Action`-Attributs.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-314">To resolve this controversy, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports a single version of the `Action` attribute.</span></span>  
  
 <span data-ttu-id="cd0bd-315">B3521: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet das Attribut `wsaw10:Action` auf `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`-Elementen gemäß der Definition in WS-ADDR10-WSDL, um den `Action`-URI unabhängig von der WS-Adressierungsversion, die vom Endpunkt verwendet wird, für die entsprechenden Nachrichten zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-315">B3521: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses the `wsaw10:Action` attribute on `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements as defined in WS-ADDR10-WSDL to determine the `Action` URI for the corresponding messages irrespective of the WS-Addressing version used by the endpoint.</span></span>  
  
#### <a name="use-endpoint-reference-inside-wsdl-port"></a><span data-ttu-id="cd0bd-316">Verwenden des Endpunktverweises im WSDL-Anschluss</span><span class="sxs-lookup"><span data-stu-id="cd0bd-316">Use Endpoint Reference Inside WSDL Port</span></span>  
 <span data-ttu-id="cd0bd-317">Abschnitt 4.1 von WS-ADDR10-WSDL erweitert das `wsdl:port`-Element durch das untergeordnete `<wsa10:EndpointReference…/>`-Element, um den Endpunkt in WS-Adressierungsbegriffen zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-317">WS-ADDR10-WSDL section 4.1 extends the `wsdl:port` element to include the `<wsa10:EndpointReference…/>` child element to describe the endpoint in WS-Addressing terms.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-318"> erweitert dieses Hilfsprogramm in der WS-Adressierung 2004/08, wodurch ermöglicht wird, dass `<wsa:EndpointReference…/>` als untergeordnetes Element von `wsdl:port` angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-318"> expands this utility on WS-Addressing 2004/08, allowing `<wsa:EndpointReference…/>` to appear as a child element of `wsdl:port`.</span></span>  
  
-   <span data-ttu-id="cd0bd-319">R3531: Wenn einem Endpunkt eine Richtlinienalternative mit einer `<wsaw10:UsingAddressing/>`-Richtlinienassertion angehängt ist, kann das entsprechende`wsdl:port`-Element ein untergeordnetes Element`<wsa10:EndpointReference …/>` enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-319">R3531: If an endpoint has an attached policy alternative with a `<wsaw10:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa10:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="cd0bd-320">R3532: Wenn ein `wsdl:port` enthält ein untergeordnetes Element `<wsa10:EndpointReference …/>`, die `wsa10:EndpointReference/wsa10:Address` untergeordnete Elementwert entsprechen muss von der `@address` Attribut des nebengeordneten Elements `wsdl:port` / `wsdl:location` Element.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-320">R3532: If a `wsdl:port` contains a child element `<wsa10:EndpointReference …/>`, the `wsa10:EndpointReference/wsa10:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
-   <span data-ttu-id="cd0bd-321">R3533: Wenn einem Endpunkt eine Richtlinienalternative mit einer `<wsap:UsingAddressing/>`-Richtlinienassertion angehängt ist, kann das entsprechende`wsdl:port`-Element ein untergeordnetes Element`<wsa:EndpointReference …/>` enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-321">R3533: If an endpoint has an attached policy alternative with `<wsap:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="cd0bd-322">R3534: Wenn ein `wsdl:port` enthält ein untergeordnetes Element `<wsa:EndpointReference …/>`, die `wsa:EndpointReference/wsa:Address` untergeordnete Elementwert entsprechen muss von der `@address` Attribut des nebengeordneten Elements `wsdl:port` / `wsdl:location` Element.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-322">R3534: If a `wsdl:port` contains a child element `<wsa:EndpointReference …/>`, the `wsa:EndpointReference/wsa:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="cd0bd-323">Gestaltung mit WS-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cd0bd-323">Composition with WS-Security</span></span>  
 <span data-ttu-id="cd0bd-324">Gemäß den Sicherheitsüberlegungsabschnitten in WS-ADDR und WS-ADDR10 wird empfohlen, dass alle adressierenden Header zusammen mit dem Nachrichtentext signiert werden, um sie zusammenzubinden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-324">According to security consideration sections in WS-ADDR and WS-ADDR10, all addressing message headers are recommended to be signed together with the message body to bind them together.</span></span>  
  
 <span data-ttu-id="cd0bd-325">Wenn WS-Sicherheit für den Nachrichtenintegritätsschutz verwendet wird, müssen die WS-Adressierungs-Nachrichtenheader genauso wie die Header, die aus Referenzparametern oder -eigenschaften (oder beidem) entstanden sind, zusammen mit dem Text der Nachricht signiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-325">When WS-Security is used for message integrity protection, WS-Addressing message headers as well as headers resulted from reference parameters or properties (or both) must be signed together with the body of the message.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="cd0bd-326">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd0bd-326">Examples</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="cd0bd-327">Unidirektionale Nachricht</span><span class="sxs-lookup"><span data-stu-id="cd0bd-327">One-Way Message</span></span>  
 <span data-ttu-id="cd0bd-328">In diesem Szenario sendet der Absender eine unidirektionale Nachricht zum Empfänger.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-328">In this scenario, the sender sends a one-way message to the receiver.</span></span> <span data-ttu-id="cd0bd-329">SOAP 1.2, HTTP 1.1 und W3C WS-Adressierung 1.0 werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-329">SOAP 1.2, HTTP 1.1, and W3C WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="cd0bd-330">Die Anforderungsnachrichtenstruktur: Zu den Nachrichtenheadern gehören die Elemente `wsa10:To` und `wsa10:Action`.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-330">The Request Message Structure: The message headers include `wsa10:To` and `wsa10:Action` elements.</span></span> <span data-ttu-id="cd0bd-331">Der Nachrichtentext schließt ein bestimmtes `<app:Ping>`-Element vom Anwendungsnamespace ein.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-331">The message body includes a specific `<app:Ping>` element from the application namespace.</span></span>  
  
 <span data-ttu-id="cd0bd-332">HTTP-Header: Das Ziel in POST entspricht den URI in die `wsa10:To` Element.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-332">HTTP Headers: The destination in POST matches the URI in the `wsa10:To` element.</span></span>  
  
 <span data-ttu-id="cd0bd-333">Der Content-Type-Header entspricht dem Wert `application/soap+xml`, wie von SOAP 1.2 vorausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-333">The Content-Type header has the value of `application/soap+xml` as required by SOAP 1.2.</span></span> <span data-ttu-id="cd0bd-334">Die Parameter `charset` und `action` sind eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-334">Parameters `charset` and `action` are included.</span></span> <span data-ttu-id="cd0bd-335">Der Parameter `action` des Content-Type-Headers entspricht dem Wert des `wsa10:Action`-Nachrichtenheaders.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-335">The `action` parameter of the Content-Type header matches the value of the `wsa10:Action` message header.</span></span>  
  
```  
POST http://fabrikam123.com/Service HTTP/1.1  
Content-Type: application/soap+xml; charset=utf-8;    
              action="http://fabrikam123.com/Service/OneWay"  
Host: 131.107.72.15  
Content-Length: 1501  
Expect: 100-continue  
Proxy-Connection: Keep-Alive  
<s12:Envelope>  
  <s12:Header>  
    <wsa10:To s12:mustUnderstand="1">  
        http://fabrikam123.com/Service  
    </wsa10:To>  
    <wsa10:Action s12:mustUnderstand="1">  
        http://fabrikam123.com/Service/OneWay   
    </wsa10:Action>  
  </s12:Header>  
  <s12:Body>  
    <Ping xmlns="http://fabrikam123.com/Service/">  
      <Text>Hello World</Text>  
    </Ping>  
  </s12:Body>  
</s12:Envelope>  
```  
  
 <span data-ttu-id="cd0bd-336">Der Empfänger antwortet mit einer leeren HTTP-Antwort und dem Status 202.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-336">The receiver responds with an empty HTTP response and status 202.</span></span> <span data-ttu-id="cd0bd-337">Ein Beispiel für die HTTP-Antwort:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-337">An example of the HTTP response:</span></span>  
  
```  
HTTP/1.1 202 Accepted  
Date: Fri, 15 Jul 2005 08:56:07 GMT  
Server: Microsoft-IIS/6.0  
MicrosoftOfficeWebServer: 5.0_Pub  
X-Powered-By: ASP.NET  
X-AspNet-Version: 2.0.50215  
Cache-Control: private  
Content-Length: 0  
```  
  
## <a name="soap-message-transmission-optimization-mechanism"></a><span data-ttu-id="cd0bd-338">SOAP-Nachrichten-Übertragungsoptimierungsmechanismus</span><span class="sxs-lookup"><span data-stu-id="cd0bd-338">SOAP Message Transmission Optimization Mechanism</span></span>  
 <span data-ttu-id="cd0bd-339">In diesem Abschnitt werden die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Implementierungsdetails für das HTTP-SOAP MTOM beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-339">This section describes the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementation details for the HTTP SOAP MTOM.</span></span> <span data-ttu-id="cd0bd-340">Die MTOM-Technologie ist ein SOAP-Nachrichtencodierungsmechanismus der gleichen Klasse wie traditionelle Text-/XML-Codierung oder [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Binärcodierung.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-340">MTOM technology is SOAP message encoding mechanism of the same class as traditional text/XML encoding or [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Binary encoding.</span></span> <span data-ttu-id="cd0bd-341">Zu MTOM gehören folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-341">MTOM includes the following:</span></span>  
  
-   <span data-ttu-id="cd0bd-342">Ein XML-Codierungs- und Verpackungsmechanismus, der von [XOP] beschrieben wird, und XML-Informationselemente, die base64-codierte Binärdaten enthalten, die in einzelne Binärteile optimiert wurden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-342">An XML encoding and packaging mechanism described by [XOP] that optimizes XML information items containing base64-encoded binary data into separate binary parts.</span></span>  
  
-   <span data-ttu-id="cd0bd-343">Eine MIME-Kapselung des XOP-Pakets, das das XML-Infoset und jeden Binärteil des XOP-Pakets in einen einzelnen MIME-Teil serialisiert.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-343">A MIME encapsulation of the XOP package that serializes the XML Infoset and each binary part of the XOP package into a separate MIME part.</span></span>  
  
-   <span data-ttu-id="cd0bd-344">Eine MIME-XOP-Codierung, die auf SOAP 1.x Envelope angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-344">A MIME XOP encoding applied to SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="cd0bd-345">Eine HTTP-Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-345">An HTTP transport binding.</span></span>  
  
 <span data-ttu-id="cd0bd-346">Es ist möglich, MTOM bei Nicht-HTTP-Transportmethoden mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-346">It is possible to use MTOM with non-HTTP transports with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="cd0bd-347">In diesem Thema konzentrieren wir uns jedoch auf HTTP.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-347">However, in this topic we will focus on HTTP.</span></span>  
  
 <span data-ttu-id="cd0bd-348">Das MTOM-Format setzt einen großen Satz von Spezifikationen ein, der MTOM selbst, XOP und MIME abdeckt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-348">The MTOM format leverages a large set of specifications covering MTOM itself, XOP, and MIME.</span></span> <span data-ttu-id="cd0bd-349">Die Modularität dieses Spezifikationssatzes macht es schwierig, die genauen Anforderungen an die Format- und Verarbeitungssemantik zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-349">Modularity of this specification set makes it somewhat difficult to reconstruct exact requirements on the format and processing semantics.</span></span> <span data-ttu-id="cd0bd-350">In diesem Abschnitt werden die Format- und Verarbeitungsanforderungen an MTOM-HTTP-Bindungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-350">This section describes the format and processing requirements for MTOM HTTP binding.</span></span>  
  
### <a name="mtom-message-encoding"></a><span data-ttu-id="cd0bd-351">MTOM-Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="cd0bd-351">MTOM Message Encoding</span></span>  
  
#### <a name="generating-mtom-messages"></a><span data-ttu-id="cd0bd-352">Generieren von MTOM-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="cd0bd-352">Generating MTOM messages</span></span>  
 <span data-ttu-id="cd0bd-353">[XOP] Abschnitt 3.1 beschreibt den Vorgang der Codierung von XML mit Elementinformationselementen, die base24-Werte enthalten, in ein abstrakt definiertes XOP-Paket.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-353">The [XOP] section 3.1 describes the process of encoding XML with element information items that contain base64 values into an abstractly defined XOP package.</span></span>  
  
 <span data-ttu-id="cd0bd-354">Die folgende Sequenz von Schritten beschreibt den MTOM-spezifischen Codierungsprozess:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-354">The following sequence of steps describes the MTOM-specific encoding process:</span></span>  
  
1.  <span data-ttu-id="cd0bd-355">Sorgen Sie dafür, dass der zu codierende SOAP-Umschlag kein Elementinformationselement mit einem `[namespace name]` von "http://www.w3.org/2004/08/xop/include" und einem `[local name]` von `Include` enthält.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-355">Ensure that the SOAP Envelope to be encoded contains no element information item with a `[namespace name]` of "http://www.w3.org/2004/08/xop/include" and a `[local name]` of `Include`.</span></span>  
  
2.  <span data-ttu-id="cd0bd-356">Erstellen Sie ein leeres MIME-Paket.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-356">Create an empty MIME package.</span></span>  
  
3.  <span data-ttu-id="cd0bd-357">Identifizieren Sie die Elementinformationselemente, die optimiert werden sollten, innerhalb des Original XML Infoset.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-357">Identify within the Original XML Infoset the element information items to be optimized.</span></span> <span data-ttu-id="cd0bd-358">Für die zu optimierenden Elemente müssen die Zeichen, aus denen das `[children]` des Elementinformationselements besteht, die vorschriftsmäßige Form von `xs:base64Binary` besitzen (siehe XSD-2, 3.2.16 base64Binary) und dürfen keine Leerzeichen enthalten, die vor dem Nicht-Leerzeichen-Inhalt, in der gleichen Zeile oder dahinter stehen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-358">For the items to be optimized, the characters that make up the `[children]` of the element information item must be in the canonical form of `xs:base64Binary` (see XSD-2, 3.2.16 base64Binary) and must not contain any whitespace characters preceding, inline with, or following the non-whitespace content.</span></span>  
  
4.  <span data-ttu-id="cd0bd-359">Erstellen Sie einen XOP SOAP-Umschlag, der eine Kopie des Original-SOAP-Umschlags ist, aber bei dem das untergeordnete Element jedes Elementinformationselements, das im vorherigen Schritt identifiziert wurde, durch ein `xop:Include`-Elementinformationselement ersetzt wurde, das wie folgt erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-359">Create an XOP SOAP Envelope that is a copy of the Original SOAP Envelope, but with the children of each element information item identified in the previous step replaced by an `xop:Include` element information item constructed as follows:</span></span>  
  
    1.  <span data-ttu-id="cd0bd-360">Wandeln Sie die ersetzten Zeichen in Binärdaten um, indem Sie sie als base64-codierte Daten verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-360">Transform the replaced characters into binary data by processing them as base64-encoded data.</span></span>  
  
    2.  <span data-ttu-id="cd0bd-361">Generieren Sie einen eindeutigen Content-ID-Headerwert, der die Anforderungen R3133 und R3134 zufriedenstellt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-361">Generate a unique Content-ID header value that satisfies requirements R3133 and R3134.</span></span>  
  
    3.  <span data-ttu-id="cd0bd-362">Generieren Sie einen Content-Transfer-Encoding-MIME-Header mit dem Wert "binär".</span><span class="sxs-lookup"><span data-stu-id="cd0bd-362">Generate a Content-Transfer-Encoding MIME header with the value binary.</span></span>  
  
    4.  <span data-ttu-id="cd0bd-363">Wenn das optimierte Elementinformationselement (das [übergeordnete Element] des neu eingefügten `xop:Include`-Elementinformationselements) ein `xmime:contentType`-Attributelement besitzt, generieren Sie einen Content-Type-MIME-Header mit dem Wert des `xmime:contentType`-Attributs.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-363">If the element information item being optimized (the [parent] of the newly inserted `xop:Include` element information item) has an `xmime:contentType` attribute information item, generate a Content-Type MIME header with the value of the `xmime:contentType` attribute.</span></span>  
  
    5.  <span data-ttu-id="cd0bd-364">Generieren Sie ein neues MIME-Teil mit einem Inhalt aus Binärdaten, die aus den ersetzten Zeichen entschlüsselt wurden, die als base64, Content-ID-Header aus 4b, Content-Transfer-Encoding-Header und Content-Type-Header bei Generierung in Schritt 4d aus 4c verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-364">Generate a new binary MIME part with content formed by binary data decoded from the replaced characters processed as base64, Content-ID header from 4b, Content- Transfer-Encoding header from 4c, Content-Type header if generated in step 4d.</span></span>  
  
    6.  <span data-ttu-id="cd0bd-365">Fügen Sie ein `href`-Attribut zum `xop:Include`-Element mit dem Wert "cid: uri" hinzu, der in Schritt 4b aus dem Content-ID-Headerwert erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-365">Add an `href` attribute to the `xop:Include` element with the value cid: uri derived from Content-ID header value generated in step 4b.</span></span> <span data-ttu-id="cd0bd-366">Entfernen Sie die umschließenden "\<" und ">" Zeichen "," URL-Escape-Zeichenfolge, die verbleibenden, und fügen das Präfix `cid:`.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-366">Remove the enclosing "\<" and ">" characters, URL-escape the remaining string, and add the prefix `cid:`.</span></span> <span data-ttu-id="cd0bd-367">Der folgende minimale Zeichensatz ist erforderlich, um RFC1738 und RFC2396 mit einem Escapezeichen zu versehen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-367">The following minimum character set is required to be escaped by RFC1738 and RFC2396.</span></span> <span data-ttu-id="cd0bd-368">Andere Zeichen können mit Escapezeichen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-368">Other characters can be escaped.</span></span>  
  
        ```  
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">  
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"  
        ```  
  
5.  <span data-ttu-id="cd0bd-369">Erstellen Sie ein Stamm-MIME-Teil mit dem XOP SOAP-Umschlag aus Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-369">Create a root MIME part with the XOP SOAP Envelope from step 4.</span></span>  
  
6.  <span data-ttu-id="cd0bd-370">Schreiben Sie die HTTP-Header, einschließlich des HTTP Content-Type-Headers.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-370">Write the HTTP headers, including the HTTP Content-Type header.</span></span>  
  
7.  <span data-ttu-id="cd0bd-371">Schreiben Sie das MIME-Paket.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-371">Write the MIME package.</span></span>  
  
#### <a name="processing-mtom-messages"></a><span data-ttu-id="cd0bd-372">Verarbeiten von MTOM-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="cd0bd-372">Processing MTOM messages</span></span>  
 <span data-ttu-id="cd0bd-373">Die Verarbeitung einer MTOM-Nachricht ist das genaue Gegenteil des Vorgangs, der im vorangehenden Abschnitt "Generieren von MTOM-Nachrichten" beschrieben wurde:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-373">Processing of an MTOM message is the exact reverse of the process described in the preceding "Generating MTOM messages" section:</span></span>  
  
1.  <span data-ttu-id="cd0bd-374">Stellen Sie sicher, dass der Stamm-MIME-Teil den Content-Type `application/xop+xml` hat.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-374">Ensure the root MIME part has the Content-Type `application/xop+xml`.</span></span>  
  
2.  <span data-ttu-id="cd0bd-375">Erstellen Sie einen SOAP-Umschlag, indem Sie den Stamm-MIME-Teil des Pakets als XML-Dokument analysieren.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-375">Construct a SOAP Envelope by parsing the root MIME part of the package as an XML document.</span></span> <span data-ttu-id="cd0bd-376">Die Zeichencodierung wird vom Parameter `charset` des Content-Type des Stamm-MIME-Teils bestimmt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-376">Character encoding is determined by the `charset` parameter of the Content-Type of the root MIME part.</span></span>  
  
3.  <span data-ttu-id="cd0bd-377">Für jedes Elementinformationselement im erstellten SOAP-Umschlag, der, als einziges Mitglied seiner [untergeordneten] Eigenschaft, ein `xop:Include`-Elementinformationselement enthält:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-377">For each element information item in the constructed SOAP Envelope, which has, as the sole member of its [children] property, an `xop:Include` element information item:</span></span>  
  
    1.  <span data-ttu-id="cd0bd-378">Löschen Sie das Präfix `cid:`, und entfernen Sie alle URI-Escape-Zeichensequenzen (RFC 2396) im Wert des `@href`-Attributs des Elements `xop:Include`.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-378">Remove the `cid:` prefix and unescape all URI-escape sequences (RFC 2396) in the value of the `@href` attribute of the `xop:Include` element.</span></span> <span data-ttu-id="cd0bd-379">Schließen Sie die Ergebniszeichenfolge in "\<", ">".</span><span class="sxs-lookup"><span data-stu-id="cd0bd-379">Enclose the result string in "\<", ">".</span></span>  
  
    2.  <span data-ttu-id="cd0bd-380">Suchen Sie den MIME-Teil mit dem Content-ID-Headerwert, der mit der in Schritt 3a abgeleiteten Zeichenfolge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-380">Locate the MIME part with the Content-ID header value that matches the string derived in step 3a.</span></span>  
  
    3.  <span data-ttu-id="cd0bd-381">Ersetzen Sie das Elementinformationselement `xop:Include`, das in der Eigenschaft `children` jedes Elements vorkommt, durch Zeicheninformationselemente, die die vorschriftsmäßige base64-Codierung (siehe XSD-2, 3.2.16 base64Binary) des Entitätstexts des in Schritt 3b identifizierten MIME-Teils repräsentieren (ersetzen Sie wirksam das Elementinformationselement `xop:Include` durch die Daten, die im Paketteil rekonstruiert wurden).</span><span class="sxs-lookup"><span data-stu-id="cd0bd-381">Replace the `xop:Include` element information item that appears in the `children` property of each item with the character information items that represent the canonical base64 encoding (see XSD-2, 3.2.16 base64Binary) of the entity body of the MIME part identified in step 3b (effectively replace the `xop:Include` element information item with the data reconstructed from the package part).</span></span>  
  
#### <a name="http-content-type-header"></a><span data-ttu-id="cd0bd-382">HTTP Content-Type Header</span><span class="sxs-lookup"><span data-stu-id="cd0bd-382">HTTP Content-Type Header</span></span>  
 <span data-ttu-id="cd0bd-383">Im Folgenden finden Sie eine Liste der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Klärungen des Formats des HTTP Content-Type-Headers einer SOAP 1.x MTOM-verschlüsselten Nachricht, die aus den Anforderungen, die in der MTOM-Spezifikation selbst genannt werden, abgeleitet sind und von MTOM und RFC 2387 abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-383">The following is a list of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clarifications for the format of the HTTP Content-Type header of a SOAP 1.x MTOM-encoded message derived from requirements stated in the MTOM specification itself and are derived from MTOM and RFC 2387.</span></span>  
  
-   <span data-ttu-id="cd0bd-384">R4131: Ein HTTP-Content-Type-Header muss den Wert mehrteilig/verwandt (Groß- und Kleinschreibung nicht beachtend) und seine Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-384">R4131: An HTTP Content-Type header must have the value of multipart/related (case-insensitive) and its parameters.</span></span> <span data-ttu-id="cd0bd-385">Bei den Parameternamen braucht die Groß- und Kleinschreibung nicht berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-385">Parameter names are case-insensitive.</span></span> <span data-ttu-id="cd0bd-386">Die Parameterreihenfolge ist nicht wichtig.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-386">Parameter order is not significant.</span></span>  
  
-   <span data-ttu-id="cd0bd-387">Das komplette Backus-Naur Form (BNF) des Content-Type-Headers für MIME-Nachrichten wird in RFC 2045, Abschnitt 5.1 aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-387">The full Backus-Naur Form (BNF) of the Content-Type header for MIME messages is listed in RFC 2045, section 5.1.</span></span>  
  
-   <span data-ttu-id="cd0bd-388">R4132: Ein HTTP Content-Type-Header muss über einen Typparameter mit dem Wert `application/xop+xml` verfügen, der von doppelten Anführungszeichen umschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-388">R4132: An HTTP Content-Type header must have a type parameter with the value `application/xop+xml` enclosed in double quotation marks.</span></span>  
  
 <span data-ttu-id="cd0bd-389">Während die Anforderung, Anführungszeichen zu verwenden, nicht explizit in RFC 2387 ist, der Text berücksichtigt, dass alle der mehrteiligen/verwandten Medientyp Parameter, die am wahrscheinlichsten enthalten Zeichen wie reserviert "@" or "/" und daher doppelte Anführungszeichen benötigen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-389">While the requirement to use double quotation marks is not explicit in RFC 2387, the text observes that all of the multipart/related media type parameters most likely contain reserved characters like "@" or "/" and therefore need double quotation marks.</span></span>  
  
-   <span data-ttu-id="cd0bd-390">R4133: Ein HTTP Content-Type-Header sollte einen Startparameter mit dem Wert des Content-ID-Headers des MIME-Teils, der den SOAP 1.x Envelope enthält, in doppelten Anführungszeichen besitzen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-390">R4133: An HTTP Content-Type header should have a start parameter with the value of the Content-ID header of the MIME part that contains the SOAP 1.x Envelope, enclosed in double quotation marks.</span></span> <span data-ttu-id="cd0bd-391">Wenn der Startparameter weggelassen wird, muss der erste MIME-Teil den SOAP 1.x Envelope enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-391">If the start parameter is omitted, the first MIME part must contain the SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="cd0bd-392">R4134: Zum HTTP Content-Type-Header für eine SOAP 1.1 MTOM-codierte Nachricht muss der Startinfo-Parameter, umgeben von doppelten Anführungszeichen, mit dem Wert von text/xml gehören.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-392">R4134: An HTTP Content-Type header for a SOAP 1.1 MTOM encoded message must include the start-info parameter with the value of text/xml, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="cd0bd-393">R4135: Zum HTTP Content-Type-Header für eine SOAP 1.2 MTOM-codierte Nachricht muss der Startinfo-Parameter mit dem Wert von `application/soap+xml`, umgeben von doppelten Anführungszeichen, gehören.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-393">R4135: An HTTP Content-Type header for a SOAP 1.2 MTOM-encoded message must include the start-info parameter with the value of `application/soap+xml`, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="cd0bd-394">R4136: Der HTTP Content-Type-Header für eine SOAP 1.x MTOM-codierte Nachricht muss den Grenzparameter mit dem Wert (umgeben von doppelten Anführungszeichen), der der MIME-Grenz-BNF entspricht, die in RFC 2046, Abschnitt 5.1.1 definiert wird, enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-394">R4136: HTTP Content-Type header for a SOAP 1.x MTOM-encoded message must have the boundary parameter with the value (enclosed in double quotation marks) that matches the MIME boundary BNF defined in RFC 2046, section 5.1.1</span></span>  
  
    ```  
    boundary := 0*69<bchars> bcharsnospace   
    bchars := bcharsnospace / " "   
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+"   
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"  
    ```  
  
     <span data-ttu-id="cd0bd-395">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-395">Examples:</span></span>  
  
     <span data-ttu-id="cd0bd-396">RICHTIG</span><span class="sxs-lookup"><span data-stu-id="cd0bd-396">CORRECT</span></span>  
  
    ```  
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"  
    ```  
  
     <span data-ttu-id="cd0bd-397">RICHTIG</span><span class="sxs-lookup"><span data-stu-id="cd0bd-397">CORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
    ```  
  
     <span data-ttu-id="cd0bd-398">FALSCH</span><span class="sxs-lookup"><span data-stu-id="cd0bd-398">INCORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"   
    ```  
  
#### <a name="infoset-mime-part"></a><span data-ttu-id="cd0bd-399">Infoset-MIME-Teil</span><span class="sxs-lookup"><span data-stu-id="cd0bd-399">Infoset MIME Part</span></span>  
 <span data-ttu-id="cd0bd-400">SOAP 1.x Envelope ist als Stammteil des XOP MIME-Paket gekapselt und wird häufig der `infoset`-Teil genannt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-400">The SOAP 1.x Envelope is encapsulated as a root part of the XOP MIME package and is often called the `infoset` part.</span></span>  
  
-   <span data-ttu-id="cd0bd-401">R4141: SOAP 1.x Envelope muss als Stammteil des XOP MIME-Pakets, das als `infoset`-Teil bezeichnet wird und auf das vom HTTP Content-Type verwiesen wird, gekapselt werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-401">R4141: The SOAP 1.x Envelope must be encapsulated as a root part of the XOP MIME package, called the `infoset` part and referenced from the HTTP Content-Type.</span></span>  
  
-   <span data-ttu-id="cd0bd-402">R4142: Der SOAP-`Infoset`-Teil muss die folgenden MIME-Köpfe einschließen: `Content-ID`, `Content-Transfer-Encoding` und `Content-Type`.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-402">R4142: The SOAP `Infoset` part must include the following MIME headers: `Content-ID`, `Content-Transfer-Encoding`, and `Content-Type`.</span></span>  
  
 <span data-ttu-id="cd0bd-403">Das Format des Content-ID-Headers wird von RFC 2045 als</span><span class="sxs-lookup"><span data-stu-id="cd0bd-403">The format of the Content-ID header is defined by RFC 2045 as</span></span>  
  
```  
"Content-ID" ":" msg-id  
```  
  
 <span data-ttu-id="cd0bd-404">definiert, wobei `msg-id` in RFC 2822 (das RFC 822, auf das in RFC 2045 verwiesen wird, ablöst) als:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-404">where `msg-id` is defined in RFC 2822 (that supersedes RFC 822, referenced in RFC 2045) as:</span></span>  
  
```  
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]  
```  
  
 <span data-ttu-id="cd0bd-405">eingeschlossen ist, wird effektiv eine e-Mail-Adresse in "\<" und ">".</span><span class="sxs-lookup"><span data-stu-id="cd0bd-405">and is effectively an e-mail address enclosed within "\<" and  ">".</span></span> <span data-ttu-id="cd0bd-406">Das `[CFWS]`-Präfix und -Suffix wurden in RFC 2822 hinzugefügt, um Kommentare auszuführen, und sollten nicht verwendet werden, um die Kompatibilität aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-406">The `[CFWS]` prefix and suffix were added in RFC 2822 to carry comments and should not be used to preserve interoperability.</span></span>  
  
 <span data-ttu-id="cd0bd-407">R4143: Der Wert des Content-ID-Headers des Infoset MIME-Teils muss der Produktion `msg-id` von RFC 2822 folgen, wobei die Präfix- und Suffixteile des `[CFWS]` entfallen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-407">R4143: The value of the Content-ID header for the Infoset MIME part must follow `msg-id` production from RFC 2822 with the `[CFWS]` prefix and suffix parts omitted.</span></span>  
  
 <span data-ttu-id="cd0bd-408">Eine Reihe von MIME-Implementierungen gelockert Anforderungen für den Wert "\<" und ">" ist eine e-Mail-Adresse und verwendet `absoluteURI` eingeschlossen "\<", ">" zusätzlich zur e-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-408">A number of MIME implementations relaxed requirements for the value enclosed within "\<" and ">" to be an e-mail address and used `absoluteURI` enclosed in "\<" , ">" in addition to the e-mail address.</span></span> <span data-ttu-id="cd0bd-409">Diese Version von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet Werte des Content-ID MIME Headers in der Form:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-409">This version of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses values of the Content-ID MIME header of the form:</span></span>  
  
```  
Content-ID: <http://tempuri.org/0>   
```  
  
 <span data-ttu-id="cd0bd-410">R4144: MTOM-Prozessoren sollten Content-ID-Headerwerte akzeptieren, die der folgenden entspannten `msg-id` entsprechen.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-410">R4144: MTOM processors should accept Content-ID header values that match the following relaxed `msg-id`.</span></span>  
  
```  
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]  
mail-address   =     id-left "@" id-right  
```  
  
 <span data-ttu-id="cd0bd-411">MIME (RFC 2045) stellt den Content-Transfer-Encoding-Header bereit, um die Codierung des Inhalts des MIME-Teils zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-411">MIME (RFC 2045) provides the Content-Transfer-Encoding header to communicate encoding of the content of the MIME part.</span></span> <span data-ttu-id="cd0bd-412">Der für das Content-Transfer-Encoding definierte Standard ist 7-Bit; da dies für die meisten SOAP-Nachrichten nicht geeignet ist, wird der Content-Transfer-Encoding-Header für eine bessere Interoperabilität benötigt:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-412">The default defined for Content-Transfer-Encoding is 7-bit, which is not suitable for most SOAP messages, so the Content-Transfer-Encoding header is needed for greater interoperability:</span></span>  
  
-   <span data-ttu-id="cd0bd-413">R4145: Der SOAP-Infosetteil muss den Content-Transfer-Encoding-Header enthalten.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-413">R4145: The SOAP Infoset part must contain the Content-Transfer-Encoding header.</span></span>  
  
-   <span data-ttu-id="cd0bd-414">R4146: Wenn die SOAP-Umschlag-Zeichencodierung UTF-8 ist, muss der Wert des Content-Transfer-Encoding-Headers 8-Bit sein.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-414">R4146: If the SOAP Envelope character encoding is UTF-8, the value of the Content-Transfer-Encoding header must be 8-bit.</span></span>  
  
-   <span data-ttu-id="cd0bd-415">R4147: Wenn die SOAP-Umschlag-Zeichencodierung UTF-16 ist, muss der Wert des Content-Transfer-Encoding-Headers binär sein.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-415">R4147: If the SOAP Envelope character encoding is UTF-16, the value of the Content-Transfer-Encoding header must be binary.</span></span>  
  
-   <span data-ttu-id="cd0bd-416">Gemäß [XOP] Abschnitt 5,</span><span class="sxs-lookup"><span data-stu-id="cd0bd-416">According to [XOP] section 5,</span></span>  
  
-   <span data-ttu-id="cd0bd-417">R4148: SOAP1. 1 infosetteil muss enthalten Content-Type-Header mit Medien Typ Application/Xop + Xml und Parametertyp = "Text/Xml" und Charset</span><span class="sxs-lookup"><span data-stu-id="cd0bd-417">R4148: SOAP1.1 Infoset part must contain Content-Type header with media type application/xop+xml and parameters type="text/xml" and charset</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="text/xml"  
    ```  
  
-   <span data-ttu-id="cd0bd-418">R4149: Der SOAP 1.2-infosetteil muss den Content-Type-Header mit Medientyp enthalten `application/xop+xml` und Parametertyp = "`application/soap+xml`" und `charset`.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-418">R4149: The SOAP 1.2 Infoset part must contain the Content-Type header with media type `application/xop+xml` and parameters type="`application/soap+xml`" and `charset`.</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="application/soap+xml"  
    ```  
  
     <span data-ttu-id="cd0bd-419">Obwohl XOP den Parameter `charset` für `application/xop+xml` als optional definiert, wird er ähnlich der BP 1.1-Anforderung an den Parameter `charset` des Medientyps `text/xml` für die Interoperabilität benötigt.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-419">While XOP defines the `charset` parameter for `application/xop+xml` to be optional, it is needed for interoperability similar to the BP 1.1 requirement on the `charset` parameter for the `text/xml` media type.</span></span>  
  
-   <span data-ttu-id="cd0bd-420">R4140: Die Parameter `type` und `charset` müssen im Content-Type-Header des SOAP 1.x-Infosetteils enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-420">R41410: The `type` and `charset` parameters must be present on the Content-Type header of the SOAP 1.x Infoset part.</span></span>  
  
#### <a name="wcf-endpoint-support-for-mtom"></a><span data-ttu-id="cd0bd-421">WCF-Endpunkt-Unterstützung für MTOM</span><span class="sxs-lookup"><span data-stu-id="cd0bd-421">WCF Endpoint Support for MTOM</span></span>  
 <span data-ttu-id="cd0bd-422">Der Zweck von MTOM ist es, eine SOAP-Nachricht zu codieren, um base64-codierte Daten zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-422">The purpose of MTOM is to encode a SOAP message to optimize base64-encoded data.</span></span> <span data-ttu-id="cd0bd-423">Die folgende Liste führt Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-423">The following is a list of constraints:</span></span>  
  
-   <span data-ttu-id="cd0bd-424">R4151: Jedes Elementinformationselement, das base64-codierte Daten enthält, kann optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-424">R4151: Any element information item that contains base64-encoded data may be optimized.</span></span>  
  
-   <span data-ttu-id="cd0bd-425">B4152: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] optimiert Elementinformationselemente, die base64-codierte Daten enthalten und deren Länge 1024 Bytes überschreitet.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-425">B4152: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] optimizes element information items that contain base64-encoded data and exceed 1024 bytes in length.</span></span>  
  
 <span data-ttu-id="cd0bd-426">Ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkt, der konfiguriert wird, um MTOM zu verwenden, sendet immer MTOM-codierte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-426">A [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint configured to use MTOM will always send MTOM-encoded messages.</span></span> <span data-ttu-id="cd0bd-427">Selbst wenn kein Teil die erforderlichen Kriterien erfüllt, ist die Nachricht noch immer MTOM-codiert (als MIME-Paket mit einem einzelnen MIME-Teil serialisiert, der den SOAP-Umschlag enthält).</span><span class="sxs-lookup"><span data-stu-id="cd0bd-427">Even if no parts meet the required criteria, the message is still MTOM-encoded (serialized as a MIME package with a single MIME part containing the SOAP envelope).</span></span>  
  
### <a name="ws-policy-assertion-for-mtom"></a><span data-ttu-id="cd0bd-428">WS-Policy-Assertion für MTOM</span><span class="sxs-lookup"><span data-stu-id="cd0bd-428">WS-Policy Assertion for MTOM</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="cd0bd-429"> verwendet die folgende Richtlinienassertion, um die MTOM-Verwendung durch den Endpunkt anzugeben:</span><span class="sxs-lookup"><span data-stu-id="cd0bd-429"> uses the following policy assertion to indicate MTOM usage by endpoint:</span></span>  
  
```xml  
<wsoma:OptimizedMimeSerialization ... />  
```  
  
-   <span data-ttu-id="cd0bd-430">R4211: Die vorangehende Richtlinienassertion verfügt über ein Endpoint Policy Subject und gibt an, dass alle Nachrichten, die an den Endpunkt gesendet und von diesem empfangen werden, durch den Einsatz von MTOM optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-430">R4211: The preceding policy assertion has an Endpoint Policy Subject and specifies that all messages sent to and received from the endpoint must be optimized using MTOM.</span></span>  
  
-   <span data-ttu-id="cd0bd-431">B4212: Wenn er für die Verwendung der MTOM-Optimierung konfiguriert ist, fügt der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Endpunkt der Richtlinie, die an die entsprechende `wsdl:binding` angehängt ist, eine MTOM-Richtlinienassertion hinzu.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-431">B4212: When configured to use MTOM optimization, an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint adds an MTOM Policy assertion to the policy attached to the corresponding `wsdl:binding`.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="cd0bd-432">Gestaltung mit WS-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cd0bd-432">Composition with WS-Security</span></span>  
 <span data-ttu-id="cd0bd-433">MTOM ist ein Codierungsmechanismus, der der `text/xml`-und [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Binary XML ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-433">MTOM is an encoding mechanism that is similar to `text/xml` and [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Binary XML.</span></span> <span data-ttu-id="cd0bd-434">MTOM bietet eine natürliche Zusammensetzung aus WS-Sicherheit und anderen WS-*-Protokollen: eine über WS-Sicherheit gesicherte Nachricht kann durch den Einsatz von MTOM optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-434">MTOM offers natural composition with WS-Security and other WS-* protocols: a message secured using WS-Security can be optimized using MTOM.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="cd0bd-435">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cd0bd-435">Examples</span></span>  
  
#### <a name="wcf-soap-11-message-encoded-using-mtom"></a><span data-ttu-id="cd0bd-436">WCF-SOAP 1.1-Nachricht, mit MTOM codiert</span><span class="sxs-lookup"><span data-stu-id="cd0bd-436">WCF SOAP 1.1 Message Encoded Using MTOM</span></span>  
  
```  
POST http://131.107.72.15/Mtom/svc/service.svc/Soap11MtomUTF8 HTTP/1.1  
SOAPAction: "http://xmlsoap.org/echoBinaryAsString"  
Content-Type: multipart/related;type="application/xop+xml";  
              start="<http://tempuri.org/0>";start-info="text/xml";  
       boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
Host: 131.107.72.15  
Content-Length: 1501  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
Content-ID: <http://tempuri.org/0>  
Content-Transfer-Encoding: 8bit  
Content-Type: application/xop+xml;charset=utf-8;type="text/xml"  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
  <s:Body>  
    <EchoBinaryAsString xmlns="http://xmlsoap.org/Ping">  
      <array>  
        <xop:Include   
         href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206521093670"   
         xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
      </array>  
    </EchoBinaryAsString>  
  </s:Body>  
</s:Envelope>  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
Content-ID: <http://tempuri.org/1/632618206521093670>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
…Binary Content..  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1  
```  
  
#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a><span data-ttu-id="cd0bd-437">WCF Secure SOAP 1.2-Nachricht, mit MTOM codiert</span><span class="sxs-lookup"><span data-stu-id="cd0bd-437">WCF Secure SOAP 1.2 Message Encoded Using MTOM</span></span>  
 <span data-ttu-id="cd0bd-438">In diesem Beispiel wird eine Nachricht mit MTOM und SOAP 1.2 codiert, die mit WS-Sicherheit geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-438">In this example, a message is encoded using MTOM and SOAP 1.2 that is protected using WS-Security.</span></span> <span data-ttu-id="cd0bd-439">Die für die Codierung identifizierten Binärteile sind die Inhalte des `BinarySecurityToken`, `CipherValue` der `EncryptedData`, die zu der verschlüsselten Signatur und dem verschlüsselten Text gehören.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-439">The binary parts identified for encoding are the contents of the `BinarySecurityToken`, `CipherValue` of the `EncryptedData` corresponding to the encrypted signature and encrypted body.</span></span> <span data-ttu-id="cd0bd-440">Beachten Sie, dass der `CipherValue` des `EncryptedKey` nicht von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] zur Optimierung identifiziert wurde, da seine Länge geringer als 1024 Bytes ist.</span><span class="sxs-lookup"><span data-stu-id="cd0bd-440">Note that the `CipherValue` of the `EncryptedKey` was not identified for optimization by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because its length is less then 1024 bytes.</span></span>  
  
```  
POST http://131.107.72.15/Mtom/service.svc/Soap12MtomSecureSignEncrypt HTTP/1.1  
Content-Type: multipart/related; type="application/xop+xml";  
              start="<http://tempuri.org/0>";  
            boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3";  
              start-info="application/soap+xml";   
              action="http://xmlsoap.org/echoBinaryAsString"  
Host: 131.107.72.15  
Content-Length: 1941  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/0>  
Content-Transfer-Encoding: 8bit  
Content-Type: application/xop+xml;charset=utf-8;type="application/soap+xml"  
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/" xmlns:u="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
  <s:Header>  
    <o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-5">  
        <u:Created>2005-09-09T06:57:32.488Z</u:Created>  
        <u:Expires>2005-09-09T07:02:32.488Z</u:Expires>  
      </u:Timestamp>  
      <o:BinarySecurityToken u:Id="uuid-4d4ee765-5717-4d53-9ac9-99bddc07df6c-2" ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509v3" EncodingType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0#Base64Binary">  
        <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F1%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
      </o:BinarySecurityToken>  
      <e:EncryptedKey Id="_1" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#rsa-oaep-mgf1p"/>  
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
          <o:SecurityTokenReference>  
            <o:KeyIdentifier ValueType="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0#X509SubjectKeyIdentifier">Xeg55vRyK3ZhAEhEf+YT0z986L0=</o:KeyIdentifier>  
          </o:SecurityTokenReference>  
        </KeyInfo>  
        <e:CipherData>          <e:CipherValue>oQfpxwT8/SAGyZQzKE2b4yO6dXuQj7pwJ+5CGL3Rf7C06bQ5ttMoQ9GLJcQYkXTzin+WwHEgs5bj5ml9HKTW9QAU5JJ6lksdymmQvWP5ZtGPBVchO4sofEGoCKmBiZL/DYS/cnbzgnc/3a6NYnc10y2fWGaGLiqa00zijAw7o0Y=</e:CipherValue>  
        </e:CipherData>  
      </e:EncryptedKey>  
      <c:DerivedKeyToken u:Id="_2" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc">  
        <o:SecurityTokenReference>  
          <o:Reference URI="#_1"/>  
        </o:SecurityTokenReference>  
        <c:Nonce>OrEPRX7fISIS4sXYWPMv3g==</c:Nonce>  
      </c:DerivedKeyToken>  
      <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:DataReference URI="#_3"/>  
        <e:DataReference URI="#_4"/>  
      </e:ReferenceList>  
      <e:EncryptedData Id="_4" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
        <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>  
        <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
          <o:SecurityTokenReference>  
            <o:Reference URI="#_2"/>  
          </o:SecurityTokenReference>  
        </KeyInfo>  
        <e:CipherData>  
          <e:CipherValue>  
            <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F2%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
          </e:CipherValue>  
        </e:CipherData>  
      </e:EncryptedData>  
    </o:Security>  
  </s:Header>  
  <s:Body u:Id="_0">  
    <e:EncryptedData Id="_3" Type="http://www.w3.org/2001/04/xmlenc#Content" xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
      <e:EncryptionMethod Algorithm="http://www.w3.org/2001/04/xmlenc#aes256-cbc"/>  
      <KeyInfo xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <o:SecurityTokenReference xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
          <o:Reference URI="#_2"/>  
        </o:SecurityTokenReference>  
      </KeyInfo>  
      <e:CipherData>  
        <e:CipherValue>  
          <xop:Include href="cid:http%3A%2F%2Ftempuri.org%2F3%2F632618206525089430" xmlns:xop="http://www.w3.org/2004/08/xop/include"/>  
        </e:CipherValue>  
      </e:CipherData>  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/1/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary content of BinarySecurityToken - X509 Certificate...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/2/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary serialization of the encrypted primary signature...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3  
Content-ID: <http://tempuri.org/3/632618206525089430>  
Content-Transfer-Encoding: binary  
Content-Type: application/octet-stream  
...Binary serialization of the encrypted Body...  
--uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=3--  
```
