---
title: Häufige Sicherheitsszenarien
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: 21c8279890d1d1cf746e98f875efb6b1ff869c73
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295079"
---
# <a name="common-security-scenarios"></a><span data-ttu-id="bb0e0-102">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="bb0e0-102">Common Security Scenarios</span></span>

<span data-ttu-id="bb0e0-103">Die Themen in diesem Abschnitt katalogisieren eine Anzahl möglicher Client- und Dienstsicherheitskonfigurationen.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-103">The topics in this section catalog a number of possible client and service security configurations.</span></span> <span data-ttu-id="bb0e0-104">Die Konfigurationen ändern sich aufgrund verschiedenster Faktoren.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-104">Configurations vary according to a number of factors.</span></span> <span data-ttu-id="bb0e0-105">Zum Beispiel ob sich ein Dienst oder Client im Intranet befindet oder ob die Sicherheit von Windows oder vom Transport (wie HTTPS) gewährleistet wird.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-105">For example, whether a service or client is on an intranet, or whether the security is provided by Windows or transport (such as HTTPS).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb0e0-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="bb0e0-106">In This Section</span></span>  

 [<span data-ttu-id="bb0e0-107">Internet: Ungesicherter Client und Dienst</span><span class="sxs-lookup"><span data-stu-id="bb0e0-107">Internet Unsecured Client and Service</span></span>](internet-unsecured-client-and-service.md)  
 <span data-ttu-id="bb0e0-108">Ein Beispiel eines öffentlichen, ungesicherten Clients und Diensts.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-108">An example of a public, unsecured client and service.</span></span>  
  
 [<span data-ttu-id="bb0e0-109">Intranet: Ungesicherter Client und Dienst</span><span class="sxs-lookup"><span data-stu-id="bb0e0-109">Intranet Unsecured Client and Service</span></span>](intranet-unsecured-client-and-service.md)  
 <span data-ttu-id="bb0e0-110">Ein grundlegender Windows Communication Foundation (WCF)-Dienst, der entwickelt wurde, um Informationen zu einem sicheren privaten Netzwerk für eine WCF-Anwendung bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-110">A basic Windows Communication Foundation (WCF) service developed to provide information on a secure private network to a WCF application.</span></span>  
  
 [<span data-ttu-id="bb0e0-111">Transportsicherheit mit Standardauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="bb0e0-111">Transport Security with Basic Authentication</span></span>](transport-security-with-basic-authentication.md)  
 <span data-ttu-id="bb0e0-112">Mit dieser Anwendung können sich Clients anhand einer benutzerdefinierten Authentifizierung anmelden.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-112">The application allows clients to log on using custom authentication.</span></span>  
  
 [<span data-ttu-id="bb0e0-113">Transportsicherheit mit Windows-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="bb0e0-113">Transport Security with Windows Authentication</span></span>](transport-security-with-windows-authentication.md)  
 <span data-ttu-id="bb0e0-114">Zeigt einen von der Windows-Sicherheit gesicherten Client und Dienst.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-114">Shows a client and service secured by Windows security.</span></span>  
  
 [<span data-ttu-id="bb0e0-115">Transportsicherheit mit einem anonymen Client</span><span class="sxs-lookup"><span data-stu-id="bb0e0-115">Transport Security with an Anonymous Client</span></span>](transport-security-with-an-anonymous-client.md)  
 <span data-ttu-id="bb0e0-116">Dieses Szenario verwendet die Transportsicherheit (wie HTTPS), um Vertraulichkeit und Integrität sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-116">This scenario uses transport security (such as HTTPS) to ensure confidentiality and integrity.</span></span>  
  
 [<span data-ttu-id="bb0e0-117">Transportsicherheit mit Zertifikatauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="bb0e0-117">Transport Security with Certificate Authentication</span></span>](transport-security-with-certificate-authentication.md)  
 <span data-ttu-id="bb0e0-118">Zeigt einen mit einem Zertifikat gesicherten Client und Dienst.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-118">Shows a client and service secured by a certificate.</span></span>  
  
 [<span data-ttu-id="bb0e0-119">Nachrichtensicherheit mit einem anonymen Client</span><span class="sxs-lookup"><span data-stu-id="bb0e0-119">Message Security with an Anonymous Client</span></span>](message-security-with-an-anonymous-client.md)  
 <span data-ttu-id="bb0e0-120">Zeigt einen von der WCF-Nachrichten Sicherheit gesicherten Client und Dienst.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-120">Shows a client and service secured by WCF message security.</span></span>  
  
 [<span data-ttu-id="bb0e0-121">Nachrichtensicherheit über einen Benutzernamenclient</span><span class="sxs-lookup"><span data-stu-id="bb0e0-121">Message Security with a User Name Client</span></span>](message-security-with-a-user-name-client.md)  
 <span data-ttu-id="bb0e0-122">Der Client ist eine Windows Forms-Anwendung, mit der sich die Clients mithilfe eines Domänenbenutzernamens und -Kennworts anmelden können.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-122">The client is a Windows Forms application that allows clients to log on using a domain user name and password.</span></span>  
  
 [<span data-ttu-id="bb0e0-123">Nachrichtensicherheit durch einem Zertifikatclient</span><span class="sxs-lookup"><span data-stu-id="bb0e0-123">Message Security with a Certificate Client</span></span>](message-security-with-a-certificate-client.md)  
 <span data-ttu-id="bb0e0-124">Server haben Zertifikate, und jeder Client hat ein Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-124">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="bb0e0-125">Ein Sicherheitskontext wird durch eine TLS-Aushandlung erstellt.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-125">A security context is established through Transport Layer Security (TLS) negotiation.</span></span>  
  
 [<span data-ttu-id="bb0e0-126">Nachrichtensicherheit über einen Windows-Client</span><span class="sxs-lookup"><span data-stu-id="bb0e0-126">Message Security with a Windows Client</span></span>](message-security-with-a-windows-client.md)  
 <span data-ttu-id="bb0e0-127">Eine Variante des Zertifikatsclients.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-127">A variation of the certificate client.</span></span> <span data-ttu-id="bb0e0-128">Server haben Zertifikate, und jeder Client hat ein Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-128">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="bb0e0-129">Ein Sicherheitskontext wird durch eine TLS-Aushandlung erstellt.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-129">A security context is established through TLS negotiation.</span></span>  
  
 [<span data-ttu-id="bb0e0-130">Nachrichtensicherheit mit einem Windows-Client ohne Anmeldeinformationen-Aushandlung</span><span class="sxs-lookup"><span data-stu-id="bb0e0-130">Message Security with a Windows Client without Credential Negotiation</span></span>](message-security-with-a-windows-client-without-credential-negotiation.md)  
 <span data-ttu-id="bb0e0-131">Zeigt einen von einer Kerberos-Domäne gesicherten Client und Dienst.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-131">Shows a client and service secured by a Kerberos domain.</span></span>  
  
 [<span data-ttu-id="bb0e0-132">Nachrichtensicherheit durch gegenseitige Zertifikate</span><span class="sxs-lookup"><span data-stu-id="bb0e0-132">Message Security with Mutual Certificates</span></span>](message-security-with-mutual-certificates.md)  
 <span data-ttu-id="bb0e0-133">Server haben Zertifikate, und jeder Client hat ein Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-133">Servers have certificates, and each client has a certificate.</span></span> <span data-ttu-id="bb0e0-134">Das Serverzertifikat wird mit der Anwendung verteilt und steht außerhalb des Bereichs zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-134">The server certificate is distributed with the application and is available out of band.</span></span>  
  
 [<span data-ttu-id="bb0e0-135">Nachrichtensicherheit durch ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="bb0e0-135">Message Security with Issued Tokens</span></span>](message-security-with-issued-tokens.md)  
 <span data-ttu-id="bb0e0-136">Verbundsicherheit, die Vertrauenswürdigkeit zwischen unabhängigen Domänen ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-136">Federated security that enables the establishment of trust between independent domains.</span></span>  
  
 [<span data-ttu-id="bb0e0-137">Vertrauenswürdiges Subsystem</span><span class="sxs-lookup"><span data-stu-id="bb0e0-137">Trusted Subsystem</span></span>](trusted-subsystem.md)  
 <span data-ttu-id="bb0e0-138">Ein Client greift auf einen oder mehrere Webdienste zu, die über das Netzwerk verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-138">A client accesses one or more Web services that are distributed across a network.</span></span> <span data-ttu-id="bb0e0-139">Die Webdienste greifen auf zusätzliche Ressourcen (z. B. Datenbanken oder andere Webdienste) zu, die gesichert werden müssen.</span><span class="sxs-lookup"><span data-stu-id="bb0e0-139">The Web services access additional resources (such as databases or other Web services) that must be secured.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="bb0e0-140">Referenz</span><span class="sxs-lookup"><span data-stu-id="bb0e0-140">Reference</span></span>  

 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="bb0e0-141">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="bb0e0-141">Related Sections</span></span>  

 [<span data-ttu-id="bb0e0-142">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="bb0e0-142">Authorization</span></span>](authorization-in-wcf.md)  
  
 [<span data-ttu-id="bb0e0-143">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="bb0e0-143">Security Overview</span></span>](security-overview.md)  
  
 [<span data-ttu-id="bb0e0-144">Security</span><span class="sxs-lookup"><span data-stu-id="bb0e0-144">Security</span></span>](security.md)  
  
 [<span data-ttu-id="bb0e0-145">Bindungen und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="bb0e0-145">Bindings and Security</span></span>](bindings-and-security.md)  
  
 [<span data-ttu-id="bb0e0-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="bb0e0-146">Securing Services and Clients</span></span>](securing-services-and-clients.md)  
  
 [<span data-ttu-id="bb0e0-147">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="bb0e0-147">Authentication</span></span>](authentication-in-wcf.md)  
  
 [<span data-ttu-id="bb0e0-148">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="bb0e0-148">Authorization</span></span>](authorization-in-wcf.md)  
  
 [<span data-ttu-id="bb0e0-149">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="bb0e0-149">Federation and Issued Tokens</span></span>](federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="bb0e0-150">Überwachung</span><span class="sxs-lookup"><span data-stu-id="bb0e0-150">Auditing</span></span>](auditing-security-events.md)  
  
## <a name="see-also"></a><span data-ttu-id="bb0e0-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bb0e0-151">See also</span></span>

- [<span data-ttu-id="bb0e0-152">Sicherheitsleitfaden und empfohlene Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="bb0e0-152">Security Guidance and Best Practices</span></span>](security-guidance-and-best-practices.md)
- <span data-ttu-id="bb0e0-153">[Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="bb0e0-153">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
