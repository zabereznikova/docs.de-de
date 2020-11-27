---
title: Windows Communication Foundation-Datenschutzinformationen
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Communication Foundation, privacy information
- WCF, privacy information
- privacy information [WCF]
ms.assetid: c9553724-f3e7-45cb-9ea5-450a22d309d9
ms.openlocfilehash: 5ecd1c39a4ad6a146c734aab8349c5caa4212662
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249942"
---
# <a name="windows-communication-foundation-privacy-information"></a><span data-ttu-id="e7ec3-102">Windows Communication Foundation-Datenschutzinformationen</span><span class="sxs-lookup"><span data-stu-id="e7ec3-102">Windows Communication Foundation Privacy Information</span></span>

<span data-ttu-id="e7ec3-103">Microsoft ist bestrebt, den Schutz von Endbenutzern zu schützen.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-103">Microsoft is committed to protecting end user privacy.</span></span> <span data-ttu-id="e7ec3-104">Wenn Sie eine Anwendung mit Windows Communication Foundation (WCF), Version 3,0, erstellen, wirkt sich die Anwendung möglicherweise auf den Datenschutz der Endbenutzer aus.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-104">When you build an application using Windows Communication Foundation (WCF), version 3.0, your application may impact your end users' privacy.</span></span> <span data-ttu-id="e7ec3-105">Die Anwendung erfasst z. B. unter Umständen explizit Kontaktinformationen des Benutzers oder fordert Informationen an und sendet diese über das Internet an Ihre Website.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-105">For example, your application may explicitly collect user contact information, or it may request or send information over the Internet to your Web site.</span></span> <span data-ttu-id="e7ec3-106">Wenn Sie Microsoft-Technologie in Ihre Anwendung einbetten, kann sich das Verhalten dieser Technologie ebenfalls auf den Datenschutz auswirken.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-106">If you embed Microsoft technology in your application, that technology may have its own behavior that might affect privacy.</span></span> <span data-ttu-id="e7ec3-107">WCF sendet keine Informationen von Ihrer Anwendung an Microsoft, es sei denn, Sie oder der Endbenutzer haben diese an uns gesendet.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-107">WCF does not send any information to Microsoft from your application unless you or the end user choose to send it to us.</span></span>  
  
## <a name="wcf-in-brief"></a><span data-ttu-id="e7ec3-108">WCF in Kürze</span><span class="sxs-lookup"><span data-stu-id="e7ec3-108">WCF in Brief</span></span>  

 <span data-ttu-id="e7ec3-109">WCF ist ein verteiltes Messaging Framework, das das Microsoft .NET Framework verwendet, das Entwicklern das Erstellen verteilter Anwendungen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-109">WCF is a distributed messaging framework using the Microsoft .NET Framework that allows developers to build distributed applications.</span></span> <span data-ttu-id="e7ec3-110">Zwischen zwei Anwendungen übermittelte Nachrichten enthalten Header- und Textinformationen.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-110">Messages communicated between two applications contain header and body information.</span></span>  
  
 <span data-ttu-id="e7ec3-111">Header können je nach von der Anwendung verwendeten Diensten unter anderem Meldungsrouting, Sicherheitsinformationen und Transaktionen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-111">Headers may contain message routing, security information, transactions, and more depending on the services used by the application.</span></span> <span data-ttu-id="e7ec3-112">Nachrichten werden in der Regel standardmäßig verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-112">Messages are typically encrypted by default.</span></span> <span data-ttu-id="e7ec3-113">Eine Ausnahme ist die Verwendung der `BasicHttpBinding`, die für nicht gesicherte, ältere Webdienste konzipiert wurde.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-113">The one exception is when using the `BasicHttpBinding`, which was designed for use with non-secured, legacy Web services.</span></span> <span data-ttu-id="e7ec3-114">Als Anwendungs-Designer sind Sie für den abschließenden Entwurf verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-114">As the application designer, you are responsible for the final design.</span></span> <span data-ttu-id="e7ec3-115">Nachrichten im SOAP-Text enthalten anwendungsspezifische Daten. Allerdings können diese Daten, z. b. Anwendungs definierte persönliche Informationen, mithilfe von WCF-Verschlüsselungs-oder Vertraulichkeits Features gesichert werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-115">Messages in the SOAP body contain application-specific data; however, this data, such as application-defined personal information, can be secured by using WCF encryption or confidentiality features.</span></span> <span data-ttu-id="e7ec3-116">In den folgenden Abschnitten werden die Funktionen beschrieben, die sich auf den Datenschutz auswirken können.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-116">The following sections describe the features that potentially impact privacy.</span></span>  
  
## <a name="messaging"></a><span data-ttu-id="e7ec3-117">Messaging</span><span class="sxs-lookup"><span data-stu-id="e7ec3-117">Messaging</span></span>  

 <span data-ttu-id="e7ec3-118">Jede WCF-Nachricht verfügt über einen Adress Header, der das Nachrichten Ziel angibt, und wo die Antwort gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-118">Each WCF message has an address header that specifies the message destination and where the reply should go.</span></span>  
  
 <span data-ttu-id="e7ec3-119">Die Adresskomponente einer Endpunktadresse ist ein URI (Uniform Resource Identifier), der den Endpunkt identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-119">The address component of an endpoint address is a Uniform Resource Identifier (URI) that identifies the endpoint.</span></span> <span data-ttu-id="e7ec3-120">Die Adresse kann eine Netzwerkadresse oder eine logische Adresse sein.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-120">The address can be a network address or a logical address.</span></span> <span data-ttu-id="e7ec3-121">Die Adresse kann den Computernamen (Hostname, vollqualifizierter Domänenname) und eine IP-Adresse einschließen.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-121">The address may include machine name (hostname, fully qualified domain name) and an IP address.</span></span> <span data-ttu-id="e7ec3-122">Die Endpunktadresse kann außerdem eine GUID (Globally Unique Identifier) oder eine Auflistung von GUIDs für die temporäre Adressierung zum Ermitteln jeder Adresse enthalten.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-122">The endpoint address may also contain a globally unique identifier (GUID), or a collection of GUIDs for temporary addressing used to discern each address.</span></span> <span data-ttu-id="e7ec3-123">Jede Nachricht enthält eine Nachrichten-ID, die eine GUID ist.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-123">Each message contains a message ID that is a GUID.</span></span> <span data-ttu-id="e7ec3-124">Dieses Feature folgt dem WS-Addressierungs-Verweisstandard.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-124">This feature follows the WS-Addressing reference standard.</span></span>  
  
 <span data-ttu-id="e7ec3-125">Die WCF-Messaging Schicht schreibt keine persönlichen Informationen auf den lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-125">The WCF messaging layer does not write any personal information to the local machine.</span></span> <span data-ttu-id="e7ec3-126">Sie kann jedoch persönliche Daten auf der Netzwerkebene weitergeben, wenn ein Diensteentwickler einen Dienst erstellt hat, der solche Informationen verfügbar macht (z. B. durch das Verwenden des Namens einer Person in einem Endpunktnamen oder durch das Aufnehmen persönlicher Daten in die WSDL des Endpunkts, ohne dass Clients zum Zugriff auf die WSDL HTTPS verwenden müssen).</span><span class="sxs-lookup"><span data-stu-id="e7ec3-126">However, it might propagate personal information at the network level if a service developer has created a service that exposes such information (for example, by using a person's name in an endpoint name, or including personal information in the endpoint's Web Services Description Language but not requiring clients to use https to access the WSDL).</span></span> <span data-ttu-id="e7ec3-127">Wenn ein Entwickler das [Service Model Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) -Tool für einen Endpunkt ausführt, der persönliche Informationen verfügbar macht, könnte die Ausgabe des Tools diese Informationen enthalten, und die Ausgabedatei wird auf die lokale Festplatte geschrieben.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-127">Also, if a developer runs the [ServiceModel Metadata Utility Tool (Svcutil.exe)](servicemodel-metadata-utility-tool-svcutil-exe.md) tool against an endpoint that exposes personal information, the tool's output could contain that information, and the output file is written to the local hard disk.</span></span>  
  
## <a name="hosting"></a><span data-ttu-id="e7ec3-128">Hosting</span><span class="sxs-lookup"><span data-stu-id="e7ec3-128">Hosting</span></span>  

 <span data-ttu-id="e7ec3-129">Das Hosting-Feature in WCF ermöglicht es Anwendungen, bei Bedarf zu starten oder die Port Freigabe zwischen mehreren Anwendungen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-129">The hosting feature in WCF allows applications to start on demand or to enable port sharing between multiple applications.</span></span> <span data-ttu-id="e7ec3-130">Eine WCF-Anwendung kann in Internetinformationsdienste (IIS) gehostet werden, ähnlich wie ASP.net.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-130">A WCF application can be hosted in Internet Information Services (IIS), similar to ASP.NET.</span></span>  
  
 <span data-ttu-id="e7ec3-131">Das Hosting macht keine spezifischen Informationen im Netzwerk verfügbar und behält keine Daten auf dem Computer bei.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-131">Hosting does not expose any specific information on the network and it does not keep data on the machine.</span></span>  
  
## <a name="message-security"></a><span data-ttu-id="e7ec3-132">Nachrichtensicherheit</span><span class="sxs-lookup"><span data-stu-id="e7ec3-132">Message Security</span></span>  

 <span data-ttu-id="e7ec3-133">WCF-Sicherheit stellt die Sicherheitsfunktionen für Messaging Anwendungen bereit.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-133">WCF security provides the security capabilities for messaging applications.</span></span> <span data-ttu-id="e7ec3-134">Die bereitgestellten Sicherheitsfunktionen bieten Authentifizierung und Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-134">The security functions provided include authentication and authorization.</span></span>  
  
 <span data-ttu-id="e7ec3-135">Die Authentifizierung wird ausgeführt, indem Anmeldeinformationen zwischen den Clients und Diensten übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-135">Authentication is performed by passing credentials between the clients and services.</span></span> <span data-ttu-id="e7ec3-136">Die Authentifizierung kann entweder durch Sicherheit auf Transportebene oder durch SOAP-Sicherheit auf Nachrichtenebene erfolgen:</span><span class="sxs-lookup"><span data-stu-id="e7ec3-136">Authentication can be either through transport-level security or through SOAP message-level security, as follows:</span></span>  
  
- <span data-ttu-id="e7ec3-137">Bei der SOAP-Nachrichtensicherheit erfolgt die Authentifizierung durch Anmeldeinformationen wie Benutzername/Kennwörter, X.509-Zertifikate, Kerberos-Tickets und SAML-Token, die alle je nach Aussteller persönliche Daten enthalten können.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-137">In SOAP message security, authentication is performed through credentials like username/passwords, X.509 certificates, Kerberos tickets, and SAML tokens, all of which might contain personal information, depending on the issuer.</span></span>  
  
- <span data-ttu-id="e7ec3-138">Bei der Transportsicherheit erfolgt die Authentifizierung durch herkömmliche Transportauthentifizierungsmechanismen wie HTTP-Authentifizierungsschemas (Basic, Hashwert, Negotiate, Integrierte Windows-Authentifizierung, NTLM, Keine, Anonym) und Formularauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-138">Using transport security, authentication is done through traditional transport authentication mechanisms like HTTP authentication schemes (Basic, Digest, Negotiate, Integrated Windows Authorization, NTLM, None, and Anonymous), and form authentication.</span></span>  
  
 <span data-ttu-id="e7ec3-139">Die Authentifizierung kann zu einer sicheren Sitzung zwischen den kommunizierenden Endpunkten führen.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-139">Authentication can result in a secure session established between the communicating endpoints.</span></span> <span data-ttu-id="e7ec3-140">Die Sitzung wird durch eine GUID identifiziert, die über die Lebensdauer der Sicherheitssitzung reicht.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-140">The session is identified by a GUID that lasts the lifetime of the security session.</span></span> <span data-ttu-id="e7ec3-141">Die folgende Tabelle zeigt, welche Elemente wo gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-141">The following table shows what is kept and where.</span></span>  
  
|<span data-ttu-id="e7ec3-142">Daten</span><span class="sxs-lookup"><span data-stu-id="e7ec3-142">Data</span></span>|<span data-ttu-id="e7ec3-143">Storage</span><span class="sxs-lookup"><span data-stu-id="e7ec3-143">Storage</span></span>|  
|----------|-------------|  
|<span data-ttu-id="e7ec3-144">Präsentationsanmeldeinformationen, z. B. Benutzername, X.509-Zertifikate, Kerberos-Token und Verweise auf Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-144">Presentation credentials, such as username, X.509 certificates, Kerberos tokens, and references to credentials.</span></span>|<span data-ttu-id="e7ec3-145">Standardmäßige Windows-Verwaltungsmechanismen für Anmeldeinformationen, z. B. der Windows-Zertifikatspeicher.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-145">Standard Windows credential management mechanisms such as the Windows certificate store.</span></span>|  
|<span data-ttu-id="e7ec3-146">Benutzermitgliedschaftsinformationen, z. B. Benutzernamen und Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-146">User membership information, such as usernames and passwords.</span></span>|<span data-ttu-id="e7ec3-147">ASP.net-Mitgliedschafts Anbieter.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-147">ASP.NET membership providers.</span></span>|  
|<span data-ttu-id="e7ec3-148">Identitätsinformationen über den Dienst zum Authentifizieren des Diensts gegenüber Clients.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-148">Identity information about the service used to authenticate the service to clients.</span></span>|<span data-ttu-id="e7ec3-149">Endpunktadresse des Diensts.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-149">Endpoint address of the service.</span></span>|  
|<span data-ttu-id="e7ec3-150">Aufruferdaten.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-150">Caller information.</span></span>|<span data-ttu-id="e7ec3-151">Überwachungsprotokolle.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-151">Auditing logs.</span></span>|  
  
## <a name="auditing"></a><span data-ttu-id="e7ec3-152">Überwachung</span><span class="sxs-lookup"><span data-stu-id="e7ec3-152">Auditing</span></span>  

 <span data-ttu-id="e7ec3-153">Bei der Überwachung wird der Erfolg und das Fehlschlagen von Authentifizierungs- und Autorisierungsereignissen aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-153">Auditing records the success and failure of authentication and authorization events.</span></span> <span data-ttu-id="e7ec3-154">Überwachungsdatensätze enthalten die folgenden Daten: Dienst-URI, Aktions-URI und Identifikation des Aufrufers.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-154">Auditing records contain the following data: service URI, action URI, and the caller's identification.</span></span>  
  
 <span data-ttu-id="e7ec3-155">Bei der Überwachung werden Daten auch dann aufgezeichnet, wenn der Administrator die Konfiguration der Nachrichtenprotokollierung ändert (aktiviert oder deaktiviert), da bei der Nachrichtenprotokollierung anwendungsspezifische Daten im Header und Text erfasst werden können.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-155">Auditing also records when the administrator modifies the configuration of message logging (turning it on or off), because message logging may log application-specific data in headers and bodies.</span></span> <span data-ttu-id="e7ec3-156">Für Windows XP wird ein Datensatz im Anwendungs Ereignisprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-156">For Windows XP, a record is logged in the application event log.</span></span> <span data-ttu-id="e7ec3-157">Für Windows Vista und Windows Server 2003 wird ein Datensatz im Sicherheits Ereignisprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-157">For Windows Vista and Windows Server 2003, a record is logged in the security event log.</span></span>  
  
## <a name="transactions"></a><span data-ttu-id="e7ec3-158">Transaktionen</span><span class="sxs-lookup"><span data-stu-id="e7ec3-158">Transactions</span></span>  

 <span data-ttu-id="e7ec3-159">Die Transaktions Funktion stellt Transaktionsdienste für eine WCF-Anwendung bereit.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-159">The transactions feature provides transactional services to a WCF application.</span></span>  
  
 <span data-ttu-id="e7ec3-160">Bei der Transaktionsweitergabe verwendete Transaktionsheader enthalten möglicherweise Transaktions-IDs oder Eintragung-IDs, die GUIDs sind.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-160">Transaction headers used in transaction propagation may contain Transaction IDs or Enlistment IDs, which are GUIDs.</span></span>  
  
 <span data-ttu-id="e7ec3-161">Das Transaktionsfeature verwendet den MSDTC (Microsoft Distributed Transaction Coordinator)-Transaktions-Manager (eine Windows-Komponente) zum Verwalten des Transaktionszustands.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-161">The Transactions feature uses the Microsoft Distributed Transaction Coordinator (MSDTC) Transaction Manager (a Windows component) to manage transaction state.</span></span> <span data-ttu-id="e7ec3-162">Standardmäßig sind Kommunikationen zwischen Transaktions-Managern verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-162">By default, communications between Transactions Managers are encrypted.</span></span> <span data-ttu-id="e7ec3-163">Transaktions-Manager protokollieren möglicherweise Endpunktverweise, TransaktionsIDs und Eintragung-IDs als Teil ihres permanenten Zustands.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-163">Transaction Managers may log endpoint references, Transaction IDs, and Enlistment IDs as part of their durable state.</span></span> <span data-ttu-id="e7ec3-164">Die Lebensdauer dieses Zustands wird von der Lebensdauer der Protokolldatei des Transaktions-Managers bestimmt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-164">The lifetime of this state is determined by the lifetime of the Transaction Manager’s log file.</span></span> <span data-ttu-id="e7ec3-165">Der MSDTC-Dienst besitzt dieses Protokoll und behält es bei.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-165">The MSDTC service owns and maintains this log.</span></span>  
  
 <span data-ttu-id="e7ec3-166">Die Transaktionsfunktion implementiert die Standards WS-Coordination und WS-Atomic-Transaktion.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-166">The Transactions feature implements the WS-Coordination and WS-Atomic Transaction standards.</span></span>  
  
## <a name="reliable-sessions"></a><span data-ttu-id="e7ec3-167">Zuverlässige Sitzungen</span><span class="sxs-lookup"><span data-stu-id="e7ec3-167">Reliable Sessions</span></span>  

 <span data-ttu-id="e7ec3-168">Zuverlässige Sitzungen in WCF ermöglichen die Übertragung von Nachrichten, wenn Transport-oder Vermittler Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-168">Reliable sessions in WCF provide the transfer of messages when transport or intermediary failures occur.</span></span> <span data-ttu-id="e7ec3-169">Sie bieten auch dann genau eine Übertragung von Nachrichten, wenn die Verbindung zum zugrunde liegenden Transport unterbrochen wird (z. B. eine TCP-Verbindung in einem drahtlosen Netzwerk) oder eine Nachricht verloren geht (ein HTTP-Proxy verwirft eine aus- oder eingehende Nachricht).</span><span class="sxs-lookup"><span data-stu-id="e7ec3-169">They provide an exactly-once transfer of messages even when the underlying transport disconnects (for example, a TCP connection on a wireless network) or loses a message (an HTTP proxy dropping an outgoing or incoming message).</span></span> <span data-ttu-id="e7ec3-170">Zuverlässige Sitzungen heben außerdem die Neuordnung von Nachrichten auf (z. B. beim Multipfad-Routing), wodurch die Reihenfolge beibehalten wird, in der die Nachrichten gesendet wurden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-170">Reliable sessions also recover message reordering (as may happen in the case of multipath routing), preserving the order in which the messages were sent.</span></span>  
  
 <span data-ttu-id="e7ec3-171">Zuverlässige Sitzungen werden mit dem WS-RM (WS-ReliableMessaging)-Protokoll implementiert.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-171">Reliable sessions are implemented using the WS-ReliableMessaging (WS-RM) protocol.</span></span> <span data-ttu-id="e7ec3-172">Sie fügen WS-RM-Header hinzu, die Sitzungsinformationen enthalten, die zum Identifizieren aller einer bestimmten zuverlässigen Sitzung zugeordneten Nachrichten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-172">They add WS-RM headers that contain session information, which is used to identify all messages associated with a particular reliable session.</span></span> <span data-ttu-id="e7ec3-173">Jede WS-RM-Sitzung hat einen Bezeichner, der eine GUID ist.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-173">Each WS-RM session has an identifier, which is a GUID.</span></span>  
  
 <span data-ttu-id="e7ec3-174">Auf dem Computer des Endbenutzers werden keine persönlichen Informationen aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-174">No personal information is retained on the end user's machine.</span></span>  
  
## <a name="queued-channels"></a><span data-ttu-id="e7ec3-175">In der Warteschlange stehende Kanäle</span><span class="sxs-lookup"><span data-stu-id="e7ec3-175">Queued Channels</span></span>  

 <span data-ttu-id="e7ec3-176">Warteschlangen speichern Nachrichten von einer sendenden Anwendung für eine empfangende Anwendung und leiten sie später an die empfangende Anwendung weiter.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-176">Queues store messages from a sending application on behalf of a receiving application and later forward these messages to the receiving application.</span></span> <span data-ttu-id="e7ec3-177">Sie sichern die Nachrichtenübertragung von sendenden Anwendungen an empfangende Anwendungen, wenn z. B. die empfangende Anwendung flüchtig ist.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-177">They help ensure the transfer of messages from sending applications to receiving applications when, for example, the receiving application is transient.</span></span> <span data-ttu-id="e7ec3-178">WCF bietet Unterstützung für Warteschlangen mithilfe von Microsoft Message Queuing (MSMQ) als Transport.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-178">WCF provides support for queuing by using Microsoft Message Queuing (MSMQ) as a transport.</span></span>  
  
 <span data-ttu-id="e7ec3-179">Das Feature für in der Warteschlange stehende Kanäle fügt einer Nachricht keine Header hinzu.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-179">The queued channels feature does not add headers to a message.</span></span> <span data-ttu-id="e7ec3-180">Es erstellt stattdessen eine Message Queuing-Nachricht mit entsprechenden Einstellungen und ruft Message Queuing-Methoden zum Platzieren der Nachricht in die Message Queuing-Warteschlange auf.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-180">Instead it creates a Message Queuing message with appropriate Message Queuing message properties set, and invokes Message Queuing methods to put the message in the Message Queuing queue.</span></span> <span data-ttu-id="e7ec3-181">Message Queuing ist eine in Windows enthaltene optionale Komponente.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-181">Message Queuing is an optional component that ships with Windows.</span></span>  
  
 <span data-ttu-id="e7ec3-182">Auf dem Computer des Endbenutzers werden von der Funktion für die Warteschlangen Kanäle keine Informationen beibehalten, da Message Queuing als Warteschlangen Infrastruktur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-182">No information is retained on the end user's machine by the queued channels feature, because it uses Message Queuing as the queuing infrastructure.</span></span>  
  
## <a name="com-integration"></a><span data-ttu-id="e7ec3-183">COM+-Integration</span><span class="sxs-lookup"><span data-stu-id="e7ec3-183">COM+ Integration</span></span>  

 <span data-ttu-id="e7ec3-184">Diese Funktion umschließt vorhandene com-und com+-Funktionen, um Dienste zu erstellen, die mit WCF-Diensten kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-184">This feature wraps existing COM and COM+ functionality to create services that are compatible with WCF services.</span></span> <span data-ttu-id="e7ec3-185">Diese Funktion verwendet keine bestimmten Header und behält keine Daten auf dem Computer des Endbenutzers bei.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-185">This feature does not use specific headers and it does not retain data on the end user's machine.</span></span>  
  
## <a name="com-service-moniker"></a><span data-ttu-id="e7ec3-186">COM-Dienstmoniker</span><span class="sxs-lookup"><span data-stu-id="e7ec3-186">COM Service Moniker</span></span>  

 <span data-ttu-id="e7ec3-187">Dadurch wird ein nicht verwalteter Wrapper für einen WCF-Standard Client bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-187">This provides an unmanaged wrapper to a standard WCF client.</span></span> <span data-ttu-id="e7ec3-188">Dieses Feature verwendet keine bestimmten Header, und es behält keine Daten auf dem Computer bei.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-188">This feature does not have specific headers on the wire nor does it persist data on the machine.</span></span>  
  
## <a name="peer-channel"></a><span data-ttu-id="e7ec3-189">Peerkanal</span><span class="sxs-lookup"><span data-stu-id="e7ec3-189">Peer Channel</span></span>  

 <span data-ttu-id="e7ec3-190">Ein Peerkanal ermöglicht die Entwicklung von Anwendungen mit mehreren Parteien mithilfe von WCF.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-190">A peer channel enables development of multiparty applications using WCF.</span></span> <span data-ttu-id="e7ec3-191">Mehrparteienmessaging tritt im Kontext eines Netzes auf.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-191">Multiparty messaging occurs in the context of a mesh.</span></span> <span data-ttu-id="e7ec3-192">Netze werden mit einem Namen identifiziert, den Knoten verknüpfen können.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-192">Meshes are identified by a name that nodes can join.</span></span> <span data-ttu-id="e7ec3-193">Jeder Knoten im Peerkanal erstellt einen TCP-Listener an einem vom Benutzer angegebenen Anschluss und stellt Verbindungen mit anderen Knoten im Netz her, um die Flexibilität zu sichern.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-193">Each node in the peer channel creates a TCP listener at a user-specified port and establishes connections with other nodes in the mesh to ensure resiliency.</span></span> <span data-ttu-id="e7ec3-194">Für diese Verbindungen tauschen Knoten auch bestimmte Daten wie die Listeneradresse und die IP-Adresse des Computers mit anderen Knoten im Netz aus.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-194">To connect to other nodes in the mesh, nodes also exchange some data, including the listener address and the machine's IP addresses, with other nodes in the mesh.</span></span> <span data-ttu-id="e7ec3-195">Innerhalb des Netzes gesendete Nachrichten können Sicherheitsinformationen enthalten, die sich auf den Absender beziehen, um Nachrichtenspoofing und -manipulation zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-195">Messages sent around in the mesh can contain security information that pertains to the sender to prevent message spoofing and tampering.</span></span>  
  
 <span data-ttu-id="e7ec3-196">Auf dem Computer des Endbenutzers werden keine persönlichen Informationen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-196">No personal information is stored on the end user's machine.</span></span>  
  
## <a name="it-professional-experience"></a><span data-ttu-id="e7ec3-197">Arbeit von IT-Fachleuten</span><span class="sxs-lookup"><span data-stu-id="e7ec3-197">IT Professional Experience</span></span>  
  
### <a name="tracing"></a><span data-ttu-id="e7ec3-198">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="e7ec3-198">Tracing</span></span>  

 <span data-ttu-id="e7ec3-199">Das Diagnose Feature der WCF-Infrastruktur protokolliert Nachrichten, die die Transport-und Dienstmodell Schichten durchlaufen, sowie die Aktivitäten und Ereignisse, die diesen Nachrichten zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-199">The diagnostics feature of the WCF infrastructure logs messages that pass through the transport and service model layers, and the activities and events associated with these messages.</span></span> <span data-ttu-id="e7ec3-200">Dieses Feature ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-200">This feature is turned off by default.</span></span> <span data-ttu-id="e7ec3-201">Sie wird mithilfe der Konfigurationsdatei der Anwendung aktiviert, und das Ablauf Verfolgungs Verhalten kann mithilfe des WCF-WMI-Anbieters zur Laufzeit geändert werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-201">It is enabled using the application’s configuration file and the tracing behavior may be modified using the WCF WMI provider at run time.</span></span> <span data-ttu-id="e7ec3-202">Wenn das Feature aktiviert ist, gibt die Ablaufverfolgungsinfrastruktur eine Diagnoseablaufverfolgung mit Nachrichten, Aktivitäten und Verarbeitungsereignissen an konfigurierte Listener aus.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-202">When enabled, the tracing infrastructure emits a diagnostic trace that contains messages, activities, and processing events to configured listeners.</span></span> <span data-ttu-id="e7ec3-203">Format und Speicherort der Ausgabe werden durch die Listener-Konfigurationsauswahl des Administrators bestimmt; normalerweise ist es eine Datei im XML-Format.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-203">The format and location of the output are determined by the administrator’s listener configuration choices, but is typically an XML formatted file.</span></span> <span data-ttu-id="e7ec3-204">Der Administrator ist verantwortlich für das Festlegen der Zugriffssteuerungsliste (ACL) für die Ablaufverfolgungsdateien.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-204">The administrator is responsible for setting the access control list (ACL) on the trace files.</span></span> <span data-ttu-id="e7ec3-205">Insbesondere beim Hosten durch WAS (Windows Activation System) muss der Administrator sicherstellen, dass die Dateien nicht im öffentlichen virtuellen Stammverzeichnis befinden, falls dies nicht gewünscht ist.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-205">In particular, when hosted by Windows Activation System (WAS), the administrator should make sure the files are not served from the public virtual root directory if that is not desired.</span></span>  
  
 <span data-ttu-id="e7ec3-206">Es gibt zwei Typen von Ablaufverfolgung, Nachrichtenprotokollierung und Dienstmodell-Diagnoseablaufverfolgung, die im folgenden Abschnitt beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-206">There are two types of tracing: Message logging and Service Model diagnostic tracing, described in the following section.</span></span> <span data-ttu-id="e7ec3-207">Jeder Typ wird über seine eigene Ablaufverfolgungsquelle konfiguriert: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> und <xref:System.ServiceModel>.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-207">Each type is configured through its own trace source: <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> and <xref:System.ServiceModel>.</span></span> <span data-ttu-id="e7ec3-208">Beide Protokollierungs-Ablaufverfolgungsquellen erfassen Daten, die lokale Daten der Anwendung sind.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-208">Both of these logging trace sources capture data that is local to the application.</span></span>  
  
### <a name="message-logging"></a><span data-ttu-id="e7ec3-209">Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="e7ec3-209">Message Logging</span></span>  

 <span data-ttu-id="e7ec3-210">Die Ablaufverfolgungsquelle für die Nachrichtenprotokollierung (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) ermöglicht einem Administrator das Protokollieren der Nachrichten, die das System durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-210">The message logging trace source (<xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>) allows an administrator to log the messages that flow through the system.</span></span> <span data-ttu-id="e7ec3-211">Über die Konfiguration kann der Benutzer entscheiden, ob ganze Nachrichten oder nur Nachrichtenheader protokolliert werden, ob die Protokollierung auf der Transport- und/oder der Dienstmodellebene erfolgt und ob falsch formatierte Nachrichten erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-211">Through configuration, the user may decide to log entire messages or message headers only, whether to log at the transport and/or service model layers, and whether to include malformed messages.</span></span> <span data-ttu-id="e7ec3-212">Außerdem kann der Benutzer die Filterung konfigurieren, um einzuschränken, welche Nachrichten protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-212">Also, the user may configure filtering to restrict which messages are logged.</span></span>  
  
 <span data-ttu-id="e7ec3-213">Standardmäßig ist die Nachrichtenprotokollierung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-213">By default, message logging is disabled.</span></span> <span data-ttu-id="e7ec3-214">Der Administrator auf dem lokalen Computer kann verhindern, dass der Administrator auf Anwendungsebene die Nachrichtenprotokollierung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-214">The local machine administrator can prevent the application-level administrator from turning message logging on.</span></span>  
  
#### <a name="encrypted-and-decrypted-message-logging"></a><span data-ttu-id="e7ec3-215">Verschlüsselte und entschlüsselte Nachrichtenprotokollierung</span><span class="sxs-lookup"><span data-stu-id="e7ec3-215">Encrypted and Decrypted Message Logging</span></span>  

 <span data-ttu-id="e7ec3-216">Nachrichten werden wie in den folgenden Begriffen beschrieben protokolliert, verschlüsselt oder entschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-216">Messages are logged, encrypted, or decrypted, as described in the following terms.</span></span>  
  
 <span data-ttu-id="e7ec3-217">Transportprotokollierung</span><span class="sxs-lookup"><span data-stu-id="e7ec3-217">Transport Logging</span></span>  
 <span data-ttu-id="e7ec3-218">Protokolliert auf der Transportebene empfangene und gesendete Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-218">Logs messages received and sent at the transport level.</span></span> <span data-ttu-id="e7ec3-219">Diese Nachrichten enthalten alle Header und werden möglicherweise vor dem Versenden und beim Empfangen verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-219">These messages contain all headers, and may be encrypted before being sent on the wire and when being received.</span></span>  
  
 <span data-ttu-id="e7ec3-220">Wenn Nachrichten vor dem Versenden und beim Empfangen verschlüsselt werden, werden sie auch verschlüsselt protokolliert.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-220">If messages are encrypted before being sent on the wire and when they are received, they are logged encrypted as well.</span></span> <span data-ttu-id="e7ec3-221">Eine Ausnahme ist die Verwendung eines Sicherheitsprotokolls (HTTPS); die Nachrichten werden vor dem Senden und nach dem Empfangen entschlüsselt protokolliert, auch wenn sie beim Versenden verschlüsselt sind.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-221">An exception is when a security protocol is used (https): they are then logged decrypted before being sent and after being received even if they are encrypted on the wire.</span></span>  
  
 <span data-ttu-id="e7ec3-222">Dienstprotokollierung</span><span class="sxs-lookup"><span data-stu-id="e7ec3-222">Service Logging</span></span>  
 <span data-ttu-id="e7ec3-223">Protokolliert auf der Dienstmodellebene empfangene oder gesendete Nachrichten nach der Kanalheader-Verarbeitung, unmittelbar vor und nach der Eingabe von Benutzercode.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-223">Logs messages received or sent at the service model level, after channel header processing has occurred, just before and after entering user code.</span></span>  
  
 <span data-ttu-id="e7ec3-224">Auf dieser Ebene protokollierte Nachrichten werden entschlüsselt, auch wenn sie für die Übertragung gesichert und verschlüsselt wurden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-224">Messages logged at this level are decrypted even if they were secured and encrypted on the wire.</span></span>  
  
 <span data-ttu-id="e7ec3-225">Protokollierung falsch formatierter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="e7ec3-225">Malformed Message Logging</span></span>  
 <span data-ttu-id="e7ec3-226">Protokolliert Meldungen, die von der WCF-Infrastruktur nicht verstanden oder verarbeitet werden können.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-226">Logs messages that the WCF infrastructure cannot understand or process.</span></span>  
  
 <span data-ttu-id="e7ec3-227">Nachrichten werden unverändert protokolliert, d. h. verschlüsselt oder nicht verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-227">Messages are logged as-is, that is, encrypted or not</span></span>  
  
 <span data-ttu-id="e7ec3-228">Wenn Nachrichten in entschlüsselter oder unverschlüsselter Form protokolliert werden, entfernt WCF standardmäßig Sicherheitsschlüssel und potenziell persönliche Informationen aus den Nachrichten, bevor diese protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-228">When messages are logged in decrypted or unencrypted form, by default WCF removes security keys and potentially personal information from the messages before logging them.</span></span> <span data-ttu-id="e7ec3-229">In den nächsten Abschnitten wird beschrieben, welche Informationen wann entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-229">The next sections describe what information is removed, and when.</span></span> <span data-ttu-id="e7ec3-230">Der Computeradministrator und der Anwendungsbereitsteller müssen bestimmte Konfigurationsschritte durchführen, um das Standardverhalten so zu ändern, dass Schlüssel und mögliche persönliche Informationen protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-230">The machine administrator and application deployer must both take certain configuration actions to change the default behavior to log keys and potentially personal information.</span></span>  
  
#### <a name="information-removed-from-message-headers-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="e7ec3-231">Aus Nachrichtenheadern bei der Protokollierung entschlüsselter/unverschlüsselter Nachrichten entfernte Informationen</span><span class="sxs-lookup"><span data-stu-id="e7ec3-231">Information Removed from Message Headers When Logging Decrypted/Unencrypted Messages</span></span>  

 <span data-ttu-id="e7ec3-232">Wenn Nachrichten in entschlüsselter/unverschlüsselter Form protokolliert werden, werden standardmäßig vor dem Protokollieren Sicherheitsschlüssel und mögliche persönliche Informationen aus Nachrichtenheadern und Nachrichtentext entfernt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-232">When messages are logged in decrypted/unencrypted form, security keys and potentially personal information are removed by default from message headers and message bodies before they are logged.</span></span> <span data-ttu-id="e7ec3-233">In der folgenden Liste wird gezeigt, was WCF Schlüssel und potenziell persönliche Informationen berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-233">The following list shows what WCF considers keys and potentially personal information.</span></span>  
  
 <span data-ttu-id="e7ec3-234">Schlüssel, die entfernt werden:</span><span class="sxs-lookup"><span data-stu-id="e7ec3-234">Keys that are removed:</span></span>  
  
 <span data-ttu-id="e7ec3-235">\- Für xmlns: WST = " http://schemas.xmlsoap.org/ws/2004/04/trust " und xmlns: WST = " http://schemas.xmlsoap.org/ws/2005/02/trust "</span><span class="sxs-lookup"><span data-stu-id="e7ec3-235">\- For xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust"</span></span>  
  
 <span data-ttu-id="e7ec3-236">wst:BinarySecret</span><span class="sxs-lookup"><span data-stu-id="e7ec3-236">wst:BinarySecret</span></span>  
  
 <span data-ttu-id="e7ec3-237">wst:Entropy</span><span class="sxs-lookup"><span data-stu-id="e7ec3-237">wst:Entropy</span></span>  
  
 <span data-ttu-id="e7ec3-238">\- Für xmlns: wsse = " http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd " und xmlns: wsse = " http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd "</span><span class="sxs-lookup"><span data-stu-id="e7ec3-238">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="e7ec3-239">wsse:Password</span><span class="sxs-lookup"><span data-stu-id="e7ec3-239">wsse:Password</span></span>  
  
 <span data-ttu-id="e7ec3-240">wsse:Nonce</span><span class="sxs-lookup"><span data-stu-id="e7ec3-240">wsse:Nonce</span></span>  
  
 <span data-ttu-id="e7ec3-241">Mögliche persönliche Informationen, die entfernt werden:</span><span class="sxs-lookup"><span data-stu-id="e7ec3-241">Potentially personal information that is removed:</span></span>  
  
 <span data-ttu-id="e7ec3-242">\- Für xmlns: wsse = " http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd " und xmlns: wsse = " http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd "</span><span class="sxs-lookup"><span data-stu-id="e7ec3-242">\- For xmlns:wsse="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.1.xsd" and xmlns:wsse="http://docs.oasis-open.org/wss/2005/xx/oasis-2005xx-wss-wssecurity-secext-1.1.xsd"</span></span>  
  
 <span data-ttu-id="e7ec3-243">wsse:Username</span><span class="sxs-lookup"><span data-stu-id="e7ec3-243">wsse:Username</span></span>  
  
 <span data-ttu-id="e7ec3-244">wsse:BinarySecurityToken</span><span class="sxs-lookup"><span data-stu-id="e7ec3-244">wsse:BinarySecurityToken</span></span>  
  
 <span data-ttu-id="e7ec3-245">\- Bei xmlns: SAML = "urn: Oasis: names: TC: SAML: 1.0: Assert" werden die fett formatierten Elemente entfernt:</span><span class="sxs-lookup"><span data-stu-id="e7ec3-245">\- For xmlns:saml="urn:oasis:names:tc:SAML:1.0:assertion" the items in bold (below) are removed:</span></span>  
  
 <span data-ttu-id="e7ec3-246">\<Assertion</span><span class="sxs-lookup"><span data-stu-id="e7ec3-246">\<Assertion</span></span>  
  
 <span data-ttu-id="e7ec3-247">MajorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-247">MajorVersion="1"</span></span>  
  
 <span data-ttu-id="e7ec3-248">MinorVersion="1"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-248">MinorVersion="1"</span></span>  
  
 <span data-ttu-id="e7ec3-249">AssertionId="[ID]"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-249">AssertionId="[ID]"</span></span>  
  
 <span data-ttu-id="e7ec3-250">Issuer="[string]"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-250">Issuer="[string]"</span></span>  
  
 <span data-ttu-id="e7ec3-251">IssueInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-251">IssueInstant="[dateTime]"</span></span>  
  
 >  
  
 \<Conditions NotBefore="[dateTime]" NotOnOrAfter="[dateTime]">  
  
 \<AudienceRestrictionCondition>  
  
 <span data-ttu-id="e7ec3-252">\<Audience>RT\</Audience>+</span><span class="sxs-lookup"><span data-stu-id="e7ec3-252">\<Audience>[uri]\</Audience>+</span></span>  
  
 \</AudienceRestrictionCondition>*  
  
 \<DoNotCacheCondition />*  
  
 <span data-ttu-id="e7ec3-253"><\!--abstrakter Basistyp</span><span class="sxs-lookup"><span data-stu-id="e7ec3-253"><\!-- abstract base type</span></span>  
  
 \<Condition />*  
  
 -->  
  
 <span data-ttu-id="e7ec3-254">\</Conditions>?</span><span class="sxs-lookup"><span data-stu-id="e7ec3-254">\</Conditions>?</span></span>  
  
 \<Advice>  
  
 <span data-ttu-id="e7ec3-255">\<AssertionIDReference>Name\</AssertionIDReference>\*</span><span class="sxs-lookup"><span data-stu-id="e7ec3-255">\<AssertionIDReference>[ID]\</AssertionIDReference>\*</span></span>  
  
 <span data-ttu-id="e7ec3-256">\<Assertion>Assertion\</Assertion>\*</span><span class="sxs-lookup"><span data-stu-id="e7ec3-256">\<Assertion>[assertion]\</Assertion>\*</span></span>  
  
 <span data-ttu-id="e7ec3-257">[any]\*</span><span class="sxs-lookup"><span data-stu-id="e7ec3-257">[any]\*</span></span>  
  
 <span data-ttu-id="e7ec3-258">\</Advice>?</span><span class="sxs-lookup"><span data-stu-id="e7ec3-258">\</Advice>?</span></span>  
  
 <span data-ttu-id="e7ec3-259"><\!--Abstrakte Basis Typen</span><span class="sxs-lookup"><span data-stu-id="e7ec3-259"><\!-- Abstract base types</span></span>  
  
 \<Statement />*  
  
 \<SubjectStatement>  
  
 \<Subject>  
  
 `<NameIdentifier`  
  
 `NameQualifier="[string]"?`  
  
 `Format="[uri]"?`  
  
 `>`  
  
 `[string]`  
  
 `</NameIdentifier>?`  
  
 \<SubjectConfirmation>  
  
 <span data-ttu-id="e7ec3-260">\<ConfirmationMethod>anyUri\</ConfirmationMethod>+</span><span class="sxs-lookup"><span data-stu-id="e7ec3-260">\<ConfirmationMethod>[anyUri]\</ConfirmationMethod>+</span></span>  
  
 <span data-ttu-id="e7ec3-261">\<SubjectConfirmationData>[beliebig] \</SubjectConfirmationData> ?</span><span class="sxs-lookup"><span data-stu-id="e7ec3-261">\<SubjectConfirmationData>[any]\</SubjectConfirmationData>?</span></span>  
  
 <span data-ttu-id="e7ec3-262">\<ds:KeyInfo>...\</ds:KeyInfo>?</span><span class="sxs-lookup"><span data-stu-id="e7ec3-262">\<ds:KeyInfo>...\</ds:KeyInfo>?</span></span>  
  
 <span data-ttu-id="e7ec3-263">\</SubjectConfirmation>?</span><span class="sxs-lookup"><span data-stu-id="e7ec3-263">\</SubjectConfirmation>?</span></span>  
  
 \</Subject>  
  
 \</SubjectStatement>*  
  
 -->  
  
 <span data-ttu-id="e7ec3-264">\<AuthenticationStatement</span><span class="sxs-lookup"><span data-stu-id="e7ec3-264">\<AuthenticationStatement</span></span>  
  
 <span data-ttu-id="e7ec3-265">AuthenticationMethod="[uri]"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-265">AuthenticationMethod="[uri]"</span></span>  
  
 <span data-ttu-id="e7ec3-266">AuthenticationInstant="[dateTime]"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-266">AuthenticationInstant="[dateTime]"</span></span>  
  
 >  
  
 <span data-ttu-id="e7ec3-267">[Subject]</span><span class="sxs-lookup"><span data-stu-id="e7ec3-267">[Subject]</span></span>  
  
 `<SubjectLocality`  
  
 `IPAddress="[string]"?`  
  
 `DNSAddress="[string]"?`  
  
 `/>?`  
  
 <span data-ttu-id="e7ec3-268"><Autorität Bindung</span><span class="sxs-lookup"><span data-stu-id="e7ec3-268"><AuthorityBinding</span></span>  
  
 <span data-ttu-id="e7ec3-269">AuthorityKind="[QName]"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-269">AuthorityKind="[QName]"</span></span>  
  
 <span data-ttu-id="e7ec3-270">Location="[uri]"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-270">Location="[uri]"</span></span>  
  
 <span data-ttu-id="e7ec3-271">Binding="[uri]"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-271">Binding="[uri]"</span></span>  
  
 />*  
  
 \</AuthenticationStatement>*  
  
 \<AttributeStatement>  
  
 <span data-ttu-id="e7ec3-272">[Subject]</span><span class="sxs-lookup"><span data-stu-id="e7ec3-272">[Subject]</span></span>  
  
 <span data-ttu-id="e7ec3-273">\<Attribut</span><span class="sxs-lookup"><span data-stu-id="e7ec3-273">\<Attribute</span></span>  
  
 <span data-ttu-id="e7ec3-274">AttributeName="[string]"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-274">AttributeName="[string]"</span></span>  
  
 <span data-ttu-id="e7ec3-275">AttributeNamespace="[uri]"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-275">AttributeNamespace="[uri]"</span></span>  
  
 >  
  
 `<AttributeValue>[any]</AttributeValue>+`  
  
 \</Attribute>+  
  
 \</AttributeStatement>*  
  
 <span data-ttu-id="e7ec3-276">\<AuthorizationDecisionStatement</span><span class="sxs-lookup"><span data-stu-id="e7ec3-276">\<AuthorizationDecisionStatement</span></span>  
  
 <span data-ttu-id="e7ec3-277">Resource="[uri]"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-277">Resource="[uri]"</span></span>  
  
 <span data-ttu-id="e7ec3-278">Decision = "[zulassen&#124;verweigern&#124;unbestimmt]"</span><span class="sxs-lookup"><span data-stu-id="e7ec3-278">Decision="[Permit&#124;Deny&#124;Indeterminate]"</span></span>  
  
 >  
  
 <span data-ttu-id="e7ec3-279">[Subject]</span><span class="sxs-lookup"><span data-stu-id="e7ec3-279">[Subject]</span></span>  
  
 <span data-ttu-id="e7ec3-280">\<Action Namespace="[uri]">Schnür\</Action>+</span><span class="sxs-lookup"><span data-stu-id="e7ec3-280">\<Action Namespace="[uri]">[string]\</Action>+</span></span>  
  
 \<Evidence>  
  
 <span data-ttu-id="e7ec3-281">\<AssertionIDReference>Name\</AssertionIDReference>+</span><span class="sxs-lookup"><span data-stu-id="e7ec3-281">\<AssertionIDReference>[ID]\</AssertionIDReference>+</span></span>  
  
 <span data-ttu-id="e7ec3-282">\<Assertion>Assertion\</Assertion>+</span><span class="sxs-lookup"><span data-stu-id="e7ec3-282">\<Assertion>[assertion]\</Assertion>+</span></span>  
  
 <span data-ttu-id="e7ec3-283">\</Evidence>?</span><span class="sxs-lookup"><span data-stu-id="e7ec3-283">\</Evidence>?</span></span>  
  
 \</AuthorizationDecisionStatement>*  
  
 \</Assertion>  
  
#### <a name="information-removed-from-message-bodies-when-logging-decryptedunencrypted-messages"></a><span data-ttu-id="e7ec3-284">Aus Nachrichtentext bei der Protokollierung entschlüsselter/unverschlüsselter Nachrichten entfernte Informationen</span><span class="sxs-lookup"><span data-stu-id="e7ec3-284">Information Removed from Message Bodies When Logging Decrypted/Unencrypted Messages</span></span>  

 <span data-ttu-id="e7ec3-285">Wie bereits beschrieben, entfernt WCF Schlüssel und bekannte potenziell persönliche Informationen aus Nachrichten Headern für protokollierte entschlüsselte/unverschlüsselte Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-285">As previously described, WCF removes keys and known potentially personal information from message headers for logged decrypted/unencrypted messages.</span></span> <span data-ttu-id="e7ec3-286">Außerdem entfernt WCF Schlüssel und bekannte potenziell persönliche Informationen aus Nachrichten Textteilen für die Textelemente und Aktionen in der folgenden Liste, in denen die an den Schlüsselaustausch beteiligten Sicherheitsmeldungen beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-286">In addition, WCF removes keys and known potentially personal information from message bodies for the body elements and actions in the following list, which describe security messages involved in key exchange.</span></span>  
  
 <span data-ttu-id="e7ec3-287">Für die folgenden Namespaces:</span><span class="sxs-lookup"><span data-stu-id="e7ec3-287">For the following namespaces:</span></span>  
  
 <span data-ttu-id="e7ec3-288">xmlns: WST = " http://schemas.xmlsoap.org/ws/2004/04/trust " und xmlns: WST = " http://schemas.xmlsoap.org/ws/2005/02/trust " (z. b. wenn keine Aktion verfügbar ist)</span><span class="sxs-lookup"><span data-stu-id="e7ec3-288">xmlns:wst="http://schemas.xmlsoap.org/ws/2004/04/trust" and xmlns:wst="http://schemas.xmlsoap.org/ws/2005/02/trust" (for example, if no action available)</span></span>  
  
 <span data-ttu-id="e7ec3-289">Informationen werden für diese Textelemente entfernt, die Schlüsselaustausch einschließen:</span><span class="sxs-lookup"><span data-stu-id="e7ec3-289">Information is removed for these body elements, which involve key exchange:</span></span>  
  
 <span data-ttu-id="e7ec3-290">wst:RequestSecurityToken</span><span class="sxs-lookup"><span data-stu-id="e7ec3-290">wst:RequestSecurityToken</span></span>  
  
 <span data-ttu-id="e7ec3-291">wst:RequestSecurityTokenResponse</span><span class="sxs-lookup"><span data-stu-id="e7ec3-291">wst:RequestSecurityTokenResponse</span></span>  
  
 <span data-ttu-id="e7ec3-292">wst:RequestSecurityTokenResponseCollection</span><span class="sxs-lookup"><span data-stu-id="e7ec3-292">wst:RequestSecurityTokenResponseCollection</span></span>  
  
 <span data-ttu-id="e7ec3-293">Informationen werden auch für jede der folgenden Aktionen entfernt:</span><span class="sxs-lookup"><span data-stu-id="e7ec3-293">Information is also removed for each of the following Actions:</span></span>  
  
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
  
#### <a name="no-information-is-removed-from-application-specific-headers-and-body-data"></a><span data-ttu-id="e7ec3-294">Aus anwendungsspezifischen Headern und Textdaten werden keine Informationen entfernt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-294">No Information Is Removed from Application-specific Headers and Body Data</span></span>  

 <span data-ttu-id="e7ec3-295">WCF verfolgt keine persönlichen Informationen in anwendungsspezifischen Headern (z. b. Abfrage Zeichenfolgen) oder Textdaten (z. b. Kreditkartennummer).</span><span class="sxs-lookup"><span data-stu-id="e7ec3-295">WCF does not track personal information in application-specific headers (for example, query strings) or body data (for example, credit card number).</span></span>  
  
 <span data-ttu-id="e7ec3-296">Bei aktivierter Nachrichtenprotokollierung sind persönliche Informationen in anwendungsspezifischen Headern und Textdaten unter Umständen in den Protokollen sichtbar.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-296">When message logging is on, personal information in application-specific headers and body information may be visible in the logs.</span></span> <span data-ttu-id="e7ec3-297">Der Anwendungsbereitsteller ist für das Festlegen der ACLs für die Konfigurations- und Protokolldateien verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-297">Again, the application deployer is responsible for setting the ACLs on the configuration and log files.</span></span> <span data-ttu-id="e7ec3-298">Sie können die Protokollierung auch deaktivieren, wenn Sie nicht möchten, dass diese Informationen sichtbar sind, oder diese Informationen nach der Protokollierung aus den Protokolldateien herausfiltern.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-298">They also can turn off logging if they don't want this information to be visible, or filter out this information from the log files after it is logged.</span></span>  
  
### <a name="service-model-tracing"></a><span data-ttu-id="e7ec3-299">Dienstmodell-Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="e7ec3-299">Service Model Tracing</span></span>  

 <span data-ttu-id="e7ec3-300">Die Dienstmodell-Ablaufverfolgungsquelle (<xref:System.ServiceModel>) aktiviert die Ablaufverfolgung von mit der Nachrichtenverarbeitung verknüpften Aktivitäten und Ereignissen.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-300">The Service Model trace source (<xref:System.ServiceModel>) enables tracing of activities and events related to message processing.</span></span> <span data-ttu-id="e7ec3-301">Diese Funktion verwendet die .NET Framework-Diagnosefunktionalität von <xref:System.Diagnostics>.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-301">This feature uses the .NET Framework diagnostic functionality from <xref:System.Diagnostics>.</span></span> <span data-ttu-id="e7ec3-302">Wie bei der <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A>-Eigenschaft können der Speicherort und die ACL mit den Konfigurationsdateien der .NET Framework-Anwendung vom Benutzer konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-302">As with the <xref:System.ServiceModel.Configuration.DiagnosticSection.MessageLogging%2A> property, the location and its ACL are user-configurable using .NET Framework application configuration files.</span></span> <span data-ttu-id="e7ec3-303">Wie bei der Nachrichtenprotokollierung wird der Speicherort der Datei immer konfiguriert, wenn der Administrator die Ablaufverfolgung aktiviert; der Administrator steuert also die ACL.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-303">As with message logging, the file location is always configured when the administrator enables tracing; thus, the administrator controls the ACL.</span></span>  
  
 <span data-ttu-id="e7ec3-304">Ablaufverfolgungen enthalten Nachrichtenheader, wenn sich eine Nachricht im Gültigkeitsbereich befindet.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-304">Traces contain message headers when a message is in scope.</span></span> <span data-ttu-id="e7ec3-305">Dabei gilt die gleiche Regel für das Ausblenden möglicher persönlicher Informationen in Nachrichtenheadern wie im vorherigen Abschnitt: Die zuvor identifizierten persönlichen Informationen werden standardmäßig aus den Headern in Ablaufverfolgungen entfernt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-305">The same rules for hiding potentially personal information in message headers in the previous section apply: the personal information previously identified is removed by default from the headers in traces.</span></span> <span data-ttu-id="e7ec3-306">Der Computeradministrator und der Anwendungsbereitsteller müssen die Konfiguration ändern, damit mögliche persönliche Informationen protokolliert werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-306">Both the machine administrator and the application deployer must modify the configuration in order to log potentially personal information.</span></span> <span data-ttu-id="e7ec3-307">Allerdings werden in anwendungsspezifischen Headern enthaltene persönliche Informationen in Ablaufverfolgungen protokolliert.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-307">However, personal information contained in application-specific headers is logged in traces.</span></span> <span data-ttu-id="e7ec3-308">Der Anwendungsbereitsteller ist für das Festlegen der ACLs für die Konfigurations- und Ablaufverfolgungsdateien verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-308">The application deployer is responsible for setting the ACLs on the configuration and trace files.</span></span> <span data-ttu-id="e7ec3-309">Sie können die Ablauf Verfolgung auch deaktivieren, um diese Informationen auszublenden oder diese Informationen aus den Ablauf Verfolgungs Dateien herausfiltern, nachdem Sie protokolliert wurden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-309">They can also turn off tracing to hide this information or filter out this information from the trace files after it's logged.</span></span>  
  
 <span data-ttu-id="e7ec3-310">Als Teil der Dienstmodell-Ablaufverfolgung verknüpfen eindeutige IDs (die als Aktivitäts-IDs bezeichnet werden, in der Regel eine GUID) unterschiedliche Aktivitäten, wenn eine Nachricht verschiedene Teile der Infrastruktur durchläuft.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-310">As part of ServiceModel Tracing, Unique IDs (called Activity IDs, and typically a GUID) link different activities together as a message flows through different parts of the infrastructure.</span></span>  
  
#### <a name="custom-trace-listeners"></a><span data-ttu-id="e7ec3-311">Benutzerdefinierte Ablaufverfolgungslistener</span><span class="sxs-lookup"><span data-stu-id="e7ec3-311">Custom Trace Listeners</span></span>  

 <span data-ttu-id="e7ec3-312">Sowohl für die Nachrichtenprotokollierung als auch die Ablaufverfolgung kann ein benutzerdefinierter Ablaufverfolgungslistener konfiguriert werden, der Ablaufverfolgungen und Nachrichten überträgt, z. B. an eine Remotedatenbank.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-312">For both message logging and tracing, a custom trace listener can be configured, which can send traces and messages on the wire (for example, to a remote database).</span></span> <span data-ttu-id="e7ec3-313">Der Anwendungsbereitsteller ist für das Konfigurieren benutzerdefinierter Listener oder das Ermöglichen dieser Aktion durch Benutzer verantwortlich.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-313">The application deployer is responsible for configuring custom listeners or enabling users to do so.</span></span> <span data-ttu-id="e7ec3-314">Sie sind auch für alle persönlichen Informationen verantwortlich, die am Remote Standort verfügbar gemacht werden, und für die korrekte Anwendung von ACLs auf diesen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-314">They are also responsible for any personal information exposed at the remote location and for properly applying ACLs to this location.</span></span>  
  
### <a name="other-features-for-it-professionals"></a><span data-ttu-id="e7ec3-315">Andere Features für IT-Fachleute</span><span class="sxs-lookup"><span data-stu-id="e7ec3-315">Other features for IT Professionals</span></span>  

 <span data-ttu-id="e7ec3-316">WCF verfügt über einen WMI-Anbieter, der die Konfigurationsinformationen der WCF-Infrastruktur über WMI (ausgeliefert in Windows) verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-316">WCF has a WMI provider that exposes the WCF infrastructure configuration information through WMI (shipped with Windows).</span></span> <span data-ttu-id="e7ec3-317">Standardmäßig steht die WMI-Schnittstelle Administratoren zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-317">By default, the WMI interface is available to administrators.</span></span>  
  
 <span data-ttu-id="e7ec3-318">Die WCF-Konfiguration verwendet den .NET Framework Konfigurations Mechanismus.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-318">WCF configuration uses the .NET Framework configuration mechanism.</span></span> <span data-ttu-id="e7ec3-319">Die Konfigurationsdateien werden auf dem Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-319">The configuration files are stored on the machine.</span></span> <span data-ttu-id="e7ec3-320">Der Anwendungsentwickler und der Administrator erstellen die Konfigurationsdateien und die ACL für jede Anwendungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-320">The application developer and the administrator create the configuration files and ACL for each of the application's requirements.</span></span> <span data-ttu-id="e7ec3-321">Eine Konfigurationsdatei kann Endpunktadressen und Links zu Zertifikaten im Zertifikatspeicher enthalten.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-321">A configuration file can contain endpoint addresses and links to certificates in the certificate store.</span></span> <span data-ttu-id="e7ec3-322">Mithilfe der Zertifikate können Anwendungsdaten zum Konfigurieren verschiedener Eigenschaften der von der Anwendung verwendeten Funktionen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-322">The certificates can be used to provide application data to configure various properties of the features used by the application.</span></span>  
  
 <span data-ttu-id="e7ec3-323">WCF verwendet auch die .NET Framework Prozess-dumpfunktion, indem die-Methode aufgerufen wird <xref:System.Environment.FailFast%2A> .</span><span class="sxs-lookup"><span data-stu-id="e7ec3-323">WCF also uses the .NET Framework process dump functionality by calling the <xref:System.Environment.FailFast%2A> method.</span></span>  
  
### <a name="it-pro-tools"></a><span data-ttu-id="e7ec3-324">Tools für IT-Fachleute</span><span class="sxs-lookup"><span data-stu-id="e7ec3-324">IT Pro Tools</span></span>  

 <span data-ttu-id="e7ec3-325">WCF stellt außerdem die folgenden IT-Experten bereit, die im Windows SDK ausgeliefert werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-325">WCF also provides the following IT professional tools, which ship in the Windows SDK.</span></span>  
  
#### <a name="svctraceviewerexe"></a><span data-ttu-id="e7ec3-326">SvcTraceViewer.exe</span><span class="sxs-lookup"><span data-stu-id="e7ec3-326">SvcTraceViewer.exe</span></span>  

 <span data-ttu-id="e7ec3-327">Der Viewer zeigt WCF-Ablauf Verfolgungs Dateien an.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-327">The viewer displays WCF trace files.</span></span> <span data-ttu-id="e7ec3-328">Der Viewer zeigt an, welche Daten in den Ablaufverfolgungen enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-328">The viewer shows whatever information is contained in the traces.</span></span>  
  
#### <a name="svcconfigeditorexe"></a><span data-ttu-id="e7ec3-329">SvcConfigEditor.exe</span><span class="sxs-lookup"><span data-stu-id="e7ec3-329">SvcConfigEditor.exe</span></span>  

 <span data-ttu-id="e7ec3-330">Der Editor ermöglicht dem Benutzer das Erstellen und Bearbeiten von WCF-Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-330">The editor allows the user to create and edit WCF configuration files.</span></span> <span data-ttu-id="e7ec3-331">Der Editor zeigt an, welche Daten in den Konfigurationsdateien enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-331">The editor shows whatever information is contained in the configuration files.</span></span> <span data-ttu-id="e7ec3-332">Für die gleiche Aufgabe kann auch ein Text-Editor verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-332">The same task can be accomplished with a text editor.</span></span>  
  
#### <a name="servicemodel_reg"></a><span data-ttu-id="e7ec3-333">ServiceModel_Reg</span><span class="sxs-lookup"><span data-stu-id="e7ec3-333">ServiceModel_Reg</span></span>  

 <span data-ttu-id="e7ec3-334">Mit diesem Tool kann der Benutzer ServiceModel-Installationen auf einem Computer verwalten.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-334">This tool allows the user to manage ServiceModel installs on a machine.</span></span> <span data-ttu-id="e7ec3-335">Das Tool zeigt die Statusmeldungen bei der Ausführung in einem Konsolenfenster an und zeigt möglicherweise Informationen zur Konfiguration der WCF-Installation an.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-335">The tool displays status messages in a console window when it runs and, in the process, may display information about the configuration of the WCF installation.</span></span>  
  
#### <a name="wsatconfigexe-and-wsatuidll"></a><span data-ttu-id="e7ec3-336">WSATConfig.exe und WSATUI.dll</span><span class="sxs-lookup"><span data-stu-id="e7ec3-336">WSATConfig.exe and WSATUI.dll</span></span>  

 <span data-ttu-id="e7ec3-337">Diese Tools ermöglichen IT-Experten, interoperable WS-AtomicTransaction Netzwerkunterstützung in WCF zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-337">These tools allow IT Professionals to configure interoperable WS-AtomicTransaction network support in WCF.</span></span> <span data-ttu-id="e7ec3-338">Mithilfe der Tools kann der Benutzer die Werte der in der Registrierung gespeicherten am häufigsten verwendeten WS-AtomicTransaction-Einstellungen anzeigen und ändern.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-338">The tools display and allow the user to change the values of the most commonly used WS-AtomicTransaction settings stored in the registry.</span></span>  
  
## <a name="cross-cutting-features"></a><span data-ttu-id="e7ec3-339">Querschnittliche Funktionen</span><span class="sxs-lookup"><span data-stu-id="e7ec3-339">Cross-cutting Features</span></span>  

 <span data-ttu-id="e7ec3-340">Die folgenden Features sind querschnittliche Features.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-340">The following features are cross-cutting.</span></span> <span data-ttu-id="e7ec3-341">Das heißt, sie können mit allen vorangehenden Funktionen zusammengesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-341">That is, they can be composed with any of the preceding features.</span></span>  
  
### <a name="service-framework"></a><span data-ttu-id="e7ec3-342">Dienstframework</span><span class="sxs-lookup"><span data-stu-id="e7ec3-342">Service Framework</span></span>  

 <span data-ttu-id="e7ec3-343">Header können eine Instanz-ID enthalten; dies ist eine GUID, die eine Nachricht einer Instanz einer CLR-Klasse zuordnet.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-343">Headers can contain an instance ID, which is a GUID that associates a message with an instance of a CLR class.</span></span>  
  
 <span data-ttu-id="e7ec3-344">Die WSDL (Web Services Description Language) enthält eine Definition des Anschlusses.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-344">The Web Services Description Language (WSDL) contains a definition of the port.</span></span> <span data-ttu-id="e7ec3-345">Jeder Anschluss verfügt über eine Endpunktadresse und eine Bindung, die die von der Anwendung verwendeten Dienste darstellt.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-345">Each port has an endpoint address and a binding that represents the services used by the application.</span></span> <span data-ttu-id="e7ec3-346">Das Verfügbarmachen der WSDL kann mithilfe der Konfiguration deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-346">Exposing WSDL can be turned off using configuration.</span></span> <span data-ttu-id="e7ec3-347">Auf dem Computer werden keine Informationen beibehalten.</span><span class="sxs-lookup"><span data-stu-id="e7ec3-347">No information is retained on the machine.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7ec3-348">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7ec3-348">See also</span></span>

- [<span data-ttu-id="e7ec3-349">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="e7ec3-349">Windows Communication Foundation</span></span>](index.md)
- [<span data-ttu-id="e7ec3-350">Security</span><span class="sxs-lookup"><span data-stu-id="e7ec3-350">Security</span></span>](./feature-details/security.md)
