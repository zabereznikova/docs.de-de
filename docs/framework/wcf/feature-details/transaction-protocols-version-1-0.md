---
title: Transaktionsprotokolle, Version 1.0
ms.date: 03/30/2017
ms.assetid: 034679af-0002-402e-98a8-ef73dcd71bb6
ms.openlocfilehash: 9e21da0dfdda514e60b6f53090f5225b57aa1b75
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720373"
---
# <a name="transaction-protocols-version-10"></a><span data-ttu-id="2b651-102">Transaktionsprotokolle, Version 1.0</span><span class="sxs-lookup"><span data-stu-id="2b651-102">Transaction Protocols version 1.0</span></span>
<span data-ttu-id="2b651-103">Windows Communication Foundation (WCF) Version 1 implementiert Version 1,0 der WS-Atomic Transaction-und WS-Coordination-Protokolle.</span><span class="sxs-lookup"><span data-stu-id="2b651-103">Windows Communication Foundation (WCF) version 1 implements version 1.0 of the WS-Atomic Transaction and WS-Coordination protocols.</span></span> <span data-ttu-id="2b651-104">Weitere Informationen zu Version 1,1 finden Sie unter [Transaktionsprotokolle](transaction-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="2b651-104">For more information about version 1.1, see [Transaction Protocols](transaction-protocols.md).</span></span>  
  
|<span data-ttu-id="2b651-105">Spezifikation/Dokument</span><span class="sxs-lookup"><span data-stu-id="2b651-105">Specification/Document</span></span>|<span data-ttu-id="2b651-106">Link</span><span class="sxs-lookup"><span data-stu-id="2b651-106">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="2b651-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="2b651-107">WS-Coordination</span></span>|<http://specs.xmlsoap.org/ws/2004/10/wscoor/wscoor.pdf>|  
|<span data-ttu-id="2b651-108">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="2b651-108">WS-AtomicTransaction</span></span>|<http://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf>|  
  
 <span data-ttu-id="2b651-109">Die Interoperabilität für diese Protokolle ist für zwei Ebenen erforderlich: zwischen Anwendungen und zwischen Transaktions-Managern (siehe folgende Abbildung).</span><span class="sxs-lookup"><span data-stu-id="2b651-109">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="2b651-110">In den Spezifikationen werden die Nachrichtenformate und der Nachrichtenaustausch für beide Interoperabilitätsebenen ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b651-110">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="2b651-111">Bestimmte Sicherheits- und Zuverlässigkeitsstufen sowie Codierungen gelten für einen Austausch von Anwendung zu Anwendung wie bei einem normalen Anwendungsaustausch.</span><span class="sxs-lookup"><span data-stu-id="2b651-111">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="2b651-112">Für eine erfolgreiche Interoperabilität zwischen den Transaktions-Managern ist eine Einigung auf eine bestimmte Bindung erforderlich, weil diese in der Regel nicht vom Benutzer konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="2b651-112">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="2b651-113">In diesem Thema wird die Verbindung der WS-Atomic-Transaktion (WS-AT)-Spezifikation und der Sicherheitsfunktion beschrieben. Außerdem wird die für eine Kommunikation zwischen den Transaktions-Managern verwendete sichere Bindung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b651-113">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="2b651-114">Der in diesem Dokument beschriebene Ansatz wurde erfolgreich mit anderen Implementierungen von WS-AT und WS-Coordination getestet, u.&#160;a. IBM, IONA und Sun Microsystems.</span><span class="sxs-lookup"><span data-stu-id="2b651-114">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="2b651-115">In der folgenden Abbildung wird die Interoperabilität zwischen zwei Transaktions-Managern, dem Transaktions-Manager 1 und dem Transaktions-Manager 2 und zwei Anwendungen, Anwendung 1 und Anwendung 2, veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="2b651-115">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2:</span></span>  
  
 ![Screenshot, der die Interaktion zwischen Transaktions-Managern anzeigt](./media/transaction-protocols/transaction-managers-flow.gif)  
  
 <span data-ttu-id="2b651-117">Betrachten Sie ein typisches WS-Coordination/WS-AtomicTransaction-Szenario mit einem Initiator (I) und einem Teilnehmer (P).</span><span class="sxs-lookup"><span data-stu-id="2b651-117">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="2b651-118">Sowohl Initiator als auch Teilnehmer verfügen über Transaktions-Manager (ITM und PTM).</span><span class="sxs-lookup"><span data-stu-id="2b651-118">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="2b651-119">In diesem Thema wird das Zweiphasen-Commit als 2PC bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2b651-119">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b651-120">1. "kreatecoordinationcontext"</span><span class="sxs-lookup"><span data-stu-id="2b651-120">1. CreateCoordinationContext</span></span>|<span data-ttu-id="2b651-121">12. Antwort der Anwendungs Nachricht</span><span class="sxs-lookup"><span data-stu-id="2b651-121">12. Application Message Response</span></span>|  
|<span data-ttu-id="2b651-122">2. "kreatecoordinationcontextresponse"</span><span class="sxs-lookup"><span data-stu-id="2b651-122">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="2b651-123">13. Commit (Abschluss)</span><span class="sxs-lookup"><span data-stu-id="2b651-123">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="2b651-124">3. registrieren (Abschluss)</span><span class="sxs-lookup"><span data-stu-id="2b651-124">3. Register (Completion)</span></span>|<span data-ttu-id="2b651-125">14. Prepare (2PC)</span><span class="sxs-lookup"><span data-stu-id="2b651-125">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="2b651-126">4. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="2b651-126">4. RegisterResponse</span></span>|<span data-ttu-id="2b651-127">15. vorbereiten (2PC)</span><span class="sxs-lookup"><span data-stu-id="2b651-127">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="2b651-128">5. Anwendungs Nachricht</span><span class="sxs-lookup"><span data-stu-id="2b651-128">5. Application Message</span></span>|<span data-ttu-id="2b651-129">16. vorbereitet (2PC)</span><span class="sxs-lookup"><span data-stu-id="2b651-129">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="2b651-130">6. "kreatecoordinationcontext" mit Kontext</span><span class="sxs-lookup"><span data-stu-id="2b651-130">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="2b651-131">17. vorbereitet (2PC)</span><span class="sxs-lookup"><span data-stu-id="2b651-131">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="2b651-132">7. Register (permanent)</span><span class="sxs-lookup"><span data-stu-id="2b651-132">7. Register (Durable)</span></span>|<span data-ttu-id="2b651-133">18. Commit (Abschluss)</span><span class="sxs-lookup"><span data-stu-id="2b651-133">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="2b651-134">8. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="2b651-134">8. RegisterResponse</span></span>|<span data-ttu-id="2b651-135">19. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="2b651-135">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="2b651-136">9. "kreatecoordinationcontextresponse"</span><span class="sxs-lookup"><span data-stu-id="2b651-136">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="2b651-137">20. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="2b651-137">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="2b651-138">10. Register (permanent)</span><span class="sxs-lookup"><span data-stu-id="2b651-138">10. Register (Durable)</span></span>|<span data-ttu-id="2b651-139">21. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="2b651-139">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="2b651-140">11. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="2b651-140">11. RegisterResponse</span></span>|<span data-ttu-id="2b651-141">22. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="2b651-141">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="2b651-142">In diesem Dokument wird die Verbindung der WS-AtomicTransaction (WS-AT)-Spezifikation und der Sicherheitsfunktion beschrieben. Außerdem wird die für eine Kommunikation zwischen den Transaktions-Managern verwendete sichere Bindung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b651-142">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="2b651-143">Der in diesem Dokument beschriebene Ansatz wurde erfolgreich mit anderen Implementierungen von WS-AT und WS-Coordination getestet.</span><span class="sxs-lookup"><span data-stu-id="2b651-143">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="2b651-144">In der Abbildung und in der Tabelle werden vier Nachrichtenklassen vom Standpunkt der Sicherheit dargestellt:</span><span class="sxs-lookup"><span data-stu-id="2b651-144">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
- <span data-ttu-id="2b651-145">Aktivierungsnachrichten (CreateCoordinationContext und CreateCoordinationContextResponse).</span><span class="sxs-lookup"><span data-stu-id="2b651-145">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
- <span data-ttu-id="2b651-146">Registrierungsnachrichten (Register und RegisterResponse)</span><span class="sxs-lookup"><span data-stu-id="2b651-146">Registration messages (Register and RegisterResponse)</span></span>  
  
- <span data-ttu-id="2b651-147">Protokollnachrichten (Prepare, Rollback, Commit, Aborted usw.).</span><span class="sxs-lookup"><span data-stu-id="2b651-147">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
- <span data-ttu-id="2b651-148">Anwendungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="2b651-148">Application messages.</span></span>  
  
 <span data-ttu-id="2b651-149">Die ersten drei Nachrichten werden als Transaktions-Manager-Nachrichten betrachtet, deren Bindungskonfiguration weiter unten in diesem Thema unter „Anwendungsnachrichtenaustausch“ behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="2b651-149">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="2b651-150">Bei der vierten Klasse von Nachrichten handelt es sich um Nachrichten von Anwendung zu Anwendung, die weiter unten in diesem Thema im Abschnitt "Nachrichtenbeispiele" beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="2b651-150">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="2b651-151">In diesem Abschnitt werden die Protokoll Bindungen beschrieben, die von WCF für jede dieser Klassen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b651-151">This section describes the protocol bindings used for each of these classes by WCF.</span></span>  
  
 <span data-ttu-id="2b651-152">Die folgenden XML-Namespaces und zugeordneten Präfixe werden in diesem Thema verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b651-152">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="2b651-153">Präfix</span><span class="sxs-lookup"><span data-stu-id="2b651-153">Prefix</span></span>|<span data-ttu-id="2b651-154">Namespace-URI</span><span class="sxs-lookup"><span data-stu-id="2b651-154">Namespace URI</span></span>|  
|------------|-------------------|  
|<span data-ttu-id="2b651-155">s11</span><span class="sxs-lookup"><span data-stu-id="2b651-155">s11</span></span>|`http://schemas.xmlsoap.org/soap/envelope`|  
|<span data-ttu-id="2b651-156">wsa</span><span class="sxs-lookup"><span data-stu-id="2b651-156">wsa</span></span>|`http://www.w3.org/2004/08/addressing`|  
|<span data-ttu-id="2b651-157">wscoor</span><span class="sxs-lookup"><span data-stu-id="2b651-157">wscoor</span></span>|`http://schemas.xmlsoap.org/ws/2004/10/wscoor`|  
|<span data-ttu-id="2b651-158">wsat</span><span class="sxs-lookup"><span data-stu-id="2b651-158">wsat</span></span>|`http://schemas.xmlsoap.org/ws/2004/10/wsat`|  
|<span data-ttu-id="2b651-159">t</span><span class="sxs-lookup"><span data-stu-id="2b651-159">t</span></span>|`http://schemas.xmlsoap.org/ws/2005/02/trust`|  
|<span data-ttu-id="2b651-160">o</span><span class="sxs-lookup"><span data-stu-id="2b651-160">o</span></span>|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd`|  
|<span data-ttu-id="2b651-161">xsd</span><span class="sxs-lookup"><span data-stu-id="2b651-161">xsd</span></span>|`http://www.w3.org/2001/XMLSchema`|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="2b651-162">Transaktions-Manager-Bindungen</span><span class="sxs-lookup"><span data-stu-id="2b651-162">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="2b651-163">R1001: Transaktions-Manager müssen SOAP&#160;1.1 und WS-Adressierung&#160;2004/08 für den WS-Atomic-Transaktion- und den WS-Coordination-Nachrichtenaustausch verwenden.</span><span class="sxs-lookup"><span data-stu-id="2b651-163">R1001: Transaction Managers must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="2b651-164">Anwendungsnachrichten werden nicht auf diese Bindungen eingeschränkt und werden später beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b651-164">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="2b651-165">HTTPS-Bindungen des Transaktions-Managers</span><span class="sxs-lookup"><span data-stu-id="2b651-165">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="2b651-166">Die HTTPS-Bindung des Transaktions-Managers richtet sich lediglich nach der Transportsicherheit, um Sicherheit zu gewährleisten und eine Vertrauenswürdigkeit zwischen den einzelnen Absender-Empfänger-Paaren in der Transaktionsstruktur herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2b651-166">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="2b651-167">HTTPS-Transportkonfiguration</span><span class="sxs-lookup"><span data-stu-id="2b651-167">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="2b651-168">X.509-Zertifikate werden verwendet, um eine Transaktions-Manager-Identität herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2b651-168">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="2b651-169">Die Client/Server-Authentifizierung ist erforderlich, und die Client/Server-Autorisierung wird als Implementierungsdetail beibehalten:</span><span class="sxs-lookup"><span data-stu-id="2b651-169">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
- <span data-ttu-id="2b651-170">R1111: Über die Verbindung vorgestellte X.509-Zertifikate müssen einen Antragstellernamen aufweisen, der dem vollqualifizierten Domänennamen (FQDN) des sendenden Computers entspricht.</span><span class="sxs-lookup"><span data-stu-id="2b651-170">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
- <span data-ttu-id="2b651-171">B1112: DNS muss zwischen den einzelnen Absender-Empfänger-Paaren im System funktionieren, damit eine Prüfung der X.509-Antragstellernamen erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="2b651-171">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="2b651-172">Bindungskonfiguration von Aktivierung und Registrierung</span><span class="sxs-lookup"><span data-stu-id="2b651-172">Activation and Registration Binding Configuration</span></span>  
 <span data-ttu-id="2b651-173">WCF erfordert eine Anforderungs-/Antwort-Duplex Bindung mit Korrelation über HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2b651-173">WCF requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="2b651-174">(Weitere Informationen über Korrelation und Beschreibungen der Anforderungs-/Antwortnachrichten-Austauschmuster finden Sie unter WS-AtomicTransaction, Abschnitt 8.)</span><span class="sxs-lookup"><span data-stu-id="2b651-174">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="2b651-175">Bindungskonfiguration des 2PC-Protokolls</span><span class="sxs-lookup"><span data-stu-id="2b651-175">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="2b651-176">WCF unterstützt unidirektionale (Datagramm) Nachrichten über HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2b651-176">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="2b651-177">Korrelation unter den Nachrichten wird als Implementierungsdetail beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2b651-177">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="2b651-178">B2131: Implementierungen müssen unterstützen `wsa:ReferenceParameters` , wie in WS-Adressierung beschrieben, um eine Korrelation der 2PC-Nachrichten von WCF zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="2b651-178">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="2b651-179">Gemischte Sicherheitsbindung des Transaktions-Managers</span><span class="sxs-lookup"><span data-stu-id="2b651-179">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="2b651-180">Dabei handelt es sich um eine alternative Bindung (gemischter Modus), die Transportsicherheit in Kombination mit dem von der WS-Koordination ausgestellten tokenmodell zur Identitäts Einrichtung verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b651-180">This is an alternate (mixed mode) binding that uses transport security combined with the  WS-Coordination Issued Token model for identity establishment purposes.</span></span>  <span data-ttu-id="2b651-181">Aktivierung und Registrierung sind die einzigen Elemente, die sich zwischen den beiden Bindungen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="2b651-181">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="2b651-182">HTTPS-Transportkonfiguration</span><span class="sxs-lookup"><span data-stu-id="2b651-182">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="2b651-183">X.509-Zertifikate werden verwendet, um eine Transaktions-Manager-Identität herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2b651-183">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="2b651-184">Die Client/Server-Authentifizierung ist erforderlich, und die Client/Server-Autorisierung wird als Implementierungsdetail beibehalten:</span><span class="sxs-lookup"><span data-stu-id="2b651-184">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="2b651-185">Bindungskonfiguration von Aktivierungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="2b651-185">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="2b651-186">Aktivierungsnachrichten nehmen in der Regel nicht an der Interoperabilität teil, da sie normalerweise zwischen einer Anwendung und dem lokalen Transaktions-Manager auftreten.</span><span class="sxs-lookup"><span data-stu-id="2b651-186">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="2b651-187">B1221: WCF verwendet die Duplex-HTTPS-Bindung (beschrieben in [Messaging Protokollen](messaging-protocols.md)) für Aktivierungs Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="2b651-187">B1221: WCF uses duplex HTTPS binding (described in [Messaging Protocols](messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="2b651-188">Anforderungs- und Antwortnachrichten werden mithilfe von WS-Addressing&#160;2004/08 korreliert.</span><span class="sxs-lookup"><span data-stu-id="2b651-188">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="2b651-189">In der WS-Atomic Transaktion-Spezifikation, Abschnitt 8, werden die Korrelation und die Nachrichtenaustauschmuster ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b651-189">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
- <span data-ttu-id="2b651-190">R1222: Beim Eingang eines `CreateCoordinationContext` muss der Koordinator ein `SecurityContextToken` mit zugewiesenem geheimen `STx` ausgeben.</span><span class="sxs-lookup"><span data-stu-id="2b651-190">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="2b651-191">Dieses Token wird entsprechend der WS-Trust-Spezifikation in einem `t:IssuedTokens`-Header zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b651-191">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
- <span data-ttu-id="2b651-192">R1223: Falls die Aktivierung innerhalb eines bereits vorhandenen Koordinationskontexts stattfindet, muss der `t:IssuedTokens`-Header, bei dem `SecurityContextToken` dem bereits vorhandenem Kontext zugewiesen ist, in der `CreateCoordinationContext`-Nachricht fließen.</span><span class="sxs-lookup"><span data-stu-id="2b651-192">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="2b651-193">Ein neuer `t:IssuedTokens` Header sollte zum Anfügen an die ausgehende `wscoor:CreateCoordinationContextResponse` Nachricht generiert werden.</span><span class="sxs-lookup"><span data-stu-id="2b651-193">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="2b651-194">Bindungskonfiguration von Registrierungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="2b651-194">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="2b651-195">B1231: WCF verwendet Duplex-HTTPS-Bindung (beschrieben in [Messaging Protokollen](messaging-protocols.md)).</span><span class="sxs-lookup"><span data-stu-id="2b651-195">B1231: WCF uses duplex HTTPS binding (described in [Messaging Protocols](messaging-protocols.md)).</span></span> <span data-ttu-id="2b651-196">Anforderungs- und Antwortnachrichten werden mithilfe von WS-Addressing&#160;2004/08 korreliert.</span><span class="sxs-lookup"><span data-stu-id="2b651-196">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="2b651-197">In der WS-AtomicTransaction-Spezifikation, Abschnitt 8, werden weitere Details zur Korrelation und die Nachrichtenaustauschmuster ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b651-197">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="2b651-198">R1232: für ausgehende `wscoor:Register` Nachrichten muss der `IssuedTokenOverTransport` in [Sicherheitsprotokollen](security-protocols.md)beschriebene Authentifizierungsmodus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b651-198">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](security-protocols.md).</span></span>  
  
 <span data-ttu-id="2b651-199">Das- `wsse:Timestamp` Element muss mithilfe der ausgestellten signiert werden `SecurityContextToken STx` .</span><span class="sxs-lookup"><span data-stu-id="2b651-199">The `wsse:Timestamp` element must be signed using the `SecurityContextToken STx` issued.</span></span> <span data-ttu-id="2b651-200">Diese Signatur ist Beweis für den Besitz des einer bestimmten Transaktion zugewiesenen Tokens und wird für die Authentifizierung einer Teilnehmerliste während der Transaktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b651-200">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="2b651-201">Die RegistrationResponse-Nachricht wird über HTTPS zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="2b651-201">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="2b651-202">Bindungskonfiguration des 2PC-Protokolls</span><span class="sxs-lookup"><span data-stu-id="2b651-202">2PC Protocol Binding Configuration</span></span>  
 <span data-ttu-id="2b651-203">WCF unterstützt unidirektionale (Datagramm) Nachrichten über HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2b651-203">WCF supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="2b651-204">Korrelation unter den Nachrichten wird als Implementierungsdetail beibehalten.</span><span class="sxs-lookup"><span data-stu-id="2b651-204">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="2b651-205">B2131: Implementierungen müssen unterstützen `wsa:ReferenceParameters` , wie in WS-Adressierung beschrieben, um eine Korrelation der 2PC-Nachrichten von WCF zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="2b651-205">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of WCF’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="2b651-206">Austausch von Anwendungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="2b651-206">Application Message Exchange</span></span>  
 <span data-ttu-id="2b651-207">In Anwendungen können beliebige Bindungen für Nachrichten verwendet werden, die von Anwendung zu Anwendung gesendet werden, solange die Bindung die folgenden Sicherheitsanforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="2b651-207">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
- <span data-ttu-id="2b651-208">R2001: Nachrichten von Anwendung zu Anwendung müssen im Nachrichtenheader den `t:IssuedTokens`-Header zusammen mit `CoordinationContext` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2b651-208">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
- <span data-ttu-id="2b651-209">R2002: Integrität und Vertraulichkeit von `t:IssuedToken` müssen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2b651-209">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="2b651-210">Der `CoordinationContext`-Header enthält `wscoor:Identifier`.</span><span class="sxs-lookup"><span data-stu-id="2b651-210">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="2b651-211">Die Definition von `xsd:AnyURI` ermöglicht die Verwendung von absoluten und relativen URIs. WCF unterstützt jedoch nur `wscoor:Identifiers` , bei denen es sich um absolute URIs handelt.</span><span class="sxs-lookup"><span data-stu-id="2b651-211">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, WCF supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="2b651-212">Wenn die `wscoor:Identifier` von `wscoor:CoordinationContext` ein relativer URI ist, werden Fehler von transaktionalen WCF-Diensten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b651-212">If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional WCF services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="2b651-213">Nachrichtenbeispiele</span><span class="sxs-lookup"><span data-stu-id="2b651-213">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="2b651-214">CreateCoordinationContext-Anforderungs-/Antwortmeldungen</span><span class="sxs-lookup"><span data-stu-id="2b651-214">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="2b651-215">Die folgenden Nachrichten folgen einem Anforderungs-/Antwortmuster.</span><span class="sxs-lookup"><span data-stu-id="2b651-215">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext"></a><span data-ttu-id="2b651-216">CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="2b651-216">CreateCoordinationContext</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wscoor/CreateCoordinationContext</Action>  
    <a:MessageID>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</MessageID>  
    <a:ReplyTo>  
      <Address>https://...</a:Address>  
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security>  
      <u:Timestamp>  
        <wsu:Created>2005-12-15T23:36:09.921Z</wsu:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</wsu:Expires>  
      </u:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:CreateCoordinationContext>  
      <wscoor:CoordinationType>...</wscoor:CoordinationType>  
    </wscoor:CreateCoordinationContext>  
  </s:Body>  
</s11:Envelope>  
```  
  
#### <a name="createcoordinationcontextresponse"></a><span data-ttu-id="2b651-217">CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="2b651-217">CreateCoordinationContextResponse</span></span>  
  
```xml  
<s:Envelope>  
  <!-- Data below is shown in the clear for  
       illustration purposes only. -->  
  <s:Header>  
    <a:Action>./ws/2004/10/wscoor/CreateCoordinationContextResponse </a:Action>  
    <a:RelatesTo>urn:uuid:069f5104-fd88-4264-9f99-60032a82854e</a:RelatesTo>  
    <a:To s:mustUnderstand="1">https://... </a:To>  
    <t:IssuedTokens>  
 <wst:RequestSecurityTokenResponse
    xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
    xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd"
    xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"  
    xmlns:wsc="http://schemas.xmlsoap.org/ws/2005/02/sc"  
    xmlns:wsp="http://schemas.xmlsoap.org/ws/2004/09/policy">  
    <wst:TokenType>http://schemas.xmlsoap.org/ws/2005/02/sc/sct</wst:TokenType>  
    <wst:RequestedSecurityToken>  
      <wsc:SecurityContextToken>  
        <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
        </wssu:Identifier>  
      </wsc:SecurityContextToken>
    </wst:RequestedSecurityToken>  
    <wsp:AppliesTo>  
        http://fabrikam123.com/CCi  
    </wsp:AppliesTo>
    <wst:RequestedAttachedReference>  
      <wsse:SecurityTokenReference >  
        <wsse:Reference
           ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
           URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedAttachedReference>  
    <wst:RequestedUnattachedReference>  
      <wsse:SecurityTokenReference>  
        <wsse:Reference
          ValueType="http://schemas.xmlsoap.org/ws/2005/02/sc/sct"  
          URI="http://fabrikam123.com/SCTi"/>  
      </wsse:SecurityTokenReference>  
    </wst:RequestedUnattachedReference>  
    <wst:RequestedProofToken>  
      <wst:BinarySecret
        Type="http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey">  
        <!-- base64 encoded value -->  
      </wst:BinarySecret>  
    </wst:RequestedProofToken>  
    <wst:Lifetime>  
      <wssu:Created>2005-10-24T20:19:26.526Z</wssu:Created>  
      <wssu:Expires>2005-10-25T06:24:26.526Z</wssu:Expires>  
    </wst:Lifetime>  
    <wst:KeySize>256</wst:KeySize>  
</wst:RequestSecurityTokenResponse>  
    </t:IssuedTokens>  
    <o:Security xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
      <u:Timestamp u:Id="_0">  
        <u:Created>2005-12-15T23:36:12.015Z</u:Created>  
        <u:Expires>2005-12-15T23:41:12.015Z</u:Expires>  
      </u:Timestamp>  
    </o:Security>  
  </s:Header>  
  <s:Body>  
    <wscoor:CreateCoordinationContextResponse>  
      <wscoor:CoordinationContext>  
        <wscoor:Identifier>  
     http://fabrikam123.com/CCi  
      </wscoor:Identifier>  
        <wscoor:Expires>...</wscoor:Expires>  
        <wscoor:CoordinationType>...</wscoor:CoordinationType>  
        <wscoor:RegistrationService>  
          <a:Address>https://...</a:Address>  
          <a:ReferenceParameters>  
             ...  
          </a:ReferenceParameters>  
        </wscoor:RegistrationService>  
      </wscoor:CoordinationContext>  
    </wscoor:CreateCoordinationContextResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="registration-messages"></a><span data-ttu-id="2b651-218">Registrierungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="2b651-218">Registration Messages</span></span>  
 <span data-ttu-id="2b651-219">Bei den folgenden Nachrichten handelt es sich um Registrierungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="2b651-219">The following messages are registration messages.</span></span>  
  
#### <a name="register"></a><span data-ttu-id="2b651-220">Registrieren</span><span class="sxs-lookup"><span data-stu-id="2b651-220">Register</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://schemas.xmlsoap.org/ws/2004/10/wscoor/Register</a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e</a:MessageID>  
    <a:ReplyTo>  
      <a:Address>https://...</a:Address>
    </a:ReplyTo>  
    <a:To>https://...</a:To>  
    <wsse:Security
      s:mustUnderstand="1"
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsc:SecurityContextToken>  
      <wssu:Identifier>  
          http://fabrikam123.com/SCTi  
      </wssu:Identifier>  
      </wsc:SecurityContextToken>  
      <!-- supporting signature over the timestamp -->  
      <wsse:Signature xmlns:ds="http://www.w3.org/2000/09/xmldsig#">  
        <ds:SignedInfo>  
          <ds:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
          <ds:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#hmac-sha1"/>  
          <ds:Reference URI="#_0">  
            <ds:Transforms>  
              <ds:Transform Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>  
            </ds:Transforms>  
            <ds:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>  
            <ds:DigestValue>  
              alRzyhjLgoUOYoh8cx4n75eTcUk=  
            </ds:DigestValue>  
          </ds:Reference>  
        </ds:SignedInfo>  
        <ds:SignatureValue>YZYjnVvSOVasAQqQxaaviTSWtqI=</ds:SignatureValue>  
        <ds:KeyInfo>  
          <wsse:SecurityTokenReference  
            xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd">  
            <wsse:Reference
              URI="http://fabrikam123.com/SCTi"/>  
          </wsse:SecurityTokenReference>  
        </ds:KeyInfo>  
      </wsse:Signature>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:Register>  
      <wscoor:ProtocolIdentifier>...</wscoor:ProtocolIdentifier>  
      <wscoor:ParticipantProtocolService>  
        <a:Address>https://... </a:Address>  
      </wscoor:ParticipantProtocolService>  
    </wscoor:Register>  
  </s:Body>  
</s:Envelope>  
```  
  
#### <a name="register-response"></a><span data-ttu-id="2b651-221">Register Response</span><span class="sxs-lookup"><span data-stu-id="2b651-221">Register Response</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>  
      http://schemas.xmlsoap.org/ws/2004/10/wscoor/RegisterResponse  
    </a:Action>  
    <a:MessageID>urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088d</a:MessageID>  
    <a:RelatesTo>  
      urn:uuid:ed418b86-a75e-4aea-9d4e-a5d0cb5c088e
    </a:RelatesTo>  
    <a:To>https://...</a:To>  
    <wsse:Security
      s:mustUnderstand="1"
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp>  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
    </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wscoor:RegisterResponse>  
      <wscoor:CoordinatorProtocolService>  
        <a:Address>https://...</a:Address>  
        <a:ReferenceParameters>  
          ...  
        </a:ReferenceParameters>  
      </wscoor:CoordinatorProtocolService>  
    </wscoor:RegisterResponse>  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="2b651-222">Zweiphasen-Commit-Protokollnachrichten</span><span class="sxs-lookup"><span data-stu-id="2b651-222">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="2b651-223">Die folgende Nachricht bezieht sich auf das Zweiphasen-Commit-Protokoll (2PC).</span><span class="sxs-lookup"><span data-stu-id="2b651-223">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit"></a><span data-ttu-id="2b651-224">Commit</span><span class="sxs-lookup"><span data-stu-id="2b651-224">Commit</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
    <a:Action>http://.../ws/2004/10/wsat/Commit</a:Action>  
    <a:To>https://...</a:To>  
    <wsse:Security
      s:mustUnderstand="1"
      xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"  
      xmlns:wssu="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd">  
      <wssu:Timestamp wssu:Id="_0" >  
        <wssu:Created>2005-12-15T23:36:13.827Z</wssu:Created>  
        <wssu:Expires>2005-12-15T23:41:13.827Z</wssu:Expires>  
      </wssu:Timestamp>  
   </wsse:Security>  
  </s:Header>  
  <s:Body xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">  
    <wsat:Commit />  
  </s:Body>  
</s:Envelope>  
```  
  
### <a name="application-messages"></a><span data-ttu-id="2b651-225">Anwendungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="2b651-225">Application Messages</span></span>  
 <span data-ttu-id="2b651-226">Bei den folgenden Nachrichten handelt es sich um Anwendungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="2b651-226">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="2b651-227">Anwendungsnachrichtenanforderung</span><span class="sxs-lookup"><span data-stu-id="2b651-227">Application message-Request</span></span>  
  
```xml  
<s:Envelope>  
  <s:Header>  
<!-- Addressing headers, all signed-->  
    <wsse:Security s:mustUnderstand="1">  
      <wssu:Timestamp wssu:Id="timestamp">
        <wssu:Created>2005-10-25T06:29:18.703Z</wssu:Created>  
        <wssu:Expires>2005-10-25T06:34:18.703Z</wssu:Expires>  
      </wssu:Timestamp>  
      <wsse:BinarySecurityToken
          wssu:Id="IA_Certificate"
          ValueType="...#X509v3"
          EncodingType="...#Base64Binary">  
        <!-- IA certificate -->  
      </wsse:BinarySecurityToken>  
      <e:EncryptedKey Id="encrypted_key">  
            <!-- ephemeral key encrypted for PA certificate -->
        <e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
          <e:DataReference URI="#encrypted_body"/>  
          <e:DataReference URI="#encrypted_CCi"/>  
          <e:DataReference URI="#encrypted_issuedtokens"/>  
        </e:ReferenceList>  
      </e:EncryptedKey>  
      <Signature xmlns="http://www.w3.org/2000/09/xmldsig#">  
        <!-- signature over Addressing headers, Timestamp, and Body -->  
      </Signature>  
    </wsse:Security>  
    <wsse11:EncryptedHeader>  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader>
      <!-- encrypted wst:IssuedTokens header containing SCTi -->  
      <!-- wst:IssuedTokens header is taken verbatim from message #2 above, omitted for brevity -->  
    </wsse11:EncryptedHeader>  
  </s:Header>  
  <s:Body wssu:Id="body">  
    <!-- encrypted content of the Body element of the application message -->
    <e:EncryptedData Id="encrypted_body"
           Type="http://www.w3.org/2001/04/xmlenc#Content"
           xmlns:e="http://www.w3.org/2001/04/xmlenc#">  
...  
    </e:EncryptedData>  
  </s:Body>  
</s:Envelope>  
```
