---
title: Transaktionsprotokolle, Version 1.0
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 034679af-0002-402e-98a8-ef73dcd71bb6
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 544e505dd182d331179d9a6d3da4815b849fdd95
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="transaction-protocols-version-10"></a><span data-ttu-id="d331c-102">Transaktionsprotokolle, Version 1.0</span><span class="sxs-lookup"><span data-stu-id="d331c-102">Transaction Protocols version 1.0</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="d331c-103"> Version 1 implementiert Version 1.0 der Protokolle WS-Atomic Transaction und WS-Coordination.</span><span class="sxs-lookup"><span data-stu-id="d331c-103"> version 1 implements version 1.0 of the WS-Atomic Transaction and WS-Coordination protocols.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="d331c-104">Version 1.1, finden Sie unter [Transaktionsprotokolle](../../../../docs/framework/wcf/feature-details/transaction-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="d331c-104"> version 1.1, see [Transaction Protocols](../../../../docs/framework/wcf/feature-details/transaction-protocols.md).</span></span>  
  
|<span data-ttu-id="d331c-105">Spezifikation/Dokument</span><span class="sxs-lookup"><span data-stu-id="d331c-105">Specification/Document</span></span>|<span data-ttu-id="d331c-106">Link</span><span class="sxs-lookup"><span data-stu-id="d331c-106">Link</span></span>|  
|-----------------------------|----------|  
|<span data-ttu-id="d331c-107">WS-Coordination</span><span class="sxs-lookup"><span data-stu-id="d331c-107">WS-Coordination</span></span>|<span data-ttu-id="d331c-108">http://msdn.microsoft.com/ws/2005/08/ws-coordination/</span><span class="sxs-lookup"><span data-stu-id="d331c-108">http://msdn.microsoft.com/ws/2005/08/ws-coordination/</span></span>|  
|<span data-ttu-id="d331c-109">WS-AtomicTransaction</span><span class="sxs-lookup"><span data-stu-id="d331c-109">WS-AtomicTransaction</span></span>|<span data-ttu-id="d331c-110">http://msdn.microsoft.com/ws/2005/08/ws-atomictransaction/</span><span class="sxs-lookup"><span data-stu-id="d331c-110">http://msdn.microsoft.com/ws/2005/08/ws-atomictransaction/</span></span>|  
  
 <span data-ttu-id="d331c-111">Die Interoperabilität für diese Protokolle ist für zwei Ebenen erforderlich: zwischen Anwendungen und zwischen Transaktions-Managern (siehe folgende Abbildung).</span><span class="sxs-lookup"><span data-stu-id="d331c-111">Interoperability on these protocol specifications is required at two levels: between applications and between transaction managers (see the following figure).</span></span> <span data-ttu-id="d331c-112">In den Spezifikationen werden die Nachrichtenformate und der Nachrichtenaustausch für beide Interoperabilitätsebenen ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d331c-112">Specifications describe in great detail the message formats and message exchange for both interoperability levels.</span></span> <span data-ttu-id="d331c-113">Bestimmte Sicherheits- und Zuverlässigkeitsstufen sowie Codierungen gelten für einen Austausch von Anwendung zu Anwendung wie bei einem normalen Anwendungsaustausch.</span><span class="sxs-lookup"><span data-stu-id="d331c-113">Certain security, reliability, and encodings for application-to-application exchange apply as they do for regular application exchange.</span></span> <span data-ttu-id="d331c-114">Für eine erfolgreiche Interoperabilität zwischen den Transaktions-Managern ist eine Einigung auf eine bestimmte Bindung erforderlich, weil diese in der Regel nicht vom Benutzer konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="d331c-114">However, successful interoperability between transaction managers requires agreement on the particular binding, because it is usually not configured by the user.</span></span>  
  
 <span data-ttu-id="d331c-115">In diesem Thema wird die Verbindung der WS-AtomicTransaction (WS-AT)-Spezifikation und der Sicherheitsfunktion beschrieben. Außerdem wird die für eine Kommunikation zwischen den Transaktions-Managern verwendete sichere Bindung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d331c-115">This topic describes a composition of the WS-Atomic Transaction (WS-AT) specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="d331c-116">Der in diesem Dokument beschriebene Ansatz wurde erfolgreich mit anderen Implementierungen von WS-AT und WS-Coordination getestet, u.&#160;a. IBM, IONA und Sun Microsystems.</span><span class="sxs-lookup"><span data-stu-id="d331c-116">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination including IBM, IONA, Sun Microsystems, and others.</span></span>  
  
 <span data-ttu-id="d331c-117">In der folgenden Abbildung wird die Interoperabilität zwischen zwei Transaktions-Managern beschrieben, Transaktions-Manager 1 und Transaktions-Manager 2, sowie zwischen zwei Anwendungen, Anwendung 1 und Anwendung 2.</span><span class="sxs-lookup"><span data-stu-id="d331c-117">The following figure depicts the interoperability between two transaction managers, Transaction Manager 1 and Transaction Manager 2, and two applications, Application 1 and Application 2.</span></span>  
  
 <span data-ttu-id="d331c-118">![Transaktionsprotokolle](../../../../docs/framework/wcf/feature-details/media/transactionmanagers.gif "Transaktionsergebnis")</span><span class="sxs-lookup"><span data-stu-id="d331c-118">![Transaction Protocols](../../../../docs/framework/wcf/feature-details/media/transactionmanagers.gif "TransactionManagers")</span></span>  
  
 <span data-ttu-id="d331c-119">Betrachten Sie ein typisches WS-Coordination/WS-Atomic-Transaktionsszenario mit einem Initiator (I) und einem Teilnehmer (P).</span><span class="sxs-lookup"><span data-stu-id="d331c-119">Consider a typical WS-Coordination/WS-Atomic Transaction scenario with one Initiator (I) and one Participant (P).</span></span> <span data-ttu-id="d331c-120">Sowohl Initiator als auch Teilnehmer verfügen über Transaktions-Manager (ITM und PTM).</span><span class="sxs-lookup"><span data-stu-id="d331c-120">Both Initiator and Participant have Transaction Managers, (ITM and PTM, respectively).</span></span> <span data-ttu-id="d331c-121">In diesem Thema wird das Zweiphasen-Commit als 2PC bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="d331c-121">Two-phase commit is referred to as 2PC in this topic.</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d331c-122">1. CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="d331c-122">1. CreateCoordinationContext</span></span>|<span data-ttu-id="d331c-123">12. Anwendungsnachrichtenantwort</span><span class="sxs-lookup"><span data-stu-id="d331c-123">12. Application Message Response</span></span>|  
|<span data-ttu-id="d331c-124">2. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="d331c-124">2. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="d331c-125">13. Commit (Abschluss)</span><span class="sxs-lookup"><span data-stu-id="d331c-125">13. Commit (Completion)</span></span>|  
|<span data-ttu-id="d331c-126">3. Register (Abschluss)</span><span class="sxs-lookup"><span data-stu-id="d331c-126">3. Register (Completion)</span></span>|<span data-ttu-id="d331c-127">14. Prepare (2PC)</span><span class="sxs-lookup"><span data-stu-id="d331c-127">14. Prepare (2PC)</span></span>|  
|<span data-ttu-id="d331c-128">4. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="d331c-128">4. RegisterResponse</span></span>|<span data-ttu-id="d331c-129">15. Prepare (2PC)</span><span class="sxs-lookup"><span data-stu-id="d331c-129">15. Prepare (2PC)</span></span>|  
|<span data-ttu-id="d331c-130">5. Anwendungsnachricht</span><span class="sxs-lookup"><span data-stu-id="d331c-130">5. Application Message</span></span>|<span data-ttu-id="d331c-131">16. Prepared (2PC)</span><span class="sxs-lookup"><span data-stu-id="d331c-131">16. Prepared (2PC)</span></span>|  
|<span data-ttu-id="d331c-132">6. CreateCoordinationContext mit Kontext</span><span class="sxs-lookup"><span data-stu-id="d331c-132">6. CreateCoordinationContext with Context</span></span>|<span data-ttu-id="d331c-133">17. Prepared (2PC)</span><span class="sxs-lookup"><span data-stu-id="d331c-133">17. Prepared (2PC)</span></span>|  
|<span data-ttu-id="d331c-134">7. Register (Durable)</span><span class="sxs-lookup"><span data-stu-id="d331c-134">7. Register (Durable)</span></span>|<span data-ttu-id="d331c-135">18. Commit ausgeführt (Abschluss)</span><span class="sxs-lookup"><span data-stu-id="d331c-135">18. Committed (Completion)</span></span>|  
|<span data-ttu-id="d331c-136">8. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="d331c-136">8. RegisterResponse</span></span>|<span data-ttu-id="d331c-137">19. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="d331c-137">19. Commit (2PC)</span></span>|  
|<span data-ttu-id="d331c-138">9. CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="d331c-138">9. CreateCoordinationContextResponse</span></span>|<span data-ttu-id="d331c-139">20. Commit (2PC)</span><span class="sxs-lookup"><span data-stu-id="d331c-139">20. Commit (2PC)</span></span>|  
|<span data-ttu-id="d331c-140">10. Register (Durable)</span><span class="sxs-lookup"><span data-stu-id="d331c-140">10. Register (Durable)</span></span>|<span data-ttu-id="d331c-141">21. Commit ausgeführt (2PC)</span><span class="sxs-lookup"><span data-stu-id="d331c-141">21. Committed (2PC)</span></span>|  
|<span data-ttu-id="d331c-142">11. RegisterResponse</span><span class="sxs-lookup"><span data-stu-id="d331c-142">11. RegisterResponse</span></span>|<span data-ttu-id="d331c-143">22. Commit ausgeführt (2PC)</span><span class="sxs-lookup"><span data-stu-id="d331c-143">22. Committed (2PC)</span></span>|  
  
 <span data-ttu-id="d331c-144">In diesem Dokument wird die Verbindung der WS-AtomicTransaction (WS-AT)-Spezifikation und der Sicherheitsfunktion beschrieben. Außerdem wird die für eine Kommunikation zwischen den Transaktions-Managern verwendete sichere Bindung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d331c-144">This document describes a composition of the WS-AtomicTransaction specification with security and describes the secure binding used for communication between transaction managers.</span></span> <span data-ttu-id="d331c-145">Der in diesem Dokument beschriebene Ansatz wurde erfolgreich mit anderen Implementierungen von WS-AT und WS-Coordination getestet.</span><span class="sxs-lookup"><span data-stu-id="d331c-145">The approach described in this document has been successfully tested with other implementations of WS-AT and WS-Coordination.</span></span>  
  
 <span data-ttu-id="d331c-146">In der Abbildung und in der Tabelle werden vier Nachrichtenklassen vom Standpunkt der Sicherheit dargestellt:</span><span class="sxs-lookup"><span data-stu-id="d331c-146">The figure and table illustrate four classes of messages from the viewpoint of security:</span></span>  
  
-   <span data-ttu-id="d331c-147">Aktivierungsnachrichten (CreateCoordinationContext und CreateCoordinationContextResponse).</span><span class="sxs-lookup"><span data-stu-id="d331c-147">Activation messages (CreateCoordinationContext and CreateCoordinationContextResponse).</span></span>  
  
-   <span data-ttu-id="d331c-148">Registrierungsnachrichten (Register und RegisterResponse)</span><span class="sxs-lookup"><span data-stu-id="d331c-148">Registration messages (Register and RegisterResponse)</span></span>  
  
-   <span data-ttu-id="d331c-149">Protokollnachrichten (Prepare, Rollback, Commit, Aborted usw.).</span><span class="sxs-lookup"><span data-stu-id="d331c-149">Protocol messages (Prepare, Rollback, Commit, Aborted, and so on).</span></span>  
  
-   <span data-ttu-id="d331c-150">Anwendungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="d331c-150">Application messages.</span></span>  
  
 <span data-ttu-id="d331c-151">Die ersten drei Nachrichten werden als Transaktions-Manager-Nachrichten betrachtet, deren Bindungskonfiguration weiter unten in diesem Thema unter "Anwendungsnachrichtenaustausch" behandelt wird.</span><span class="sxs-lookup"><span data-stu-id="d331c-151">The first three message classes are considered Transaction Manager messages and their binding configuration is described in the "Application Message Exchange" later in this topic.</span></span> <span data-ttu-id="d331c-152">Bei der vierten Klasse von Nachrichten handelt es sich um Nachrichten von Anwendung zu Anwendung, die weiter unten in diesem Thema im Abschnitt "Nachrichtenbeispiele" beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d331c-152">The fourth class of message is application to application messages and is described in the "Message Examples" section later in this topic.</span></span> <span data-ttu-id="d331c-153">In diesem Abschnitt werden die für jede dieser Klassen von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendeten Protokollbindungen beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d331c-153">This section describes the protocol bindings used for each of these classes by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 <span data-ttu-id="d331c-154">Die folgenden XML-Namespaces und zugeordneten Präfixe werden in diesem Thema verwendet.</span><span class="sxs-lookup"><span data-stu-id="d331c-154">The following XML Namespaces and associated prefixes are used throughout this document.</span></span>  
  
|<span data-ttu-id="d331c-155">Präfix</span><span class="sxs-lookup"><span data-stu-id="d331c-155">Prefix</span></span>|<span data-ttu-id="d331c-156">Namespace-URI</span><span class="sxs-lookup"><span data-stu-id="d331c-156">Namespace URI</span></span>|  
|------------|-------------------|  
|<span data-ttu-id="d331c-157">s11</span><span class="sxs-lookup"><span data-stu-id="d331c-157">s11</span></span>|<span data-ttu-id="d331c-158">http://schemas.xmlsoap.org/soap/envelope (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="d331c-158">http://schemas.xmlsoap.org/soap/envelope</span></span>|  
|<span data-ttu-id="d331c-159">wsa</span><span class="sxs-lookup"><span data-stu-id="d331c-159">wsa</span></span>|<span data-ttu-id="d331c-160">http://www.w3.org/2004/08/Addressing</span><span class="sxs-lookup"><span data-stu-id="d331c-160">http://www.w3.org/2004/08/addressing</span></span>|  
|<span data-ttu-id="d331c-161">wscoor</span><span class="sxs-lookup"><span data-stu-id="d331c-161">wscoor</span></span>|<span data-ttu-id="d331c-162">http://schemas.xmlsoap.org/ws/2004/10/wscoor</span><span class="sxs-lookup"><span data-stu-id="d331c-162">http://schemas.xmlsoap.org/ws/2004/10/wscoor</span></span>|  
|<span data-ttu-id="d331c-163">wsat</span><span class="sxs-lookup"><span data-stu-id="d331c-163">wsat</span></span>|<span data-ttu-id="d331c-164">http://schemas.xmlsoap.org/ws/2004/10/wsat</span><span class="sxs-lookup"><span data-stu-id="d331c-164">http://schemas.xmlsoap.org/ws/2004/10/wsat</span></span>|  
|<span data-ttu-id="d331c-165">t</span><span class="sxs-lookup"><span data-stu-id="d331c-165">t</span></span>|<span data-ttu-id="d331c-166">http://schemas.xmlsoap.org/ws/2005/02/trust</span><span class="sxs-lookup"><span data-stu-id="d331c-166">http://schemas.xmlsoap.org/ws/2005/02/trust</span></span>|  
|<span data-ttu-id="d331c-167">o</span><span class="sxs-lookup"><span data-stu-id="d331c-167">o</span></span>|<span data-ttu-id="d331c-168">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd</span><span class="sxs-lookup"><span data-stu-id="d331c-168">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd</span></span>|  
|<span data-ttu-id="d331c-169">xsd</span><span class="sxs-lookup"><span data-stu-id="d331c-169">xsd</span></span>|<span data-ttu-id="d331c-170">http://www.w3.org/2001/XMLSchema</span><span class="sxs-lookup"><span data-stu-id="d331c-170">http://www.w3.org/2001/XMLSchema</span></span>|  
  
## <a name="transaction-manager-bindings"></a><span data-ttu-id="d331c-171">Transaktions-Manager-Bindungen</span><span class="sxs-lookup"><span data-stu-id="d331c-171">Transaction Manager Bindings</span></span>  
 <span data-ttu-id="d331c-172">R1001: Transaktions-Manager müssen SOAP&#160;1.1 und WS-Adressierung&#160;2004/08 für den WS-AtomicTransaction- und den WS-Coordination-Nachrichtenaustausch verwenden.</span><span class="sxs-lookup"><span data-stu-id="d331c-172">R1001: Transaction Managers must use SOAP 1.1 and WS-Addressing 2004/08 for WS-Atomic Transaction and WS-Coordination message exchanges.</span></span>  
  
 <span data-ttu-id="d331c-173">Anwendungsnachrichten werden nicht auf diese Bindungen eingeschränkt und werden später beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d331c-173">Application messages are not constrained to these bindings and are described later.</span></span>  
  
### <a name="transaction-manager-https-binding"></a><span data-ttu-id="d331c-174">HTTPS-Bindungen des Transaktions-Managers</span><span class="sxs-lookup"><span data-stu-id="d331c-174">Transaction Manager HTTPS Binding</span></span>  
 <span data-ttu-id="d331c-175">Die HTTPS-Bindung des Transaktions-Managers richtet sich lediglich nach der Transportsicherheit, um Sicherheit zu gewährleisten und eine Vertrauenswürdigkeit zwischen den einzelnen Absender-Empfänger-Paaren in der Transaktionsstruktur herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d331c-175">The transaction manager HTTPS binding relies solely on transport security to achieve security and establish trust between each sender-receiver pair in the transaction tree.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="d331c-176">HTTPS-Transportkonfiguration</span><span class="sxs-lookup"><span data-stu-id="d331c-176">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="d331c-177">X.509-Zertifikate werden verwendet, um eine Transaktions-Manager-Identität herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d331c-177">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="d331c-178">Die Client/Server-Authentifizierung ist erforderlich, und die Client/Server-Autorisierung wird als Implementierungsdetail beibehalten:</span><span class="sxs-lookup"><span data-stu-id="d331c-178">Client/server authentication is required, and client/server authorization is left as an implementation detail:</span></span>  
  
-   <span data-ttu-id="d331c-179">R1111: Über die Verbindung vorgestellte X.509-Zertifikate müssen einen Antragstellernamen aufweisen, der dem vollqualifizierten Domänennamen (FQDN) des sendenden Computers entspricht.</span><span class="sxs-lookup"><span data-stu-id="d331c-179">R1111: X.509 certificates presented over the wire must have a subject name that matches the fully qualified domain name (FQDN) of the originating machine.</span></span>  
  
-   <span data-ttu-id="d331c-180">B1112: DNS muss zwischen den einzelnen Absender-Empfänger-Paaren im System funktionieren, damit eine Prüfung der X.509-Antragstellernamen erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="d331c-180">B1112: DNS must be functional between each sender-receiver pair in the system for X.509 subject name checks to succeed.</span></span>  
  
#### <a name="activation-and-registration-binding-configuration"></a><span data-ttu-id="d331c-181">Bindungskonfiguration von Aktivierung und Registrierung</span><span class="sxs-lookup"><span data-stu-id="d331c-181">Activation and Registration Binding Configuration</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d331c-182"> erfordert Anforderungs-/Antwort-Duplexbindung mit Korrelation über HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d331c-182"> requires request/reply duplex binding with correlation over HTTPS.</span></span> <span data-ttu-id="d331c-183">(Weitere Informationen über Korrelation und Beschreibungen der Anforderungs-/Antwortnachrichten-Austauschmuster finden Sie unter WS-AtomicTransaction, Abschnitt 8.)</span><span class="sxs-lookup"><span data-stu-id="d331c-183">(For more information about correlation and descriptions of the request/reply message exchange patterns, see WS-Atomic Transaction, Section 8.)</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="d331c-184">Bindungskonfiguration des 2PC-Protokolls</span><span class="sxs-lookup"><span data-stu-id="d331c-184">2PC Protocol Binding Configuration</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d331c-185"> unterstützt unidirektionale (Datagramm-) Nachrichten über HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d331c-185"> supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="d331c-186">Korrelation unter den Nachrichten wird als Implementierungsdetail beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d331c-186">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="d331c-187">B2131: Implementierungen müssen unterstützen `wsa:ReferenceParameters` wie beschrieben in WS-Adressierung Korrelation von erzielen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]des 2PC-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="d331c-187">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]’s 2PC messages.</span></span>  
  
### <a name="transaction-manager-mixed-security-binding"></a><span data-ttu-id="d331c-188">Gemischte Sicherheitsbindung des Transaktions-Managers</span><span class="sxs-lookup"><span data-stu-id="d331c-188">Transaction Manager Mixed Security Binding</span></span>  
 <span data-ttu-id="d331c-189">Dies ist eine alternative Bindung, verwendet transportsicherheit kombiniert mit dem WS-Coordination Issued Token-Modell zu identitätserstellungszwecken (Gemischter Modus).</span><span class="sxs-lookup"><span data-stu-id="d331c-189">This is an alternate (mixed mode) binding that uses transport security combined with the  WS-Coordination Issued Token model for identity establishment purposes.</span></span>  <span data-ttu-id="d331c-190">Aktivierung und Registrierung sind die einzigen Elemente, die sich zwischen den beiden Bindungen unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="d331c-190">Activation and Registration are the only elements that differ between the two bindings.</span></span>  
  
#### <a name="https-transport-configuration"></a><span data-ttu-id="d331c-191">HTTPS-Transportkonfiguration</span><span class="sxs-lookup"><span data-stu-id="d331c-191">HTTPS Transport Configuration</span></span>  
 <span data-ttu-id="d331c-192">X.509-Zertifikate werden verwendet, um eine Transaktions-Manager-Identität herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d331c-192">X.509 certificates are used to establish Transaction Manager Identity.</span></span> <span data-ttu-id="d331c-193">Die Client/Server-Authentifizierung ist erforderlich, und die Client/Server-Autorisierung wird als Implementierungsdetail beibehalten:</span><span class="sxs-lookup"><span data-stu-id="d331c-193">Client/Server authentication is required, and client/server authorization is left as an implementation detail.</span></span>  
  
#### <a name="activation-message-binding-configuration"></a><span data-ttu-id="d331c-194">Bindungskonfiguration von Aktivierungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="d331c-194">Activation Message Binding Configuration</span></span>  
 <span data-ttu-id="d331c-195">Aktivierungsnachrichten nehmen in der Regel nicht an der Interoperabilität teil, da sie normalerweise zwischen einer Anwendung und dem lokalen Transaktions-Manager auftreten.</span><span class="sxs-lookup"><span data-stu-id="d331c-195">Activation Messages usually do not participate in interoperability because they typically occur between an application and its local Transaction Manager.</span></span>  
  
 <span data-ttu-id="d331c-196">B1221: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] duplexbindung HTTPS verwendet (beschrieben [Messaging-Protokolle](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) für Aktivierungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="d331c-196">B1221: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)) for Activation messages.</span></span> <span data-ttu-id="d331c-197">Anforderungs- und Antwortnachrichten werden mithilfe von WS-Addressing&#160;2004/08 korreliert.</span><span class="sxs-lookup"><span data-stu-id="d331c-197">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="d331c-198">In der WS-AtomicTransaction-Spezifikation, Abschnitt 8, werden die Korrelation und die Nachrichtenaustauschmuster ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d331c-198">WS-Atomic Transaction specification, Section 8, describes further details about correlation and the message exchange patterns.</span></span>  
  
-   <span data-ttu-id="d331c-199">R1222: Beim Eingang eines `CreateCoordinationContext` muss der Koordinator ein `SecurityContextToken` mit zugewiesenem geheimen `STx` ausgeben.</span><span class="sxs-lookup"><span data-stu-id="d331c-199">R1222: Upon receiving a `CreateCoordinationContext`, the Coordinator must issue a `SecurityContextToken` with associated secret `STx`.</span></span> <span data-ttu-id="d331c-200">Dieses Token wird entsprechend der WS-Trust-Spezifikation in einem `t:IssuedTokens`-Header zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d331c-200">This token is returned inside a `t:IssuedTokens` header following WS-Trust specification.</span></span>  
  
-   <span data-ttu-id="d331c-201">R1223: Falls die Aktivierung innerhalb eines bereits vorhandenen Koordinationskontexts stattfindet, muss der `t:IssuedTokens`-Header, bei dem `SecurityContextToken` dem bereits vorhandenem Kontext zugewiesen ist, in der `CreateCoordinationContext`-Nachricht fließen.</span><span class="sxs-lookup"><span data-stu-id="d331c-201">R1223: If Activation occurs within an existing Coordination Context, the `t:IssuedTokens` header with the `SecurityContextToken` associated with existing Context must flow on the `CreateCoordinationContext` message.</span></span>  
  
 <span data-ttu-id="d331c-202">Ein neues `t:IssuedTokens` Header generiert werden soll, zum Anfügen an den ausgehenden `wscoor:CreateCoordinationContextResponse` Nachricht.</span><span class="sxs-lookup"><span data-stu-id="d331c-202">A new `t:IssuedTokens` header should be generated for attaching to the outgoing `wscoor:CreateCoordinationContextResponse` message.</span></span>  
  
#### <a name="registration-message-binding-configuration"></a><span data-ttu-id="d331c-203">Bindungskonfiguration von Registrierungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="d331c-203">Registration Message Binding Configuration</span></span>  
 <span data-ttu-id="d331c-204">B1231: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] duplexbindung HTTPS verwendet (beschrieben [Messaging-Protokolle](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span><span class="sxs-lookup"><span data-stu-id="d331c-204">B1231: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses duplex HTTPS binding (described in [Messaging Protocols](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)).</span></span> <span data-ttu-id="d331c-205">Anforderungs- und Antwortnachrichten werden mithilfe von WS-Addressing&#160;2004/08 korreliert.</span><span class="sxs-lookup"><span data-stu-id="d331c-205">Request and Reply messages are correlated using WS-Addressing 2004/08.</span></span>  
  
 <span data-ttu-id="d331c-206">In der WS-AtomicTransaction-Spezifikation, Abschnitt 8, werden weitere Details zur Korrelation und die Nachrichtenaustauschmuster ausführlich beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d331c-206">WS-AtomicTransaction, Section 8, describes further details about correlation and descriptions of the message exchange patterns.</span></span>  
  
 <span data-ttu-id="d331c-207">R1232: Ausgehende `wscoor:Register` Nachrichten verwenden müssen die `IssuedTokenOverTransport` Authentifizierungsmodus in beschriebenen [Sicherheitsprotokolle](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="d331c-207">R1232: Outgoing `wscoor:Register` messages must use the `IssuedTokenOverTransport` authentication mode described in [Security Protocols](../../../../docs/framework/wcf/feature-details/security-protocols.md).</span></span>  
  
 <span data-ttu-id="d331c-208">Die `wsse:Timestamp` Element muss signiert sein, mit der `SecurityContextToken``STx` ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="d331c-208">The `wsse:Timestamp` element must be signed using the `SecurityContextToken``STx` issued.</span></span> <span data-ttu-id="d331c-209">Diese Signatur ist Beweis für den Besitz des einer bestimmten Transaktion zugewiesenen Tokens und wird für die Authentifizierung einer Teilnehmerliste während der Transaktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="d331c-209">This signature is a proof of possession of the token associated with particular transaction and is used to authenticate a participant enlisting in the transaction.</span></span> <span data-ttu-id="d331c-210">Die RegistrationResponse-Nachricht wird über HTTPS zurückgesendet.</span><span class="sxs-lookup"><span data-stu-id="d331c-210">The RegistrationResponse message is sent back over HTTPS.</span></span>  
  
#### <a name="2pc-protocol-binding-configuration"></a><span data-ttu-id="d331c-211">Bindungskonfiguration des 2PC-Protokolls</span><span class="sxs-lookup"><span data-stu-id="d331c-211">2PC Protocol Binding Configuration</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="d331c-212"> unterstützt unidirektionale (Datagramm-) Nachrichten über HTTPS.</span><span class="sxs-lookup"><span data-stu-id="d331c-212"> supports one-way (datagram) messages over HTTPS.</span></span> <span data-ttu-id="d331c-213">Korrelation unter den Nachrichten wird als Implementierungsdetail beibehalten.</span><span class="sxs-lookup"><span data-stu-id="d331c-213">Correlation among the messages is left as an implementation detail.</span></span>  
  
 <span data-ttu-id="d331c-214">B2131: Implementierungen müssen unterstützen `wsa:ReferenceParameters` wie beschrieben in WS-Adressierung Korrelation von erzielen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]des 2PC-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="d331c-214">B2131: Implementations must support `wsa:ReferenceParameters` as described in WS-Addressing to achieve correlation of [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]’s 2PC messages.</span></span>  
  
## <a name="application-message-exchange"></a><span data-ttu-id="d331c-215">Austausch von Anwendungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="d331c-215">Application Message Exchange</span></span>  
 <span data-ttu-id="d331c-216">In Anwendungen können beliebige Bindungen für Nachrichten verwendet werden, die von Anwendung zu Anwendung gesendet werden, solange die Bindung die folgenden Sicherheitsanforderungen erfüllt:</span><span class="sxs-lookup"><span data-stu-id="d331c-216">Applications are free to use any particular binding for application-to-application messages, as long as the binding meets the following security requirements:</span></span>  
  
-   <span data-ttu-id="d331c-217">R2001: Nachrichten von Anwendung zu Anwendung müssen im Nachrichtenheader den `t:IssuedTokens`-Header zusammen mit `CoordinationContext` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d331c-217">R2001: Application-to-application messages must flow the `t:IssuedTokens` header along with the `CoordinationContext` in the header of the message.</span></span>  
  
-   <span data-ttu-id="d331c-218">R2002: Integrität und Vertraulichkeit von `t:IssuedToken` müssen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d331c-218">R2002: Integrity and confidentiality of `t:IssuedToken` must be provided.</span></span>  
  
 <span data-ttu-id="d331c-219">Der `CoordinationContext`-Header enthält `wscoor:Identifier`.</span><span class="sxs-lookup"><span data-stu-id="d331c-219">The `CoordinationContext` header contains `wscoor:Identifier`.</span></span> <span data-ttu-id="d331c-220">Während die Definition von `xsd:AnyURI` die Verwendung der absoluten und relativen URIs zulässt, unterstützt [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] lediglich `wscoor:Identifiers`, wobei es sich um absolute URIs handelt.</span><span class="sxs-lookup"><span data-stu-id="d331c-220">While the definition of `xsd:AnyURI` allows the use of both absolute and relative URIs, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] supports only `wscoor:Identifiers`, which are absolute URIs.</span></span>  
  
 <span data-ttu-id="d331c-221">Falls es sich bei `wscoor:Identifier` von `wscoor:CoordinationContext` um einen relativen URI handelt, werden von den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Transaktionsdiensten Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="d331c-221">If the `wscoor:Identifier` of the `wscoor:CoordinationContext` is a relative URI, faults will be returned from transactional [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span>  
  
## <a name="message-examples"></a><span data-ttu-id="d331c-222">Nachrichtenbeispiele</span><span class="sxs-lookup"><span data-stu-id="d331c-222">Message Examples</span></span>  
  
### <a name="createcoordinationcontext-requestresponse-messages"></a><span data-ttu-id="d331c-223">CreateCoordinationContext-Anforderungs-/Antwortmeldungen</span><span class="sxs-lookup"><span data-stu-id="d331c-223">CreateCoordinationContext Request/Response Messages</span></span>  
 <span data-ttu-id="d331c-224">Die folgenden Nachrichten folgen einem Anforderungs-/Antwortmuster.</span><span class="sxs-lookup"><span data-stu-id="d331c-224">The following messages follow a request/response pattern.</span></span>  
  
#### <a name="createcoordinationcontext"></a><span data-ttu-id="d331c-225">CreateCoordinationContext</span><span class="sxs-lookup"><span data-stu-id="d331c-225">CreateCoordinationContext</span></span>  
  
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
        <wsu:Created>2005-12-15T23:36:09.921Z</u:Created>  
        <wsu:Expires>2005-12-15T23:41:09.921Z</u:Expires>  
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
  
#### <a name="createcoordinationcontextresponse"></a><span data-ttu-id="d331c-226">CreateCoordinationContextResponse</span><span class="sxs-lookup"><span data-stu-id="d331c-226">CreateCoordinationContextResponse</span></span>  
  
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
  
### <a name="registration-messages"></a><span data-ttu-id="d331c-227">Registrierungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="d331c-227">Registration Messages</span></span>  
 <span data-ttu-id="d331c-228">Bei den folgenden Nachrichten handelt es sich um Registrierungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="d331c-228">The following messages are registration messages.</span></span>  
  
#### <a name="register"></a><span data-ttu-id="d331c-229">Register</span><span class="sxs-lookup"><span data-stu-id="d331c-229">Register</span></span>  
  
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
  
#### <a name="register-response"></a><span data-ttu-id="d331c-230">Register Response</span><span class="sxs-lookup"><span data-stu-id="d331c-230">Register Response</span></span>  
  
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
  
### <a name="two-phase-commit-protocol-messages"></a><span data-ttu-id="d331c-231">Zweiphasen-Commit-Protokollnachrichten</span><span class="sxs-lookup"><span data-stu-id="d331c-231">Two Phase Commit Protocol Messages</span></span>  
 <span data-ttu-id="d331c-232">Die folgende Nachricht bezieht sich auf das Zweiphasen-Commit-Protokoll (2PC).</span><span class="sxs-lookup"><span data-stu-id="d331c-232">The following message relates to the two-phase commit (2PC) protocol.</span></span>  
  
#### <a name="commit"></a><span data-ttu-id="d331c-233">Commit</span><span class="sxs-lookup"><span data-stu-id="d331c-233">Commit</span></span>  
  
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
  
### <a name="application-messages"></a><span data-ttu-id="d331c-234">Anwendungsnachrichten</span><span class="sxs-lookup"><span data-stu-id="d331c-234">Application Messages</span></span>  
 <span data-ttu-id="d331c-235">Bei den folgenden Nachrichten handelt es sich um Anwendungsnachrichten.</span><span class="sxs-lookup"><span data-stu-id="d331c-235">The following messages are application messages.</span></span>  
  
#### <a name="application-message-request"></a><span data-ttu-id="d331c-236">Anwendungsnachrichtenanforderung</span><span class="sxs-lookup"><span data-stu-id="d331c-236">Application message-Request</span></span>  
  
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
    <wsse11:EncryptedHeader >  
     <!-- encrypted wscoor:CoordinationContext header containing CCi -->  
    </wsse11:EncryptedHeader>  
    <wsse11:EncryptedHeader   
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
