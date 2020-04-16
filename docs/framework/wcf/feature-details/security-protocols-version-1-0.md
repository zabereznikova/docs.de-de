---
title: Sicherheitsprotokolle, Version&#160;1.0
ms.date: 03/30/2017
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
ms.openlocfilehash: 0b86d870350d8728134cd2b42bbeb232183535bc
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463804"
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="f10bf-102">Sicherheitsprotokolle, Version&#160;1.0</span><span class="sxs-lookup"><span data-stu-id="f10bf-102">Security Protocols version 1.0</span></span>
<span data-ttu-id="f10bf-103">Die Webdienste-Sicherheitsprotokolle bieten Webdiensten Sicherheitsmechanismen, die alle vorhandenen Nachrichtensicherheitsanforderungen eines Unternehmens abdecken.</span><span class="sxs-lookup"><span data-stu-id="f10bf-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="f10bf-104">In diesem Abschnitt werden die Details der Windows Communication Foundation <xref:System.ServiceModel.Channels.SecurityBindingElement>(WCF) Version 1.0 (in der implementiert) für die folgenden Sicherheitsprotokolle für Webdienste beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f10bf-104">This section describes the Windows Communication Foundation (WCF) version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="f10bf-105">Spezifikation/Dokument</span><span class="sxs-lookup"><span data-stu-id="f10bf-105">Specification/Document</span></span>|<span data-ttu-id="f10bf-106">Link</span><span class="sxs-lookup"><span data-stu-id="f10bf-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="f10bf-107">WSS: SOAP-Nachrichtensicherheit 1,0</span><span class="sxs-lookup"><span data-stu-id="f10bf-107">WSS: SOAP Message Security 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|
|<span data-ttu-id="f10bf-108">WSS: Username Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="f10bf-108">WSS: Username Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="f10bf-109">WSS: X509 Token Profile 1,0</span><span class="sxs-lookup"><span data-stu-id="f10bf-109">WSS: X509 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|
|<span data-ttu-id="f10bf-110">WSS: SAML 1.1 Token Profile 1,0</span><span class="sxs-lookup"><span data-stu-id="f10bf-110">WSS: SAML 1.1 Token Profile 1.0</span></span>|<https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|
|<span data-ttu-id="f10bf-111">WSS: SOAP-Nachrichtensicherheit 1.1</span><span class="sxs-lookup"><span data-stu-id="f10bf-111">WSS: SOAP Message Security 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|
|<span data-ttu-id="f10bf-112">WSS: Username Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="f10bf-112">WSS Username Token Profile 1.1</span></span>|<https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|
|<span data-ttu-id="f10bf-113">WSS: X.509 Token Profile 1,1</span><span class="sxs-lookup"><span data-stu-id="f10bf-113">WSS: X.509 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|
|<span data-ttu-id="f10bf-114">WSS: Kerberos Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="f10bf-114">WSS: Kerberos Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|
|<span data-ttu-id="f10bf-115">WSS: SAML 1.1 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="f10bf-115">WSS: SAML 1.1 Token Profile 1.1</span></span>|<https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|
|<span data-ttu-id="f10bf-116">WS-Secure Conversation</span><span class="sxs-lookup"><span data-stu-id="f10bf-116">WS-Secure Conversation</span></span>|<https://specs.xmlsoap.org/ws/2005/02/sc/WS-SecureConversation.pdf>|
|<span data-ttu-id="f10bf-117">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="f10bf-117">WS-Trust</span></span>|<https://specs.xmlsoap.org/ws/2005/02/trust/ws-trust.pdf>|
|<span data-ttu-id="f10bf-118">Anwendungshinweis:</span><span class="sxs-lookup"><span data-stu-id="f10bf-118">Application Note:</span></span><br /><br /> <span data-ttu-id="f10bf-119">Verwenden von WS-Trust für TLS Handshake</span><span class="sxs-lookup"><span data-stu-id="f10bf-119">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="f10bf-120">Wird veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="f10bf-120">To be published</span></span>|  
|<span data-ttu-id="f10bf-121">Anwendungshinweis:</span><span class="sxs-lookup"><span data-stu-id="f10bf-121">Application Note:</span></span><br /><br /> <span data-ttu-id="f10bf-122">Verwenden von WS-Trust für SPNEGO</span><span class="sxs-lookup"><span data-stu-id="f10bf-122">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="f10bf-123">Wird veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="f10bf-123">To be published</span></span>|  
|<span data-ttu-id="f10bf-124">Anwendungshinweis:</span><span class="sxs-lookup"><span data-stu-id="f10bf-124">Application Note:</span></span><br /><br /> <span data-ttu-id="f10bf-125">Webdienste-Adressierungsendpunktverweise und -identität</span><span class="sxs-lookup"><span data-stu-id="f10bf-125">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="f10bf-126">Wird veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="f10bf-126">To be published</span></span>|  
|<span data-ttu-id="f10bf-127">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="f10bf-127">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="f10bf-128">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="f10bf-128">(2005/07)</span></span>|<https://specs.xmlsoap.org/ws/2005/07/securitypolicy/ws-securitypolicy.pdf><br /><br /> <span data-ttu-id="f10bf-129">in der durch [errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) geänderten Fassung, die dem TECHNISCHEN Ausschuss von OASIS WS-SX vorgelegt wurde</span><span class="sxs-lookup"><span data-stu-id="f10bf-129">as amended by [errata](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html) submitted to OASIS WS-SX Technical Committee</span></span> |  
  
 <span data-ttu-id="f10bf-130">WCF, Version 1, bietet 17 Authentifizierungsmodi, die als Grundlage für die Sicherheitskonfiguration von Webdiensten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="f10bf-130">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="f10bf-131">Jeder Modus wird für einen allgemeinen Satz von Bereitstellungsanforderungen optimiert, z.&#160;B.:</span><span class="sxs-lookup"><span data-stu-id="f10bf-131">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
- <span data-ttu-id="f10bf-132">Anmeldeinformationen, die zum Authentifizieren von Client und Dienst verwendet werden</span><span class="sxs-lookup"><span data-stu-id="f10bf-132">Credentials used to authenticate client and service.</span></span>  
  
- <span data-ttu-id="f10bf-133">Nachrichten- oder Transportsicherheitsschutzmechanismen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-133">Message or transport security protection mechanisms.</span></span>  
  
- <span data-ttu-id="f10bf-134">Nachrichtenaustauschmuster</span><span class="sxs-lookup"><span data-stu-id="f10bf-134">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="f10bf-135">Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="f10bf-135">Authentication Mode</span></span>|<span data-ttu-id="f10bf-136">Clientauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="f10bf-136">Client Authentication</span></span>|<span data-ttu-id="f10bf-137">Serverauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="f10bf-137">Server Authentication</span></span>|<span data-ttu-id="f10bf-138">Mode</span><span class="sxs-lookup"><span data-stu-id="f10bf-138">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="f10bf-139">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="f10bf-139">UserNameOverTransport</span></span>|<span data-ttu-id="f10bf-140">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-140">User name/password</span></span>|<span data-ttu-id="f10bf-141">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-141">X509</span></span>|<span data-ttu-id="f10bf-142">Transport</span><span class="sxs-lookup"><span data-stu-id="f10bf-142">Transport</span></span>|  
|<span data-ttu-id="f10bf-143">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="f10bf-143">CertificateOverTransport</span></span>|<span data-ttu-id="f10bf-144">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-144">X509</span></span>|<span data-ttu-id="f10bf-145">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-145">X509</span></span>|<span data-ttu-id="f10bf-146">Transport</span><span class="sxs-lookup"><span data-stu-id="f10bf-146">Transport</span></span>|  
|<span data-ttu-id="f10bf-147">KerberosOverTransport.</span><span class="sxs-lookup"><span data-stu-id="f10bf-147">KerberosOverTransport</span></span>|<span data-ttu-id="f10bf-148">Windows</span><span class="sxs-lookup"><span data-stu-id="f10bf-148">Windows</span></span>|<span data-ttu-id="f10bf-149">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-149">X509</span></span>|<span data-ttu-id="f10bf-150">Transport</span><span class="sxs-lookup"><span data-stu-id="f10bf-150">Transport</span></span>|  
|<span data-ttu-id="f10bf-151">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="f10bf-151">IssuedTokenOverTransport</span></span>|<span data-ttu-id="f10bf-152">Im Verbund</span><span class="sxs-lookup"><span data-stu-id="f10bf-152">Federated</span></span>|<span data-ttu-id="f10bf-153">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-153">X509</span></span>|<span data-ttu-id="f10bf-154">Transport</span><span class="sxs-lookup"><span data-stu-id="f10bf-154">Transport</span></span>|  
|<span data-ttu-id="f10bf-155">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="f10bf-155">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="f10bf-156">Windows Sspi wurde verhandelt</span><span class="sxs-lookup"><span data-stu-id="f10bf-156">Windows Sspi Negotiated</span></span>|<span data-ttu-id="f10bf-157">Windows Sspi wurde verhandelt</span><span class="sxs-lookup"><span data-stu-id="f10bf-157">Windows Sspi Negotiated</span></span>|<span data-ttu-id="f10bf-158">Transport</span><span class="sxs-lookup"><span data-stu-id="f10bf-158">Transport</span></span>|  
|<span data-ttu-id="f10bf-159">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="f10bf-159">AnonymousForCertificate</span></span>|<span data-ttu-id="f10bf-160">Keine</span><span class="sxs-lookup"><span data-stu-id="f10bf-160">None</span></span>|<span data-ttu-id="f10bf-161">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-161">X509</span></span>|<span data-ttu-id="f10bf-162">`Message`</span><span class="sxs-lookup"><span data-stu-id="f10bf-162">Message</span></span>|  
|<span data-ttu-id="f10bf-163">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="f10bf-163">UserNameForCertificate</span></span>|<span data-ttu-id="f10bf-164">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-164">User name/password</span></span>|<span data-ttu-id="f10bf-165">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-165">X509</span></span>|<span data-ttu-id="f10bf-166">`Message`</span><span class="sxs-lookup"><span data-stu-id="f10bf-166">Message</span></span>|  
|<span data-ttu-id="f10bf-167">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="f10bf-167">MutualCertificate</span></span>|<span data-ttu-id="f10bf-168">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-168">X509</span></span>|<span data-ttu-id="f10bf-169">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-169">X509</span></span>|<span data-ttu-id="f10bf-170">`Message`</span><span class="sxs-lookup"><span data-stu-id="f10bf-170">Message</span></span>|  
|<span data-ttu-id="f10bf-171">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="f10bf-171">MutualCertificateDuplex</span></span>|<span data-ttu-id="f10bf-172">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-172">X509</span></span>|<span data-ttu-id="f10bf-173">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-173">X509</span></span>|<span data-ttu-id="f10bf-174">`Message`</span><span class="sxs-lookup"><span data-stu-id="f10bf-174">Message</span></span>|  
|<span data-ttu-id="f10bf-175">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="f10bf-175">IssuedTokenForCertificate</span></span>|<span data-ttu-id="f10bf-176">Im Verbund</span><span class="sxs-lookup"><span data-stu-id="f10bf-176">Federated</span></span>|<span data-ttu-id="f10bf-177">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-177">X509</span></span>|<span data-ttu-id="f10bf-178">`Message`</span><span class="sxs-lookup"><span data-stu-id="f10bf-178">Message</span></span>|  
|<span data-ttu-id="f10bf-179">Kerberos</span><span class="sxs-lookup"><span data-stu-id="f10bf-179">Kerberos</span></span>|<span data-ttu-id="f10bf-180">Windows</span><span class="sxs-lookup"><span data-stu-id="f10bf-180">Windows</span></span>|<span data-ttu-id="f10bf-181">Windows</span><span class="sxs-lookup"><span data-stu-id="f10bf-181">Windows</span></span>|<span data-ttu-id="f10bf-182">`Message`</span><span class="sxs-lookup"><span data-stu-id="f10bf-182">Message</span></span>|  
|<span data-ttu-id="f10bf-183">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="f10bf-183">IssuedToken</span></span>|<span data-ttu-id="f10bf-184">Im Verbund</span><span class="sxs-lookup"><span data-stu-id="f10bf-184">Federated</span></span>|<span data-ttu-id="f10bf-185">Im Verbund</span><span class="sxs-lookup"><span data-stu-id="f10bf-185">Federated</span></span>|<span data-ttu-id="f10bf-186">`Message`</span><span class="sxs-lookup"><span data-stu-id="f10bf-186">Message</span></span>|  
|<span data-ttu-id="f10bf-187">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="f10bf-187">SspiNegotiated</span></span>|<span data-ttu-id="f10bf-188">Windows Sspi wurde verhandelt</span><span class="sxs-lookup"><span data-stu-id="f10bf-188">Windows Sspi Negotiated</span></span>|<span data-ttu-id="f10bf-189">Windows Sspi wurde verhandelt</span><span class="sxs-lookup"><span data-stu-id="f10bf-189">Windows Sspi Negotiated</span></span>|<span data-ttu-id="f10bf-190">`Message`</span><span class="sxs-lookup"><span data-stu-id="f10bf-190">Message</span></span>|  
|<span data-ttu-id="f10bf-191">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f10bf-191">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="f10bf-192">Keine</span><span class="sxs-lookup"><span data-stu-id="f10bf-192">None</span></span>|<span data-ttu-id="f10bf-193">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="f10bf-193">X509, TLS-Nego</span></span>|<span data-ttu-id="f10bf-194">`Message`</span><span class="sxs-lookup"><span data-stu-id="f10bf-194">Message</span></span>|  
|<span data-ttu-id="f10bf-195">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f10bf-195">UserNameForSslNegotiated</span></span>|<span data-ttu-id="f10bf-196">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-196">User name/password</span></span>|<span data-ttu-id="f10bf-197">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="f10bf-197">X509, TLS-Nego</span></span>|<span data-ttu-id="f10bf-198">`Message`</span><span class="sxs-lookup"><span data-stu-id="f10bf-198">Message</span></span>|  
|<span data-ttu-id="f10bf-199">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f10bf-199">MutualSslNegotiated</span></span>|<span data-ttu-id="f10bf-200">X509</span><span class="sxs-lookup"><span data-stu-id="f10bf-200">X509</span></span>|<span data-ttu-id="f10bf-201">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="f10bf-201">X509, TLS-Nego</span></span>|<span data-ttu-id="f10bf-202">`Message`</span><span class="sxs-lookup"><span data-stu-id="f10bf-202">Message</span></span>|  
|<span data-ttu-id="f10bf-203">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f10bf-203">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="f10bf-204">Im Verbund</span><span class="sxs-lookup"><span data-stu-id="f10bf-204">Federated</span></span>|<span data-ttu-id="f10bf-205">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="f10bf-205">X509, TLS-Nego</span></span>|<span data-ttu-id="f10bf-206">`Message`</span><span class="sxs-lookup"><span data-stu-id="f10bf-206">Message</span></span>|  
  
 <span data-ttu-id="f10bf-207">Endpunkte, die solche Authentifizierungsmodi verwenden, können ihre Sicherheitsanforderungen über WS-SecurityPolicy (WS-SP) ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="f10bf-207">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="f10bf-208">Dieses Dokument beschreibt die Struktur der Sicherheitsheader und der Infrastrukturnachrichten für jeden Authentifizierungsmodus und bietet Richtlinien- und Nachrichtenbeispiele.</span><span class="sxs-lookup"><span data-stu-id="f10bf-208">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="f10bf-209">WCF nutzt WS-SecureConversation, um Unterstützung für sichere Sitzungen zum Schutz des Austauschs von mehreren Nachrichten zwischen Anwendungen bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-209">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="f10bf-210">Weitere Informationen zur Implementierung finden Sie unten unter "Sichere Sitzungen".</span><span class="sxs-lookup"><span data-stu-id="f10bf-210">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="f10bf-211">Zusätzlich zu den Authentifizierungsmodi bietet WCF Einstellungen zur Steuerung allgemeiner Schutzmechanismen, die für die meisten nachrichtensicherheitsbasierten Authentifizierungsmodi gelten, z. B. Signaturreihenfolge im Vergleich zu Verschlüsselungsvorgängen, Algorithmussammlungen, Schlüsselableitung und Signaturbestätigung.</span><span class="sxs-lookup"><span data-stu-id="f10bf-211">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="f10bf-212">Die folgenden XML-Präfixe und -Namespaces werden in diesem Dokument verwendet.</span><span class="sxs-lookup"><span data-stu-id="f10bf-212">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="f10bf-213">Präfix</span><span class="sxs-lookup"><span data-stu-id="f10bf-213">Prefix</span></span>|<span data-ttu-id="f10bf-214">Namespace</span><span class="sxs-lookup"><span data-stu-id="f10bf-214">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="f10bf-215">s</span><span class="sxs-lookup"><span data-stu-id="f10bf-215">s</span></span>|<http://www.w3.org/2003/05/soap-envelope/>|
|<span data-ttu-id="f10bf-216">sp</span><span class="sxs-lookup"><span data-stu-id="f10bf-216">sp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/>|
|<span data-ttu-id="f10bf-217">a</span><span class="sxs-lookup"><span data-stu-id="f10bf-217">a</span></span>|<http://www.w3.org/2005/08/addressing>|  
|<span data-ttu-id="f10bf-218">wsse</span><span class="sxs-lookup"><span data-stu-id="f10bf-218">wsse</span></span>|<span data-ttu-id="f10bf-219">TBD – OASIS WSS 1,0 URI</span><span class="sxs-lookup"><span data-stu-id="f10bf-219">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="f10bf-220">wsse11</span><span class="sxs-lookup"><span data-stu-id="f10bf-220">wsse11</span></span>|<span data-ttu-id="f10bf-221">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="f10bf-221">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="f10bf-222">wsu</span><span class="sxs-lookup"><span data-stu-id="f10bf-222">wsu</span></span>|<span data-ttu-id="f10bf-223">TBD – OASIS WSS 1.0 Utility URI</span><span class="sxs-lookup"><span data-stu-id="f10bf-223">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="f10bf-224">ds</span><span class="sxs-lookup"><span data-stu-id="f10bf-224">ds</span></span>|<span data-ttu-id="f10bf-225">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="f10bf-225">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="f10bf-226">wst</span><span class="sxs-lookup"><span data-stu-id="f10bf-226">wst</span></span>|<span data-ttu-id="f10bf-227">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="f10bf-227">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="f10bf-228">wssc</span><span class="sxs-lookup"><span data-stu-id="f10bf-228">wssc</span></span>|<span data-ttu-id="f10bf-229">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="f10bf-229">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="f10bf-230">wsaw</span><span class="sxs-lookup"><span data-stu-id="f10bf-230">wsaw</span></span>|<span data-ttu-id="f10bf-231">TBD – WS-Addressing-Richtliniennamespace</span><span class="sxs-lookup"><span data-stu-id="f10bf-231">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="f10bf-232">wsp</span><span class="sxs-lookup"><span data-stu-id="f10bf-232">wsp</span></span>|<http://schemas.xmlsoap.org/ws/2004/09/policy>|  
|<span data-ttu-id="f10bf-233">mssp</span><span class="sxs-lookup"><span data-stu-id="f10bf-233">mssp</span></span>|<http://schemas.xmlsoap.org/ws/2005/07/securitypolicy>|
  
## <a name="1-token-profiles"></a><span data-ttu-id="f10bf-234">1. Token-Profile</span><span class="sxs-lookup"><span data-stu-id="f10bf-234">1. Token Profiles</span></span>  
 <span data-ttu-id="f10bf-235">Webdienst-Sicherheitsspezifikationen stellen Anmeldeinformationen als Sicherheitstoken dar.</span><span class="sxs-lookup"><span data-stu-id="f10bf-235">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="f10bf-236">WCF unterstützt die folgenden Tokentypen:</span><span class="sxs-lookup"><span data-stu-id="f10bf-236">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="f10bf-237">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="f10bf-237">1.1 UsernameToken</span></span>  
 <span data-ttu-id="f10bf-238">WCF folgt den Profilen UsernameToken10 und UsernameToken11 mit den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="f10bf-238">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="f10bf-239">Das R1101 PasswordType-Attribut auf Element UsernameToken\Password MUSS entweder weggelassen werden oder über den Wert #PasswordText (Standard) verfügen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-239">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="f10bf-240">Man kann #PasswordDigest über Erweiterbarkeit implementieren.</span><span class="sxs-lookup"><span data-stu-id="f10bf-240">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="f10bf-241">Es wurde beobachtet, dass #PasswordDigest oft für einen Kennwortschutzmechanismus gehalten wurde, der sicher genug ist.</span><span class="sxs-lookup"><span data-stu-id="f10bf-241">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="f10bf-242">Aber #PasswordDigest kann nicht als Ersatz für eine Verschlüsselung von UsernameToken dienen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-242">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="f10bf-243">Das primäre Ziel von #PasswordDigest ist ein Schutz vor Replay-Angriffen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-243">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="f10bf-244">In WCF-Authentifizierungsmodi werden Wiederholungsangriffsbedrohungen durch die Verwendung von Nachrichtensignaturen verringert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-244">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="f10bf-245">B1102 WCF gibt niemals Nonce und Erstellte Unterelemente des UsernameToken aus.</span><span class="sxs-lookup"><span data-stu-id="f10bf-245">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="f10bf-246">Diese Unterelemente sollen die Replay-Erkennung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-246">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="f10bf-247">WCF verwendet stattdessen Nachrichtensignaturen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-247">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="f10bf-248">OASIS WSS SOAP Message Security UsernameToken Profile&#160;1.1 (UsernameToken11) hat eine Schlüsselableitung der Kennwortfunktion eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f10bf-248">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="f10bf-249">B1103 Das UsernameToken-Kennwort DARF NICHT für die Schlüsselableitung und daher nicht für kryptografische Vorgänge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f10bf-249">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="f10bf-250">Begründung: Kennwörter werden im Allgemeinen als zu schwach für die Verwendung in kryptografischen Vorgängen angesehen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-250">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="f10bf-251">1.2 X509 Token</span><span class="sxs-lookup"><span data-stu-id="f10bf-251">1.2 X509 Token</span></span>  
 <span data-ttu-id="f10bf-252">WCF unterstützt X509v3-Zertifikate als Anmeldeinformationstyp und folgt X509TokenProfile1.0 und X509TokenProfile1.1 mit den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="f10bf-252">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="f10bf-253">R1201 Das ValueType-Attribut auf dem BinarySecurityToken-Element muss den Wert #X509v3 besitzen, wenn es ein X509v3-Zertifikat enthält.</span><span class="sxs-lookup"><span data-stu-id="f10bf-253">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="f10bf-254">WSS X509 Token Profile 1.0 und 1.1 definieren auch #X509PKIPathv1 und #PKCS7 als Werttypen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-254">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="f10bf-255">WCF unterstützt diese Typen nicht.</span><span class="sxs-lookup"><span data-stu-id="f10bf-255">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="f10bf-256">R1202 Wenn eine SubjectKeyIdentifier (SKI)-Erweiterung in einem X509-Zertifikat vorliegt, sollte wsse:KeyIdentifier als externe Referenz für das Token verwendet werden, wobei das ValueType-Attribut #X509SubjectKeyIdentifier und sein Inhalt der base64-codierte Wert der SKI-Erweiterung des Zertifikats ist.</span><span class="sxs-lookup"><span data-stu-id="f10bf-256">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="f10bf-257">SKI-Verweise werden überall implementiert und haben sich als äußerst interoperabler Typ für externe Verweise erwiesen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-257">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="f10bf-258">R1203 Ein externer Verweis auf das X509-Sicherheitstoken SOLLTE NICHT ds:X509IssuerSerial verwenden.</span><span class="sxs-lookup"><span data-stu-id="f10bf-258">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="f10bf-259">R1204 Wenn X509TokenProfile1.1 verwendet wird, SOLLTE eine externe Referenz auf das X509-Sicherheitstoken den Fingerabdruck, der von WS-Sicherheit&#160;1.1 eingeführt wird, verwenden.</span><span class="sxs-lookup"><span data-stu-id="f10bf-259">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="f10bf-260">WCF unterstützt X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="f10bf-260">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="f10bf-261">Es gibt jedoch Interoperabilitätsprobleme mit X509IssuerSerial: WCF verwendet eine Zeichenfolge, um zwei Werte von X509IssuerSerial zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-261">However There are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="f10bf-262">Wenn man also Komponenten des Antragstellernamens neu ordnet und an einen WCF-Dienst einen Verweis auf ein Zertifikat sendet, wird er möglicherweise nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="f10bf-262">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="f10bf-263">1.3 Kerberos-Token</span><span class="sxs-lookup"><span data-stu-id="f10bf-263">1.3 Kerberos Token</span></span>  
 <span data-ttu-id="f10bf-264">WCF unterstützt KerberosTokenProfile1.1 für die Windows-Authentifizierung mit den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="f10bf-264">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="f10bf-265">R1301 Ein Kerberos-Token muss den Wert eines GSS-ummantelten Kerberos&#160;v4&#160;AP_REQ tragen, gemäß der Definition in GSS_API und der Kerberos-Spezifikation, und muss das ValueType-Attribut mit dem Wert #GSS_Kerberosv5_AP_REQ besitzen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-265">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="f10bf-266">WCF verwendet GSS-umschlossene Kerberos AP-REQ, keinen nackten AP-REQ.</span><span class="sxs-lookup"><span data-stu-id="f10bf-266">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="f10bf-267">Hierbei handelt es sich um eine empfohlene Vorgehensweise bezüglich der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="f10bf-267">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="f10bf-268">1.4 SAML v1.1 Token</span><span class="sxs-lookup"><span data-stu-id="f10bf-268">1.4 SAML v1.1 Token</span></span>  
 <span data-ttu-id="f10bf-269">WCF unterstützt WSS SAML-Tokenprofile 1.0 und 1.1 für SAML v1.1-Token.</span><span class="sxs-lookup"><span data-stu-id="f10bf-269">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="f10bf-270">Es ist möglich, andere Versionen von SAML-Tokenformaten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="f10bf-270">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="f10bf-271">1.5 Sicherheitskontexttoken</span><span class="sxs-lookup"><span data-stu-id="f10bf-271">1.5 Security Context Token</span></span>  
 <span data-ttu-id="f10bf-272">WCF unterstützt das in WS-SecureConversation eingeführte Sicherheitskontexttoken (Security Context Token, SCT).</span><span class="sxs-lookup"><span data-stu-id="f10bf-272">WCF supports the Security Context Token (SCT) introduced in WS-SecureConversation.</span></span> <span data-ttu-id="f10bf-273">SCT wird verwendet, um einen Sicherheitskontext darzustellen, der in SecureConversation genauso etabliert ist wie in den Binärverhandlungsprotokollen TLS und SSPI (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="f10bf-273">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="f10bf-274">2. Allgemeine Nachrichtensicherheitsparameter</span><span class="sxs-lookup"><span data-stu-id="f10bf-274">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="f10bf-275">2.1 TimeStamp</span><span class="sxs-lookup"><span data-stu-id="f10bf-275">2.1 TimeStamp</span></span>  
 <span data-ttu-id="f10bf-276">Die <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A>-Eigenschaft der <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse steuert, ob ein Zeitstempel vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f10bf-276">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="f10bf-277">WCF serialisiert wsse:TimeStamp immer mit den Feldern wsse:Created und wsse:Expires.</span><span class="sxs-lookup"><span data-stu-id="f10bf-277">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="f10bf-278">Der wsse:TimeStamp wird immer signiert, wenn Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f10bf-278">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="f10bf-279">2.2 Schutzreihenfolge</span><span class="sxs-lookup"><span data-stu-id="f10bf-279">2.2 Protection Order</span></span>  
 <span data-ttu-id="f10bf-280">WCF unterstützt die Meldungsschutzanordnung "Vor Verschlüsseln" und "Vor Signieren verschlüsseln" (Sicherheitsrichtlinie 1.1).</span><span class="sxs-lookup"><span data-stu-id="f10bf-280">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="f10bf-281">"Sign Before Encrypt" wird u.&#160;a. aus den folgenden Gründen empfohlen: Mit "Encrypt Before Sign" geschützte Nachrichten sind Signaturersatzangriffen ausgesetzt, sofern der WS-Sicherheit&#160;1.1 SignatureConfirmation-Mechanismus nicht verwendet wird, und eine Signatur über verschlüsselten Inhalt erschwert die Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="f10bf-281">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="f10bf-282">2.3 Signaturschutz</span><span class="sxs-lookup"><span data-stu-id="f10bf-282">2.3 Signature Protection</span></span>  
 <span data-ttu-id="f10bf-283">Wenn Encrypt Before Sign verwendet wird, ist es empfehlenswert, die Signatur zu schützen, um Brute-Force-Angriffe zu verhindern, die versuchen, den verschlüsselten Inhalt oder den Signaturschlüssel zu erraten (besonders dann, wenn ein benutzerdefiniertes Token zusammen mit schwachen Schlüsselmaterialien verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="f10bf-283">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="f10bf-284">2.4 Algorithmussuites</span><span class="sxs-lookup"><span data-stu-id="f10bf-284">2.4 Algorithm Suite</span></span>  
 <span data-ttu-id="f10bf-285">WCF unterstützt alle in Security Policy 1.1 aufgeführten Algorithmussammlungen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-285">WCF supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="f10bf-286">2.5 Schlüsselableitung</span><span class="sxs-lookup"><span data-stu-id="f10bf-286">2.5 Key Derivation</span></span>  
 <span data-ttu-id="f10bf-287">WCF verwendet "Key Derivation for symmetrische Keys", wie in WS-SecureConversation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f10bf-287">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="f10bf-288">2.6 Signaturbestätigung</span><span class="sxs-lookup"><span data-stu-id="f10bf-288">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="f10bf-289">Signaturbestätigung kann als Schutz gegen Angriffe von Mittelsmännern eingesetzt werden, um den Signatursatz zu schützen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-289">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="f10bf-290">2.7 Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="f10bf-290">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="f10bf-291">Jeder Authentifizierungsmodus beschreibt ein bestimmtes Layout für den Sicherheitsheader.</span><span class="sxs-lookup"><span data-stu-id="f10bf-291">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="f10bf-292">Elemente innerhalb des Sicherheitsheaders sind teilweise geordnet.</span><span class="sxs-lookup"><span data-stu-id="f10bf-292">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="f10bf-293">Um die Reihenfolge der untergeordneten Sicherheitsheaderelemente zu definieren, definiert die WS-Sicherheitsrichtlinie die folgenden Sicherheitsheader-Layoutmodi:</span><span class="sxs-lookup"><span data-stu-id="f10bf-293">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f10bf-294">Strict</span><span class="sxs-lookup"><span data-stu-id="f10bf-294">Strict</span></span>|<span data-ttu-id="f10bf-295">Dem Sicherheitsheader werden Elemente gemäß den durchnummerierten Layout-Regeln, die im Abschnitt&#160;7.7.1 der Sicherheitsrichtlinien beschrieben werden, und gemäß dem allgemeinen Prinzip der "Deklaration vor der Verwendung" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f10bf-295">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="f10bf-296">Lax</span><span class="sxs-lookup"><span data-stu-id="f10bf-296">Lax</span></span>|<span data-ttu-id="f10bf-297">Die Elemente werden dem Sicherheitsheader in einer beliebigen Reihenfolge hinzugefügt, die der WSS: SOAP Message Security entspricht.</span><span class="sxs-lookup"><span data-stu-id="f10bf-297">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="f10bf-298">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="f10bf-298">LaxTimestampFirst</span></span>|<span data-ttu-id="f10bf-299">Ebenso wie Lax, nur dass das erste Element im Sicherheitsheader ein wsse:Timestamp sein muss</span><span class="sxs-lookup"><span data-stu-id="f10bf-299">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="f10bf-300">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="f10bf-300">LaxTimestampLast</span></span>|<span data-ttu-id="f10bf-301">Ebenso wie Lax, nur dass das letzte Element im Sicherheitsheader ein wsse:Timestamp sein muss</span><span class="sxs-lookup"><span data-stu-id="f10bf-301">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="f10bf-302">WCF unterstützt alle vier Modi für das Layout von Sicherheitsheadern.</span><span class="sxs-lookup"><span data-stu-id="f10bf-302">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="f10bf-303">Sicherheitsheader-Struktur und Nachrichtenbeispiele für die Authentifizierungsmodi unten folgen dem "Strict"-Modus.</span><span class="sxs-lookup"><span data-stu-id="f10bf-303">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="f10bf-304">2. Allgemeine Nachrichtensicherheitsparameter</span><span class="sxs-lookup"><span data-stu-id="f10bf-304">2. Common Message Security Parameters</span></span>  
 <span data-ttu-id="f10bf-305">Dieser Abschnitt bietet Beispielrichtlinien für jeden Authentifizierungsmodus, zusammen mit Beispielen, die die Sicherheitsheader-Struktur in Nachrichten, die zwischen Client und Dienst ausgetauscht werden, zeigen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-305">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="f10bf-306">6.1 Transportschutz</span><span class="sxs-lookup"><span data-stu-id="f10bf-306">6.1 Transport Protection</span></span>  
 <span data-ttu-id="f10bf-307">WCF bietet fünf Authentifizierungsmodi, die sicheren Transport zum Schutz von Nachrichten verwenden. UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport und SspiNegotiatedOverTransport.</span><span class="sxs-lookup"><span data-stu-id="f10bf-307">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="f10bf-308">Diese Authentifizierungsmodi werden mit der in der Sicherheitsrichtlinie beschriebenen Transportbindung erstellt.</span><span class="sxs-lookup"><span data-stu-id="f10bf-308">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="f10bf-309">Für den UserNameOverTransport-Authentifizierungsmodus ist das UsernameToken ein signiertes unterstützendes Token.</span><span class="sxs-lookup"><span data-stu-id="f10bf-309">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="f10bf-310">Für die anderen Authentifizierungsmodi wird das Token als signiertes unterzeichnendes Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f10bf-310">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="f10bf-311">Anhang&#160;C.1.2 und&#160;C.1.3 von SecurityPolicy beschreiben detailliert das Sicherheitsheader-Layout.</span><span class="sxs-lookup"><span data-stu-id="f10bf-311">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="f10bf-312">Die folgenden Beispielsicherheitsheader zeigen das "Strict"-Layout für einen gegebenen Authentifizierungsmodus an.</span><span class="sxs-lookup"><span data-stu-id="f10bf-312">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="f10bf-313">Der Wert der "Derived-Keys"-Eigenschaft für die Token ist in allen Fällen "false".</span><span class="sxs-lookup"><span data-stu-id="f10bf-313">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="f10bf-314">Die Werte der verschiedenen Eigenschaften der Transportbindung sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f10bf-314">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="f10bf-315">Timestamp: true</span><span class="sxs-lookup"><span data-stu-id="f10bf-315">Timestamp: true</span></span>  
  
 <span data-ttu-id="f10bf-316">Sicherheitsheader-Layout: Strict</span><span class="sxs-lookup"><span data-stu-id="f10bf-316">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="f10bf-317">Algorithmussammlung: Basic256</span><span class="sxs-lookup"><span data-stu-id="f10bf-317">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="f10bf-318">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="f10bf-318">6.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="f10bf-319">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein Benutzernamentoken, das auf der SOAP-Schicht als signiertes unterstützendes Token angezeigt wird, das immer vom Initiator an den Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="f10bf-319">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="f10bf-320">Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-320">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="f10bf-321">Die verwendete Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="f10bf-321">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="f10bf-322">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-322">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='UsernameOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:SignedSupportingTokens >  
        <wsp:Policy>  
          <sp:UsernameToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:WssUsernameToken10 />
            </wsp:Policy>  
          </sp:UsernameToken>  
        </wsp:Policy>  
      </sp:SignedSupportingTokens>  
      <sp:Wss11 >  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10 >  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="f10bf-323">Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="f10bf-323">Security Header Layout</span></span>  
  
 <span data-ttu-id="f10bf-324">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-324">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken>  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-325">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-325">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="f10bf-326">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="f10bf-326">6.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="f10bf-327">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt wird, das immer vom Initiator an den Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="f10bf-327">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="f10bf-328">Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-328">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="f10bf-329">Die verwendete Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="f10bf-329">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="f10bf-330">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-330">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CertificateOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding xmlns:sp='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy' >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
             <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy>  
              <sp:RequireThumbprintReference />
              <sp:WssX509V3Token10 />
            </wsp:Policy>  
          </sp:X509Token>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="f10bf-331">Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="f10bf-331">Security Header Layout</span></span>  
  
 <span data-ttu-id="f10bf-332">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-332">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wse:Timestamp u:Id="_0">  
  ...  
  </wse:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-333">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-333">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="f10bf-334">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="f10bf-334">6.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="f10bf-335">In diesem Authentifizierungsmodus unterstützt der Client den Dienst als solchen nicht, sondern präsentiert ein Token, das von einem Sicherheitstokendienst (Security Token Service, STS) ausgegeben wird, und einen freigegebenen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="f10bf-335">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="f10bf-336">Das ausgegebene Token wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt, das immer vom Initiator an den Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="f10bf-336">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="f10bf-337">Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="f10bf-338">Die Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="f10bf-338">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="f10bf-339">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-339">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='IssuedTokenOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding >  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:IssuedToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <sp:RequestSecurityTokenTemplate>  
              <wst:KeyType>  
              http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
              </wst:KeyType>
            </sp:RequestSecurityTokenTemplate>  
            <wsp:Policy>  
              <sp:RequireInternalReference />
            </wsp:Policy>  
          </sp:IssuedToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="f10bf-340">Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="f10bf-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="f10bf-341">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-341">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-342">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="f10bf-343">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="f10bf-343">6.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="f10bf-344">Mit diesem Authentifizierungsmodus wird der Client mit einem Kerberos-Ticket dem Dienst gegenüber authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-344">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="f10bf-345">Das Kerberos-Token wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f10bf-345">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="f10bf-346">Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-346">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="f10bf-347">Die Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="f10bf-347">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="f10bf-348">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-348">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='KerberosOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:KerberosToken  
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
            <wsp:Policy>  
              <sp:WssGssKerberosV5ApReqToken11 />
            </wsp:Policy>  
          </sp:KerberosToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
 <span data-ttu-id="f10bf-349">Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="f10bf-349">Security Header Layout</span></span>  
  
 <span data-ttu-id="f10bf-350">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-350">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken ValueType="...#GSS_Kerberosv5_AP_REQ">  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-351">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-351">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="f10bf-352">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="f10bf-352">6.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="f10bf-353">Bei diesem Modus wird ein Aushandlungsprotokoll verwendet, um Client- und Serverauthentifizierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-353">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="f10bf-354">Wenn möglich wird Kerberos verwendet, ansonsten NTLM.</span><span class="sxs-lookup"><span data-stu-id="f10bf-354">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="f10bf-355">Das resultierende SCT wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt, das immer vom Initiator an den Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="f10bf-355">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="f10bf-356">Der Dienst wird zusätzlich auf der Transportschicht über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-356">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="f10bf-357">Die verwendete Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="f10bf-357">The binding used is a transport binding.</span></span> <span data-ttu-id="f10bf-358">"SPNEGO" (Verhandlung) beschreibt, wie WCF das sSPI-binäre Aushandlungsprotokoll mit WS-Trust verwendet.</span><span class="sxs-lookup"><span data-stu-id="f10bf-358">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="f10bf-359">Die Sicherheitsheaderbeispiele in diesem Abschnitt gelten, nachdem der SCT durch den SPNEGO-Handshake eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="f10bf-359">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="f10bf-360">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-360">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SspiNegotiatedOverTransport_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:TransportBinding>  
        <wsp:Policy>  
          <sp:TransportToken>  
            <wsp:Policy>  
              <sp:HttpsToken RequireClientCertificate='false' />
            </wsp:Policy>  
          </sp:TransportToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
        </wsp:Policy>  
      </sp:TransportBinding>  
      <sp:EndorsingSupportingTokens>  
        <wsp:Policy>  
          <sp:SpnegoContextToken
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
            <wsp:Policy />
          </sp:SpnegoContextToken>  
          <sp:SignedParts>  
            <sp:Header Name='To'
Namespace='http://www.w3.org/2005/08/addressing' />
          </sp:SignedParts>  
        </wsp:Policy>  
      </sp:EndorsingSupportingTokens>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples"></a><span data-ttu-id="f10bf-361">Beispiele für Sicherheitsheader</span><span class="sxs-lookup"><span data-stu-id="f10bf-361">Security Header Examples</span></span>  
 <span data-ttu-id="f10bf-362">Sobald das Sicherheitskontexttoken einmal durch SPNEGO unter Verwendung der WS-Trust-Binäraushandlung eingeführt wurde, besitzen die Anwendungsnachrichten Sicherheitsheader mit der folgenden Struktur.</span><span class="sxs-lookup"><span data-stu-id="f10bf-362">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="f10bf-363">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-363">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:SecurityContextToken u:Id="uuid-2202746a-7725-453d-8747-809cb718dab0-29" >  
  ...  
  </wssc:SecurityContextToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-364">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-364">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="f10bf-365">6.2 Verwenden von X.509-Zertifikaten zur Dienstauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="f10bf-365">6.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="f10bf-366">In diesem Abschnitt werden die folgenden Authentifizierungsmodi beschrieben: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate und IssuedTokenForCertificate.</span><span class="sxs-lookup"><span data-stu-id="f10bf-366">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="f10bf-367">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="f10bf-367">6.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="f10bf-368">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das auf der SOAP-Schicht als das Initiatortoken angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f10bf-368">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="f10bf-369">Der Dienst wird ebenfalls über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-369">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="f10bf-370">Die verwendete Bindung ist eine asymmetrische Bindung mit den folgenden Eigenschaftswerten:</span><span class="sxs-lookup"><span data-stu-id="f10bf-370">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="f10bf-371">Initiator-Token: das X.509-Zertifikat des Clients, wobei der Inclusion-Modus auf .../IncludeToken/AlwaysToRecipient festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="f10bf-371">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="f10bf-372">Empfängertoken: das X.509-Zertifikat des Servers, wobei der Inclusion-Modus auf .../IncludeToken/Never festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="f10bf-372">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="f10bf-373">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="f10bf-373">Token Protection: False</span></span>  
  
 <span data-ttu-id="f10bf-374">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-374">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f10bf-375">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f10bf-375">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f10bf-376">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-376">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="f10bf-377">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-377">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificate_WSS10_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-378">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-378">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-379">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-379">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-380">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-380">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-381">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-381">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="f10bf-382">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-382">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-383">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-383">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="f10bf-384">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="f10bf-384">6.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="f10bf-385">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das auf der SOAP-Schicht als das Initiatortoken angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f10bf-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="f10bf-386">Der Dienst wird ebenfalls über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="f10bf-387">Die verwendete Bindung ist eine asymmetrische Bindung mit den folgenden Eigenschaftswerten:</span><span class="sxs-lookup"><span data-stu-id="f10bf-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="f10bf-388">Initiator-Token: das X.509-Zertifikat des Clients, wobei der Inclusion-Modus auf .../IncludeToken/AlwaysToRecipient festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="f10bf-388">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="f10bf-389">Empfänger-Token: das X.509-Zertifikat des Servers, wobei der Inclusion-Modus auf .../IncludeToken/AlwaysToInitiator festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="f10bf-389">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="f10bf-390">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="f10bf-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="f10bf-391">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f10bf-392">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f10bf-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f10bf-393">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="f10bf-394">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-394">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='MutualCertificateDuplex_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:AsymmetricBinding>  
        <wsp:Policy>  
          <sp:InitiatorToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:InitiatorToken>  
          <sp:RecipientToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToInitiator' >  
                <wsp:Policy>  
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:RecipientToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:AsymmetricBinding>  
      <sp:Wss10>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
        </wsp:Policy>  
      </sp:Wss10>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-395">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-396">Anforderung und Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-396">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
    <xenc:ReferenceList>  
    ...  
    </xenc:ReferenceList>  
  </xenc:EncryptedKey>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-397">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-397">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-398">Anforderung und Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-398">Request and Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="f10bf-399">6.2.3 Verwenden von SymmetricBinding mit X.509-Dienstauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="f10bf-399">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="f10bf-400">"WSS10" bot lediglich eingeschränkten Support für Szenarien mit X509-Token.</span><span class="sxs-lookup"><span data-stu-id="f10bf-400">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="f10bf-401">Beispielsweise gab es keine Möglichkeit, Signatur- und Verschlüsselungsschutz für Nachrichten bereitzustellen, die nur Dienst-X509-Token verwenden.</span><span class="sxs-lookup"><span data-stu-id="f10bf-401">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="f10bf-402">"WSS11" hat die Verwendung von EncryptedKey als symmetrisches Token eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f10bf-402">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="f10bf-403">Jetzt könnte ein temporärer Schlüssel, der für das X.509-Zertifikat verschlüsselt wurde, sowohl für den Anforderungs- als auch für den Antwortnachrichtenschutz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f10bf-403">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="f10bf-404">Die unten in Abschnitt&#160;6.4 beschriebenen Authentifizierungsmodi verwenden dieses Muster.</span><span class="sxs-lookup"><span data-stu-id="f10bf-404">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="f10bf-405">Die WS-Sicherheitsrichtlinie beschreibt dieses Muster unter Verwendung von SymmetricBinding mit dem Dienst-X509-Token als Schutztoken.</span><span class="sxs-lookup"><span data-stu-id="f10bf-405">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="f10bf-406">Die Authentifizierungsmodi AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 und IssuedTokenForCertificate verwenden alle eine ähnliche Instanz von sp:SymmetricBinding mit den folgenden Eigenschaftswerten:</span><span class="sxs-lookup"><span data-stu-id="f10bf-406">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="f10bf-407">Schutztoken: das X.509-Zertifikat des Servers, wobei der Einschlussmodus auf .../IncludeToken/Never festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="f10bf-407">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="f10bf-408">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="f10bf-408">Token Protection: False</span></span>  
  
 <span data-ttu-id="f10bf-409">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-409">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f10bf-410">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f10bf-410">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f10bf-411">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-411">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="f10bf-412">Die oben erwähnten Authentifizierungsmodi unterscheiden sich nur durch die unterstützenden Token, die sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="f10bf-412">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="f10bf-413">AnonymousForCertificate besitzt keine unterstützenden Token, MutualCertificate WSS 1.1 besitzt das X509-Zertifikat des Clients als unterzeichnendes unterstützendes Token, UserNameForCertificate besitzt ein Benutzernamentoken als signiertes unterstützendes Token und IssuedTokenForCertificate besitzt das ausgestellte Token als unterzeichnendes unterstützendes Token.</span><span class="sxs-lookup"><span data-stu-id="f10bf-413">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="f10bf-414">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-414">Policy</span></span>  
  
 <span data-ttu-id="f10bf-415">Symmetrische Bindung</span><span class="sxs-lookup"><span data-stu-id="f10bf-415">Symmetric Binding</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SymmetricCert_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:X509Token
sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Never' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:RequireThumbprintReference />
                  <sp:WssX509V3Token10 />
                </wsp:Policy>  
              </sp:X509Token>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />  
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting Token Assertions appear here -->  
      ...  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
          <sp:RequireSignatureConfirmation />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="f10bf-416">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="f10bf-416">6.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="f10bf-417">Mit diesem Authentifizierungsmodus ist der Client anonym, und der Dienst wird mit einem X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-417">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="f10bf-418">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung im Abschnitt&#160;6.4.2.</span><span class="sxs-lookup"><span data-stu-id="f10bf-418">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="f10bf-419">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-419">Policy</span></span>  
  
 <span data-ttu-id="f10bf-420">Weitere Informationen zu den Bindungen finden Sie unter "Richtlinie" im Abschnitt&#160;6.2.3.</span><span class="sxs-lookup"><span data-stu-id="f10bf-420">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-421">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-421">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-422">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-422">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-423">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-423">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-424">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-424">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-425">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-425">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-426">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-426">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="f10bf-427">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="f10bf-427">6.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="f10bf-428">Bei diesem Authentifizierungsmodus authentifiziert sich der Client dem Dienst gegenüber mit einem Benutzernamentoken, das auf der SOAP-Schicht als signiertes unterstützendes Token angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f10bf-428">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="f10bf-429">Der Dienst wird über ein X.509-Zertifikat am Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-429">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="f10bf-430">Die verwendete Bindung ist eine symmetrische Bindung, deren Schutztoken ein Schlüssel ist, der vom Client generiert und über den öffentlichen Schlüssel des Diensts verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="f10bf-430">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="f10bf-431">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-431">Policy</span></span>  
  
 <span data-ttu-id="f10bf-432">Weitere Informationen zu den Bindungen finden Sie unter "Richtlinie" im Abschnitt&#160;6.2.3.</span><span class="sxs-lookup"><span data-stu-id="f10bf-432">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="f10bf-433">Signiertes unterstützendes Token</span><span class="sxs-lookup"><span data-stu-id="f10bf-433">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-434">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-434">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-435">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-435">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-436">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-436">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-437">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-437">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-438">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-438">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-439">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-439">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="f10bf-440">6.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="f10bf-440">6.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="f10bf-441">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f10bf-441">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="f10bf-442">Der Dienst wird ebenfalls über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-442">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="f10bf-443">Die verwendete Bindung ist eine symmetrische Bindung, deren Schutztoken ein Schlüssel ist, der vom Client generiert und über den öffentlichen Schlüssel des Diensts verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="f10bf-443">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="f10bf-444">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-444">Policy</span></span>  
  
 <span data-ttu-id="f10bf-445">Weitere Informationen zu den Bindungen finden Sie unter „Richtlinie“ im Abschnitt&#160;6.2.3.</span><span class="sxs-lookup"><span data-stu-id="f10bf-445">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="f10bf-446">Ausstellendes unterstützendes Token</span><span class="sxs-lookup"><span data-stu-id="f10bf-446">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />
        <sp:WssX509V3Token10 />
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-447">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-447">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-448">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-448">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-449">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-449">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-450">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-450">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-451">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-451">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-452">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-452">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="f10bf-453">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="f10bf-453">6.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="f10bf-454">In diesem Authentifizierungsmodus unterstützt der Client den Dienst als solchen nicht, sondern präsentiert ein Token, das von einem Sicherheitstokendienst (Security Token Service, STS) ausgegeben wird, und einen geteilten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="f10bf-454">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="f10bf-455">Das ausgestellte Token wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f10bf-455">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="f10bf-456">Der Dienst wird über ein X.509-Zertifikat am Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-456">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="f10bf-457">Die verwendete Bindung ist eine symmetrische Bindung, deren Schutztoken ein Schlüssel ist, der vom Client generiert und über den öffentlichen Schlüssel des Diensts verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="f10bf-457">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="f10bf-458">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-458">Policy</span></span>  
  
 <span data-ttu-id="f10bf-459">Weitere Informationen zu den Bindungen finden Sie unter „Richtlinie“ im Abschnitt&#160;6.2.3.</span><span class="sxs-lookup"><span data-stu-id="f10bf-459">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="f10bf-460">Ausstellendes unterstützendes Token</span><span class="sxs-lookup"><span data-stu-id="f10bf-460">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
       </wst:KeyType>  
     </sp:RequestSecurityTokenTemplate>  
     <wsp:Policy>  
       <sp:RequireDerivedKeys />
       <sp:RequireInternalReference />
     </wsp:Policy>  
   </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-461">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-461">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-462">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-462">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-463">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-463">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-464">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-464">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-465">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-465">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <xenc:EncryptedKey>  
  ...  
  </xenc:EncryptedKey>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-466">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-466">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wssc:DerivedKeyToken>  
  ...  
  </wssc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
## <a name="63-kerberos"></a><span data-ttu-id="f10bf-467">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="f10bf-467">6.3 Kerberos</span></span>  
 <span data-ttu-id="f10bf-468">Mit diesem Authentifizierungsmodus wird der Client mit einem Kerberos-Ticket dem Dienst gegenüber authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-468">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="f10bf-469">Dieses gleiche Ticket bietet auch Serverauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f10bf-469">That same ticket also provides server authentication.</span></span> <span data-ttu-id="f10bf-470">Die verwendete Bindung ist eine symmetrische Bindung mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f10bf-470">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="f10bf-471">Schutztoken: Kerberos-Ticket, Einschlussmodus ist auf .../IncludeToken/Once festgelegt</span><span class="sxs-lookup"><span data-stu-id="f10bf-471">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="f10bf-472">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="f10bf-472">Token Protection: False</span></span>  
  
 <span data-ttu-id="f10bf-473">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-473">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f10bf-474">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f10bf-474">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f10bf-475">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-475">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="f10bf-476">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-476">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='Kerberos_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:KerberosToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/Once' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:WssGssKerberosV5ApReqToken11 />
                </wsp:Policy>  
              </sp:KerberosToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic128 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-477">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-477">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-478">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-478">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsse:BinarySecurityToken>  
  ...  
  </wsse:BinarySecurityToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-479">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-479">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-480">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-480">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-481">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-481">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-482">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-482">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="f10bf-483">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="f10bf-483">6.4 IssuedToken</span></span>  
 <span data-ttu-id="f10bf-484">In diesem Authentifizierungsmodus unterstützt der Client den Dienst als solchen nicht. Stattdessen präsentiert der Client ein Token, das von einem Security Token Service (STS) ausgegeben wird, und einen freigegebenen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="f10bf-484">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="f10bf-485">Der Dienst wird dem Client gegenüber nicht authentifiziert. Stattdessen verschlüsselt STS den geteilten Schlüssel als Teil des ausgestellten Tokens, sodass nur der Dienst den Schlüssel entschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="f10bf-485">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="f10bf-486">Die verwendete Bindung ist eine symmetrische Bindung mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f10bf-486">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="f10bf-487">Schutztoken: ausgestelltes Token, Einschlussmodus ist auf .../IncludeToken/AlwaysToRecipient festgelegt</span><span class="sxs-lookup"><span data-stu-id="f10bf-487">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="f10bf-488">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="f10bf-488">Token Protection: False</span></span>  
  
 <span data-ttu-id="f10bf-489">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-489">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f10bf-490">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f10bf-490">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f10bf-491">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-491">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="f10bf-492">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-492">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple3_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <sp:RequestSecurityTokenTemplate>  
                  <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
                  </wst:KeyType>
                </sp:RequestSecurityTokenTemplate>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:RequireInternalReference />
                </wsp:Policy>  
              </sp:IssuedToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-493">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-493">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-494">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-494">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-495">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-495">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-496">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-496">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-497">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-497">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-498">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-498">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="f10bf-499">6.5 Verwenden von SslNegotiated zur Dienstauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="f10bf-499">6.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="f10bf-500">Dieser Abschnitt beschreibt eine Gruppe von Authentifizierungsmodi, die eine symmetrische Bindung verwenden, deren Schutztoken ein Sicherheitskontexttoken über WS-SecureConversation (WS-SC) ist, dessen Schlüsselwert ausgeführt wird, indem das TLS-Protokoll über WS-Trust (WS-T) RST/RSTR-Nachrichten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f10bf-500">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="f10bf-501">Genaue Informationen über die TLS-Handshake-Implementierung mit WS-Trust werden in TLSNEGO beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f10bf-501">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="f10bf-502">In diesen Nachrichtenbeispielen wird davon ausgegangen, dass SCT bereits mit einem verbundenen Sicherheitskontext über einen Handshake etabliert ist.</span><span class="sxs-lookup"><span data-stu-id="f10bf-502">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="f10bf-503">Die verwendete Bindung ist eine symmetrische Bindung mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f10bf-503">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="f10bf-504">Schutztoken: SslContextToken, Einschlussmodus ist auf .../IncludeToken/Never festgelegt</span><span class="sxs-lookup"><span data-stu-id="f10bf-504">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="f10bf-505">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="f10bf-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="f10bf-506">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f10bf-507">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f10bf-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f10bf-508">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-508">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="f10bf-509">6.5.1 Richtlinie für SslNegotiated-Dienstauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="f10bf-509">6.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="f10bf-510">Die Richtlinien für alle Authentifizierungsmodi in diesem Abschnitt sind ähnlich und unterscheiden sich nur durch bestimmte signierte unterstützende oder ausstellende Token, die verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f10bf-510">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient'>  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                </wsp:Policy>  
              </mssp:SslContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <!-- Supporting token assertions go here -->  
      ..  
      <sp:Wss11>
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="f10bf-511">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f10bf-511">6.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="f10bf-512">Mit diesem Authentifizierungsmodus ist der Client anonym, und der Dienst wird mit einem X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-512">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="f10bf-513">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung in&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="f10bf-513">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="f10bf-514">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-514">Policy</span></span>  
  
 <span data-ttu-id="f10bf-515">Weitere Informationen zu den Bindungen finden Sie unter „Richtlinie“ im Abschnitt&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="f10bf-515">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-516">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-516">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-517">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-517">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-518">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-518">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-519">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-519">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-520">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-520">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-521">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-521">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="f10bf-522">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f10bf-522">6.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="f10bf-523">Bei diesem Authentifizierungsmodus wird der Client über ein Benutzernamentoken authentifiziert, das auf der SOAP-Schicht als signiertes unterstützendes Token angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f10bf-523">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="f10bf-524">Der Dienst wird über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-524">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="f10bf-525">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung im Abschnitt&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="f10bf-525">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="f10bf-526">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-526">Policy</span></span>  
  
 <span data-ttu-id="f10bf-527">Weitere Informationen zu den Bindungen finden Sie im Abschnitt&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="f10bf-527">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="f10bf-528">Signiertes unterstützendes Token</span><span class="sxs-lookup"><span data-stu-id="f10bf-528">Signed Supporting Token</span></span>  
  
```xml  
<sp:SignedSupportingTokens>  
  <wsp:Policy>  
    <sp:UsernameToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:WssUsernameToken10 />
      </wsp:Policy>  
    </sp:UsernameToken>  
  </wsp:Policy>  
</sp:SignedSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-529">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-529">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-530">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-530">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-531">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-531">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-532">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-532">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-533">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-533">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-534">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-534">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="f10bf-535">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f10bf-535">6.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="f10bf-536">In diesem Authentifizierungsmodus unterstützt der Client den Dienst als solchen nicht, sondern präsentiert ein Token, das von einem Sicherheitstokendienst (Security Token Service, STS) ausgegeben wird, und einen freigegebenen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="f10bf-536">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="f10bf-537">Das ausgestellte Token wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f10bf-537">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="f10bf-538">Der Dienst wird über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-538">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="f10bf-539">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung in&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="f10bf-539">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="f10bf-540">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-540">Policy</span></span>  
  
 <span data-ttu-id="f10bf-541">Weitere Informationen zu den Bindungen finden Sie im Abschnitt&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="f10bf-541">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="f10bf-542">Ausstellendes unterstützendes Token</span><span class="sxs-lookup"><span data-stu-id="f10bf-542">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:IssuedToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <sp:RequestSecurityTokenTemplate>  
        <wst:KeyType>  
http://schemas.xmlsoap.org/ws/2005/02/trust/SymmetricKey  
        </wst:KeyType>
      </sp:RequestSecurityTokenTemplate>  
      <wsp:Policy>  
        <sp:RequireDerivedKeys />
        <sp:RequireInternalReference />
      </wsp:Policy>  
    </sp:IssuedToken>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-543">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-543">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-544">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-544">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-545">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-545">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-546">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-546">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-547">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-547">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <saml:Assertion>  
  ...  
  </saml:Assertion>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-548">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-548">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsse11:SignatureConfirmation />  
  <wsse11:SignatureConfirmation />  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="f10bf-549">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="f10bf-549">6.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="f10bf-550">Bei diesem Authentifizierungsmodus werden sowohl der Client als auch der Dienst mit X.509-Zertifikaten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="f10bf-550">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="f10bf-551">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung in&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="f10bf-551">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="f10bf-552">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-552">Policy</span></span>  
  
 <span data-ttu-id="f10bf-553">Weitere Informationen zu den Bindungen finden Sie im Abschnitt&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="f10bf-553">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="f10bf-554">Ausstellendes unterstützendes Token</span><span class="sxs-lookup"><span data-stu-id="f10bf-554">Endorsing Supporting Token</span></span>  
  
```xml  
<sp:EndorsingSupportingTokens>  
  <wsp:Policy>  
    <sp:X509Token sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
      <wsp:Policy>  
        <sp:RequireThumbprintReference />
        <sp:WssX509V3Token10 />
      </wsp:Policy>  
    </sp:X509Token>  
  </wsp:Policy>  
</sp:EndorsingSupportingTokens>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-555">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-555">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-556">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-556">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-557">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-557">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-558">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-558">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-559">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-559">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-560">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-560">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="f10bf-561">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="f10bf-561">6.6 SspiNegotiated</span></span>  
 <span data-ttu-id="f10bf-562">Bei diesem Authentifizierungsmodus wird ein Aushandlungsprotokoll verwendet, um Client- und Serverauthentifizierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-562">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="f10bf-563">Wenn möglich wird Kerberos verwendet, ansonsten NTLM.</span><span class="sxs-lookup"><span data-stu-id="f10bf-563">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="f10bf-564">Die verwendete Bindung ist eine symmetrische Bindung mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f10bf-564">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="f10bf-565">Schutztoken: SpnegoContextToken, Einschlussmodus ist auf .../IncludeToken/AlwaysToRecipient festgelegt</span><span class="sxs-lookup"><span data-stu-id="f10bf-565">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="f10bf-566">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="f10bf-566">Token Protection: False</span></span>  
  
 <span data-ttu-id="f10bf-567">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-567">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="f10bf-568">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="f10bf-568">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="f10bf-569">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="f10bf-569">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="f10bf-570">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-570">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='CustomBinding_ISimple13_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                </wsp:Policy>  
              </sp:SpnegoContextToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-571">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-571">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-572">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-572">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-573">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-573">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-574">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-574">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-575">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-575">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-576">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-576">Response</span></span>  
  
```xml  
<wsse:Security>  
<wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
### <a name="67-secureconversation"></a><span data-ttu-id="f10bf-577">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="f10bf-577">6.7 SecureConversation</span></span>  
 <span data-ttu-id="f10bf-578">Die verwendete Bindung ist eine symmetrische Bindung, wobei das Schutztoken ein SCT über WS-SecureConversation (WS-SC) ist.</span><span class="sxs-lookup"><span data-stu-id="f10bf-578">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="f10bf-579">Das SCT wird über WS-Trust (WS-Trust) oder WS-SecureConversation (WS-SC) gemäß einer ummantelten Bindung ausgehandelt, die selbst eine symmetrische Bindung ist und ein Aushandlungsprotokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="f10bf-579">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="f10bf-580">Das Aushandlungsprotokoll verwendet Kerberos, um, falls möglich, Client- und Serverauthentifizierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f10bf-580">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="f10bf-581">Wenn Kerberos nicht verwendet werden kann, greift es wieder auf NTLM zurück.</span><span class="sxs-lookup"><span data-stu-id="f10bf-581">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="f10bf-582">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="f10bf-582">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SecureConversation_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <sp:SecureConversationToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                <wsp:Policy>  
                  <sp:RequireDerivedKeys />
                  <sp:BootstrapPolicy>  
                    <wsp:Policy>  
                      <sp:SignedParts>  
                        <sp:Body />
                        <sp:Header Name='To' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='From' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='FaultTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='ReplyTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='MessageID' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='RelatesTo' Namespace='http://www.w3.org/2005/08/addressing' />
                        <sp:Header Name='Action' Namespace='http://www.w3.org/2005/08/addressing' />
                      </sp:SignedParts>  
                      <sp:EncryptedParts>  
                        <sp:Body />
                      </sp:EncryptedParts>  
                      <sp:SymmetricBinding>  
                        <wsp:Policy>  
                          <sp:ProtectionToken>  
                            <wsp:Policy>  
                              <sp:SpnegoContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' >  
                                <wsp:Policy>  
                                  <sp:RequireDerivedKeys />
                                </wsp:Policy>  
                              </sp:SpnegoContextToken>  
                            </wsp:Policy>  
                          </sp:ProtectionToken>  
                          <sp:AlgorithmSuite>  
                            <wsp:Policy>  
                              <sp:Basic256 />
                            </wsp:Policy>  
                          </sp:AlgorithmSuite>  
                          <sp:Layout>  
                            <wsp:Policy>  
                              <sp:Strict />
                            </wsp:Policy>  
                          </sp:Layout>  
                          <sp:IncludeTimestamp />
                          <sp:EncryptSignature />
                          <sp:OnlySignEntireHeadersAndBody />
                        </wsp:Policy>  
                      </sp:SymmetricBinding>  
                      <sp:Wss11>  
                        <wsp:Policy>  
                          <sp:MustSupportRefKeyIdentifier />
                          <sp:MustSupportRefIssuerSerial />
                          <sp:MustSupportRefThumbprint />
                          <sp:MustSupportRefEncryptedKey />
                        </wsp:Policy>  
                      </sp:Wss11>  
                      <sp:Trust10>  
                        <wsp:Policy>  
                          <sp:MustSupportIssuedTokens />
                          <sp:RequireClientEntropy />
                          <sp:RequireServerEntropy />
                        </wsp:Policy>  
                      </sp:Trust10>  
                    </wsp:Policy>  
                  </sp:BootstrapPolicy>  
                </wsp:Policy>  
              </sp:SecureConversationToken>  
            </wsp:Policy>  
          </sp:ProtectionToken>  
          <sp:AlgorithmSuite>  
            <wsp:Policy>  
              <sp:Basic256 />
            </wsp:Policy>  
          </sp:AlgorithmSuite>  
          <sp:Layout>  
            <wsp:Policy>  
              <sp:Strict />
            </wsp:Policy>  
          </sp:Layout>  
          <sp:IncludeTimestamp />
          <sp:EncryptSignature />
          <sp:OnlySignEntireHeadersAndBody />
        </wsp:Policy>  
      </sp:SymmetricBinding>  
      <sp:Wss11>  
        <wsp:Policy>  
          <sp:MustSupportRefKeyIdentifier />
          <sp:MustSupportRefIssuerSerial />
          <sp:MustSupportRefThumbprint />
          <sp:MustSupportRefEncryptedKey />
        </wsp:Policy>  
      </sp:Wss11>  
      <sp:Trust10>  
        <wsp:Policy>  
          <sp:MustSupportIssuedTokens />
          <sp:RequireClientEntropy />
          <sp:RequireServerEntropy />
        </wsp:Policy>  
      </sp:Trust10>  
      <wsaw:UsingAddressing />
    </wsp:All>  
  </wsp:ExactlyOne>  
</wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="f10bf-583">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="f10bf-583">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="f10bf-584">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-584">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-585">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-585">Response</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1">  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
  <xenc:EncryptedData>  
  ...  
  </xenc:EncryptedData>  
</wsse:Security>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="f10bf-586">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="f10bf-586">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="f10bf-587">Anforderung</span><span class="sxs-lookup"><span data-stu-id="f10bf-587">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:SecurityContextToken>  
  ...  
  </wsc:SecurityContextToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```  
  
 <span data-ttu-id="f10bf-588">Antwort</span><span class="sxs-lookup"><span data-stu-id="f10bf-588">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <wsc:DerivedKeyToken>  
  ...  
  </wsc:DerivedKeyToken>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
  <xenc:ReferenceList>  
  ...  
  </xenc:ReferenceList>  
</wsse:Security>  
```
