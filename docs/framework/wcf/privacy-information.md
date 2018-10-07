---
title: Windows Communication Foundation-Datenschutzinformationen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
ms.openlocfilehash: 717e38b15767b744816c0a57c97827a1a35c95b3
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2018
ms.locfileid: "48847814"
---
# <a name="windows-communication-foundation-privacy-information"></a><span data-ttu-id="29eb8-102">Windows Communication Foundation-Datenschutzinformationen</span><span class="sxs-lookup"><span data-stu-id="29eb8-102">Windows Communication Foundation Privacy Information</span></span>
<span data-ttu-id="29eb8-103">Microsoft verpflichtet sich, die persönlichen Daten von Endbenutzern vertraulich zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="29eb8-103">Microsoft is committed to protecting end-users' privacy.</span></span> <span data-ttu-id="29eb8-104">Bei der Erstellung einer Anwendung mithilfe von Windows Communication Foundation (WCF), Version 3.0, kann Ihre Anwendung Datenschutz der Endbenutzer beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="29eb8-104">When you build an application using Windows Communication Foundation (WCF), version 3.0, your application may impact your end-users' privacy.</span></span> <span data-ttu-id="29eb8-105">Die Anwendung erfasst z. B. unter Umständen explizit Kontaktinformationen des Benutzers oder fordert Informationen an und sendet diese über das Internet an Ihre Website.</span><span class="sxs-lookup"><span data-stu-id="29eb8-105">For example, your application may explicitly collect user contact information, or it may request or send information over the Internet to your Web site.</span></span> <span data-ttu-id="29eb8-106">Wenn Sie Microsoft-Technologie in Ihre Anwendung einbetten, kann sich das Verhalten dieser Technologie ebenfalls auf den Datenschutz auswirken.</span><span class="sxs-lookup"><span data-stu-id="29eb8-106">If you embed Microsoft technology in your application, that technology may have its own behavior that might affect privacy.</span></span> <span data-ttu-id="29eb8-107">WCF sendet nicht an Microsoft aus Ihrer Anwendung Informationen, sofern Ihnen oder dem Endbenutzer Sie uns senden möchten.</span><span class="sxs-lookup"><span data-stu-id="29eb8-107">WCF does not send any information to Microsoft from your application unless you or the end-user choose to send it to us.</span></span>  
  
## <a name="wcf-in-brief"></a><span data-ttu-id="29eb8-108">WCF in Kürze</span><span class="sxs-lookup"><span data-stu-id="29eb8-108">WCF in Brief</span></span>  
 <span data-ttu-id="29eb8-109">WCF ist ein verteiltes Messagingframework, das mithilfe von Microsoft .NET Framework, die Entwickler verteilte Anwendungen erstellen kann.</span><span class="sxs-lookup"><span data-stu-id="29eb8-109">WCF is a distributed messaging framework using the Microsoft .NET Framework that allows developers to build distributed applications.</span></span> <span data-ttu-id="29eb8-110">Zwischen zwei Anwendungen übermittelte Nachrichten enthalten Header- und Textinformationen.</span><span class="sxs-lookup"><span data-stu-id="29eb8-110">Messages communicated between two applications contain header and body information.</span></span>  
  
 <span data-ttu-id="29eb8-111">Header können je nach von der Anwendung verwendeten Diensten unter anderem Meldungsrouting, Sicherheitsinformationen und Transaktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="29eb8-111">Headers may contain message routing, security information, transactions, and more depending on the services used by the application.</span></span> <span data-ttu-id="29eb8-112">Nachrichten werden in der Regel standardmäßig verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="29eb8-112">Messages are typically encrypted by default.</span></span> <span data-ttu-id="29eb8-113">Eine Ausnahme ist die Verwendung der `BasicHttpBinding`, die für nicht gesicherte, ältere Webdienste konzipiert wurde.</span><span class="sxs-lookup"><span data-stu-id="29eb8-113">The one exception is when using the `BasicHttpBinding`, which was designed for use with non-secured, legacy Web services.</span></span> <span data-ttu-id="29eb8-114">Als Anwendungs-Designer sind Sie für den abschließenden Entwurf verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="29eb8-114">As the application designer, you are responsible for the final design.</span></span> <span data-ttu-id="29eb8-115">Nachrichten in der SOAP-Text enthalten anwendungsspezifische Daten; Allerdings können diese Daten, z. B. Anwendung definierte persönliche Daten gesichert werden, mithilfe von verschlüsselungs- oder vertraulichkeitsfunktionen WCF-Funktionen.</span><span class="sxs-lookup"><span data-stu-id="29eb8-115">Messages in the SOAP body contain application-specific data; however, this data, such as application-defined personal information, can be secured by using WCF encryption or confidentiality features.</span></span> <span data-ttu-id="29eb8-116">In den folgenden Abschnitten werden die Funktionen beschrieben, die sich auf den Datenschutz auswirken können.</span><span class="sxs-lookup"><span data-stu-id="29eb8-116">The following sections describe the features that potentially impact privacy.</span></span>  
  
## <a name="messaging"></a><span data-ttu-id="29eb8-117">Messaging</span><span class="sxs-lookup"><span data-stu-id="29eb8-117">Messaging</span></span>  
 <span data-ttu-id="29eb8-118">Jede WCF-Nachricht besitzt einen Adressheader, der angibt, das Ziel der Nachricht und, in dem die Antwort.</span><span class="sxs-lookup"><span data-stu-id="29eb8-118">Each WCF message has an address header that specifies the message destination and where the reply should go.</span></span>  
  
 <span data-ttu-id="29eb8-119">Die Adresskomponente einer Endpunktadresse ist ein URI (Uniform Resource Identifier), der den Endpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="29eb8-119">The address component of an endpoint address is a Uniform Resource Identifier (URI) that identifies the endpoint.</span></span> <span data-ttu-id="29eb8-120">Die Adresse kann eine Netzwerkadresse oder eine logische Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="29eb8-120">The address can be a network address or a logical address.</span></span> <span data-ttu-id="29eb8-121">Die Adresse kann den Computernamen (Hostname, vollqualifizierter Domänenname) und eine IP-Adresse einschließen.</span><span class="sxs-lookup"><span data-stu-id="29eb8-121">The address may include machine name (hostname, fully qualified domain name) and an IP address.</span></span> <span data-ttu-id="29eb8-122">Die Endpunktadresse kann außerdem eine GUID (Globally Unique Identifier) oder eine Auflistung von GUIDs für die temporäre Adressierung zum Ermitteln jeder Adresse enthalten.</span><span class="sxs-lookup"><span data-stu-id="29eb8-122">The endpoint address may also contain a globally unique identifier (GUID), or a collection of GUIDs for temporary addressing used to discern each address.</span></span> <span data-ttu-id="29eb8-123">Jede Nachricht enthält eine Nachrichten-ID, die eine GUID ist.</span><span class="sxs-lookup"><span data-stu-id="29eb8-123">Each message contains a message ID that is a GUID.</span></span> <span data-ttu-id="29eb8-124">Diese Funktion folgt dem WS-Addressierungs-Verweisstandard.</span><span class="sxs-lookup"><span data-stu-id="29eb8-124">This feature follows the WS-Addressing reference standard.</span></span>  
  
 <span data-ttu-id="29eb8-125">Der WCF-Messagingebene schreibt keine persönlichen Informationen nicht auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="29eb8-125">The WCF messaging layer does not write any personal information to the local machine.</span></span> <span data-ttu-id="29eb8-126">Sie kann jedoch persönliche Daten auf der Netzwerkebene weitergeben, wenn ein Diensteentwickler einen Dienst erstellt hat, der solche Informationen verfügbar macht (z. B. durch das Verwenden des Namens einer Person in einem Endpunktnamen oder durch das Aufnehmen persönlicher Daten in die WSDL des Endpunkts, ohne dass Clients zum Zugriff auf die WSDL HTTPS verwenden müssen).</span><span class="sxs-lookup"><span data-stu-id="29eb8-126">However, it might propagate personal information at the network level if a service developer has created a service that exposes such information (for example, by using a person's name in an endpoint name, or including personal information in the endpoint's Web Services Description Language but not requiring clients to use https to access the WSDL).</span></span> <span data-ttu-id="29eb8-127">Auch wenn ein Entwickler ausgeführt wird. die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) -Tool gegen einen Endpunkt, die persönlichen Daten, die Ausgabe des Tools verfügbar macht, kann diese Informationen enthalten, und in die Ausgabedatei geschrieben der lokale Festplatte.</span><span class="sxs-lookup"><span data-stu-id="29eb8-127">Also, if a developer runs the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool against an endpoint that exposes personal information, the tool's output could contain that information, and the output file is written to the local hard disk.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="29eb8-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="29eb8-128">Hosting</span></span>  
 <span data-ttu-id="29eb8-129">Die Hostingfunktion in WCF ermöglicht Anwendungen, um bei Bedarf starten oder Aktivieren der Anschlussfreigabe zwischen mehreren Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="29eb8-129">The hosting feature in WCF allows applications to start on demand or to enable port sharing between multiple applications.</span></span> <span data-ttu-id="29eb8-130">Kann eine WCF-Anwendung in IIS (Internetinformationsdienste), ähnlich wie gehostet werden [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="29eb8-130">An WCF application can be hosted in Internet Information Services (IIS), similar to [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)].</span></span>  
  
 <span data-ttu-id="29eb8-131">Das Hosting macht keine spezifischen Informationen im Netzwerk verfügbar und behält keine Daten auf dem Computer bei.</span><span class="sxs-lookup"><span data-stu-id="29eb8-131">Hosting does not expose any specific information on the network and it does not keep data on the machine.</span></span>  
  
## <a name="message-security"></a><span data-ttu-id="29eb8-132">Nachrichtensicherheit</span><span class="sxs-lookup"><span data-stu-id="29eb8-132">Message Security</span></span>  
 <span data-ttu-id="29eb8-133">WCF-Sicherheit stellt die Sicherheitsfunktionen für Messaginganwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="29eb8-133">WCF security provides the security capabilities for messaging applications.</span></span> <span data-ttu-id="29eb8-134">Die bereitgestellten Sicherheitsfunktionen bieten Authentifizierung und Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="29eb8-134">The security functions provided include authentication and authorization.</span></span>  
  
 <span data-ttu-id="29eb8-135">Die Authentifizierung wird ausgeführt, indem Anmeldeinformationen zwischen den Clients und Diensten übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-135">Authentication is performed by passing credentials between the clients and services.</span></span> <span data-ttu-id="29eb8-136">Die Authentifizierung kann entweder durch Sicherheit auf Transportebene oder durch SOAP-Sicherheit auf Nachrichtenebene erfolgen:</span><span class="sxs-lookup"><span data-stu-id="29eb8-136">Authentication can be either through transport-level security or through SOAP message-level security, as follows:</span></span>  
  
-   <span data-ttu-id="29eb8-137">Bei der SOAP-Nachrichtensicherheit erfolgt die Authentifizierung durch Anmeldeinformationen wie Benutzername/Kennwörter, X.509-Zertifikate, Kerberos-Tickets und SAML-Token, die alle je nach Aussteller persönliche Daten enthalten können.</span><span class="sxs-lookup"><span data-stu-id="29eb8-137">In SOAP message security, authentication is performed through credentials like username/passwords, X.509 certificates, Kerberos tickets, and SAML tokens, all of which might contain personal information, depending on the issuer.</span></span>  
  
-   <span data-ttu-id="29eb8-138">Bei der Transportsicherheit erfolgt die Authentifizierung durch herkömmliche Transportauthentifizierungsmechanismen wie HTTP-Authentifizierungsschemas (Basic, Digest, Negotiate, Integrierte Windows-Authentifizierung, NTLM, Keine, Anonym) und Formularauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="29eb8-138">Using transport security, authentication is done through traditional transport authentication mechanisms like HTTP authentication schemes (Basic, Digest, Negotiate, Integrated Windows Authorization, NTLM, None, and Anonymous), and form authentication.</span></span>  
  
 <span data-ttu-id="29eb8-139">Die Authentifizierung kann zu einer sicheren Sitzung zwischen den kommunizierenden Endpunkten führen.</span><span class="sxs-lookup"><span data-stu-id="29eb8-139">Authentication can result in a secure session established between the communicating endpoints.</span></span> <span data-ttu-id="29eb8-140">Die Sitzung wird durch eine GUID identifiziert, die über die Lebensdauer der Sicherheitssitzung reicht.</span><span class="sxs-lookup"><span data-stu-id="29eb8-140">The session is identified by a GUID that lasts the lifetime of the security session.</span></span> <span data-ttu-id="29eb8-141">Die folgende Tabelle zeigt, welche Elemente wo gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-141">The following table shows what is kept and where.</span></span>  
  
|<span data-ttu-id="29eb8-142">Daten</span><span class="sxs-lookup"><span data-stu-id="29eb8-142">Data</span></span>|<span data-ttu-id="29eb8-143">Speicher</span><span class="sxs-lookup"><span data-stu-id="29eb8-143">Storage</span></span>|  
|----------|-------------|  
|<span data-ttu-id="29eb8-144">Präsentationsanmeldeinformationen, z. B. Benutzername, X.509-Zertifikate, Kerberos-Token und Verweise auf Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="29eb8-144">Presentation credentials, such as username, X.509 certificates, Kerberos tokens, and references to credentials.</span></span>|<span data-ttu-id="29eb8-145">Standardmäßige Windows-Verwaltungsmechanismen für Anmeldeinformationen, z. B. der Windows-Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="29eb8-145">Standard Windows credential management mechanisms such as the Windows certificate store.</span></span>|  
|<span data-ttu-id="29eb8-146">Benutzermitgliedschaftsinformationen, z. B. Benutzernamen und Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="29eb8-146">User membership information, such as usernames and passwords.</span></span>|[!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)]<span data-ttu-id="29eb8-147">-Mitgliedschaftsanbieter.</span><span class="sxs-lookup"><span data-stu-id="29eb8-147"> membership providers.</span></span>|  
|<span data-ttu-id="29eb8-148">Identitätsinformationen über den Dienst zum Authentifizieren des Diensts gegenüber Clients.</span><span class="sxs-lookup"><span data-stu-id="29eb8-148">Identity information about the service used to authenticate the service to clients.</span></span>|<span data-ttu-id="29eb8-149">Endpunktadresse des Diensts.</span><span class="sxs-lookup"><span data-stu-id="29eb8-149">Endpoint address of the service.</span></span>|  
|<span data-ttu-id="29eb8-150">Aufruferdaten.</span><span class="sxs-lookup"><span data-stu-id="29eb8-150">Caller information.</span></span>|<span data-ttu-id="29eb8-151">Überwachungsprotokolle.</span><span class="sxs-lookup"><span data-stu-id="29eb8-151">Auditing logs.</span></span>|  
  
## <a name="auditing"></a><span data-ttu-id="29eb8-152">Überwachung</span><span class="sxs-lookup"><span data-stu-id="29eb8-152">Auditing</span></span>  
 <span data-ttu-id="29eb8-153">Bei der Überwachung wird der Erfolg und das Fehlschlagen von Authentifizierungs- und Autorisierungsereignissen aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="29eb8-153">Auditing records the success and failure of authentication and authorization events.</span></span> <span data-ttu-id="29eb8-154">Überwachungsdatensätze enthalten die folgenden Daten: Dienst-URI, Aktions-URI und Identifikation des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="29eb8-154">Auditing records contain the following data: service URI, action URI, and the caller's identification.</span></span>  
  
 <span data-ttu-id="29eb8-155">Bei der Überwachung werden Daten auch dann aufgezeichnet, wenn der Administrator die Konfiguration der Nachrichtenprotokollierung ändert (aktiviert oder deaktiviert), da bei der Nachrichtenprotokollierung anwendungsspezifische Daten im Header und Text erfasst werden können.</span><span class="sxs-lookup"><span data-stu-id="29eb8-155">Auditing also records when the administrator modifies the configuration of message logging (turning it on or off), because message logging may log application-specific data in headers and bodies.</span></span> <span data-ttu-id="29eb8-156">In [!INCLUDE[wxp](../../../includes/wxp-md.md)] wird ein Datensatz im Anwendungsereignisprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="29eb8-156">For [!INCLUDE[wxp](../../../includes/wxp-md.md)], a record is logged in the application event log.</span></span> <span data-ttu-id="29eb8-157">In [!INCLUDE[wv](../../../includes/wv-md.md)] und [!INCLUDE[ws2003](../../../includes/ws2003-md.md)] wird ein Datensatz im Sicherheitsereignisprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="29eb8-157">For [!INCLUDE[wv](../../../includes/wv-md.md)] and [!INCLUDE[ws2003](../../../includes/ws2003-md.md)], a record is logged in the security event log.</span></span>  
  
## <a name="transactions"></a><span data-ttu-id="29eb8-158">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="29eb8-158">Transactions</span></span>  
 <span data-ttu-id="29eb8-159">Die Transaktionsfunktion stellt Transaktionsdienste für eine WCF-Anwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="29eb8-159">The transactions feature provides transactional services to a WCF application.</span></span>  
  
 <span data-ttu-id="29eb8-160">Bei der Transaktionsweitergabe verwendete Transaktionsheader enthalten möglicherweise TransaktionsIDs oder Eintragung-IDs, die GUIDs sind.</span><span class="sxs-lookup"><span data-stu-id="29eb8-160">Transaction headers used in transaction propagation may contain Transaction IDs or Enlistment IDs, which are GUIDs.</span></span>  
  
 <span data-ttu-id="29eb8-161">Das Tansaktionsfeature verwendet den MSDTC (Microsoft Distributed Transaction Coordinator)-Transaktions-Manager (eine Windows-Komponente) zum Verwalten des Transaktionszustands.</span><span class="sxs-lookup"><span data-stu-id="29eb8-161">The Transactions feature uses the Microsoft Distributed Transaction Coordinator (MSDTC) Transaction Manager (a Windows component) to manage transaction state.</span></span> <span data-ttu-id="29eb8-162">Standardmäßig sind Kommunikationen zwischen Transaktions-Managern verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="29eb8-162">By default, communications between Transactions Managers are encrypted.</span></span> <span data-ttu-id="29eb8-163">Transaktions-Manager protokollieren möglicherweise Endpunktverweise, Transaktions-IDs und Eintragung-IDs als Teil ihres permanenten Zustands.</span><span class="sxs-lookup"><span data-stu-id="29eb8-163">Transaction Managers may log endpoint references, Transaction IDs, and Enlistment IDs as part of their durable state.</span></span> <span data-ttu-id="29eb8-164">Die Lebensdauer dieses Zustands wird von der Lebensdauer der Protokolldatei des Transaktions-Managers bestimmt.</span><span class="sxs-lookup"><span data-stu-id="29eb8-164">The lifetime of this state is determined by the lifetime of the Transaction Manager’s log file.</span></span> <span data-ttu-id="29eb8-165">Der MSDTC-Dienst besitzt dieses Protokoll und behält es bei.</span><span class="sxs-lookup"><span data-stu-id="29eb8-165">The MSDTC service owns and maintains this log.</span></span>  
  
 <span data-ttu-id="29eb8-166">Die Transaktionsfunktion implementiert die Standards WS-Coordination und WS-Atomic Transaction.</span><span class="sxs-lookup"><span data-stu-id="29eb8-166">The Transactions feature implements the WS-Coordination and WS-Atomic Transaction standards.</span></span>  
  
## <a name="reliable-sessions"></a><span data-ttu-id="29eb8-167">Zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="29eb8-167">Reliable Sessions</span></span>  
 <span data-ttu-id="29eb8-168">Zuverlässige Sitzungen in WCF bieten die Übertragung von Nachrichten an, wenn Transport- oder Vermittler Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="29eb8-168">Reliable sessions in WCF provide the transfer of messages when transport or intermediary failures occur.</span></span> <span data-ttu-id="29eb8-169">Sie bieten auch dann genau eine Übertragung von Nachrichten, wenn die Verbindung zum zugrunde liegenden Transport unterbrochen wird (z. B. eine TCP-Verbindung in einem drahtlosen Netzwerk) oder eine Nachricht verloren geht (ein HTTP-Proxy verwirft eine aus- oder eingehende Nachricht).</span><span class="sxs-lookup"><span data-stu-id="29eb8-169">They provide an exactly-once transfer of messages even when the underlying transport disconnects (for example, a TCP connection on a wireless network) or loses a message (an HTTP proxy dropping an outgoing or incoming message).</span></span> <span data-ttu-id="29eb8-170">Zuverlässige Sitzungen heben außerdem die Neuordnung von Nachrichten auf (z. B. beim Multipfad-Routing), wodurch die Reihenfolge beibehalten wird, in der die Nachrichten gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-170">Reliable sessions also recover message reordering (as may happen in the case of multipath routing), preserving the order in which the messages were sent.</span></span>  
  
 <span data-ttu-id="29eb8-171">Zuverlässige Sitzungen werden mit dem WS-RM (WS-ReliableMessaging)-Protokoll implementiert.</span><span class="sxs-lookup"><span data-stu-id="29eb8-171">Reliable sessions are implemented using the WS-ReliableMessaging (WS-RM) protocol.</span></span> <span data-ttu-id="29eb8-172">Sie fügen WS-RM-Header hinzu, die Sitzungsinformationen enthalten, die zum Identifizieren aller einer bestimmten zuverlässigen Sitzung zugeordneten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-172">They add WS-RM headers that contain session information, which is used to identify all messages associated with a particular reliable session.</span></span> <span data-ttu-id="29eb8-173">Jede WS-RM-Sitzung hat einen Bezeichner, der eine GUID ist.</span><span class="sxs-lookup"><span data-stu-id="29eb8-173">Each WS-RM session has an identifier, which is a GUID.</span></span>  
  
 <span data-ttu-id="29eb8-174">Auf dem Computer des Endbenutzers werden keine persönlichen Informationen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="29eb8-174">No personal information is retained on the end-user's machine.</span></span>  
  
## <a name="queued-channels"></a><span data-ttu-id="29eb8-175">In der Warteschlange stehende Kanäle</span><span class="sxs-lookup"><span data-stu-id="29eb8-175">Queued Channels</span></span>  
 <span data-ttu-id="29eb8-176">Warteschlangen speichern Nachrichten von einer sendenden Anwendung für eine empfangende Anwendung und leiten sie später an die empfangende Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="29eb8-176">Queues store messages from a sending application on behalf of a receiving application and later forward these messages to the receiving application.</span></span> <span data-ttu-id="29eb8-177">Sie sichern die Nachrichtenübertragung von sendenden Anwendungen an empfangende Anwendungen, wenn z. B. die empfangende Anwendung flüchtig ist.</span><span class="sxs-lookup"><span data-stu-id="29eb8-177">They help ensure the transfer of messages from sending applications to receiving applications when, for example, the receiving application is transient.</span></span> <span data-ttu-id="29eb8-178">WCF bietet Unterstützung für Warteschlangenvorgänge durch die Nutzung von Microsoft Message Queuing (MSMQ) als Transport.</span><span class="sxs-lookup"><span data-stu-id="29eb8-178">WCF provides support for queuing by using Microsoft Message Queuing (MSMQ) as a transport.</span></span>  
  
 <span data-ttu-id="29eb8-179">Die Funktion für in der Warteschlange stehende Kanäle fügt einer Nachricht keine Header hinzu.</span><span class="sxs-lookup"><span data-stu-id="29eb8-179">The queued channels feature does not add headers to a message.</span></span> <span data-ttu-id="29eb8-180">Es erstellt stattdessen eine Message Queuing-Nachricht mit entsprechenden Einstellungen und ruft Message Queuing-Methoden zum Platzieren der Nachricht in die Message Queuing-Warteschlange auf.</span><span class="sxs-lookup"><span data-stu-id="29eb8-180">Instead it creates a Message Queuing message with appropriate Message Queuing message properties set, and invokes Message Queuing methods to put the message in the Message Queuing queue.</span></span> <span data-ttu-id="29eb8-181">Message Queuing ist eine in Windows enthaltene optionale Komponente.</span><span class="sxs-lookup"><span data-stu-id="29eb8-181">Message Queuing is an optional component that ships with Windows.</span></span>  
  
 <span data-ttu-id="29eb8-182">Durch dieses Feature werden auf dem Computer des Endbenutzers keine Informationen beibehalten, da es Message Queuing als Warteschlangeninfrastruktur verwendet.</span><span class="sxs-lookup"><span data-stu-id="29eb8-182">No information is retained on the end-user's machine by the queued channels feature, because it uses Message Queuing as the queuing infrastructure.</span></span>  
  
## <a name="com-integration"></a><span data-ttu-id="29eb8-183">COM+-Integration</span><span class="sxs-lookup"><span data-stu-id="29eb8-183">COM+ Integration</span></span>  
 <span data-ttu-id="29eb8-184">Diese Funktion schließt vorhandene COM- und COM+-Funktionen zum Erstellen von Diensten, die mit WCF-Diensten kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="29eb8-184">This feature wraps existing COM and COM+ functionality to create services that are compatible with WCF services.</span></span> <span data-ttu-id="29eb8-185">Diese Funktion verwendet keine bestimmten Header, und es behält keine Daten auf dem Computer des Endbenutzers bei.</span><span class="sxs-lookup"><span data-stu-id="29eb8-185">This feature does not use specific headers and it does not retain data on the end-user's machine.</span></span>  
  
## <a name="com-service-moniker"></a><span data-ttu-id="29eb8-186">COM-Dienstmoniker</span><span class="sxs-lookup"><span data-stu-id="29eb8-186">COM Service Moniker</span></span>  
 <span data-ttu-id="29eb8-187">Dies bietet einen nicht verwalteten Wrapper um einem standard-WCF-Client.</span><span class="sxs-lookup"><span data-stu-id="29eb8-187">This provides an unmanaged wrapper to a standard WCF client.</span></span> <span data-ttu-id="29eb8-188">Diese Funktion verwendet keine bestimmten Header, und sie behält keine Daten auf dem Computer bei.</span><span class="sxs-lookup"><span data-stu-id="29eb8-188">This feature does not have specific headers on the wire nor does it persist data on the machine.</span></span>  
  
## <a name="peer-channel"></a><span data-ttu-id="29eb8-189">Peerkanal</span><span class="sxs-lookup"><span data-stu-id="29eb8-189">Peer Channel</span></span>  
 <span data-ttu-id="29eb8-190">Ein Peerkanal ermöglicht die Entwicklung von mehrparteienanwendungen mithilfe von WCF.</span><span class="sxs-lookup"><span data-stu-id="29eb8-190">A peer channel enables development of multiparty applications using WCF.</span></span> <span data-ttu-id="29eb8-191">Mehrparteienmessaging tritt im Kontext eines Netzes auf.</span><span class="sxs-lookup"><span data-stu-id="29eb8-191">Multiparty messaging occurs in the context of a mesh.</span></span> <span data-ttu-id="29eb8-192">Netze werden mit einem Namen identifiziert, den Knoten verknüpfen können.</span><span class="sxs-lookup"><span data-stu-id="29eb8-192">Meshes are identified by a name that nodes can join.</span></span> <span data-ttu-id="29eb8-193">Jeder Knoten im Peerkanal erstellt einen TCP-Listener an einem vom Benutzer angegebenen Anschluss und stellt Verbindungen mit anderen Knoten im Netz her, um die Flexibilität zu sichern.</span><span class="sxs-lookup"><span data-stu-id="29eb8-193">Each node in the peer channel creates a TCP listener at a user-specified port and establishes connections with other nodes in the mesh to ensure resiliency.</span></span> <span data-ttu-id="29eb8-194">Für diese Verbindungen tauschen Knoten auch bestimmte Daten wie die Listeneradresse und die IP-Adresse des Computers mit anderen Knoten im Netz aus.</span><span class="sxs-lookup"><span data-stu-id="29eb8-194">To connect to other nodes in the mesh, nodes also exchange some data, including the listener address and the machine's IP addresses, with other nodes in the mesh.</span></span> <span data-ttu-id="29eb8-195">Innerhalb des Netzes gesendete Nachrichten können Sicherheitsinformationen enthalten, die sich auf den Absender beziehen, um Nachrichtenspoofing und -manipulation zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="29eb8-195">Messages sent around in the mesh can contain security information that pertains to the sender to prevent message spoofing and tampering.</span></span>  
  
 <span data-ttu-id="29eb8-196">Auf dem Computer des Endbenutzers werden keine persönlichen Informationen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="29eb8-196">No personal information is stored on the end-user's machine.</span></span>  
  
## <a name="it-professional-experience"></a><span data-ttu-id="29eb8-197">Arbeit von IT-Fachleuten</span><span class="sxs-lookup"><span data-stu-id="29eb8-197">IT Professional Experience</span></span>  
  
### <a name="tracing"></a><span data-ttu-id="29eb8-198">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="29eb8-198">Tracing</span></span>  
 <span data-ttu-id="29eb8-199">Die Diagnosefunktion der WCF-Infrastruktur protokolliert Nachrichten, die über den Transport und Dienstebenen Ausführen-Modell, und die Aktivitäten und Ereignisse im Zusammenhang mit diesen Nachrichten übergeben.</span><span class="sxs-lookup"><span data-stu-id="29eb8-199">The diagnostics feature of the WCF infrastructure logs messages that pass through the transport and service model layers, and the activities and events associated with these messages.</span></span> <span data-ttu-id="29eb8-200">Diese Funktion ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="29eb8-200">This feature is turned off by default.</span></span> <span data-ttu-id="29eb8-201">Mithilfe der Anwendungskonfigurationsdatei aktiviert und Verhalten für die Ablaufverfolgung kann mithilfe des WCF WMI-Anbieters zur Laufzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-201">It is enabled using the application’s configuration file and the tracing behavior may be modified using the WCF WMI provider at run time.</span></span> <span data-ttu-id="29eb8-202">Wenn das Feature aktiviert ist, gibt die Ablaufverfolgungsinfrastruktur eine Diagnoseablaufverfolgung mit Nachrichten, Aktivitäten und Verarbeitungsereignissen an konfigurierte Listener aus.</span><span class="sxs-lookup"><span data-stu-id="29eb8-202">When enabled, the tracing infrastructure emits a diagnostic trace that contains messages, activities, and processing events to configured listeners.</span></span> <span data-ttu-id="29eb8-203">Format und Speicherort der Ausgabe werden durch die Listener-Konfigurationsauswahl des Administrators bestimmt; normalerweise ist es eine Datei im XML-Format.</span><span class="sxs-lookup"><span data-stu-id="29eb8-203">The format and location of the output are determined by the administrator’s listener configuration choices, but is typically an XML formatted file.</span></span> <span data-ttu-id="29eb8-204">Der Administrator ist verantwortlich für das Festlegen der Zugriffssteuerungsliste (ACL) für die Ablaufverfolgungsdateien.</span><span class="sxs-lookup"><span data-stu-id="29eb8-204">The administrator is responsible for setting the access control list (ACL) on the trace files.</span></span> <span data-ttu-id="29eb8-205">Insbesondere beim Hosten durch WAS (Windows Activation System) muss der Administrator sicherstellen, dass die Dateien nicht im öffentlichen virtuellen Stammverzeichnis befinden, falls dies nicht gewünscht ist.</span><span class="sxs-lookup"><span data-stu-id="29eb8-205">In particular, when hosted by Windows Activation System (WAS), the administrator should make sure the files are not served from the public virtual root directory if that is not desired.</span></span>  
  
 <span data-ttu-id="29eb8-206">Es gibt zwei Typen von Ablaufverfolgung, Nachrichtenprotokollierung und Dienstmodell-Diagnoseablaufverfolgung, die im folgenden Abschnitt beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-206">There are two types of tracing: Message logging and Service Model diagnostic tracing, described in the following section.</span></span> <span data-ttu-id="29eb8-207">Jeder Typ wird über seine eigene Ablaufverfolgungsquelle konfiguriert: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> und <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="29eb8-207">Each type is configured through its own trace source: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> and <xref:System.ServiceModel>.</span></span> <span data-ttu-id="29eb8-208">Beide Protokollierungs-Ablaufverfolgungsquellen erfassen Daten, die lokale Daten der Anwendung sind.</span><span class="sxs-lookup"><span data-stu-id="29eb8-208">Both of these logging trace sources capture data that is local to the application.</span></span>  
  
### <a name="message-logging"></a><span data-ttu-id="29eb8-209">Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="29eb8-209">Message Logging</span></span>  
 <span data-ttu-id="29eb8-210">Die Ablaufverfolgungsquelle für die Nachrichtenprotokollierung (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) ermöglicht einem Administrator das Protokollieren der Nachrichten, die das System durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="29eb8-210">The message logging trace source (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) allows an administrator to log the messages that flow through the system.</span></span> <span data-ttu-id="29eb8-211">Über die Konfiguration kann der Benutzer entscheiden, ob ganze Nachrichten oder nur Nachrichtenheader protokolliert werden, ob die Protokollierung auf der Transport- und/oder der Dienstmodellebene erfolgt und ob falsch formatierte Nachrichten erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-211">Through configuration, the user may decide to log entire messages or message headers only, whether to log at the transport and/or service model layers, and whether to include malformed messages.</span></span> <span data-ttu-id="29eb8-212">Außerdem kann der Benutzer die Filterung konfigurieren, um einzuschränken, welche Nachrichten protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-212">Also, the user may configure filtering to restrict which messages are logged.</span></span>  
  
 <span data-ttu-id="29eb8-213">Standardmäßig ist die Nachrichtenprotokollierung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="29eb8-213">By default, message logging is disabled.</span></span> <span data-ttu-id="29eb8-214">Der Administrator auf dem lokalen Computer kann verhindern, dass der Administrator auf Anwendungsebene die Nachrichtenprotokollierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="29eb8-214">The local machine administrator can prevent the application-level administrator from turning message logging on.</span></span>  
  
#### <a name="encrypted-and-decrypted-message-logging"></a><span data-ttu-id="29eb8-215">Verschlüsselte und entschlüsselte Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="29eb8-215">Encrypted and Decrypted Message Logging</span></span>  
 <span data-ttu-id="29eb8-216">Nachrichten werden wie in den folgenden Begriffen beschrieben protokolliert, verschlüsselt oder entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="29eb8-216">Messages are logged, encrypted, or decrypted, as described in the following terms.</span></span>  
  
 <span data-ttu-id="29eb8-217">Transportprotokollierung</span><span class="sxs-lookup"><span data-stu-id="29eb8-217">Transport Logging</span></span>  
 <span data-ttu-id="29eb8-218">Protokolliert auf der Transportebene empfangene und gesendete Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="29eb8-218">Logs messages received and sent at the transport level.</span></span> <span data-ttu-id="29eb8-219">Diese Nachrichten enthalten alle Header und werden möglicherweise vor dem Versenden und beim Empfangen verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="29eb8-219">These messages contain all headers, and may be encrypted before being sent on the wire and when being received.</span></span>  
  
 <span data-ttu-id="29eb8-220">Wenn Nachrichten vor dem Versenden und beim Empfangen verschlüsselt werden, werden sie auch verschlüsselt protokolliert.</span><span class="sxs-lookup"><span data-stu-id="29eb8-220">If messages are encrypted before being sent on the wire and when they are received, they are logged encrypted as well.</span></span> <span data-ttu-id="29eb8-221">Eine Ausnahme ist die Verwendung eines Sicherheitsprotokolls (HTTPS); die Nachrichten werden vor dem Senden und nach dem Empfangen entschlüsselt protokolliert, auch wenn sie beim Versenden verschlüsselt sind.</span><span class="sxs-lookup"><span data-stu-id="29eb8-221">An exception is when a security protocol is used (https): they are then logged decrypted before being sent and after being received even if they are encrypted on the wire.</span></span>  
  
 <span data-ttu-id="29eb8-222">Dienstprotokollierung</span><span class="sxs-lookup"><span data-stu-id="29eb8-222">Service Logging</span></span>  
 <span data-ttu-id="29eb8-223">Protokolliert auf der Dienstmodellebene empfangene oder gesendete Nachrichten nach der Kanalheader-Verarbeitung, unmittelbar vor und nach der Eingabe von Benutzercode.</span><span class="sxs-lookup"><span data-stu-id="29eb8-223">Logs messages received or sent at the service model level, after channel header processing has occurred, just before and after entering user code.</span></span>  
  
 <span data-ttu-id="29eb8-224">Auf dieser Ebene protokollierte Nachrichten werden entschlüsselt, auch wenn sie für die Übertragung gesichert und verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-224">Messages logged at this level are decrypted even if they were secured and encrypted on the wire.</span></span>  
  
 <span data-ttu-id="29eb8-225">Protokollierung falsch formatierter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="29eb8-225">Malformed Message Logging</span></span>  
 <span data-ttu-id="29eb8-226">Protokolliert Meldungen, die die WCF-Infrastruktur zu verstehen oder verarbeitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="29eb8-226">Logs messages that the WCF infrastructure cannot understand or process.</span></span>  
  
 <span data-ttu-id="29eb8-227">Nachrichten werden unverändert protokolliert, d. h. verschlüsselt oder nicht verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="29eb8-227">Messages are logged as-is, that is, encrypted or not</span></span>  
  
 <span data-ttu-id="29eb8-228">Wenn Meldungen, in protokolliert werden entfernt entschlüsselter oder unverschlüsselter Form standardmäßig WCF Sicherheitsschlüssel und mögliche persönliche Informationen aus den Nachrichten vor dem protokollieren.</span><span class="sxs-lookup"><span data-stu-id="29eb8-228">When messages are logged in decrypted or unencrypted form, by default WCF removes security keys and potentially personal information from the messages before logging them.</span></span> <span data-ttu-id="29eb8-229">In den nächsten Abschnitten wird beschrieben, welche Informationen wann entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-229">The next sections describe what information is removed, and when.</span></span> <span data-ttu-id="29eb8-230">Der Computeradministrator und der Anwendungsbereitsteller müssen bestimmte Konfigurationsschritte durchführen, um das Standardverhalten so zu ändern, dass Schlüssel und mögliche persönliche Informationen protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-230">The machine administrator and application deployer must both take certain configuration actions to change the default behavior to log keys and potentially personal information.</span></span>  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="29eb8-231">Aus Nachrichtenheadern bei der Protokollierung entschlüsselter/unverschlüsselter Nachrichten entfernte Informationen</span><span class="sxs-lookup"><span data-stu-id="29eb8-231">Information Removed from Message Headers When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="29eb8-232">Wenn Nachrichten in entschlüsselter/unverschlüsselter Form protokolliert werden, werden standardmäßig vor dem Protokollieren Sicherheitsschlüssel und mögliche persönliche Informationen aus Nachrichtenheadern und Nachrichtentext entfernt.</span><span class="sxs-lookup"><span data-stu-id="29eb8-232">When messages are logged in decrypted/unencrypted form, security keys and potentially personal information are removed by default from message headers and message bodies before they are logged.</span></span> <span data-ttu-id="29eb8-233">Die folgende Liste zeigt die WCF-Schlüssel und mögliche persönliche Informationen betrachtet.</span><span class="sxs-lookup"><span data-stu-id="29eb8-233">The following list shows what WCF considers keys and potentially personal information.</span></span>  
  
 <span data-ttu-id="29eb8-234">Schlüssel, die entfernt werden:</span><span class="sxs-lookup"><span data-stu-id="29eb8-234">Keys that are removed:</span></span>  
  
 <span data-ttu-id="29eb8-235">\- Für Xmlns:wst = "http://schemas.xmlsoap.org/ws/2004/04/trust" und Xmlns:wst = "http://schemas.xmlsoap.org/ws/2005/02/trust"</span><span class="sxs-lookup"><span data-stu-id="29eb8-235">\- For xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"</span></span>  
  
 <span data-ttu-id="29eb8-236">wst:BinarySecret</span><span class="sxs-lookup"><span data-stu-id="29eb8-236">wst:BinarySecret</span></span>  
  
 <span data-ttu-id="29eb8-237">wst:Entropy</span><span class="sxs-lookup"><span data-stu-id="29eb8-237">wst:Entropy</span></span>  
  
 <span data-ttu-id="29eb8-238">\- Für Xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" und Xmlns:wsse = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="29eb8-238">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="29eb8-239">wsse:Password</span><span class="sxs-lookup"><span data-stu-id="29eb8-239">wsse:Password</span></span>  
  
 <span data-ttu-id="29eb8-240">wsse:Nonce</span><span class="sxs-lookup"><span data-stu-id="29eb8-240">wsse:Nonce</span></span>  
  
 <span data-ttu-id="29eb8-241">Mögliche persönliche Informationen, die entfernt werden:</span><span class="sxs-lookup"><span data-stu-id="29eb8-241">Potentially personal information that is removed:</span></span>  
  
 <span data-ttu-id="29eb8-242">\- Für Xmlns:wsse = "http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" und Xmlns:wsse = "http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span><span class="sxs-lookup"><span data-stu-id="29eb8-242">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="29eb8-243">wsse:Username</span><span class="sxs-lookup"><span data-stu-id="29eb8-243">wsse:Username</span></span>  
  
 <span data-ttu-id="29eb8-244">wsse:BinarySecurityToken</span><span class="sxs-lookup"><span data-stu-id="29eb8-244">wsse:BinarySecurityToken</span></span>  
  
 <span data-ttu-id="29eb8-245">\- Für xmlns = "Urn: Oasis: Namen: Tc: SAML:1.0:assertion" werden die Objekte in Fettschrift angezeigt (siehe unten) entfernt:</span><span class="sxs-lookup"><span data-stu-id="29eb8-245">\- For xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" the items in bold (below) are removed:</span></span>  
  
 <span data-ttu-id="29eb8-246">\<Assertion</span><span class="sxs-lookup"><span data-stu-id="29eb8-246">\<Assertion</span></span>  
  
 <span data-ttu-id="29eb8-247">MajorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="29eb8-247">MajorVersion="1"</span></span>  
  
 <span data-ttu-id="29eb8-248">MinorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="29eb8-248">MinorVersion="1"</span></span>  
  
 <span data-ttu-id="29eb8-249">AssertionId="[ID]"</span><span class="sxs-lookup"><span data-stu-id="29eb8-249">AssertionId="[ID]"</span></span>  
  
 <span data-ttu-id="29eb8-250">Issuer="[string]"</span><span class="sxs-lookup"><span data-stu-id="29eb8-250">Issuer="[string]"</span></span>  
  
 <span data-ttu-id="29eb8-251">IssueInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="29eb8-251">IssueInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="29eb8-252">\<Bedingungen NotBefore = "[" DateTime "]" NotOnOrAfter "DateTime" = ></span><span class="sxs-lookup"><span data-stu-id="29eb8-252">\<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]"></span></span>  
  
 <span data-ttu-id="29eb8-253">\<AudienceRestrictionCondition></span><span class="sxs-lookup"><span data-stu-id="29eb8-253">\<AudienceRestrictionCondition></span></span>  
  
 <span data-ttu-id="29eb8-254">\<Zielgruppe > [Uri]\</Audience > +</span><span class="sxs-lookup"><span data-stu-id="29eb8-254">\<Audience>[uri]\</Audience>+</span></span>  
  
 <span data-ttu-id="29eb8-255">\</AudienceRestrictionCondition>\*</span><span class="sxs-lookup"><span data-stu-id="29eb8-255">\</AudienceRestrictionCondition>\*</span></span>  
  
 <span data-ttu-id="29eb8-256">\<DoNotCacheCondition / > \*</span><span class="sxs-lookup"><span data-stu-id="29eb8-256">\<DoNotCacheCondition />\*</span></span>  
  
 <span data-ttu-id="29eb8-257"><\!--abstrakten Basistyp.</span><span class="sxs-lookup"><span data-stu-id="29eb8-257"><\!-- abstract base type</span></span>  
  
 <span data-ttu-id="29eb8-258">\<Bedingung / > \*</span><span class="sxs-lookup"><span data-stu-id="29eb8-258">\<Condition />\*</span></span>  
  
 -->  
  
 <span data-ttu-id="29eb8-259">\</ Bedingungen >?</span><span class="sxs-lookup"><span data-stu-id="29eb8-259">\</Conditions>?</span></span>  
  
 <span data-ttu-id="29eb8-260">\<Ratschläge ></span><span class="sxs-lookup"><span data-stu-id="29eb8-260">\<Advice></span></span>  
  
 <span data-ttu-id="29eb8-261">\<AssertionIDReference > [ID]\</AssertionIDReference > \*</span><span class="sxs-lookup"><span data-stu-id="29eb8-261">\<AssertionIDReference>[ID]\</AssertionIDReference>\*</span></span>  
  
 <span data-ttu-id="29eb8-262">\<Assertion > [Assertion]\</Assertion > \*</span><span class="sxs-lookup"><span data-stu-id="29eb8-262">\<Assertion>[assertion]\</Assertion>\*</span></span>  
  
 <span data-ttu-id="29eb8-263">[any]\*</span><span class="sxs-lookup"><span data-stu-id="29eb8-263">[any]\*</span></span>  
  
 <span data-ttu-id="29eb8-264">\</-Meldung >?</span><span class="sxs-lookup"><span data-stu-id="29eb8-264">\</Advice>?</span></span>  
  
 <span data-ttu-id="29eb8-265"><\!--Abstrakter Basistypen</span><span class="sxs-lookup"><span data-stu-id="29eb8-265"><\!-- Abstract base types</span></span>  
  
 <span data-ttu-id="29eb8-266">\<Anweisung / > \*</span><span class="sxs-lookup"><span data-stu-id="29eb8-266">\<Statement />\*</span></span>  
  
 <span data-ttu-id="29eb8-267">\<SubjectStatement ></span><span class="sxs-lookup"><span data-stu-id="29eb8-267">\<SubjectStatement></span></span>  
  
 <span data-ttu-id="29eb8-268">\<Betreff ></span><span class="sxs-lookup"><span data-stu-id="29eb8-268">\<Subject></span></span>  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 <span data-ttu-id="29eb8-269">\<SubjectConfirmation ></span><span class="sxs-lookup"><span data-stu-id="29eb8-269">\<SubjectConfirmation></span></span>  
  
 <span data-ttu-id="29eb8-270">\<ConfirmationMethod > [AnyUri]\</ConfirmationMethod > +</span><span class="sxs-lookup"><span data-stu-id="29eb8-270">\<ConfirmationMethod>[anyUri]\</ConfirmationMethod>+</span></span>  
  
 <span data-ttu-id="29eb8-271">\<SubjectConfirmationData > [any]\</SubjectConfirmationData >?</span><span class="sxs-lookup"><span data-stu-id="29eb8-271">\<SubjectConfirmationData>[any]\</SubjectConfirmationData>?</span></span>  
  
 <span data-ttu-id="29eb8-272">\<DS: KeyInfo >... \</ds:KeyInfo >?</span><span class="sxs-lookup"><span data-stu-id="29eb8-272">\<ds:KeyInfo>...\</ds:KeyInfo>?</span></span>  
  
 <span data-ttu-id="29eb8-273">\</ SubjectConfirmation >?</span><span class="sxs-lookup"><span data-stu-id="29eb8-273">\</SubjectConfirmation>?</span></span>  
  
 <span data-ttu-id="29eb8-274">\</ Betreff ></span><span class="sxs-lookup"><span data-stu-id="29eb8-274">\</Subject></span></span>  
  
 <span data-ttu-id="29eb8-275">\</ SubjectStatement > \*</span><span class="sxs-lookup"><span data-stu-id="29eb8-275">\</SubjectStatement>\*</span></span>  
  
 -->  
  
 <span data-ttu-id="29eb8-276">\<AuthenticationStatement</span><span class="sxs-lookup"><span data-stu-id="29eb8-276">\<AuthenticationStatement</span></span>  
  
 <span data-ttu-id="29eb8-277">AuthenticationMethod="[uri]"</span><span class="sxs-lookup"><span data-stu-id="29eb8-277">AuthenticationMethod="[uri]"</span></span>  
  
 <span data-ttu-id="29eb8-278">AuthenticationInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="29eb8-278">AuthenticationInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="29eb8-279">[Subject]</span><span class="sxs-lookup"><span data-stu-id="29eb8-279">[Subject]</span></span>  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 <span data-ttu-id="29eb8-280"><AuthorityBinding</span><span class="sxs-lookup"><span data-stu-id="29eb8-280"><AuthorityBinding</span></span>  
  
 <span data-ttu-id="29eb8-281">AuthorityKind="[QName]"</span><span class="sxs-lookup"><span data-stu-id="29eb8-281">AuthorityKind="[QName]"</span></span>  
  
 <span data-ttu-id="29eb8-282">Location="[uri]"</span><span class="sxs-lookup"><span data-stu-id="29eb8-282">Location="[uri]"</span></span>  
  
 <span data-ttu-id="29eb8-283">Binding="[uri]"</span><span class="sxs-lookup"><span data-stu-id="29eb8-283">Binding="[uri]"</span></span>  
  
 />*  
  
 <span data-ttu-id="29eb8-284">\</ AuthenticationStatement > \*</span><span class="sxs-lookup"><span data-stu-id="29eb8-284">\</AuthenticationStatement>\*</span></span>  
  
 <span data-ttu-id="29eb8-285">\<AttributeStatement></span><span class="sxs-lookup"><span data-stu-id="29eb8-285">\<AttributeStatement></span></span>  
  
 <span data-ttu-id="29eb8-286">[Subject]</span><span class="sxs-lookup"><span data-stu-id="29eb8-286">[Subject]</span></span>  
  
 <span data-ttu-id="29eb8-287">\<Attribut</span><span class="sxs-lookup"><span data-stu-id="29eb8-287">\<Attribute</span></span>  
  
 <span data-ttu-id="29eb8-288">AttributeName="[string]"</span><span class="sxs-lookup"><span data-stu-id="29eb8-288">AttributeName="[string]"</span></span>  
  
 <span data-ttu-id="29eb8-289">AttributeNamespace="[uri]"</span><span class="sxs-lookup"><span data-stu-id="29eb8-289">AttributeNamespace="[uri]"</span></span>  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 <span data-ttu-id="29eb8-290">\</-Attribut > +</span><span class="sxs-lookup"><span data-stu-id="29eb8-290">\</Attribute>+</span></span>  
  
 <span data-ttu-id="29eb8-291">\</AttributeStatement>\*</span><span class="sxs-lookup"><span data-stu-id="29eb8-291">\</AttributeStatement>\*</span></span>  
  
 <span data-ttu-id="29eb8-292">\<AuthorizationDecisionStatement</span><span class="sxs-lookup"><span data-stu-id="29eb8-292">\<AuthorizationDecisionStatement</span></span>  
  
 <span data-ttu-id="29eb8-293">Resource="[uri]"</span><span class="sxs-lookup"><span data-stu-id="29eb8-293">Resource="[uri]"</span></span>  
  
 <span data-ttu-id="29eb8-294">Entscheidung = "[zulassen&#124;Verweigern&#124;unbestimmten]"</span><span class="sxs-lookup"><span data-stu-id="29eb8-294">Decision="[Permit&#124;Deny&#124;Indeterminate]"</span></span>  
  
 >  
  
 <span data-ttu-id="29eb8-295">[Subject]</span><span class="sxs-lookup"><span data-stu-id="29eb8-295">[Subject]</span></span>  
  
 <span data-ttu-id="29eb8-296">\<Aktion-Namespace = "[Uri]" > [String] \< /Action > +</span><span class="sxs-lookup"><span data-stu-id="29eb8-296">\<Action Namespace="[uri]">[string]\</Action>+</span></span>  
  
 <span data-ttu-id="29eb8-297">\<Beweise ></span><span class="sxs-lookup"><span data-stu-id="29eb8-297">\<Evidence></span></span>  
  
 <span data-ttu-id="29eb8-298">\<AssertionIDReference > [ID]\</AssertionIDReference > +</span><span class="sxs-lookup"><span data-stu-id="29eb8-298">\<AssertionIDReference>[ID]\</AssertionIDReference>+</span></span>  
  
 <span data-ttu-id="29eb8-299">\<Assertion > [Assertion]\</Assertion > +</span><span class="sxs-lookup"><span data-stu-id="29eb8-299">\<Assertion>[assertion]\</Assertion>+</span></span>  
  
 <span data-ttu-id="29eb8-300">\</ Beweis >?</span><span class="sxs-lookup"><span data-stu-id="29eb8-300">\</Evidence>?</span></span>  
  
 <span data-ttu-id="29eb8-301">\</AuthorizationDecisionStatement>\*</span><span class="sxs-lookup"><span data-stu-id="29eb8-301">\</AuthorizationDecisionStatement>\*</span></span>  
  
 <span data-ttu-id="29eb8-302">\</Assertion></span><span class="sxs-lookup"><span data-stu-id="29eb8-302">\</Assertion></span></span>  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="29eb8-303">Aus Nachrichtentext bei der Protokollierung entschlüsselter/unverschlüsselter Nachrichten entfernte Informationen</span><span class="sxs-lookup"><span data-stu-id="29eb8-303">Information Removed from Message Bodies When Logging Decrypted/Unencrypted Messages</span></span>  
 <span data-ttu-id="29eb8-304">Wie zuvor beschrieben, WCF entfernt Schlüssel und bekannte mögliche persönliche Informationen aus Nachrichtenheadern für Protokollierung entschlüsselter/unverschlüsselter Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="29eb8-304">As previously described, WCF removes keys and known potentially personal information from message headers for logged decrypted/unencrypted messages.</span></span> <span data-ttu-id="29eb8-305">Darüber hinaus entfällt WCF Schlüssel und bekannte mögliche persönliche Informationen aus Nachrichtentext für die Textelemente und Aktionen in der folgenden Liste, die sicherheitsmeldungen beim Schlüsselaustausch beschreiben.</span><span class="sxs-lookup"><span data-stu-id="29eb8-305">In addition, WCF removes keys and known potentially personal information from message bodies for the body elements and actions in the following list, which describe security messages involved in key exchange.</span></span>  
  
 <span data-ttu-id="29eb8-306">Für die folgenden Namespaces:</span><span class="sxs-lookup"><span data-stu-id="29eb8-306">For the following namespaces:</span></span>  
  
 <span data-ttu-id="29eb8-307">Xmlns:WST = "http://schemas.xmlsoap.org/ws/2004/04/trust" und Xmlns:wst = "http://schemas.xmlsoap.org/ws/2005/02/trust" (z. B., wenn keine Aktion verfügbar ist)</span><span class="sxs-lookup"><span data-stu-id="29eb8-307">xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" (for example, if no action available)</span></span>  
  
 <span data-ttu-id="29eb8-308">Informationen werden für diese Textelemente entfernt, die Schlüsselaustausch einschließen:</span><span class="sxs-lookup"><span data-stu-id="29eb8-308">Information is removed for these body elements, which involve key exchange:</span></span>  
  
 <span data-ttu-id="29eb8-309">wst:RequestSecurityToken</span><span class="sxs-lookup"><span data-stu-id="29eb8-309">wst:RequestSecurityToken</span></span>  
  
 <span data-ttu-id="29eb8-310">wst:RequestSecurityTokenResponse</span><span class="sxs-lookup"><span data-stu-id="29eb8-310">wst:RequestSecurityTokenResponse</span></span>  
  
 <span data-ttu-id="29eb8-311">wst:RequestSecurityTokenResponseCollection</span><span class="sxs-lookup"><span data-stu-id="29eb8-311">wst:RequestSecurityTokenResponseCollection</span></span>  
  
 <span data-ttu-id="29eb8-312">Informationen werden auch für jede der folgenden Aktionen entfernt:</span><span class="sxs-lookup"><span data-stu-id="29eb8-312">Information is also removed for each of the following Actions:</span></span>  
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Issue`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/Validate`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Amend`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Renew`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RST/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2005/02/trust/RSTR/SCT/Cancel`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RST/SCT-Amend`
  
- `http://schemas.xmlsoap.org/ws/2004/04/security/trust/RSTR/SCT-Amend`
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a><span data-ttu-id="29eb8-313">Aus anwendungsspezifischen Headern und Textdaten werden keine Informationen entfernt.</span><span class="sxs-lookup"><span data-stu-id="29eb8-313">No Information Is Removed from Application-specific Headers and Body Data</span></span>  
 <span data-ttu-id="29eb8-314">WCF verfolgt keine persönlichen Informationen in anwendungsspezifischen Headern (z. B. Abfragezeichenfolgen) oder Textdaten (z. B. Kreditkartennummer).</span><span class="sxs-lookup"><span data-stu-id="29eb8-314">WCF does not track personal information in application-specific headers (for example, query strings) or body data (for example, credit card number).</span></span>  
  
 <span data-ttu-id="29eb8-315">Bei aktivierter Nachrichtenprotokollierung sind persönliche Informationen in anwendungsspezifischen Headern und Textdaten unter Umständen in den Protokollen sichtbar.</span><span class="sxs-lookup"><span data-stu-id="29eb8-315">When message logging is on, personal information in application-specific headers and body information may be visible in the logs.</span></span> <span data-ttu-id="29eb8-316">Der Anwendungsbereitsteller ist für das Festlegen der ACLs für die Konfigurations- und Protokolldateien verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="29eb8-316">Again, the application deployer is responsible for setting the ACLs on the configuration and log files.</span></span> <span data-ttu-id="29eb8-317">Er kann auch die Protokollierung deaktivieren, wenn diese Informationen nicht sichtbar sein sollen, oder diese Informationen aus den Protokolldateien herausfiltern.</span><span class="sxs-lookup"><span data-stu-id="29eb8-317">He also can turn off logging if he does not want this information to be visible, or he may filter out this information from the log files after it is logged.</span></span>  
  
### <a name="service-model-tracing"></a><span data-ttu-id="29eb8-318">Dienstmodell-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="29eb8-318">Service Model Tracing</span></span>  
 <span data-ttu-id="29eb8-319">Die Dienstmodell-Ablaufverfolgungsquelle (<xref:System.ServiceModel>) aktiviert die Ablaufverfolgung von mit der Nachrichtenverarbeitung verknüpften Aktivitäten und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="29eb8-319">The Service Model trace source (<xref:System.ServiceModel>) enables tracing of activities and events related to message processing.</span></span> <span data-ttu-id="29eb8-320">Dieses Feature verwendet die .NET Framework-Diagnosefunktionalität von <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="29eb8-320">This feature uses the .NET Framework diagnostic functionality from <xref:System.Diagnostics>.</span></span> <span data-ttu-id="29eb8-321">Wie bei der <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>-Eigenschaft können der Speicherort und die ACL mit den Konfigurationsdateien der .NET Framework-Anwendung vom Benutzer konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-321">As with the <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> property, the location and its ACL are user-configurable using .NET Framework application configuration files.</span></span> <span data-ttu-id="29eb8-322">Wie bei der Nachrichtenprotokollierung wird der Speicherort der Datei immer konfiguriert, wenn der Administrator die Ablaufverfolgung aktiviert; der Administrator steuert also die ACL.</span><span class="sxs-lookup"><span data-stu-id="29eb8-322">As with message logging, the file location is always configured when the administrator enables tracing; thus, the administrator controls the ACL.</span></span>  
  
 <span data-ttu-id="29eb8-323">Ablaufverfolgungen enthalten Nachrichtenheader, wenn sich eine Nachricht im Gültigkeitsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="29eb8-323">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="29eb8-324">Dabei gilt die gleiche Regel für das Ausblenden möglicher persönlicher Informationen in Nachrichtenheadern wie im vorherigen Abschnitt: Die zuvor identifizierten persönlichen Informationen werden standardmäßig aus den Headern in Ablaufverfolgungen entfernt.</span><span class="sxs-lookup"><span data-stu-id="29eb8-324">The same rules for hiding potentially personal information in message headers in the previous section apply: the personal information previously identified is removed by default from the headers in traces.</span></span> <span data-ttu-id="29eb8-325">Der Computeradministrator und der Anwendungsbereitsteller müssen die Konfiguration ändern, damit mögliche persönliche Informationen protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-325">Both the machine administrator and the application deployer must modify the configuration in order to log potentially personal information.</span></span> <span data-ttu-id="29eb8-326">Allerdings werden in anwendungsspezifischen Headern enthaltene persönliche Informationen in Ablaufverfolgungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="29eb8-326">However, personal information contained in application-specific headers is logged in traces.</span></span> <span data-ttu-id="29eb8-327">Der Anwendungsbereitsteller ist für das Festlegen der ACLs für die Konfigurations- und Ablaufverfolgungsdateien verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="29eb8-327">The application deployer is responsible for setting the ACLs on the configuration and trace files.</span></span> <span data-ttu-id="29eb8-328">Er kann auch die Ablaufverfolgung deaktivieren, wenn diese Informationen nicht sichtbar sein sollen, oder diese Informationen nach der Protokollierung aus den Ablaufverfolgungsdateien herausfiltern.</span><span class="sxs-lookup"><span data-stu-id="29eb8-328">He also can turn off tracing if he does not want this information to be visible, or he can filter out this information from the trace files after it is logged.</span></span>  
  
 <span data-ttu-id="29eb8-329">Als Teil der Dienstmodell-Ablaufverfolgung verknüpfen eindeutige IDs (die als Aktivitäts-IDs bezeichnet werden, in der Regel eine GUID) unterschiedliche Aktivitäten, wenn eine Nachricht verschiedene Teile der Infrastruktur durchläuft.</span><span class="sxs-lookup"><span data-stu-id="29eb8-329">As part of ServiceModel Tracing, Unique IDs (called Activity IDs, and typically a GUID) link different activities together as a message flows through different parts of the infrastructure.</span></span>  
  
#### <a name="custom-trace-listeners"></a><span data-ttu-id="29eb8-330">Benutzerdefinierte Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="29eb8-330">Custom Trace Listeners</span></span>  
 <span data-ttu-id="29eb8-331">Sowohl für die Nachrichtenprotokollierung als auch die Ablaufverfolgung kann ein benutzerdefinierter Ablaufverfolgungslistener konfiguriert werden, der Ablaufverfolgungen und Nachrichten überträgt, z. B. an eine Remotedatenbank.</span><span class="sxs-lookup"><span data-stu-id="29eb8-331">For both message logging and tracing, a custom trace listener can be configured, which can send traces and messages on the wire (for example, to a remote database).</span></span> <span data-ttu-id="29eb8-332">Der Anwendungsbereitsteller ist für das Konfigurieren benutzerdefinierter Listener oder das Ermöglichen dieser Aktion durch Benutzer verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="29eb8-332">The application deployer is responsible for configuring custom listeners or enabling users to do so.</span></span> <span data-ttu-id="29eb8-333">Er ist außerdem für am Remotespeicherort verfügbar gemachte persönliche Informationen und für die korrekte Anwendung von ACLs auf diesen Speicherort verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="29eb8-333">He is also responsible for any personal information exposed at the remote location, and for properly applying ACLs to this location.</span></span>  
  
### <a name="other-features-for-it-professionals"></a><span data-ttu-id="29eb8-334">Andere Funktionen für IT-Fachleute</span><span class="sxs-lookup"><span data-stu-id="29eb8-334">Other features for IT Professionals</span></span>  
 <span data-ttu-id="29eb8-335">WCF bietet es sich um einen WMI-Anbieter, der die Konfigurationsinformationen des WCF-Infrastruktur über WMI (im Lieferumfang von Windows enthalten) verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="29eb8-335">WCF has a WMI provider that exposes the WCF infrastructure configuration information through WMI (shipped with Windows).</span></span> <span data-ttu-id="29eb8-336">Standardmäßig steht die WMI-Schnittstelle Administratoren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="29eb8-336">By default, the WMI interface is available to administrators.</span></span>  
  
 <span data-ttu-id="29eb8-337">WCF-Konfiguration verwendet die .NET Framework-Konfigurationsverfahren.</span><span class="sxs-lookup"><span data-stu-id="29eb8-337">WCF configuration uses the .NET Framework configuration mechanism.</span></span> <span data-ttu-id="29eb8-338">Die Konfigurationsdateien werden auf dem Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="29eb8-338">The configuration files are stored on the machine.</span></span> <span data-ttu-id="29eb8-339">Der Anwendungsentwickler und der Administrator erstellen die Konfigurationsdateien und die ACL für jede Anwendungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="29eb8-339">The application developer and the administrator create the configuration files and ACL for each of the application's requirements.</span></span> <span data-ttu-id="29eb8-340">Eine Konfigurationsdatei kann Endpunktadressen und Links zu Zertifikaten im Zertifikatspeicher enthalten.</span><span class="sxs-lookup"><span data-stu-id="29eb8-340">A configuration file can contain endpoint addresses and links to certificates in the certificate store.</span></span> <span data-ttu-id="29eb8-341">Mithilfe der Zertifikate können Anwendungsdaten zum Konfigurieren verschiedener Eigenschaften der von der Anwendung verwendeten Funktionen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-341">The certificates can be used to provide application data to configure various properties of the features used by the application.</span></span>  
  
 <span data-ttu-id="29eb8-342">WCF verwendet auch die prozesssicherungsfunktionalität von .NET Framework durch Aufrufen der <xref:System.Environment.FailFast%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="29eb8-342">WCF also uses the .NET Framework process dump functionality by calling the <xref:System.Environment.FailFast%2A> method.</span></span>  
  
### <a name="it-pro-tools"></a><span data-ttu-id="29eb8-343">Tools für IT-Fachleute</span><span class="sxs-lookup"><span data-stu-id="29eb8-343">IT Pro Tools</span></span>  
 <span data-ttu-id="29eb8-344">WCF bietet auch die folgenden IT professionelle Tools, die im Windows SDK ausgeliefert.</span><span class="sxs-lookup"><span data-stu-id="29eb8-344">WCF also provides the following IT professional tools, which ship in the Windows SDK.</span></span>  
  
#### <a name="svctraceviewerexe"></a><span data-ttu-id="29eb8-345">SvcTraceViewer.exe</span><span class="sxs-lookup"><span data-stu-id="29eb8-345">SvcTraceViewer.exe</span></span>  
 <span data-ttu-id="29eb8-346">Der Viewer zeigt die WCF-Ablaufverfolgungsdateien.</span><span class="sxs-lookup"><span data-stu-id="29eb8-346">The viewer displays WCF trace files.</span></span> <span data-ttu-id="29eb8-347">Der Viewer zeigt an, welche Daten in den Ablaufverfolgungen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="29eb8-347">The viewer shows whatever information is contained in the traces.</span></span>  
  
#### <a name="svcconfigeditorexe"></a><span data-ttu-id="29eb8-348">SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="29eb8-348">SvcConfigEditor.exe</span></span>  
 <span data-ttu-id="29eb8-349">Der Editor ermöglicht den Benutzer zum Erstellen und Bearbeiten von WCF-Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="29eb8-349">The editor allows the user to create and edit WCF configuration files.</span></span> <span data-ttu-id="29eb8-350">Der Editor zeigt an, welche Daten in den Konfigurationsdateien enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="29eb8-350">The editor shows whatever information is contained in the configuration files.</span></span> <span data-ttu-id="29eb8-351">Für die gleiche Aufgabe kann auch ein Text-Editor verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-351">The same task can be accomplished with a text editor.</span></span>  
  
#### <a name="servicemodelreg"></a><span data-ttu-id="29eb8-352">ServiceModel_Reg</span><span class="sxs-lookup"><span data-stu-id="29eb8-352">ServiceModel_Reg</span></span>  
 <span data-ttu-id="29eb8-353">Mit diesem Tool kann der Benutzer ServiceModel-Installationen auf einem Computer verwalten.</span><span class="sxs-lookup"><span data-stu-id="29eb8-353">This tool allows the user to manage ServiceModel installs on a machine.</span></span> <span data-ttu-id="29eb8-354">Das Tool zeigt statusmeldungen in einem Konsolenfenster ein, wenn es ausgeführt wird und in den Prozess möglicherweise Informationen zur Konfiguration der WCF-Installation angezeigt.</span><span class="sxs-lookup"><span data-stu-id="29eb8-354">The tool displays status messages in a console window when it runs and, in the process, may display information about the configuration of the WCF installation.</span></span>  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a><span data-ttu-id="29eb8-355">WSATConfig.exe und WSATUI.dll</span><span class="sxs-lookup"><span data-stu-id="29eb8-355">WSATConfig.exe and WSATUI.dll</span></span>  
 <span data-ttu-id="29eb8-356">Mit diesen Tools können IT-Experten interoperable WS-AtomicTransaction Netzwerkunterstützung in WCF zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="29eb8-356">These tools allow IT Professionals to configure interoperable WS-AtomicTransaction network support in WCF.</span></span> <span data-ttu-id="29eb8-357">Mithilfe der Tools kann der Benutzer die Werte der in der Registrierung gespeicherten am häufigsten verwendeten WS-AtomicTransaction-Einstellungen anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="29eb8-357">The tools display and allow the user to change the values of the most commonly used WS-AtomicTransaction settings stored in the registry.</span></span>  
  
## <a name="cross-cutting-features"></a><span data-ttu-id="29eb8-358">Querschnittliche Features</span><span class="sxs-lookup"><span data-stu-id="29eb8-358">Cross-cutting Features</span></span>  
 <span data-ttu-id="29eb8-359">Die folgenden Features sind querschnittliche Features.</span><span class="sxs-lookup"><span data-stu-id="29eb8-359">The following features are cross-cutting.</span></span> <span data-ttu-id="29eb8-360">Das heißt, sie können mit allen vorangehenden Features zusammengesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-360">That is, they can be composed with any of the preceding features.</span></span>  
  
### <a name="service-framework"></a><span data-ttu-id="29eb8-361">Dienstframework</span><span class="sxs-lookup"><span data-stu-id="29eb8-361">Service Framework</span></span>  
 <span data-ttu-id="29eb8-362">Header können eine Instanz-ID enthalten; dies ist eine GUID, die eine Nachricht einer Instanz einer CLR-Klasse zuordnet.</span><span class="sxs-lookup"><span data-stu-id="29eb8-362">Headers can contain an instance ID, which is a GUID that associates a message with an instance of a CLR class.</span></span>  
  
 <span data-ttu-id="29eb8-363">Die WSDL (Web Services Description Language) enthält eine Definition des Anschlusses.</span><span class="sxs-lookup"><span data-stu-id="29eb8-363">The Web Services Description Language (WSDL) contains a definition of the port.</span></span> <span data-ttu-id="29eb8-364">Jeder Anschluss verfügt über eine Endpunktadresse und eine Bindung, die die von der Anwendung verwendeten Dienste darstellt.</span><span class="sxs-lookup"><span data-stu-id="29eb8-364">Each port has an endpoint address and a binding that represents the services used by the application.</span></span> <span data-ttu-id="29eb8-365">Das Verfügbarmachen der WSDL kann mithilfe der Konfiguration deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="29eb8-365">Exposing WSDL can be turned off using configuration.</span></span> <span data-ttu-id="29eb8-366">Auf dem Computer werden keine Informationen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="29eb8-366">No information is retained on the machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29eb8-367">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29eb8-367">See Also</span></span>  
 [<span data-ttu-id="29eb8-368">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="29eb8-368">Windows Communication Foundation</span></span>](https://msdn.microsoft.com/library/fd327ade-0260-4c40-adbe-b74645ba3277)  
 [<span data-ttu-id="29eb8-369">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="29eb8-369">Security</span></span>](../../../docs/framework/wcf/feature-details/security.md)
