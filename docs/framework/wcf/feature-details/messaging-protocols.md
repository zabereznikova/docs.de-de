---
title: Messagingprotokolle
ms.date: 03/30/2017
ms.assetid: 5b20bca7-87b3-4c8f-811b-f215b5987104
ms.openlocfilehash: 3e56636e8364eec333f9585a0f62f6510561d1cc
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43868733"
---
# <a name="messaging-protocols"></a><span data-ttu-id="b8270-102">Messagingprotokolle</span><span class="sxs-lookup"><span data-stu-id="b8270-102">Messaging Protocols</span></span>
<span data-ttu-id="b8270-103">Der Windows Communication Foundation (WCF)-Kanalstapel wendet Codierungs- und Transportkanäle an interne nachrichtendarstellung in ihr kabelformat zu transformieren, und senden es mithilfe eines bestimmten Transports.</span><span class="sxs-lookup"><span data-stu-id="b8270-103">The Windows Communication Foundation (WCF) channel stack employs encoding and transport channels to transform internal message representation into its wire format and send it by using a particular transport.</span></span> <span data-ttu-id="b8270-104">Der am häufigsten verwendete Transport, der für die Interoperabilität bei Webdiensten verwendet wird, ist HTTP, und die am häufigsten von Webdiensten verwendeten Codierungen sind das XML-basierte SOAP 1.1, SOAP 1.2 und der Message Transmission Optimization Mechanism (MTOM).</span><span class="sxs-lookup"><span data-stu-id="b8270-104">The most common transport used for Web services interoperability is HTTP, and the most common encodings used by Web services are XML-based SOAP 1.1, SOAP 1.2, and Message Transmission Optimization Mechanism (MTOM).</span></span>  
  
 <span data-ttu-id="b8270-105">Dieses Thema enthält Details zur WCF-Implementierung für die folgenden Protokolle, die vom Anwender verwendete <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span><span class="sxs-lookup"><span data-stu-id="b8270-105">This topic covers WCF implementation details for the following protocols employed by <xref:System.ServiceModel.Channels.HttpTransportBindingElement>.</span></span>  
  
|<span data-ttu-id="b8270-106">Spezifikation/Dokument</span><span class="sxs-lookup"><span data-stu-id="b8270-106">Specification/document</span></span>|<span data-ttu-id="b8270-107">Link</span><span class="sxs-lookup"><span data-stu-id="b8270-107">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="b8270-108">HTTP 1.1</span><span class="sxs-lookup"><span data-stu-id="b8270-108">HTTP 1.1</span></span>|http://www.ietf.org/rfc/rfc2616.txt|  
|<span data-ttu-id="b8270-109">SOAP 1.1 HTTP-Bindung</span><span class="sxs-lookup"><span data-stu-id="b8270-109">SOAP 1.1 HTTP Binding</span></span>|<span data-ttu-id="b8270-110">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, Abschnitt 7</span><span class="sxs-lookup"><span data-stu-id="b8270-110">http://www.w3.org/TR/2000/NOTE-SOAP-20000508/, Section 7</span></span>|  
|<span data-ttu-id="b8270-111">SOAP 1,2 HTTP-Bindung</span><span class="sxs-lookup"><span data-stu-id="b8270-111">SOAP 1.2 HTTP Binding</span></span>|<span data-ttu-id="b8270-112">http://www.w3.org/TR/soap12-part2/, Abschnitt 7</span><span class="sxs-lookup"><span data-stu-id="b8270-112">http://www.w3.org/TR/soap12-part2/, Section 7</span></span>|  
  
 <span data-ttu-id="b8270-113">Dieses Thema enthält Details zur WCF-Implementierung für die folgenden Protokolle <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> und <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> einsetzen.</span><span class="sxs-lookup"><span data-stu-id="b8270-113">This topic covers WCF implementation details for the following protocols  that <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> and <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employ.</span></span>  
  
|<span data-ttu-id="b8270-114">Spezifikation/Dokument</span><span class="sxs-lookup"><span data-stu-id="b8270-114">Specification/Document</span></span>|<span data-ttu-id="b8270-115">Link</span><span class="sxs-lookup"><span data-stu-id="b8270-115">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="b8270-116">XML</span><span class="sxs-lookup"><span data-stu-id="b8270-116">XML</span></span>|http://www.w3.org/TR/REC-xml|  
|<span data-ttu-id="b8270-117">SOAP 1,1</span><span class="sxs-lookup"><span data-stu-id="b8270-117">SOAP 1.1</span></span>|http://www.w3.org/TR/2000/NOTE-SOAP-20000508/|  
|<span data-ttu-id="b8270-118">SOAP 1.2 Core</span><span class="sxs-lookup"><span data-stu-id="b8270-118">SOAP 1.2 Core</span></span>|http://www.w3.org/TR/soap12-part1/|  
|<span data-ttu-id="b8270-119">WS-Adressierung 2004/08</span><span class="sxs-lookup"><span data-stu-id="b8270-119">WS-Addressing 2004/08</span></span>|http://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/|  
|<span data-ttu-id="b8270-120">W3C Web Services Addressing 1.0 - Core</span><span class="sxs-lookup"><span data-stu-id="b8270-120">W3C Web Services Addressing 1.0 - Core</span></span>|http://www.w3.org/TR/2006/REC-ws-addr-core-20060509|  
|<span data-ttu-id="b8270-121">W3C Web Services Addressing 1.0 - SOAP-Bindung</span><span class="sxs-lookup"><span data-stu-id="b8270-121">W3C Web Services Addressing 1.0 - SOAP Binding</span></span>|http://www.w3.org/TR/2006/REC-ws-addr-soap-20060509|  
|<span data-ttu-id="b8270-122">W3C Web Services Addressing 1.0 - WSDL-Bindung</span><span class="sxs-lookup"><span data-stu-id="b8270-122">W3C Web Services Addressing 1.0 - WSDL Binding</span></span>|http://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/|  
<span data-ttu-id="b8270-123">W3C Web Services Addressing 1.0 - Metadaten</span><span class="sxs-lookup"><span data-stu-id="b8270-123">W3C Web Services Addressing 1.0 - Metadata</span></span>|http://www.w3.org/TR/ws-addr-metadata/|  
|<span data-ttu-id="b8270-124">WSDL SOAP1.1-Bindung</span><span class="sxs-lookup"><span data-stu-id="b8270-124">WSDL SOAP1.1 Binding</span></span>|http://www.w3.org/TR/wsdl/|  
|<span data-ttu-id="b8270-125">WSDL SOAP1.2-Bindung</span><span class="sxs-lookup"><span data-stu-id="b8270-125">WSDL SOAP1.2 Binding</span></span>|http://www.w3.org/Submission/wsdl11soap12/|  
  
 <span data-ttu-id="b8270-126">Dieses Thema enthält Details zur WCF-Implementierung für die folgenden Protokolle <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> verwendet.</span><span class="sxs-lookup"><span data-stu-id="b8270-126">This topic covers WCF implementation details for the following protocols that <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> employs.</span></span>  
  
|<span data-ttu-id="b8270-127">Spezifikation/Dokument</span><span class="sxs-lookup"><span data-stu-id="b8270-127">Specification/document</span></span>|<span data-ttu-id="b8270-128">Link</span><span class="sxs-lookup"><span data-stu-id="b8270-128">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="b8270-129">XOP</span><span class="sxs-lookup"><span data-stu-id="b8270-129">XOP</span></span>|http://www.w3.org/TR/xop10/|  
|<span data-ttu-id="b8270-130">MTOM + SOAP 1.2-Bindung</span><span class="sxs-lookup"><span data-stu-id="b8270-130">MTOM + SOAP 1.2 Binding</span></span>|http://www.w3.org/TR/soap12-mtom/|  
|<span data-ttu-id="b8270-131">MTOM SOAP 1.1-Bindung</span><span class="sxs-lookup"><span data-stu-id="b8270-131">MTOM SOAP 1.1 Binding</span></span>|http://www.w3.org/Submission/soap11mtom10/|  
|<span data-ttu-id="b8270-132">MTOM WS-Richtlinienassertion</span><span class="sxs-lookup"><span data-stu-id="b8270-132">MTOM WS-Policy Assertion</span></span>|<span data-ttu-id="b8270-133">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/</span><span class="sxs-lookup"><span data-stu-id="b8270-133">http://www.w3.org/Submission/2006/SUBM-WS-MTOMPolicy-20061101/.</span></span>|  
  
 <span data-ttu-id="b8270-134">Die folgenden XML-Namespaces und zugeordneten Präfixe werden überall in diesem Thema verwendet.</span><span class="sxs-lookup"><span data-stu-id="b8270-134">The following XML namespaces and associated prefixes are used throughout this topic.</span></span>  
  
|<span data-ttu-id="b8270-135">Präfix</span><span class="sxs-lookup"><span data-stu-id="b8270-135">Prefix</span></span>|<span data-ttu-id="b8270-136">Namespace Uniform Resource Identifier (URI)</span><span class="sxs-lookup"><span data-stu-id="b8270-136">Namespace Uniform Resource Identifier (URI)</span></span>|  
|------------|---------------------------------------------------|  
|<span data-ttu-id="b8270-137">s11</span><span class="sxs-lookup"><span data-stu-id="b8270-137">s11</span></span>|http://schemas.xmlsoap.org/soap/envelope|  
|<span data-ttu-id="b8270-138">s12</span><span class="sxs-lookup"><span data-stu-id="b8270-138">s12</span></span>|http://www.w3.org/2003/05/soap-envelope|  
|<span data-ttu-id="b8270-139">wsa</span><span class="sxs-lookup"><span data-stu-id="b8270-139">wsa</span></span>|http://www.w3.org/2004/08/addressing|  
|<span data-ttu-id="b8270-140">wsam</span><span class="sxs-lookup"><span data-stu-id="b8270-140">wsam</span></span>|http://www.w3.org/2007/05/addressing/metadata|  
|<span data-ttu-id="b8270-141">wsap</span><span class="sxs-lookup"><span data-stu-id="b8270-141">wsap</span></span>|http://schemas.xmlsoap.org/ws/2004/09/policy/addressing|  
|<span data-ttu-id="b8270-142">wsa10</span><span class="sxs-lookup"><span data-stu-id="b8270-142">wsa10</span></span>|http://www.w3.org/2005/08/addressing|  
|<span data-ttu-id="b8270-143">wsaw10</span><span class="sxs-lookup"><span data-stu-id="b8270-143">wsaw10</span></span>|http://www.w3.org/2006/05/addressing/wsdl|  
|<span data-ttu-id="b8270-144">xop</span><span class="sxs-lookup"><span data-stu-id="b8270-144">xop</span></span>|http://www.w3.org/2004/08/xop/include|  
|<span data-ttu-id="b8270-145">xmime</span><span class="sxs-lookup"><span data-stu-id="b8270-145">xmime</span></span>|http://www.w3.org/2004/06/xmlmime<br /><br /> http://www.w3.org/2005/05/xmlmime|  
<span data-ttu-id="b8270-146">dp</span><span class="sxs-lookup"><span data-stu-id="b8270-146">dp</span></span>|http://schemas.microsoft.com/net/2006/06/duplex|  
  
## <a name="soap-11-and-soap-12"></a><span data-ttu-id="b8270-147">SOAP 1.1 und SOAP 1.2</span><span class="sxs-lookup"><span data-stu-id="b8270-147">SOAP 1.1 and SOAP 1.2</span></span>  
  
### <a name="envelope-and-processing-model"></a><span data-ttu-id="b8270-148">Umschlag und Verarbeitungsmodell</span><span class="sxs-lookup"><span data-stu-id="b8270-148">Envelope and Processing Model</span></span>  
 <span data-ttu-id="b8270-149">WCF implementiert SOAP 1.1-umschlagsverarbeitung, die folgenden Basic Profile 1.1 (BP11) und Basic Profile 1.0 (SSBP10).</span><span class="sxs-lookup"><span data-stu-id="b8270-149">WCF implements SOAP 1.1 envelope processing following Basic Profile 1.1 (BP11) and Basic Profile 1.0 (SSBP10).</span></span> <span data-ttu-id="b8270-150">SOAP 1.2-Umschlagsverarbeitung wird unter Befolgung von SOAP12-Part1 implementiert.</span><span class="sxs-lookup"><span data-stu-id="b8270-150">SOAP 1.2 Envelope processing is implemented following SOAP12-Part1.</span></span>  
  
 <span data-ttu-id="b8270-151">Dieser Abschnitt erklärt bestimmte, die von WCF im Hinblick auf BP11 und SOAP12-Part1.</span><span class="sxs-lookup"><span data-stu-id="b8270-151">This section explains certain implementation choices taken by WCF with regard to BP11 and SOAP12-Part1.</span></span>  
  
#### <a name="mandatory-header-processing"></a><span data-ttu-id="b8270-152">Erforderliche Headerverarbeitung</span><span class="sxs-lookup"><span data-stu-id="b8270-152">Mandatory Header Processing</span></span>  
 <span data-ttu-id="b8270-153">WCF folgt den Regeln für die Verarbeitung von Headern markiert `mustUnderstand` in den SOAP 1.1- und SOAP 1.2-Spezifikationen, mit den folgenden Variationen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8270-153">WCF follows rules for processing headers marked `mustUnderstand` described in the SOAP 1.1 and SOAP 1.2 specifications, with the following variations.</span></span>  
  
 <span data-ttu-id="b8270-154">Eine Nachricht, die WCF-Kanalstapel eingibt, wird von einzelnen Kanälen, die durch zugeordnete Bindungselemente konfiguriert sind, z. B. Textnachrichtencodierung, Sicherheit, zuverlässiges Messaging und Transaktionen verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b8270-154">A message that enters the WCF channel stack is processed by individual channels configured by associated binding elements, for example, Text Message Encoding, Security, Reliable Messaging, and Transactions.</span></span> <span data-ttu-id="b8270-155">Jeder Kanal erkennt Header des zugeordneten Namespace, und kennzeichnet sie als verstanden.</span><span class="sxs-lookup"><span data-stu-id="b8270-155">Each channel recognizes headers from the associated namespace and marks them as understood.</span></span> <span data-ttu-id="b8270-156">Sobald eine Nachricht in den Verteiler eingeht, liest der Vorgangsformatierer Header, die vom entsprechenden Nachrichten-/Vorgangsvertrag erwartet werden, und kennzeichnet sie als verstanden.</span><span class="sxs-lookup"><span data-stu-id="b8270-156">Once a message enters the dispatcher, the operation formatter reads headers expected by the corresponding message/operation contract and marks them understood.</span></span> <span data-ttu-id="b8270-157">Der Verteiler überprüft, ob einige der verbleibenden Header nicht verstanden, aber als `mustUnderstand` gekennzeichnet sind, und löst eine Ausnahme aus.</span><span class="sxs-lookup"><span data-stu-id="b8270-157">Then the dispatcher verifies whether any remaining headers are not understood but marked as `mustUnderstand` and throws an exception.</span></span> <span data-ttu-id="b8270-158">Nachrichten, die an den Empfänger gerichtete `mustUnderstand`-Header enthalten, werden nicht vom Empfängeranwendungscode verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="b8270-158">Messages that contain `mustUnderstand` headers that are targeted at the recipient are not processed by recipient application code.</span></span>  
  
 <span data-ttu-id="b8270-159">Eine derartige schichtweise Verarbeitung lässt eine Trennung zwischen den Infrastrukturschichten und Anwendungsschichten auf dem SOAP-Knoten zu:</span><span class="sxs-lookup"><span data-stu-id="b8270-159">Such layered processing allows for separation between infrastructure layers and application layers of the SOAP node:</span></span>  
  
-   <span data-ttu-id="b8270-160">B1111: Header, die nicht verstanden werden werden erkannt, nach der Verarbeitung der Nachricht durch die WCF-infrastrukturkanalstapel, aber bevor sie von der Anwendung verarbeitet wird</span><span class="sxs-lookup"><span data-stu-id="b8270-160">B1111: Headers that are not understood are detected after the message is processed by the WCF infrastructure channel stack, but before it is processed by application</span></span>  
  
     <span data-ttu-id="b8270-161">Der `mustUnderstand` Headerwert variiert zwischen SOAP 1.1 und SOAP 1.2.</span><span class="sxs-lookup"><span data-stu-id="b8270-161">The `mustUnderstand` header value differs between SOAP 1.1 and SOAP 1.2.</span></span> <span data-ttu-id="b8270-162">Basic Profile 1.1 erfordert, dass der `mustUnderstand`-Wert für SOAP 1.1-Nachrichten "0" (null) oder "1" sein muss.</span><span class="sxs-lookup"><span data-stu-id="b8270-162">Basic Profile 1.1 requires that the `mustUnderstand` value be 0 or 1 for SOAP 1.1 messages.</span></span> <span data-ttu-id="b8270-163">SOAP 1.2 lässt 0 (null), 1 `false` und `true` als Werte zu, empfiehlt aber die Ausgabe einer standardisierten Darstellung der `xs:boolean`-Werte (`false`, `true`).</span><span class="sxs-lookup"><span data-stu-id="b8270-163">SOAP 1.2 allows 0, 1, `false`, and `true` as values, but recommends emitting a canonical representation of `xs:boolean` values (`false`, `true`).</span></span>  
  
-   <span data-ttu-id="b8270-164">B1112: WCF gibt `mustUnderstand` Werte 0 und 1 für SOAP 1.1 und SOAP 1.2-Versionen des SOAP-Umschlags.</span><span class="sxs-lookup"><span data-stu-id="b8270-164">B1112: WCF emits `mustUnderstand` values 0 and 1 for both SOAP 1.1 and SOAP 1.2 versions of the SOAP envelope.</span></span> <span data-ttu-id="b8270-165">WCF akzeptiert den gesamten Wertebereich `xs:boolean` für die `mustUnderstand` Header (0, 1, `false`, `true`)</span><span class="sxs-lookup"><span data-stu-id="b8270-165">WCF accepts the entire value space of `xs:boolean` for the `mustUnderstand` header (0, 1, `false`, `true`)</span></span>  
  
#### <a name="soap-faults"></a><span data-ttu-id="b8270-166">SOAP-Fehler</span><span class="sxs-lookup"><span data-stu-id="b8270-166">SOAP Faults</span></span>  
 <span data-ttu-id="b8270-167">Folgendes ist eine Liste der WCF-spezifische SOAP-Fehler-Implementierungen.</span><span class="sxs-lookup"><span data-stu-id="b8270-167">The following is a list of WCF-specific SOAP fault implementations.</span></span>  
  
-   <span data-ttu-id="b8270-168">B2121: WCF gibt die folgenden SOAP 1.1-Fehlercodes: `s11:mustUnderstand`, `s11:Client`, und `s11:Server`.</span><span class="sxs-lookup"><span data-stu-id="b8270-168">B2121: WCF returns the following SOAP 1.1 Fault Codes: `s11:mustUnderstand`, `s11:Client`, and `s11:Server`.</span></span>  
  
-   <span data-ttu-id="b8270-169">B2122: WCF gibt die folgenden SOAP 1.2-Fehlercodes: `s12:MustUnderstand`, `s12:Sender`, und `s12:Receiver`.</span><span class="sxs-lookup"><span data-stu-id="b8270-169">B2122: WCF returns the following SOAP 1.2 Fault Codes: `s12:MustUnderstand`, `s12:Sender`, and `s12:Receiver`.</span></span>  
  
### <a name="http-binding"></a><span data-ttu-id="b8270-170">HTTP-Bindung</span><span class="sxs-lookup"><span data-stu-id="b8270-170">HTTP Binding</span></span>  
  
#### <a name="soap-11-http-binding"></a><span data-ttu-id="b8270-171">SOAP 1.1 HTTP-Bindung</span><span class="sxs-lookup"><span data-stu-id="b8270-171">SOAP 1.1 HTTP Binding</span></span>  
 <span data-ttu-id="b8270-172">WCF implementiert die SOAP1. 1 HTTP-Bindung gemäß der Basic Profile 1.1-Spezifikation, Abschnitt 3.4 mit den folgenden Erklärungen:</span><span class="sxs-lookup"><span data-stu-id="b8270-172">WCF implements SOAP1.1 HTTP binding following the Basic Profile 1.1 specification section 3.4 with the following clarifications:</span></span>  
  
-   <span data-ttu-id="b8270-173">B2211: WCF-Dienst implementiert keine Umleitung von HTTP POST-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="b8270-173">B2211: WCF service does not implement redirection of HTTP POST requests.</span></span>  
  
-   <span data-ttu-id="b8270-174">B2212: WCF-Clients unterstützen HTTP-Cookies in Übereinstimmung mit 3.4.8.</span><span class="sxs-lookup"><span data-stu-id="b8270-174">B2212: WCF clients support HTTP Cookies in accordance with 3.4.8.</span></span>  
  
#### <a name="soap-12-http-binding"></a><span data-ttu-id="b8270-175">SOAP 1,2 HTTP-Bindung</span><span class="sxs-lookup"><span data-stu-id="b8270-175">SOAP 1.2 HTTP Binding</span></span>  
 <span data-ttu-id="b8270-176">WCF implementiert SOAP 1.2 HTTP-Bindung, wie in SOAP 1.2-Teil 2 (SOAP12Part2)-Spezifikation mit den folgenden Erklärungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8270-176">WCF implements SOAP 1.2 HTTP binding as described in the SOAP 1.2-part 2 (SOAP12Part2) specification with the following clarifications.</span></span>  
  
 <span data-ttu-id="b8270-177">SOAP 1.2 hat einen optionalen Aktionsparameter für den `application/soap+xml`-Medientyp eingeführt.</span><span class="sxs-lookup"><span data-stu-id="b8270-177">SOAP 1.2 introduced an optional action parameter for the `application/soap+xml` media type.</span></span> <span data-ttu-id="b8270-178">Dieser Parameter ist nützlich bei der Optimierung des Sendens von Nachrichten, ohne dass der Text der SOAP-Nachricht analysiert werden muss, wenn die WS-Adressierung nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8270-178">This parameter is useful to optimize message dispatch without requiring that the body of the SOAP message be parsed when WS-Addressing is not used.</span></span>  
  
-   <span data-ttu-id="b8270-179">R2221: Der `application/soap+xml`-Aktionsparameter muss, wenn er in einer SOAP 1.2-Anforderung vorliegt, dem Attribut `soapAction` auf dem Element `wsoap12:operation` in der dazugehörigen WSDL-Bindung entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b8270-179">R2221: The `application/soap+xml` action parameter, when present on a SOAP 1.2 request, must match the `soapAction` attribute on the `wsoap12:operation` element inside the corresponding WSDL binding.</span></span>  
  
-   <span data-ttu-id="b8270-180">R2222: Der `application/soap+xml`-Anwendungsparameter muss, wenn er in einer SOAP 1.2-Nachricht vorliegt, `wsa:Action` entsprechen, wenn die WS-Adressierung 2004/08 oder die WS-Adressierung 1.0 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8270-180">R2222: The `application/soap+xml` action parameter, when present on a SOAP 1.2 message, must match `wsa:Action` when WS-Addressing 2004/08 or WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="b8270-181">Wenn die WS-Adressierung deaktiviert ist und eine eingehende Anforderung keinen Aktionsparameter enthält, gilt die Nachrichten-`Action` als nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="b8270-181">When WS-Addressing is disabled and an incoming request does not contain an action parameter, message `Action` is considered not specified.</span></span>  
  
## <a name="ws-addressing"></a><span data-ttu-id="b8270-182">WS-Adressierung</span><span class="sxs-lookup"><span data-stu-id="b8270-182">WS-Addressing</span></span>  
 <span data-ttu-id="b8270-183">WCF implementiert 3 Versionen der WS-Adressierung:</span><span class="sxs-lookup"><span data-stu-id="b8270-183">WCF implements 3 versions of WS-Addressing:</span></span>  
  
-   <span data-ttu-id="b8270-184">WS-Adressierung 2004/08</span><span class="sxs-lookup"><span data-stu-id="b8270-184">WS-Addressing 2004/08</span></span>  
  
-   <span data-ttu-id="b8270-185">W3C Web Services Addressing 1.0 Core (ADDR10-KERN) und SOAP-Bindung (ADDR10-SOAP)</span><span class="sxs-lookup"><span data-stu-id="b8270-185">W3C Web Services Addressing 1.0 Core  (ADDR10-CORE) and SOAP Binding (ADDR10-SOAP)</span></span>  
  
-   <span data-ttu-id="b8270-186">WS-Addressing 1.0 - Metadata</span><span class="sxs-lookup"><span data-stu-id="b8270-186">WS-Addressing 1.0 - Metadata</span></span>  
  
### <a name="endpoint-references"></a><span data-ttu-id="b8270-187">Endpunktverweise</span><span class="sxs-lookup"><span data-stu-id="b8270-187">Endpoint References</span></span>  
 <span data-ttu-id="b8270-188">Alle Versionen, die WCF implementiert WS-Adressierung verwenden zur Beschreibung von Endpunkten Endpunktverweise.</span><span class="sxs-lookup"><span data-stu-id="b8270-188">All versions of WS-Addressing that WCF implements use endpoint references to describe endpoints.</span></span>  
  
#### <a name="endpoint-references-and-ws-addressing-versions"></a><span data-ttu-id="b8270-189">Endpunktverweise und WS-Adressierungsversionen</span><span class="sxs-lookup"><span data-stu-id="b8270-189">Endpoint References and WS-Addressing Versions</span></span>  
 <span data-ttu-id="b8270-190">WCF implementiert eine Reihe von infrastrukturprotokollen, die WS-Adressierung und insbesondere die `EndpointReference` Element und `W3C.WsAddressing.EndpointReferenceType` -Klasse (z. B. WS-ReliableMessaging, WS-SecureConversation und WS-Trust).</span><span class="sxs-lookup"><span data-stu-id="b8270-190">WCF implements a number of the infrastructure protocols that use WS-Addressing and in particular the `EndpointReference` element and `W3C.WsAddressing.EndpointReferenceType` class (for example, WS-ReliableMessaging, WS-SecureConversation, and WS-Trust).</span></span> <span data-ttu-id="b8270-191">WCF unterstützt die Verwendung beider Versionen der WS-Adressierung mit anderen infrastrukturprotokollen.</span><span class="sxs-lookup"><span data-stu-id="b8270-191">WCF supports the use of either version of WS-Addressing with other infrastructure protocols.</span></span> <span data-ttu-id="b8270-192">WCF-Endpunkte unterstützen eine Version der WS-Adressierung pro Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="b8270-192">WCF endpoints support one version of WS-Addressing per endpoint.</span></span>  
  
 <span data-ttu-id="b8270-193">Für R3111, den Namespace für die `EndpointReference` Element oder Nachrichtenaustausch mit WCF-Endpunkt verwendete Typ muss die Version der WS-Adressierung von diesem Endpunkt implementierten übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b8270-193">For R3111, the namespace for the `EndpointReference` element or type used in messages exchanged with a WCF endpoint must match the version of WS-Addressing implemented by this endpoint.</span></span>  
  
 <span data-ttu-id="b8270-194">Z. B., wenn ein WCF-Endpunkt WS-ReliableMessaging, implementiert die `AcksTo` Header innerhalb eines solchen Endpunkts zurückgegebenes `CreateSequenceResponse` verwendet die WS-Addressing-Version, die die `EncodingBinding` Element gibt an, für diesen Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="b8270-194">For example, if a WCF endpoint implements WS-ReliableMessaging, the `AcksTo` header returned by such an endpoint inside `CreateSequenceResponse` uses the WS-Addressing version that the `EncodingBinding` element specifies for this endpoint.</span></span>  
  
#### <a name="endpoint-references-and-metadata"></a><span data-ttu-id="b8270-195">Endpunktverweise und Metadaten</span><span class="sxs-lookup"><span data-stu-id="b8270-195">Endpoint References and Metadata</span></span>  
 <span data-ttu-id="b8270-196">Eine Anzahl von Szenarien erfordert kommunizierende Metadaten oder einen Verweis auf Metadaten für einen bestimmten Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="b8270-196">A number of scenarios require communicating metadata or a reference to metadata for a given endpoint.</span></span>  
  
 <span data-ttu-id="b8270-197">B3121: WCF wendet Mechanismen, die in Abschnitt 6, um die Metadaten für Endpunktverweise nach Wert oder Verweis aufzunehmen der WS-MetadataExchange (MEX)-Spezifikation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8270-197">B3121: WCF employs mechanisms described in the WS-MetadataExchange (MEX) specification Section 6 to include metadata for endpoint references by value or by reference.</span></span>  
  
 <span data-ttu-id="b8270-198">Betrachten Sie ein Szenario, in denen ein WCF-Dienst erfordert Authentifizierung mit einem Security Assertions Markup Language (SAML)-Token ausgegeben wird, vom Tokenaussteller unter http://sts.fabrikam123.com.</span><span class="sxs-lookup"><span data-stu-id="b8270-198">Consider a scenario where a WCF service requires authentication using a Security Assertions Markup Language (SAML) token issued by the token issuer at http://sts.fabrikam123.com.</span></span> <span data-ttu-id="b8270-199">Der WCF-Endpunkt beschreibt diese Authentifizierungsanforderung mit `sp:IssuedToken` Assertion mit einer verschachtelten `sp:Issuer` Assertion, die auf den Aussteller des Tokens verweist.</span><span class="sxs-lookup"><span data-stu-id="b8270-199">The WCF endpoint describes this authentication requirement by using `sp:IssuedToken` assertion with a nested `sp:Issuer` assertion pointing to the token issuer.</span></span> <span data-ttu-id="b8270-200">Clientanwendungen, die auf die `sp:Issuer`-Assertion zugreifen, müssen mit dem Tokenausstellerendpunkt kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="b8270-200">Client applications that access the `sp:Issuer` assertion need to know how to communicate with the token issuer endpoint.</span></span> <span data-ttu-id="b8270-201">Der Client muss Metadaten über den Tokenaussteller kennen.</span><span class="sxs-lookup"><span data-stu-id="b8270-201">The client needs to know metadata about the token issuer.</span></span> <span data-ttu-id="b8270-202">Verwenden die Erweiterungen in MEX definiert sind, bietet WCF einen Verweis auf die tokenausstellermetadaten.</span><span class="sxs-lookup"><span data-stu-id="b8270-202">Using the endpoint reference metadata extensions defined in MEX, WCF provides a reference to the token issuer metadata.</span></span>  
  
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
  
### <a name="message-addressing-headers"></a><span data-ttu-id="b8270-203">Nachrichtenadressierungsheader</span><span class="sxs-lookup"><span data-stu-id="b8270-203">Message Addressing Headers</span></span>  
  
#### <a name="message-headers"></a><span data-ttu-id="b8270-204">Nachrichtenheader</span><span class="sxs-lookup"><span data-stu-id="b8270-204">Message Headers</span></span>  
 <span data-ttu-id="b8270-205">Für beide WS-adressierungsversionen verwendet WCF die folgenden Nachrichtenheader wie den Spezifikationen `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`, und `wsa:RelatesTo`.</span><span class="sxs-lookup"><span data-stu-id="b8270-205">For both WS-Addressing versions, WCF uses the following message headers as prescribed by the specifications `wsa:To`, `wsa:ReplyTo`, `wsa:Action`, `wsa:MessageID`,and `wsa:RelatesTo`.</span></span>  
  
 <span data-ttu-id="b8270-206">B3211: Für alle Versionen, die WS-Adressierung, WCF berücksichtigt, aber nicht standardmäßig WS-Adressierungs-Nachrichtenheader `wsa:FaultTo` und `wsa:From`.</span><span class="sxs-lookup"><span data-stu-id="b8270-206">B3211: For all WS-Addressing versions, WCF honors, but does not produce out of the box, WS-Addressing message headers `wsa:FaultTo` and `wsa:From`.</span></span>  
  
 <span data-ttu-id="b8270-207">Dienstanwendungen für die Interaktion mit WCF-Anwendungen können diese Nachrichtenheader und WCF diese entsprechend verarbeitet hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b8270-207">Applications that interact with WCF applications can add these message headers and WCF will process them accordingly.</span></span>  
  
#### <a name="reference-parameters-and-properties"></a><span data-ttu-id="b8270-208">Verweisparameter und -eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b8270-208">Reference Parameters and Properties</span></span>  
 <span data-ttu-id="b8270-209">WCF implementiert die Verarbeitung von endpunktverweisparametern und Verweisparameter Endpunkt</span><span class="sxs-lookup"><span data-stu-id="b8270-209">WCF implements processing of endpoint reference parameters and reference p</span></span>  
  
 <span data-ttu-id="b8270-210">Verweiseigenschaften in Übereinstimmung mit den jeweiligen Spezifikationen.</span><span class="sxs-lookup"><span data-stu-id="b8270-210">roperties in accordance with respective specifications.</span></span>  
  
 <span data-ttu-id="b8270-211">B3221: Wenn für die Verwendung von WS-Adressierung 2004/08 konfiguriert, WCF-Endpunkten keinen Unterschied zwischen der Verarbeitung von Verweiseigenschaften und Verweisparametern.</span><span class="sxs-lookup"><span data-stu-id="b8270-211">B3221: When configured to use WS-Addressing 2004/08, WCF endpoints do not differentiate between processing Reference Properties and Reference Parameters.</span></span>  
  
### <a name="message-exchange-patterns"></a><span data-ttu-id="b8270-212">Nachrichtenaustauschmuster</span><span class="sxs-lookup"><span data-stu-id="b8270-212">Message Exchange Patterns</span></span>  
 <span data-ttu-id="b8270-213">Die Reihenfolge der Meldungen, die die webdienstvorgangsaufruf beteiligt wird als bezeichnet die *Nachrichtenaustauschmuster*.</span><span class="sxs-lookup"><span data-stu-id="b8270-213">The sequence of messages involved in the Web service operation invocation is referred to as the *message exchange pattern*.</span></span> <span data-ttu-id="b8270-214">WCF unterstützt unidirektionale, Anforderung / Antwort- und duplexnachrichten-austauschmuster.</span><span class="sxs-lookup"><span data-stu-id="b8270-214">WCF supports one-way, request-reply, and duplex message exchange patterns.</span></span> <span data-ttu-id="b8270-215">Dieser Abschnitt klärt die WS-Adressierungsanforderungen während der Nachrichtenverarbeitung, die vom verwendeten Nachrichtenaustauschmuster abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="b8270-215">This section clarifies WS-Addressing requirements on message processing depending on the message exchange pattern being used.</span></span>  
  
 <span data-ttu-id="b8270-216">Überall in diesem Abschnitt sendet der Anforderungsdienst die erste Nachricht, und der Antwortdienst empfängt die erste Nachricht.</span><span class="sxs-lookup"><span data-stu-id="b8270-216">Throughout this section, the requester sends the first message and the responder receives the first message.</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="b8270-217">Unidirektionale Nachricht</span><span class="sxs-lookup"><span data-stu-id="b8270-217">One-Way Message</span></span>  
 <span data-ttu-id="b8270-218">Wenn ein WCF-Endpunkt konfiguriert ist, zur Unterstützung von Nachrichten mit einem bestimmten `Action` um ein unidirektionales Muster befolgen, befolgt der WCF-Endpunkt die folgenden Verhalten und Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="b8270-218">When a WCF endpoint is configured to support messages with a given `Action` to follow a one-way pattern, the WCF endpoint follows the following behaviors and requirements.</span></span> <span data-ttu-id="b8270-219">Sofern nicht anders angegeben, gelten Verhalten und Regeln für beide Versionen der WS-Adressierung in WCF unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b8270-219">Unless otherwise specified, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>  
  
-   <span data-ttu-id="b8270-220">R3311: Der Anforderungsdienst muss `wsa:To`, `wsa:Action` und Header für alle Verweisparameter, die vom Endpunktverweis angegeben werden, enthalten.</span><span class="sxs-lookup"><span data-stu-id="b8270-220">R3311: The requester must include `wsa:To`, `wsa:Action`, and headers for all reference parameters specified by the endpoint reference.</span></span> <span data-ttu-id="b8270-221">Wenn die WS-Adressierung 2004/08 verwendet wird und [Verweiseigenschaften] vom Endpunktverweis angegeben werden, müssen auch die entsprechenden Header der Nachricht hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="b8270-221">When WS-Addressing 2004/08 is used and [reference properties] are specified by the endpoint reference, the corresponding headers must be added to the message too.</span></span>  
  
-   <span data-ttu-id="b8270-222">B3312: Der Anforderungsdienst kann `MessageID`-, `ReplyTo`- und `FaultTo`-Header enthalten.</span><span class="sxs-lookup"><span data-stu-id="b8270-222">B3312: The requester may include `MessageID`, `ReplyTo`, and `FaultTo` headers.</span></span> <span data-ttu-id="b8270-223">Die Empfängerinfrastruktur ignoriert sie, und sie werden an die Anwendung übergeben.</span><span class="sxs-lookup"><span data-stu-id="b8270-223">The receiver infrastructure will ignore them, and they will be passed to the application.</span></span>  
  
-   <span data-ttu-id="b8270-224">R3313: Wenn HTTP verwendet wird und keine Nachricht an den HTTP-Antwortzweig gesendet wird, muss der Antwortdienst eine HTTP-Antwort ohne Text und mit einem HTTP 202-Statuscode senden.</span><span class="sxs-lookup"><span data-stu-id="b8270-224">R3313: When HTTP is used and no message is being sent on the HTTP response leg, the responder must send an HTTP response with an empty body and an HTTP 202 status code.</span></span>  
  
     <span data-ttu-id="b8270-225">Wenn die HTTP-Transportmethode verwendet wird und der Vorgangsvertrag eine Nachricht als unidirektional ausweist, kann die HTTP-Antwort immer noch zum Senden von Infrastrukturnachrichten verwendet werden – Reliable Messaging kann beispielsweise eine `SequenceAcknowledgement`-Nachricht in einer HTTP-Antwort senden.</span><span class="sxs-lookup"><span data-stu-id="b8270-225">When the HTTP transport is in use and the operation contract declares a message one-way, the HTTP response can still be used for sending infrastructure messages—for example, reliable messaging can send a `SequenceAcknowledgement` message on an HTTP response.</span></span>  
  
-   <span data-ttu-id="b8270-226">B3314: Der WCF-Beantworter sendet keine Fehlermeldung als Antwort auf eine unidirektionale Nachricht.</span><span class="sxs-lookup"><span data-stu-id="b8270-226">B3314: The WCF responder does not send a fault message in response to a one-way message.</span></span>  
  
#### <a name="request-reply"></a><span data-ttu-id="b8270-227">Anforderung-Antwort</span><span class="sxs-lookup"><span data-stu-id="b8270-227">Request-Reply</span></span>  
 <span data-ttu-id="b8270-228">Wenn ein WCF-Endpunkt konfiguriert ist, für eine Nachricht mit einer angegebenen `Action` um das Anforderung-Antwort-Muster zu folgen, folgt der WCF-Endpunkt die Verhalten und Anforderungen, die unten.</span><span class="sxs-lookup"><span data-stu-id="b8270-228">When a WCF endpoint is configured for a message with a given `Action` to follow the request-reply pattern, the WCF endpoint follows the behaviors and requirements below.</span></span> <span data-ttu-id="b8270-229">Sofern nicht anders angegeben, gelten Verhalten und Regeln für beide Versionen der WS-Adressierung in WCF unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b8270-229">Unless specified otherwise, behaviors and rules apply for both versions of WS-Addressing supported in WCF:</span></span>  
  
-   <span data-ttu-id="b8270-230">R3321: Der anforderungsdienst muss in der Anforderung enthalten `wsa:To`, `wsa:Action`, `wsa:MessageID`, und Header für alle Verweisparameter oder Verweis Eigenschaften (oder beides) vom Endpunktverweis angegeben.</span><span class="sxs-lookup"><span data-stu-id="b8270-230">R3321: The requester must include in the request `wsa:To`, `wsa:Action`, `wsa:MessageID`, and headers for all reference parameters or reference properties (or both) specified by the endpoint reference.</span></span>  
  
-   <span data-ttu-id="b8270-231">R3322: Wenn die WS-Adressierung 2004/08 verwendet wird, muss `ReplyTo` auch in der Anforderung enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="b8270-231">R3322: When WS-Addressing 2004/08 is used, `ReplyTo` must also be included in the request.</span></span>  
  
-   <span data-ttu-id="b8270-232">R3323: Wenn WS-Adressierung 1.0 verwendet wird und `ReplyTo` ist nicht vorhanden ist, in der Anforderung, ein standardendpunktverweis, mit dem [Adresse]-Eigenschaft gleich "http://www.w3.org/2005/08/addressing/anonymous" wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="b8270-232">R3323: When WS-Addressing 1.0 is used and `ReplyTo` is not present in the request, a default endpoint reference with the [address] property equal to "http://www.w3.org/2005/08/addressing/anonymous" is used.</span></span>  
  
-   <span data-ttu-id="b8270-233">R3324: Der anforderungsdienst muss enthalten `wsa:To`, `wsa:Action`, und `wsa:RelatesTo` -Header in der Antwortnachricht als auch-Header für alle Verweisparameter oder Verweis Eigenschaften (oder beides) gemäß der `ReplyTo` -Endpunktverweis in der Anforderung.</span><span class="sxs-lookup"><span data-stu-id="b8270-233">R3324: The requester must include `wsa:To`, `wsa:Action`, and `wsa:RelatesTo` headers in the reply message, as well as headers for all reference parameters or reference properties (or both) specified by the `ReplyTo` endpoint reference in the request.</span></span>  
  
### <a name="web-services-addressing-faults"></a><span data-ttu-id="b8270-234">Fehler bei Web Services Addressing</span><span class="sxs-lookup"><span data-stu-id="b8270-234">Web Services Addressing Faults</span></span>  
 <span data-ttu-id="b8270-235">R3411: WCF erzeugt die folgenden von WS-Adressierung 2004/08 definierten Fehler.</span><span class="sxs-lookup"><span data-stu-id="b8270-235">R3411: WCF produces the following faults defined by WS-Addressing 2004/08.</span></span>  
  
|<span data-ttu-id="b8270-236">Code</span><span class="sxs-lookup"><span data-stu-id="b8270-236">Code</span></span>|<span data-ttu-id="b8270-237">Ursache</span><span class="sxs-lookup"><span data-stu-id="b8270-237">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="b8270-238">wsa:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="b8270-238">wsa:DestinationUnreachable</span></span>|<span data-ttu-id="b8270-239">Die Nachricht ist mit `ReplyTo` angekommen, das sich von der Antwortadresse, die für diesen Kanal festgelegt ist, unterscheidet; für die in der To-Headerzeile angegebene Adresse gibt es kein Endpunkt-Listening.</span><span class="sxs-lookup"><span data-stu-id="b8270-239">The message arrived with a `ReplyTo` that is different from the reply address established for this channel; there is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="b8270-240">wsa:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="b8270-240">wsa:ActionNotSupported</span></span>|<span data-ttu-id="b8270-241">Die Infrastrukturkanäle und -verteiler, die mit dem Endpunkt verbunden sind, erkennen die Aktion, die in der Headerzeile `Action` angegeben ist, nicht.</span><span class="sxs-lookup"><span data-stu-id="b8270-241">the infrastructure channels or dispatcher associated with the endpoint do not recognize the action specified in the `Action` header.</span></span>|  
  
 <span data-ttu-id="b8270-242">R3412: WCF erzeugt die folgenden von WS-Adressierung 1.0 definierten Fehler.</span><span class="sxs-lookup"><span data-stu-id="b8270-242">R3412: WCF produces the following faults defined by WS-Addressing 1.0.</span></span>  
  
|<span data-ttu-id="b8270-243">Code</span><span class="sxs-lookup"><span data-stu-id="b8270-243">Code</span></span>|<span data-ttu-id="b8270-244">Ursache</span><span class="sxs-lookup"><span data-stu-id="b8270-244">Cause</span></span>|  
|----------|-----------|  
|<span data-ttu-id="b8270-245">wsa10:InvalidAddressingHeader</span><span class="sxs-lookup"><span data-stu-id="b8270-245">wsa10:InvalidAddressingHeader</span></span>|<span data-ttu-id="b8270-246">Doppelte `wsa:To`, `wsa:ReplyTo`, `wsa:From` oder `wsa:MessageID`.</span><span class="sxs-lookup"><span data-stu-id="b8270-246">Duplicate `wsa:To`, `wsa:ReplyTo`, `wsa:From` or `wsa:MessageID`.</span></span> <span data-ttu-id="b8270-247">Doppelte `wsa:RelatesTo` mit dem gleichen `RelationshipType`.</span><span class="sxs-lookup"><span data-stu-id="b8270-247">Duplicate `wsa:RelatesTo` with the same `RelationshipType`.</span></span>|  
|<span data-ttu-id="b8270-248">wsa10:MessageAddressingHeaderRequired</span><span class="sxs-lookup"><span data-stu-id="b8270-248">wsa10:MessageAddressingHeaderRequired</span></span>|<span data-ttu-id="b8270-249">Der erforderliche Adressierungsheader fehlt.</span><span class="sxs-lookup"><span data-stu-id="b8270-249">The required Addressing header is missing.</span></span>|  
|<span data-ttu-id="b8270-250">wsa10:DestinationUnreachable</span><span class="sxs-lookup"><span data-stu-id="b8270-250">wsa10:DestinationUnreachable</span></span>|<span data-ttu-id="b8270-251">Die Nachricht ist mit `ReplyTo` angekommen, das sich von der Antwortadresse, die für diesen Kanal eingeführt wurde, unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="b8270-251">The message arrived with a `ReplyTo` that is different from the reply address established for this channel.</span></span> <span data-ttu-id="b8270-252">An der Adresse, die im To-Header angegeben ist, gibt es kein Endpunkt-Listening.</span><span class="sxs-lookup"><span data-stu-id="b8270-252">There is no endpoint listening at the address specified in the To header.</span></span>|  
|<span data-ttu-id="b8270-253">wsa10:ActionNotSupported</span><span class="sxs-lookup"><span data-stu-id="b8270-253">wsa10:ActionNotSupported</span></span>|<span data-ttu-id="b8270-254">Eine Aktion, die im `Action`-Header angegeben ist, wird von den Infrastrukturkanälen oder dem Verteiler, die/der mit dem Endpunkt verbunden sind/ist, nicht erkannt.</span><span class="sxs-lookup"><span data-stu-id="b8270-254">An action specified in the `Action` header is not recognized by the infrastructure channels or dispatcher associated with the endpoint.</span></span>|  
|<span data-ttu-id="b8270-255">wsa10:EndpointUnavailable</span><span class="sxs-lookup"><span data-stu-id="b8270-255">wsa10:EndpointUnavailable</span></span>|<span data-ttu-id="b8270-256">Der RM-Kanal schickt diesen Fehler zurück und gibt an, dass der Endpunkt die Sequenz basierend auf einer Untersuchung der Adressheader der Nachricht `CreateSequence` nicht verarbeiten wird.</span><span class="sxs-lookup"><span data-stu-id="b8270-256">The RM channel sends this fault back, indicating the endpoint will not process the sequence based upon examination of the `CreateSequence` message’s addressing headers.</span></span>|  
  
 <span data-ttu-id="b8270-257">Code in den vorangehenden Tabellen wird auf `FaultCode` in SOAP 1.1 und `SubCode` (mit Code=Sender) in SOAP 1.2 abgebildet.</span><span class="sxs-lookup"><span data-stu-id="b8270-257">Code in the preceding tables maps to `FaultCode` in SOAP 1.1 and `SubCode` (with Code=Sender) in SOAP 1.2.</span></span>  
  
### <a name="wsdl-11-binding-and-ws-policy-assertions"></a><span data-ttu-id="b8270-258">WSDL 1.1-Bindung und WS-Richtlinienassertionen</span><span class="sxs-lookup"><span data-stu-id="b8270-258">WSDL 1.1 Binding and WS-Policy Assertions</span></span>  
  
#### <a name="indicating-use-of-ws-addressing"></a><span data-ttu-id="b8270-259">Angeben der Verwendung von WS-Adressierung</span><span class="sxs-lookup"><span data-stu-id="b8270-259">Indicating Use of WS-Addressing</span></span>  
 <span data-ttu-id="b8270-260">WCF verwendet Richtlinienassertionen, um endpunktunterstützung für eine bestimmte Version von WS-Adressierung anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b8270-260">WCF uses policy assertions to indicate endpoint support for a particular WS-Addressing version.</span></span>  
  
 <span data-ttu-id="b8270-261">Die folgende Richtlinienassertion verfügt über das Endpoint Policy Subject [WS-PA] und gibt an, dass von diesem Endpunkt gesendete und empfangene Nachrichten WS-Adressierung 2004/08 verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="b8270-261">The following policy assertion has Endpoint Policy Subject [WS-PA] and indicates messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsap:UsingAddressing />  
```  
  
 <span data-ttu-id="b8270-262">Diese Richtlinienassertion erweitert die Spezifikation zur WS-Adressierung 2004/08.</span><span class="sxs-lookup"><span data-stu-id="b8270-262">This policy assertion augments the WS-Addressing 2004/08 specification.</span></span>  
  
 <span data-ttu-id="b8270-263">Die folgende Richtlinienassertion gibt an, dass gesendete/empfangene Nachrichten die WS-Adressierung 1.0 verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="b8270-263">The following policy assertion this indicates that messages sent/received must use WS-Addressing 1.0.</span></span>  
  
```xml
<wsam:Addressing/>   
```  
  
 <span data-ttu-id="b8270-264">Die folgende Richtlinienassertion verfügt über ein Endpoint Policy Subject [WS-PA] und gibt an, dass von diesem Endpunkt gesendete und empfangene Nachrichten WS-Adressierung 2004/08 verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="b8270-264">The following policy assertion has an Endpoint Policy Subject [WS-PA] and indicates that messages sent and received from the endpoint must use WS-Addressing 2004/08.</span></span>  
  
```xml  
<wsaw10:UsingAddressing />  
```  
  
 <span data-ttu-id="b8270-265">Das Element `wsaw10:UsingAddressing` wird aus der [WS-Addressing-WSDL] ausgeliehen und im Kontext von WS-Policy entsprechend der Spezifikation, Abschnitt 3.1.2, verwendet.</span><span class="sxs-lookup"><span data-stu-id="b8270-265">The `wsaw10:UsingAddressing` element is borrowed from [WS-Addressing-WSDL] and is used in the context of WS-Policy in compliance with that specification, section 3.1.2.</span></span>  
  
 <span data-ttu-id="b8270-266">Die Nutzung von Adressing verwendet nicht die Semantik von WSDL 1.1-, SOAP 1.1- und SOAP 1.2 HTTP-Bindungen.</span><span class="sxs-lookup"><span data-stu-id="b8270-266">Use of Addressing does not alter the semantics of WSDL 1.1, SOAP 1.1, and SOAP 1.2 HTTP Bindings.</span></span> <span data-ttu-id="b8270-267">Wenn beispielsweise eine Antwort auf eine Anfrage erwartet wird, die an einen Endpunkt gesendet wird, der Addressing und WSDL SOAP 1.x HTTP-Bindung verwendet, muss die Antwort unter Verwendung der HTTP-Antwort gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8270-267">For example, if a reply is expected to a request that is sent to an endpoint that uses Addressing and WSDL SOAP 1.x HTTP binding, the reply must be sent by using the HTTP response.</span></span>  
  
 <span data-ttu-id="b8270-268">Die WS-AM-Assertion von Antworten, die über die HTTP-Antwort gesendet werden, ist Folgende:</span><span class="sxs-lookup"><span data-stu-id="b8270-268">For replies sent over the http response, the WS-AM assertion is:</span></span>  
  
```xml  
<wsam:AnonymousResponses/>  
```  
  
 <span data-ttu-id="b8270-269">Die vollständige Richtlinienassertion kann wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b8270-269">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
        <wsam:AnonymousResponses />   
    </wsp:Policy>  
</wsam:Addressing>  
```  
  
 <span data-ttu-id="b8270-270">Es gibt aber Nachrichtenaustauschmuster, die davon profitieren, zwei unabhängige, entgegengesetzte HTTP-Verbindungen zwischen dem Anforderungsdienst und dem Antwortdienst etabliert zu haben, z. B. unaufgeforderte unidirektionale Nachrichten, die vom Antwortdienst gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8270-270">However, there are message exchange patterns that benefit from having two independent converse HTTP connections established between the requester and the responder, for example, unsolicited one-way messages sent by the responder.</span></span>  
  
 <span data-ttu-id="b8270-271">WCF bietet ein Feature, mit dem zwei zugrunde liegende Transportkanäle können einen Composite Duplex-Kanal bilden, bei dem ein Kanal für eingehende Nachrichten und der andere für ausgehende Nachrichten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8270-271">WCF offers a feature by which two underlying transport channels can form a Composite Duplex channel, where one channel is used for input messages and the other is used for output messages.</span></span> <span data-ttu-id="b8270-272">Im Fall des HTTP-Transports stellt Composite Duplex zwei umgekehrte HTTP-Verbindungen bereit.</span><span class="sxs-lookup"><span data-stu-id="b8270-272">In the case of the HTTP Transport, Composite Duplex provides two converse HTTP connections.</span></span> <span data-ttu-id="b8270-273">Der Anforderungsdienst verwendet eine Verbindung, um Nachrichten an den Antwortdienst zu senden, und der Antwortdienst verwendet die andere, um Nachrichten zurück an den Anforderungsdienst zu senden.</span><span class="sxs-lookup"><span data-stu-id="b8270-273">The requester uses one connection to send messages to the responder, and the responder uses the other to send messages back to the requester.</span></span>  
  
 <span data-ttu-id="b8270-274">Die WS-AM-Assertion von Antworten, die über separate HTTP-Anforderungen gesendet werden, ist Folgende:</span><span class="sxs-lookup"><span data-stu-id="b8270-274">For replies sent over separate http requests, the ws-am assertion is</span></span>  
  
```xml  
<wsam:NonAnonymousResponses/>  
```  
  
 <span data-ttu-id="b8270-275">Die vollständige Richtlinienassertion kann wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="b8270-275">The complete policy assertion might look like this:</span></span>  
  
```xml  
<wsam:Addressing>  
    <wsp:Policy>  
      <wsam:NonAnonymousResponses />   
   </wsp:Policy>  
  </wsam:Addressing>  
```  
  
 <span data-ttu-id="b8270-276">Die Verwendung der folgenden Assertion, die über Endpoint Policy Subject [WS-PA] an Endpunkten verfügt, die WSDL 1.1 SOAP 1.x HTTP-Bindungen verwenden, erfordert zwei einzelne entgegengesetzte HTTP-Verbindungen, die jeweils für den Nachrichtenfluss vom Anforderungsdienst an den Antwortdienst bzw. vom Antwortdienst an den Anforderungsdienst verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b8270-276">Use of the following assertion that has Endpoint Policy Subject [WS-PA] on endpoints that use WSDL 1.1 SOAP 1.x HTTP bindings requires two separate converse HTTP connections to be used for messages flowing from requester to responder and responder to requester, respectively.</span></span>  
  
```xml  
<cdp:CompositeDuplex/>  
```  
  
 <span data-ttu-id="b8270-277">Die vorherige Anweisung führt bei Anforderungsnachrichten zu den folgenden Anforderungen an den `wsa:ReplyTo`-Header:</span><span class="sxs-lookup"><span data-stu-id="b8270-277">The previous statement leads to the following requirements on the `wsa:ReplyTo` header for request messages:</span></span>  
  
-   <span data-ttu-id="b8270-278">R3514: Anforderung an einen Endpunkt gesendete Anforderungsnachrichten müssen eine `ReplyTo` -Header mit der `[address]` -Eigenschaft nicht gleich "http://www.w3.org/2005/08/addressing/anonymous" Wenn der Endpunkt eine WSDL 1.1 SOAP 1.x HTTP-Bindung verwendet und verfügt über eine richtlinienalternative mit einer `wsap10:UsingAddressing` oder `wsap:UsingAddressing` Assertion gekoppelt `cdp:CompositeDuplex` angefügt.</span><span class="sxs-lookup"><span data-stu-id="b8270-278">R3514: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property not equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with a `wsap10:UsingAddressing` or `wsap:UsingAddressing` assertion coupled with `cdp:CompositeDuplex` attached.</span></span>  
  
-   <span data-ttu-id="b8270-279">R3515: Anforderung an einen Endpunkt gesendete Anforderungsnachrichten müssen eine `ReplyTo` -Header mit der `[address]` -Eigenschaft gleich "http://www.w3.org/2005/08/addressing/anonymous", oder nicht über eine `ReplyTo` Header überhaupt, wenn der Endpunkt eine WSDL 1.1 SOAP 1.x HTTP-Bindung verwendet und verfügt über eine richtlinienalternative mit `wsap10:UsingAddressing` -Assertion und keiner `cdp:CompositeDuplex` -Assertion angehängt.</span><span class="sxs-lookup"><span data-stu-id="b8270-279">R3515: Request messages sent to an endpoint must have a `ReplyTo` header with the `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous", or not have a `ReplyTo` header at all, if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap10:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
-   <span data-ttu-id="b8270-280">R3516: Anforderung an einen Endpunkt gesendete Anforderungsnachrichten müssen eine `ReplyTo` -Header mit einem `[address]` -Eigenschaft gleich "http://www.w3.org/2005/08/addressing/anonymous" Wenn der Endpunkt eine WSDL 1.1 SOAP 1.x HTTP-Bindung verwendet und verfügt über eine richtlinienalternative mit `wsap:UsingAddressing` Assertion und keine `cdp:CompositeDuplex`-Assertion angehängt.</span><span class="sxs-lookup"><span data-stu-id="b8270-280">R3516: Request messages sent to an endpoint must have a `ReplyTo` header with an `[address]` property equal to "http://www.w3.org/2005/08/addressing/anonymous" if the endpoint uses a WSDL 1.1 SOAP 1.x HTTP binding and has a policy alternative with `wsap:UsingAddressing` assertion and no `cdp:CompositeDuplex` assertion attached.</span></span>  
  
 <span data-ttu-id="b8270-281">Die WS-Adressierung-WSDL-Spezifikation versucht, ähnliche Protokollbindungen zu beschreiben, indem sie ein `<wsaw:Anonymous/>`-Element mit drei Textwerten (erforderlich, optional und verboten) einführt, um die Anforderungen im `wsa:ReplyTo`-Header (Abschnitt 3.2) anzugeben.</span><span class="sxs-lookup"><span data-stu-id="b8270-281">The WS-addressing WSDL specification attempts to describe similar protocol bindings by introducing an element `<wsaw:Anonymous/>` with three textual values (required, optional, and prohibited) to indicate requirements on the `wsa:ReplyTo` header (section 3.2).</span></span> <span data-ttu-id="b8270-282">Leider ist eine derartige Elementdefinition im Kontext einer WS-Richtlinie als Assertion nicht besonders nützlich, da sie domänenspezifische Erweiterungen benötigt, um den Knotenpunkt von Alternativen zu unterstützen, die ein derartiges Element als Assertion verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8270-282">Unfortunately, such element definition is not particularly usable as an assertion in the context of WS-Policy, because it requires domain-specific extensions to support the intersection of alternatives using such an element as an assertion.</span></span> <span data-ttu-id="b8270-283">Eine derartige Elementdefinition gibt außerdem den Wert des `ReplyTo`-Headers als Gegenstück zum Endpunktverhalten auf dem Kabel an und macht ihn somit spezifisch für den HTTP-Transport.</span><span class="sxs-lookup"><span data-stu-id="b8270-283">Such element definition also indicates the value of the `ReplyTo` header as opposed to the endpoint behavior on the wire, which makes it specific to HTTP transport.</span></span>  
  
#### <a name="action-definition"></a><span data-ttu-id="b8270-284">Aktionsdefinition</span><span class="sxs-lookup"><span data-stu-id="b8270-284">Action Definition</span></span>  
 <span data-ttu-id="b8270-285">WS-Adressierung 2004/08 definiert ein `wsa:Action`-Attribut für die `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]`-Elemente.</span><span class="sxs-lookup"><span data-stu-id="b8270-285">WS-Addressing 2004/08 defines a `wsa:Action` attribute for the `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements.</span></span> <span data-ttu-id="b8270-286">WS-Adressierung 1.0 WSDL-Bindung (WS-ADDR10-WSDL) definiert ein ähnliches Attribut, `wsaw10:Action`.</span><span class="sxs-lookup"><span data-stu-id="b8270-286">WS-Addressing 1.0 WSDL Binding (WS-ADDR10-WSDL) defines a similar attribute, `wsaw10:Action`.</span></span>  
  
 <span data-ttu-id="b8270-287">Der einzige Unterschied zwischen den beiden ist die Standardaktionsmustersemantik, die in Abschnitt 3.3.2 von WS-ADDR bzw. Abschnitt 4.4.4 der 4.4.4 von WS-ADDR10-WSDL beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="b8270-287">The only difference between the two is the default Action pattern semantics described in section 3.3.2 of WS-ADDR and section 4.4.4 of WS-ADDR10-WSDL, respectively.</span></span>  
  
 <span data-ttu-id="b8270-288">Es ist sinnvoll, zwei Endpunkte verfügen, die denselben `portType` (oder der Vertrag, in der WCF-Terminologie), aber mit verschiedenen Versionen der WS-Adressierung.</span><span class="sxs-lookup"><span data-stu-id="b8270-288">It is a reasonable to have two endpoints that share the same `portType` (or contract, in WCF terminology) but using different versions of WS-Addressing.</span></span> <span data-ttu-id="b8270-289">Da aber "Aktion" durch den `portType` definiert wird und sich nicht zwischen den Endpunkten, die den `portType` implementieren, ändern sollte, ist es unmöglich, beide Standardaktionsmuster zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b8270-289">But given that Action is defined by the `portType` and should not change across the endpoints that implement the `portType`, it becomes impossible to support both default action patterns.</span></span>  
  
 <span data-ttu-id="b8270-290">Um diese kontroverse zu beheben, WCF unterstützt eine einzelne Version der `Action` Attribut.</span><span class="sxs-lookup"><span data-stu-id="b8270-290">To resolve this controversy, WCF supports a single version of the `Action` attribute.</span></span>  
  
 <span data-ttu-id="b8270-291">B3521: WCF verwendet die `wsaw10:Action` -Attribut `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` Elemente, die WS-ADDR10-WSDL, um zu bestimmen, gemäß der `Action` URI für die entsprechenden Nachrichten unabhängig von der WS-Addressing-Version, die vom Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8270-291">B3521: WCF uses the `wsaw10:Action` attribute on `wsdl:portType/wsdl:operation/[wsdl:input | wsdl:output | wsdl:fault]` elements as defined in WS-ADDR10-WSDL to determine the `Action` URI for the corresponding messages irrespective of the WS-Addressing version used by the endpoint.</span></span>  
  
#### <a name="use-endpoint-reference-inside-wsdl-port"></a><span data-ttu-id="b8270-292">Verwenden des Endpunktverweises im WSDL-Anschluss</span><span class="sxs-lookup"><span data-stu-id="b8270-292">Use Endpoint Reference Inside WSDL Port</span></span>  
 <span data-ttu-id="b8270-293">Abschnitt 4.1 von WS-ADDR10-WSDL erweitert das `wsdl:port`-Element durch das untergeordnete `<wsa10:EndpointReference…/>`-Element, um den Endpunkt in WS-Adressierungsbegriffen zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="b8270-293">WS-ADDR10-WSDL section 4.1 extends the `wsdl:port` element to include the `<wsa10:EndpointReference…/>` child element to describe the endpoint in WS-Addressing terms.</span></span> <span data-ttu-id="b8270-294">WCF erweitert dieses Hilfsprogramm in der WS-Adressierung 2004/08, sodass `<wsa:EndpointReference…/>` erscheint als untergeordnetes Element des `wsdl:port`.</span><span class="sxs-lookup"><span data-stu-id="b8270-294">WCF expands this utility on WS-Addressing 2004/08, allowing `<wsa:EndpointReference…/>` to appear as a child element of `wsdl:port`.</span></span>  
  
-   <span data-ttu-id="b8270-295">R3531: Wenn einem Endpunkt eine Richtlinienalternative mit einer `<wsaw10:UsingAddressing/>`-Richtlinienassertion angehängt ist, kann das entsprechende`wsdl:port`-Element ein untergeordnetes Element`<wsa10:EndpointReference …/>` enthalten.</span><span class="sxs-lookup"><span data-stu-id="b8270-295">R3531: If an endpoint has an attached policy alternative with a `<wsaw10:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa10:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="b8270-296">R3532: Wenn ein `wsdl:port` enthält ein untergeordnetes Element `<wsa10:EndpointReference …/>`, `wsa10:EndpointReference/wsa10:Address` untergeordnete Element muss mit dem Wert übereinstimmen von der `@address` Attributs des gleichgeordneten `wsdl:port` / `wsdl:location` Element.</span><span class="sxs-lookup"><span data-stu-id="b8270-296">R3532: If a `wsdl:port` contains a child element `<wsa10:EndpointReference …/>`, the `wsa10:EndpointReference/wsa10:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
-   <span data-ttu-id="b8270-297">R3533: Wenn einem Endpunkt eine Richtlinienalternative mit einer `<wsap:UsingAddressing/>`-Richtlinienassertion angehängt ist, kann das entsprechende`wsdl:port`-Element ein untergeordnetes Element`<wsa:EndpointReference …/>` enthalten.</span><span class="sxs-lookup"><span data-stu-id="b8270-297">R3533: If an endpoint has an attached policy alternative with `<wsap:UsingAddressing/>` policy assertion, the corresponding `wsdl:port` element can contain a child element `<wsa:EndpointReference …/>`.</span></span>  
  
-   <span data-ttu-id="b8270-298">R3534: Wenn ein `wsdl:port` enthält ein untergeordnetes Element `<wsa:EndpointReference …/>`, `wsa:EndpointReference/wsa:Address` untergeordnete Element muss mit dem Wert übereinstimmen von der `@address` Attributs des gleichgeordneten `wsdl:port` / `wsdl:location` Element.</span><span class="sxs-lookup"><span data-stu-id="b8270-298">R3534: If a `wsdl:port` contains a child element `<wsa:EndpointReference …/>`, the `wsa:EndpointReference/wsa:Address` child element value must match the value of the `@address` attribute of the sibling `wsdl:port`/`wsdl:location` element.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="b8270-299">Gestaltung mit WS-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b8270-299">Composition with WS-Security</span></span>  
 <span data-ttu-id="b8270-300">Gemäß den Sicherheitsüberlegungsabschnitten in WS-ADDR und WS-ADDR10 wird empfohlen, dass alle adressierenden Header zusammen mit dem Nachrichtentext signiert werden, um sie zusammenzubinden.</span><span class="sxs-lookup"><span data-stu-id="b8270-300">According to security consideration sections in WS-ADDR and WS-ADDR10, all addressing message headers are recommended to be signed together with the message body to bind them together.</span></span>  
  
 <span data-ttu-id="b8270-301">Wenn WS-Sicherheit für den Nachrichtenintegritätsschutz verwendet wird, müssen die WS-Adressierungs-Nachrichtenheader genauso wie die Header, die aus Referenzparametern oder -eigenschaften (oder beidem) entstanden sind, zusammen mit dem Text der Nachricht signiert werden.</span><span class="sxs-lookup"><span data-stu-id="b8270-301">When WS-Security is used for message integrity protection, WS-Addressing message headers as well as headers resulted from reference parameters or properties (or both) must be signed together with the body of the message.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b8270-302">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b8270-302">Examples</span></span>  
  
#### <a name="one-way-message"></a><span data-ttu-id="b8270-303">Unidirektionale Nachricht</span><span class="sxs-lookup"><span data-stu-id="b8270-303">One-Way Message</span></span>  
 <span data-ttu-id="b8270-304">In diesem Szenario sendet der Absender eine unidirektionale Nachricht zum Empfänger.</span><span class="sxs-lookup"><span data-stu-id="b8270-304">In this scenario, the sender sends a one-way message to the receiver.</span></span> <span data-ttu-id="b8270-305">SOAP 1.2, HTTP 1.1 und W3C WS-Adressierung 1.0 werden verwendet.</span><span class="sxs-lookup"><span data-stu-id="b8270-305">SOAP 1.2, HTTP 1.1, and W3C WS-Addressing 1.0 are used.</span></span>  
  
 <span data-ttu-id="b8270-306">Die Anforderungsnachrichtenstruktur: Zu den Nachrichtenheadern gehören die Elemente `wsa10:To` und `wsa10:Action`.</span><span class="sxs-lookup"><span data-stu-id="b8270-306">The Request Message Structure: The message headers include `wsa10:To` and `wsa10:Action` elements.</span></span> <span data-ttu-id="b8270-307">Der Nachrichtentext schließt ein bestimmtes `<app:Ping>`-Element vom Anwendungsnamespace ein.</span><span class="sxs-lookup"><span data-stu-id="b8270-307">The message body includes a specific `<app:Ping>` element from the application namespace.</span></span>  
  
 <span data-ttu-id="b8270-308">HTTP-Header: Das Ziel in POST entspricht den URI in der `wsa10:To` Element.</span><span class="sxs-lookup"><span data-stu-id="b8270-308">HTTP Headers: The destination in POST matches the URI in the `wsa10:To` element.</span></span>  
  
 <span data-ttu-id="b8270-309">Der Content-Type-Header entspricht dem Wert `application/soap+xml`, wie von SOAP 1.2 vorausgesetzt.</span><span class="sxs-lookup"><span data-stu-id="b8270-309">The Content-Type header has the value of `application/soap+xml` as required by SOAP 1.2.</span></span> <span data-ttu-id="b8270-310">Die Parameter `charset` und `action` sind eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b8270-310">Parameters `charset` and `action` are included.</span></span> <span data-ttu-id="b8270-311">Der Parameter `action` des Content-Type-Headers entspricht dem Wert des `wsa10:Action`-Nachrichtenheaders.</span><span class="sxs-lookup"><span data-stu-id="b8270-311">The `action` parameter of the Content-Type header matches the value of the `wsa10:Action` message header.</span></span>  
  
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
  
 <span data-ttu-id="b8270-312">Der Empfänger antwortet mit einer leeren HTTP-Antwort und dem Status 202.</span><span class="sxs-lookup"><span data-stu-id="b8270-312">The receiver responds with an empty HTTP response and status 202.</span></span> <span data-ttu-id="b8270-313">Ein Beispiel für die HTTP-Antwort:</span><span class="sxs-lookup"><span data-stu-id="b8270-313">An example of the HTTP response:</span></span>  
  
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
  
## <a name="soap-message-transmission-optimization-mechanism"></a><span data-ttu-id="b8270-314">SOAP-Nachrichten-Übertragungsoptimierungsmechanismus</span><span class="sxs-lookup"><span data-stu-id="b8270-314">SOAP Message Transmission Optimization Mechanism</span></span>  
 <span data-ttu-id="b8270-315">Dieser Abschnitt beschreibt die Details der WCF-Implementierung für die HTTP-SOAP MTOM.</span><span class="sxs-lookup"><span data-stu-id="b8270-315">This section describes the WCF implementation details for the HTTP SOAP MTOM.</span></span> <span data-ttu-id="b8270-316">MTOM-Technologie ist SOAP-nachrichtencodierungsmechanismus der gleichen Klasse wie traditionelle Text-/XML-Codierungs- oder WCF-binärcodierung.</span><span class="sxs-lookup"><span data-stu-id="b8270-316">MTOM technology is SOAP message encoding mechanism of the same class as traditional text/XML encoding or WCF Binary encoding.</span></span> <span data-ttu-id="b8270-317">Zu MTOM gehören folgende Elemente:</span><span class="sxs-lookup"><span data-stu-id="b8270-317">MTOM includes the following:</span></span>  
  
-   <span data-ttu-id="b8270-318">Ein XML-Codierungs- und Verpackungsmechanismus, der von [XOP] beschrieben wird, und XML-Informationselemente, die base64-codierte Binärdaten enthalten, die in einzelne Binärteile optimiert wurden.</span><span class="sxs-lookup"><span data-stu-id="b8270-318">An XML encoding and packaging mechanism described by [XOP] that optimizes XML information items containing base64-encoded binary data into separate binary parts.</span></span>  
  
-   <span data-ttu-id="b8270-319">Eine MIME-Kapselung des XOP-Pakets, das das XML-Infoset und jeden Binärteil des XOP-Pakets in einen einzelnen MIME-Teil serialisiert.</span><span class="sxs-lookup"><span data-stu-id="b8270-319">A MIME encapsulation of the XOP package that serializes the XML Infoset and each binary part of the XOP package into a separate MIME part.</span></span>  
  
-   <span data-ttu-id="b8270-320">Eine MIME-XOP-Codierung, die auf SOAP 1.x Envelope angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b8270-320">A MIME XOP encoding applied to SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="b8270-321">Eine HTTP-Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="b8270-321">An HTTP transport binding.</span></span>  
  
 <span data-ttu-id="b8270-322">Es ist möglich, MTOM mit nicht-HTTP-Transporte mit WCF zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b8270-322">It is possible to use MTOM with non-HTTP transports with WCF.</span></span> <span data-ttu-id="b8270-323">In diesem Thema konzentrieren wir uns jedoch auf HTTP.</span><span class="sxs-lookup"><span data-stu-id="b8270-323">However, in this topic we will focus on HTTP.</span></span>  
  
 <span data-ttu-id="b8270-324">Das MTOM-Format setzt einen großen Satz von Spezifikationen ein, der MTOM selbst, XOP und MIME abdeckt.</span><span class="sxs-lookup"><span data-stu-id="b8270-324">The MTOM format leverages a large set of specifications covering MTOM itself, XOP, and MIME.</span></span> <span data-ttu-id="b8270-325">Die Modularität dieses Spezifikationssatzes macht es schwierig, die genauen Anforderungen an die Format- und Verarbeitungssemantik zu rekonstruieren.</span><span class="sxs-lookup"><span data-stu-id="b8270-325">Modularity of this specification set makes it somewhat difficult to reconstruct exact requirements on the format and processing semantics.</span></span> <span data-ttu-id="b8270-326">In diesem Abschnitt werden die Format- und Verarbeitungsanforderungen an MTOM-HTTP-Bindungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b8270-326">This section describes the format and processing requirements for MTOM HTTP binding.</span></span>  
  
### <a name="mtom-message-encoding"></a><span data-ttu-id="b8270-327">MTOM-Nachrichtencodierung</span><span class="sxs-lookup"><span data-stu-id="b8270-327">MTOM Message Encoding</span></span>  
  
#### <a name="generating-mtom-messages"></a><span data-ttu-id="b8270-328">Generieren von MTOM-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="b8270-328">Generating MTOM messages</span></span>  
 <span data-ttu-id="b8270-329">[XOP] Abschnitt 3.1 beschreibt den Vorgang der Codierung von XML mit Elementinformationselementen, die base24-Werte enthalten, in ein abstrakt definiertes XOP-Paket.</span><span class="sxs-lookup"><span data-stu-id="b8270-329">The [XOP] section 3.1 describes the process of encoding XML with element information items that contain base64 values into an abstractly defined XOP package.</span></span>  
  
 <span data-ttu-id="b8270-330">Die folgende Sequenz von Schritten beschreibt den MTOM-spezifischen Codierungsprozess:</span><span class="sxs-lookup"><span data-stu-id="b8270-330">The following sequence of steps describes the MTOM-specific encoding process:</span></span>  
  
1.  <span data-ttu-id="b8270-331">Stellen Sie sicher, dass der zu codierende SOAP-Umschlag kein elementinformationselement mit enthält eine `[namespace name]` von "http://www.w3.org/2004/08/xop/include" und ein `[local name]` von `Include`.</span><span class="sxs-lookup"><span data-stu-id="b8270-331">Ensure that the SOAP Envelope to be encoded contains no element information item with a `[namespace name]` of "http://www.w3.org/2004/08/xop/include" and a `[local name]` of `Include`.</span></span>  
  
2.  <span data-ttu-id="b8270-332">Erstellen Sie ein leeres MIME-Paket.</span><span class="sxs-lookup"><span data-stu-id="b8270-332">Create an empty MIME package.</span></span>  
  
3.  <span data-ttu-id="b8270-333">Identifizieren Sie die Elementinformationselemente, die optimiert werden sollten, innerhalb des Original XML Infoset.</span><span class="sxs-lookup"><span data-stu-id="b8270-333">Identify within the Original XML Infoset the element information items to be optimized.</span></span> <span data-ttu-id="b8270-334">Für die Elemente optimiert werden, die Zeichen, die bilden die `[children]` des elementinformationselements-Element muss in kanonischer Form werden `xs:base64Binary` (Siehe XSD-2, 3.2.16 base64Binary) und darf Leerzeichen vor, oder nach dem nicht-Leerzeichen-Inhalt.</span><span class="sxs-lookup"><span data-stu-id="b8270-334">For the items to be optimized, the characters that make up the `[children]` of the element information item must be in the canonical form of `xs:base64Binary` (see XSD-2, 3.2.16 base64Binary) and must not contain any white-space characters preceding, inline with, or following the non-white-space content.</span></span>  
  
4.  <span data-ttu-id="b8270-335">Erstellen Sie einen XOP SOAP-Umschlag, der eine Kopie des Original-SOAP-Umschlags ist, aber bei dem das untergeordnete Element jedes Elementinformationselements, das im vorherigen Schritt identifiziert wurde, durch ein `xop:Include`-Elementinformationselement ersetzt wurde, das wie folgt erstellt wird:</span><span class="sxs-lookup"><span data-stu-id="b8270-335">Create an XOP SOAP Envelope that is a copy of the Original SOAP Envelope, but with the children of each element information item identified in the previous step replaced by an `xop:Include` element information item constructed as follows:</span></span>  
  
    1.  <span data-ttu-id="b8270-336">Wandeln Sie die ersetzten Zeichen in Binärdaten um, indem Sie sie als base64-codierte Daten verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="b8270-336">Transform the replaced characters into binary data by processing them as base64-encoded data.</span></span>  
  
    2.  <span data-ttu-id="b8270-337">Generieren Sie einen eindeutigen Content-ID-Headerwert, der die Anforderungen R3133 und R3134 zufriedenstellt.</span><span class="sxs-lookup"><span data-stu-id="b8270-337">Generate a unique Content-ID header value that satisfies requirements R3133 and R3134.</span></span>  
  
    3.  <span data-ttu-id="b8270-338">Generieren Sie einen Content-Transfer-Encoding-MIME-Header mit dem Wert "binär".</span><span class="sxs-lookup"><span data-stu-id="b8270-338">Generate a Content-Transfer-Encoding MIME header with the value binary.</span></span>  
  
    4.  <span data-ttu-id="b8270-339">Wenn das optimierte Elementinformationselement (das [übergeordnete Element] des neu eingefügten `xop:Include`-Elementinformationselements) ein `xmime:contentType`-Attributelement besitzt, generieren Sie einen Content-Type-MIME-Header mit dem Wert des `xmime:contentType`-Attributs.</span><span class="sxs-lookup"><span data-stu-id="b8270-339">If the element information item being optimized (the [parent] of the newly inserted `xop:Include` element information item) has an `xmime:contentType` attribute information item, generate a Content-Type MIME header with the value of the `xmime:contentType` attribute.</span></span>  
  
    5.  <span data-ttu-id="b8270-340">Generieren Sie ein neues MIME-Teil mit einem Inhalt aus Binärdaten, die aus den ersetzten Zeichen entschlüsselt wurden, die als base64, Content-ID-Header aus 4b, Content-Transfer-Encoding-Header und Content-Type-Header bei Generierung in Schritt 4d aus 4c verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="b8270-340">Generate a new binary MIME part with content formed by binary data decoded from the replaced characters processed as base64, Content-ID header from 4b, Content- Transfer-Encoding header from 4c, Content-Type header if generated in step 4d.</span></span>  
  
    6.  <span data-ttu-id="b8270-341">Fügen Sie ein `href`-Attribut zum `xop:Include`-Element mit dem Wert "cid: uri" hinzu, der in Schritt 4b aus dem Content-ID-Headerwert erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="b8270-341">Add an `href` attribute to the `xop:Include` element with the value cid: uri derived from Content-ID header value generated in step 4b.</span></span> <span data-ttu-id="b8270-342">Entfernen Sie die umschließenden "\<" und ">"-Zeichen, die URL-Escape-Zeichenfolge die verbleibenden, und fügen Sie das Präfix `cid:`.</span><span class="sxs-lookup"><span data-stu-id="b8270-342">Remove the enclosing "\<" and ">" characters, URL-escape the remaining string, and add the prefix `cid:`.</span></span> <span data-ttu-id="b8270-343">Der folgende minimale Zeichensatz ist erforderlich, um RFC1738 und RFC2396 mit einem Escapezeichen zu versehen.</span><span class="sxs-lookup"><span data-stu-id="b8270-343">The following minimum character set is required to be escaped by RFC1738 and RFC2396.</span></span> <span data-ttu-id="b8270-344">Andere Zeichen können mit Escapezeichen versehen werden.</span><span class="sxs-lookup"><span data-stu-id="b8270-344">Other characters can be escaped.</span></span>  
  
        ```  
        Hexadecimal 00-1F , 7F, 20, "<" | ">" | "#" | "%" | <">  
        "{" | "}" | "|" | "\" | "^" | "[" | "]" | "`" | "~" | "^"  
        ```  
  
5.  <span data-ttu-id="b8270-345">Erstellen Sie ein Stamm-MIME-Teil mit dem XOP SOAP-Umschlag aus Schritt 4.</span><span class="sxs-lookup"><span data-stu-id="b8270-345">Create a root MIME part with the XOP SOAP Envelope from step 4.</span></span>  
  
6.  <span data-ttu-id="b8270-346">Schreiben Sie die HTTP-Header, einschließlich des HTTP Content-Type-Headers.</span><span class="sxs-lookup"><span data-stu-id="b8270-346">Write the HTTP headers, including the HTTP Content-Type header.</span></span>  
  
7.  <span data-ttu-id="b8270-347">Schreiben Sie das MIME-Paket.</span><span class="sxs-lookup"><span data-stu-id="b8270-347">Write the MIME package.</span></span>  
  
#### <a name="processing-mtom-messages"></a><span data-ttu-id="b8270-348">Verarbeiten von MTOM-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="b8270-348">Processing MTOM messages</span></span>  
 <span data-ttu-id="b8270-349">Die Verarbeitung einer MTOM-Nachricht ist das genaue Gegenteil des Vorgangs, der im vorangehenden Abschnitt "Generieren von MTOM-Nachrichten" beschrieben wurde:</span><span class="sxs-lookup"><span data-stu-id="b8270-349">Processing of an MTOM message is the exact reverse of the process described in the preceding "Generating MTOM messages" section:</span></span>  
  
1.  <span data-ttu-id="b8270-350">Stellen Sie sicher, dass der Stamm-MIME-Teil den Content-Type `application/xop+xml` hat.</span><span class="sxs-lookup"><span data-stu-id="b8270-350">Ensure the root MIME part has the Content-Type `application/xop+xml`.</span></span>  
  
2.  <span data-ttu-id="b8270-351">Erstellen Sie einen SOAP-Umschlag, indem Sie den Stamm-MIME-Teil des Pakets als XML-Dokument analysieren.</span><span class="sxs-lookup"><span data-stu-id="b8270-351">Construct a SOAP Envelope by parsing the root MIME part of the package as an XML document.</span></span> <span data-ttu-id="b8270-352">Die Zeichencodierung wird vom Parameter `charset` des Content-Type des Stamm-MIME-Teils bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b8270-352">Character encoding is determined by the `charset` parameter of the Content-Type of the root MIME part.</span></span>  
  
3.  <span data-ttu-id="b8270-353">Für jedes Elementinformationselement im erstellten SOAP-Umschlag, der, als einziges Mitglied seiner [untergeordneten] Eigenschaft, ein `xop:Include`-Elementinformationselement enthält:</span><span class="sxs-lookup"><span data-stu-id="b8270-353">For each element information item in the constructed SOAP Envelope, which has, as the sole member of its [children] property, an `xop:Include` element information item:</span></span>  
  
    1.  <span data-ttu-id="b8270-354">Löschen Sie das Präfix `cid:`, und entfernen Sie alle URI-Escape-Zeichensequenzen (RFC 2396) im Wert des `@href`-Attributs des Elements `xop:Include`.</span><span class="sxs-lookup"><span data-stu-id="b8270-354">Remove the `cid:` prefix and unescape all URI-escape sequences (RFC 2396) in the value of the `@href` attribute of the `xop:Include` element.</span></span> <span data-ttu-id="b8270-355">Schließen Sie die Ergebniszeichenfolge "\<", ">".</span><span class="sxs-lookup"><span data-stu-id="b8270-355">Enclose the result string in "\<", ">".</span></span>  
  
    2.  <span data-ttu-id="b8270-356">Suchen Sie den MIME-Teil mit dem Content-ID-Headerwert, der mit der in Schritt 3a abgeleiteten Zeichenfolge übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="b8270-356">Locate the MIME part with the Content-ID header value that matches the string derived in step 3a.</span></span>  
  
    3.  <span data-ttu-id="b8270-357">Ersetzen Sie das Elementinformationselement `xop:Include`, das in der Eigenschaft `children` jedes Elements vorkommt, durch Zeicheninformationselemente, die die vorschriftsmäßige base64-Codierung (siehe XSD-2, 3.2.16 base64Binary) des Entitätstexts des in Schritt 3b identifizierten MIME-Teils repräsentieren (ersetzen Sie wirksam das Elementinformationselement `xop:Include` durch die Daten, die im Paketteil rekonstruiert wurden).</span><span class="sxs-lookup"><span data-stu-id="b8270-357">Replace the `xop:Include` element information item that appears in the `children` property of each item with the character information items that represent the canonical base64 encoding (see XSD-2, 3.2.16 base64Binary) of the entity body of the MIME part identified in step 3b (effectively replace the `xop:Include` element information item with the data reconstructed from the package part).</span></span>  
  
#### <a name="http-content-type-header"></a><span data-ttu-id="b8270-358">HTTP Content-Type Header</span><span class="sxs-lookup"><span data-stu-id="b8270-358">HTTP Content-Type Header</span></span>  
 <span data-ttu-id="b8270-359">Im folgenden ist eine Liste von WCF-Klärungen des Formats des HTTP Content-Type-Headers, der eine SOAP 1.x MTOM-codierte Nachricht von Anforderungen, die in der MTOM-Spezifikation selbst abgeleitet und MTOM und RFC 2387 abgeleitet sind.</span><span class="sxs-lookup"><span data-stu-id="b8270-359">The following is a list of WCF clarifications for the format of the HTTP Content-Type header of a SOAP 1.x MTOM-encoded message derived from requirements stated in the MTOM specification itself and are derived from MTOM and RFC 2387.</span></span>  
  
-   <span data-ttu-id="b8270-360">R4131: Ein HTTP-Content-Type-Header muss den Wert mehrteilig/verwandt (Groß- und Kleinschreibung nicht beachtend) und seine Parameter besitzen.</span><span class="sxs-lookup"><span data-stu-id="b8270-360">R4131: An HTTP Content-Type header must have the value of multipart/related (case-insensitive) and its parameters.</span></span> <span data-ttu-id="b8270-361">Bei den Parameternamen braucht die Groß- und Kleinschreibung nicht berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="b8270-361">Parameter names are case-insensitive.</span></span> <span data-ttu-id="b8270-362">Die Parameterreihenfolge ist nicht wichtig.</span><span class="sxs-lookup"><span data-stu-id="b8270-362">Parameter order is not significant.</span></span>  
  
-   <span data-ttu-id="b8270-363">Das komplette Backus-Naur Form (BNF) des Content-Type-Headers für MIME-Nachrichten wird in RFC 2045, Abschnitt 5.1 aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b8270-363">The full Backus-Naur Form (BNF) of the Content-Type header for MIME messages is listed in RFC 2045, section 5.1.</span></span>  
  
-   <span data-ttu-id="b8270-364">R4132: Ein HTTP Content-Type-Header muss über einen Typparameter mit dem Wert `application/xop+xml` verfügen, der von doppelten Anführungszeichen umschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="b8270-364">R4132: An HTTP Content-Type header must have a type parameter with the value `application/xop+xml` enclosed in double quotation marks.</span></span>  
  
 <span data-ttu-id="b8270-365">Während die Anforderung, die doppelte Anführungszeichen verwenden, nicht in RFC 2387 explizit ist, der Text beobachtet, dass alle der mehrteiligen/verwandten medientypparameter in den meisten Fällen reservierte Zeichen wie enthalten "\@" oder "/" aus diesem Grund benötigen Sie doppelte Anführungszeichen markiert.</span><span class="sxs-lookup"><span data-stu-id="b8270-365">While the requirement to use double quotation marks is not explicit in RFC 2387, the text observes that all of the multipart/related media type parameters most likely contain reserved characters like "\@" or "/" and therefore need double quotation marks.</span></span>  
  
-   <span data-ttu-id="b8270-366">R4133: Ein HTTP Content-Type-Header sollte einen Startparameter mit dem Wert des Content-ID-Headers des MIME-Teils, der den SOAP 1.x Envelope enthält, in doppelten Anführungszeichen besitzen.</span><span class="sxs-lookup"><span data-stu-id="b8270-366">R4133: An HTTP Content-Type header should have a start parameter with the value of the Content-ID header of the MIME part that contains the SOAP 1.x Envelope, enclosed in double quotation marks.</span></span> <span data-ttu-id="b8270-367">Wenn der Startparameter weggelassen wird, muss der erste MIME-Teil den SOAP 1.x Envelope enthalten.</span><span class="sxs-lookup"><span data-stu-id="b8270-367">If the start parameter is omitted, the first MIME part must contain the SOAP 1.x Envelope.</span></span>  
  
-   <span data-ttu-id="b8270-368">R4134: Zum HTTP Content-Type-Header für eine SOAP 1.1 MTOM-codierte Nachricht muss der Startinfo-Parameter, umgeben von doppelten Anführungszeichen, mit dem Wert von text/xml gehören.</span><span class="sxs-lookup"><span data-stu-id="b8270-368">R4134: An HTTP Content-Type header for a SOAP 1.1 MTOM encoded message must include the start-info parameter with the value of text/xml, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="b8270-369">R4135: Zum HTTP Content-Type-Header für eine SOAP 1.2 MTOM-codierte Nachricht muss der Startinfo-Parameter mit dem Wert von `application/soap+xml`, umgeben von doppelten Anführungszeichen, gehören.</span><span class="sxs-lookup"><span data-stu-id="b8270-369">R4135: An HTTP Content-Type header for a SOAP 1.2 MTOM-encoded message must include the start-info parameter with the value of `application/soap+xml`, enclosed in double quotation marks.</span></span>  
  
-   <span data-ttu-id="b8270-370">R4136: Der HTTP Content-Type-Header für eine SOAP 1.x MTOM-codierte Nachricht muss den Grenzparameter mit dem Wert (umgeben von doppelten Anführungszeichen), der der MIME-Grenz-BNF entspricht, die in RFC 2046, Abschnitt 5.1.1 definiert wird, enthalten.</span><span class="sxs-lookup"><span data-stu-id="b8270-370">R4136: HTTP Content-Type header for a SOAP 1.x MTOM-encoded message must have the boundary parameter with the value (enclosed in double quotation marks) that matches the MIME boundary BNF defined in RFC 2046, section 5.1.1</span></span>  
  
    ```  
    boundary := 0*69<bchars> bcharsnospace   
    bchars := bcharsnospace / " "   
    bcharsnospace :=    DIGIT / ALPHA / "'" / "(" / ")" / "+"   
                        / "_" / "," / "-" / "." / "/" / ":" / "=" / "?"  
    ```  
  
     <span data-ttu-id="b8270-371">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="b8270-371">Examples:</span></span>  
  
     <span data-ttu-id="b8270-372">RICHTIG</span><span class="sxs-lookup"><span data-stu-id="b8270-372">CORRECT</span></span>  
  
    ```  
    Content-Type: multipart/related; type="application/xop+xml";start=" <part0@tempuri.org>";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1";start-info="text/xml"  
    ```  
  
     <span data-ttu-id="b8270-373">RICHTIG</span><span class="sxs-lookup"><span data-stu-id="b8270-373">CORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type="application/xop+xml";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"  
    ```  
  
     <span data-ttu-id="b8270-374">FALSCH</span><span class="sxs-lookup"><span data-stu-id="b8270-374">INCORRECT</span></span>  
  
    ```  
    Content-Type: Multipart/Related; type=application/xop+xml;start=" <part0@tempuri.org>";start-info="text/xml";boundary="uuid:0ca0e16e-feb1-426c-97d8-c4508ada5e82+id=1"   
    ```  
  
#### <a name="infoset-mime-part"></a><span data-ttu-id="b8270-375">Infoset-MIME-Teil</span><span class="sxs-lookup"><span data-stu-id="b8270-375">Infoset MIME Part</span></span>  
 <span data-ttu-id="b8270-376">SOAP 1.x Envelope ist als Stammteil des XOP MIME-Paket gekapselt und wird häufig der `infoset`-Teil genannt.</span><span class="sxs-lookup"><span data-stu-id="b8270-376">The SOAP 1.x Envelope is encapsulated as a root part of the XOP MIME package and is often called the `infoset` part.</span></span>  
  
-   <span data-ttu-id="b8270-377">R4141: SOAP 1.x Envelope muss als Stammteil des XOP MIME-Pakets, das als `infoset`-Teil bezeichnet wird und auf das vom HTTP Content-Type verwiesen wird, gekapselt werden.</span><span class="sxs-lookup"><span data-stu-id="b8270-377">R4141: The SOAP 1.x Envelope must be encapsulated as a root part of the XOP MIME package, called the `infoset` part and referenced from the HTTP Content-Type.</span></span>  
  
-   <span data-ttu-id="b8270-378">R4142: Der SOAP-`Infoset`-Teil muss die folgenden MIME-Köpfe einschließen: `Content-ID`, `Content-Transfer-Encoding` und `Content-Type`.</span><span class="sxs-lookup"><span data-stu-id="b8270-378">R4142: The SOAP `Infoset` part must include the following MIME headers: `Content-ID`, `Content-Transfer-Encoding`, and `Content-Type`.</span></span>  
  
 <span data-ttu-id="b8270-379">Das Format des Content-ID-Headers wird von RFC 2045 als</span><span class="sxs-lookup"><span data-stu-id="b8270-379">The format of the Content-ID header is defined by RFC 2045 as</span></span>  
  
```  
"Content-ID" ":" msg-id  
```  
  
 <span data-ttu-id="b8270-380">definiert, wobei `msg-id` in RFC 2822 (das RFC 822, auf das in RFC 2045 verwiesen wird, ablöst) als:</span><span class="sxs-lookup"><span data-stu-id="b8270-380">where `msg-id` is defined in RFC 2822 (that supersedes RFC 822, referenced in RFC 2045) as:</span></span>  
  
```  
msg-id    =       [CFWS] "<" id-left "@" id-right ">" [CFWS]  
```  
  
 <span data-ttu-id="b8270-381">eingeschlossen ist, wird tatsächlich eine e-Mail-Adresse in "\<" und ">".</span><span class="sxs-lookup"><span data-stu-id="b8270-381">and is effectively an email address enclosed within "\<" and  ">".</span></span> <span data-ttu-id="b8270-382">Das `[CFWS]`-Präfix und -Suffix wurden in RFC 2822 hinzugefügt, um Kommentare auszuführen, und sollten nicht verwendet werden, um die Kompatibilität aufrechtzuerhalten.</span><span class="sxs-lookup"><span data-stu-id="b8270-382">The `[CFWS]` prefix and suffix were added in RFC 2822 to carry comments and should not be used to preserve interoperability.</span></span>  
  
 <span data-ttu-id="b8270-383">R4143: Der Wert des Content-ID-Headers des Infoset MIME-Teils muss der Produktion `msg-id` von RFC 2822 folgen, wobei die Präfix- und Suffixteile des `[CFWS]` entfallen.</span><span class="sxs-lookup"><span data-stu-id="b8270-383">R4143: The value of the Content-ID header for the Infoset MIME part must follow `msg-id` production from RFC 2822 with the `[CFWS]` prefix and suffix parts omitted.</span></span>  
  
 <span data-ttu-id="b8270-384">Eine Anzahl von MIME-Implementierungen gelockert, Anforderungen für den Wert eingefasst "\<" und ">" auf eine e-Mail-Adresse und verwendet `absoluteURI` eingeschlossen in "\<", ">" neben der e-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="b8270-384">A number of MIME implementations relaxed requirements for the value enclosed within "\<" and ">" to be an email address and used `absoluteURI` enclosed in "\<" , ">" in addition to the email address.</span></span> <span data-ttu-id="b8270-385">Diese Version von WCF verwendet die Werte von der Content-ID MIME Headers in der Form:</span><span class="sxs-lookup"><span data-stu-id="b8270-385">This version of WCF uses values of the Content-ID MIME header of the form:</span></span>  
  
```  
Content-ID: <http://tempuri.org/0>   
```  
  
 <span data-ttu-id="b8270-386">R4144: MTOM-Prozessoren sollten Content-ID-Headerwerte akzeptieren, die der folgenden entspannten `msg-id` entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b8270-386">R4144: MTOM processors should accept Content-ID header values that match the following relaxed `msg-id`.</span></span>  
  
```  
msg-id-relaxed =     [CFWS] "<" (absoluteURI | mail-address) ">" [CFWS]  
mail-address   =     id-left "@" id-right  
```  
  
 <span data-ttu-id="b8270-387">MIME (RFC 2045) stellt den Content-Transfer-Encoding-Header bereit, um die Codierung des Inhalts des MIME-Teils zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="b8270-387">MIME (RFC 2045) provides the Content-Transfer-Encoding header to communicate encoding of the content of the MIME part.</span></span> <span data-ttu-id="b8270-388">Der für das Content-Transfer-Encoding definierte Standard ist 7-Bit; da dies für die meisten SOAP-Nachrichten nicht geeignet ist, wird der Content-Transfer-Encoding-Header für eine bessere Interoperabilität benötigt:</span><span class="sxs-lookup"><span data-stu-id="b8270-388">The default defined for Content-Transfer-Encoding is 7-bit, which is not suitable for most SOAP messages, so the Content-Transfer-Encoding header is needed for greater interoperability:</span></span>  
  
-   <span data-ttu-id="b8270-389">R4145: Der SOAP-Infosetteil muss den Content-Transfer-Encoding-Header enthalten.</span><span class="sxs-lookup"><span data-stu-id="b8270-389">R4145: The SOAP Infoset part must contain the Content-Transfer-Encoding header.</span></span>  
  
-   <span data-ttu-id="b8270-390">R4146: Wenn die SOAP-Umschlag-Zeichencodierung UTF-8 ist, muss der Wert des Content-Transfer-Encoding-Headers 8-Bit sein.</span><span class="sxs-lookup"><span data-stu-id="b8270-390">R4146: If the SOAP Envelope character encoding is UTF-8, the value of the Content-Transfer-Encoding header must be 8-bit.</span></span>  
  
-   <span data-ttu-id="b8270-391">R4147: Wenn die SOAP-Umschlag-Zeichencodierung UTF-16 ist, muss der Wert des Content-Transfer-Encoding-Headers binär sein.</span><span class="sxs-lookup"><span data-stu-id="b8270-391">R4147: If the SOAP Envelope character encoding is UTF-16, the value of the Content-Transfer-Encoding header must be binary.</span></span>  
  
-   <span data-ttu-id="b8270-392">Gemäß [XOP] Abschnitt 5,</span><span class="sxs-lookup"><span data-stu-id="b8270-392">According to [XOP] section 5,</span></span>  
  
-   <span data-ttu-id="b8270-393">R4148: Die SOAP1. 1 infosetteil muss eine enthalten Content-Type-Header mit der Media-Type Application/Xop + Xml und Parametertyp = "Text/Xml" und Charset</span><span class="sxs-lookup"><span data-stu-id="b8270-393">R4148: SOAP1.1 Infoset part must contain Content-Type header with media type application/xop+xml and parameters type="text/xml" and charset</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="text/xml"  
    ```  
  
-   <span data-ttu-id="b8270-394">R4149: Der SOAP 1.2-infosetteil muss den Content-Type-Header mit Medientyp enthalten `application/xop+xml` und Parametertyp = "`application/soap+xml`" und `charset`.</span><span class="sxs-lookup"><span data-stu-id="b8270-394">R4149: The SOAP 1.2 Infoset part must contain the Content-Type header with media type `application/xop+xml` and parameters type="`application/soap+xml`" and `charset`.</span></span>  
  
    ```  
    Content-Type: application/xop+xml;  
                  charset=utf-8;type="application/soap+xml"  
    ```  
  
     <span data-ttu-id="b8270-395">Obwohl XOP den Parameter `charset` für `application/xop+xml` als optional definiert, wird er ähnlich der BP 1.1-Anforderung an den Parameter `charset` des Medientyps `text/xml` für die Interoperabilität benötigt.</span><span class="sxs-lookup"><span data-stu-id="b8270-395">While XOP defines the `charset` parameter for `application/xop+xml` to be optional, it is needed for interoperability similar to the BP 1.1 requirement on the `charset` parameter for the `text/xml` media type.</span></span>  
  
-   <span data-ttu-id="b8270-396">R4140: Die Parameter `type` und `charset` müssen im Content-Type-Header des SOAP 1.x-Infosetteils enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="b8270-396">R41410: The `type` and `charset` parameters must be present on the Content-Type header of the SOAP 1.x Infoset part.</span></span>  
  
#### <a name="wcf-endpoint-support-for-mtom"></a><span data-ttu-id="b8270-397">WCF-Endpunkt-Unterstützung für MTOM</span><span class="sxs-lookup"><span data-stu-id="b8270-397">WCF Endpoint Support for MTOM</span></span>  
 <span data-ttu-id="b8270-398">Der Zweck von MTOM ist es, eine SOAP-Nachricht zu codieren, um base64-codierte Daten zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="b8270-398">The purpose of MTOM is to encode a SOAP message to optimize base64-encoded data.</span></span> <span data-ttu-id="b8270-399">Die folgende Liste führt Einschränkungen auf:</span><span class="sxs-lookup"><span data-stu-id="b8270-399">The following is a list of constraints:</span></span>  
  
-   <span data-ttu-id="b8270-400">R4151: Jedes Elementinformationselement, das base64-codierte Daten enthält, kann optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="b8270-400">R4151: Any element information item that contains base64-encoded data may be optimized.</span></span>  
  
-   <span data-ttu-id="b8270-401">B4152: WCF optimiert elementinformationselemente, die base64-codierte Daten enthalten und Länge 1024 Bytes nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="b8270-401">B4152: WCF optimizes element information items that contain base64-encoded data and exceed 1024 bytes in length.</span></span>  
  
 <span data-ttu-id="b8270-402">Ein WCF-Endpunkt konfiguriert werden, um MTOM zu verwenden, sendet immer MTOM-codierte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="b8270-402">A WCF endpoint configured to use MTOM will always send MTOM-encoded messages.</span></span> <span data-ttu-id="b8270-403">Selbst wenn kein Teil die erforderlichen Kriterien erfüllt, ist die Nachricht noch immer MTOM-codiert (als MIME-Paket mit einem einzelnen MIME-Teil serialisiert, der den SOAP-Umschlag enthält).</span><span class="sxs-lookup"><span data-stu-id="b8270-403">Even if no parts meet the required criteria, the message is still MTOM-encoded (serialized as a MIME package with a single MIME part containing the SOAP envelope).</span></span>  
  
### <a name="ws-policy-assertion-for-mtom"></a><span data-ttu-id="b8270-404">WS-Policy-Assertion für MTOM</span><span class="sxs-lookup"><span data-stu-id="b8270-404">WS-Policy Assertion for MTOM</span></span>  
 <span data-ttu-id="b8270-405">Die folgende Richtlinienassertion wird von WCF verwendet, um die MTOM-Verwendung durch den Endpunkt anzugeben:</span><span class="sxs-lookup"><span data-stu-id="b8270-405">WCF uses the following policy assertion to indicate MTOM usage by endpoint:</span></span>  
  
```xml  
<wsoma:OptimizedMimeSerialization ... />  
```  
  
-   <span data-ttu-id="b8270-406">R4211: Die vorangehende Richtlinienassertion verfügt über ein Endpoint Policy Subject und gibt an, dass alle Nachrichten, die an den Endpunkt gesendet und von diesem empfangen werden, durch den Einsatz von MTOM optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="b8270-406">R4211: The preceding policy assertion has an Endpoint Policy Subject and specifies that all messages sent to and received from the endpoint must be optimized using MTOM.</span></span>  
  
-   <span data-ttu-id="b8270-407">B4212: Bei der Verwendung von MTOM-Optimierung konfiguriert, ein WCF-Endpunkt Fügt eine MTOM-Richtlinienassertion, die in das entsprechende zugeordnete Richtlinie `wsdl:binding`.</span><span class="sxs-lookup"><span data-stu-id="b8270-407">B4212: When configured to use MTOM optimization, an WCF endpoint adds an MTOM Policy assertion to the policy attached to the corresponding `wsdl:binding`.</span></span>  
  
### <a name="composition-with-ws-security"></a><span data-ttu-id="b8270-408">Gestaltung mit WS-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="b8270-408">Composition with WS-Security</span></span>  
 <span data-ttu-id="b8270-409">MTOM ist ein Codierungsmechanismus, der ähnlich wie `text/xml` und binäre WCF-XML.</span><span class="sxs-lookup"><span data-stu-id="b8270-409">MTOM is an encoding mechanism that is similar to `text/xml` and WCF Binary XML.</span></span> <span data-ttu-id="b8270-410">MTOM bietet eine natürliche Zusammensetzung aus WS-Sicherheit und anderen WS-\*-Protokollen: eine über WS-Sicherheit gesicherte Nachricht kann durch den Einsatz von MTOM optimiert werden.</span><span class="sxs-lookup"><span data-stu-id="b8270-410">MTOM offers natural composition with WS-Security and other WS-\* protocols: a message secured using WS-Security can be optimized using MTOM.</span></span>  
  
### <a name="examples"></a><span data-ttu-id="b8270-411">Beispiele</span><span class="sxs-lookup"><span data-stu-id="b8270-411">Examples</span></span>  
  
#### <a name="wcf-soap-11-message-encoded-using-mtom"></a><span data-ttu-id="b8270-412">WCF-SOAP 1.1-Nachricht, mit MTOM codiert</span><span class="sxs-lookup"><span data-stu-id="b8270-412">WCF SOAP 1.1 Message Encoded Using MTOM</span></span>  
  
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
  
#### <a name="wcf-secure-soap-12-message-encoded-using-mtom"></a><span data-ttu-id="b8270-413">WCF Secure SOAP 1.2-Nachricht, mit MTOM codiert</span><span class="sxs-lookup"><span data-stu-id="b8270-413">WCF Secure SOAP 1.2 Message Encoded Using MTOM</span></span>  
 <span data-ttu-id="b8270-414">In diesem Beispiel wird eine Nachricht mit MTOM und SOAP 1.2 codiert, die mit WS-Sicherheit geschützt wird.</span><span class="sxs-lookup"><span data-stu-id="b8270-414">In this example, a message is encoded using MTOM and SOAP 1.2 that is protected using WS-Security.</span></span> <span data-ttu-id="b8270-415">Die für die Codierung identifizierten Binärteile sind die Inhalte des `BinarySecurityToken`, `CipherValue` der `EncryptedData`, die zu der verschlüsselten Signatur und dem verschlüsselten Text gehören.</span><span class="sxs-lookup"><span data-stu-id="b8270-415">The binary parts identified for encoding are the contents of the `BinarySecurityToken`, `CipherValue` of the `EncryptedData` corresponding to the encrypted signature and encrypted body.</span></span> <span data-ttu-id="b8270-416">Beachten Sie, dass die `CipherValue` von der `EncryptedKey` wurde nicht identifiziert, für die Optimierung von WCF, da seine Länge geringer als 1024 Bytes ist.</span><span class="sxs-lookup"><span data-stu-id="b8270-416">Note that the `CipherValue` of the `EncryptedKey` was not identified for optimization by WCF, because its length is less then 1024 bytes.</span></span>  
  
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
