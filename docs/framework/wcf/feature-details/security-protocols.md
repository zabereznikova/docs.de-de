---
title: Sicherheitsprotokolle
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], protocols
ms.assetid: 57ffcbea-807c-4e43-a41c-44b3db8ed2af
ms.openlocfilehash: 1455aeeeb759f8eb2cc09c8649a5cbd6843d950a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96254011"
---
# <a name="security-protocols"></a><span data-ttu-id="58a36-102">Sicherheitsprotokolle</span><span class="sxs-lookup"><span data-stu-id="58a36-102">Security Protocols</span></span>

<span data-ttu-id="58a36-103">Die Webdienste-Sicherheitsprotokolle bieten Webdiensten Sicherheitsmechanismen, die alle vorhandenen Nachrichtensicherheitsanforderungen eines Unternehmens abdecken.</span><span class="sxs-lookup"><span data-stu-id="58a36-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="58a36-104">In diesem Abschnitt werden die Windows Communication Foundation (WCF)-Details (Implementiert in <xref:System.ServiceModel.Channels.SecurityBindingElement> ) für die folgenden Webdienste-Sicherheitsprotokolle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58a36-104">This section describes the Windows Communication Foundation (WCF) details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="58a36-105">Spezifikation/Dokument</span><span class="sxs-lookup"><span data-stu-id="58a36-105">Specification/Document</span></span>|<span data-ttu-id="58a36-106">Link</span><span class="sxs-lookup"><span data-stu-id="58a36-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="58a36-107">WSS: SOAP-Nachrichtensicherheit 1,0</span><span class="sxs-lookup"><span data-stu-id="58a36-107">WSS: SOAP Message Security 1.0</span></span>|<http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf>|  
|<span data-ttu-id="58a36-108">WSS: Username Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="58a36-108">WSS: Username Token Profile 1.0</span></span>|<http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|  
|<span data-ttu-id="58a36-109">WSS: X509 Token Profile 1,0</span><span class="sxs-lookup"><span data-stu-id="58a36-109">WSS: X509 Token Profile 1.0</span></span>|<http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf>|  
|<span data-ttu-id="58a36-110">WSS: SAML 1.1 Token Profile 1,0</span><span class="sxs-lookup"><span data-stu-id="58a36-110">WSS: SAML 1.1 Token Profile 1.0</span></span>|<http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf>|  
|<span data-ttu-id="58a36-111">WSS: SOAP-Nachrichtensicherheit 1.1</span><span class="sxs-lookup"><span data-stu-id="58a36-111">WSS: SOAP Message Security 1.1</span></span>|<http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf>|  
|<span data-ttu-id="58a36-112">WSS: Username Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="58a36-112">WSS Username Token Profile 1.1</span></span>|<http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf>|  
|<span data-ttu-id="58a36-113">WSS: X.509 Token Profile 1,1</span><span class="sxs-lookup"><span data-stu-id="58a36-113">WSS: X.509 Token Profile 1.1</span></span>|<http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf>|  
|<span data-ttu-id="58a36-114">WSS: Kerberos Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="58a36-114">WSS: Kerberos Token Profile 1.1</span></span>|<http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf>|  
|<span data-ttu-id="58a36-115">WSS: SAML 1.1 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="58a36-115">WSS: SAML 1.1 Token Profile 1.1</span></span>|<http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf>|  
|<span data-ttu-id="58a36-116">WS-Secure Conversation 1.3</span><span class="sxs-lookup"><span data-stu-id="58a36-116">WS-Secure Conversation 1.3</span></span>|<http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512/ws-secureconversation-1.3-os.pdf>|  
|<span data-ttu-id="58a36-117">WS-Trust 1.3</span><span class="sxs-lookup"><span data-stu-id="58a36-117">WS-Trust 1.3</span></span>|<http://docs.oasis-open.org/ws-sx/ws-trust/200512/ws-trust-1.3-os.pdf>|  
|<span data-ttu-id="58a36-118">Anwendungshinweis:</span><span class="sxs-lookup"><span data-stu-id="58a36-118">Application Note:</span></span><br /><br /> <span data-ttu-id="58a36-119">Verwenden von WS-Trust für TLS Handshake</span><span class="sxs-lookup"><span data-stu-id="58a36-119">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="58a36-120">Wird veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="58a36-120">To be published</span></span>|  
|<span data-ttu-id="58a36-121">Anwendungshinweis:</span><span class="sxs-lookup"><span data-stu-id="58a36-121">Application Note:</span></span><br /><br /> <span data-ttu-id="58a36-122">Verwenden von WS-Trust für SPNEGO</span><span class="sxs-lookup"><span data-stu-id="58a36-122">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="58a36-123">Wird veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="58a36-123">To be published</span></span>|  
|<span data-ttu-id="58a36-124">Anwendungshinweis:</span><span class="sxs-lookup"><span data-stu-id="58a36-124">Application Note:</span></span><br /><br /> <span data-ttu-id="58a36-125">Webdienste-Adressierungsendpunktverweise und -identität</span><span class="sxs-lookup"><span data-stu-id="58a36-125">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="58a36-126">Wird veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="58a36-126">To be published</span></span>|  
|<span data-ttu-id="58a36-127">WS-SecurityPolicy 1.2 (2007/04)</span><span class="sxs-lookup"><span data-stu-id="58a36-127">WS-SecurityPolicy 1.2 (2007/04)</span></span>|<http://www.oasis-open.org/committees/download.php/23821/ws-securitypolicy-1.2-spec-cs.pdf>|  
  
 <span data-ttu-id="58a36-128">WCF, Version 1, bietet 17 Authentifizierungs Modi, die als Grundlage für die Sicherheitskonfiguration für Webdienste verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="58a36-128">WCF, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="58a36-129">Jeder Modus wird für einen allgemeinen Satz von Bereitstellungsanforderungen optimiert, z.&#160;B.:</span><span class="sxs-lookup"><span data-stu-id="58a36-129">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
- <span data-ttu-id="58a36-130">Anmeldeinformationen, die zum Authentifizieren von Client und Dienst verwendet werden</span><span class="sxs-lookup"><span data-stu-id="58a36-130">Credentials used to authenticate client and service.</span></span>  
  
- <span data-ttu-id="58a36-131">Nachrichten- oder Transportsicherheitsschutzmechanismen.</span><span class="sxs-lookup"><span data-stu-id="58a36-131">Message or transport security protection mechanisms.</span></span>  
  
- <span data-ttu-id="58a36-132">Nachrichtenaustauschmuster</span><span class="sxs-lookup"><span data-stu-id="58a36-132">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="58a36-133">Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="58a36-133">Authentication Mode</span></span>|<span data-ttu-id="58a36-134">Clientauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="58a36-134">Client Authentication</span></span>|<span data-ttu-id="58a36-135">Serverauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="58a36-135">Server Authentication</span></span>|<span data-ttu-id="58a36-136">Mode</span><span class="sxs-lookup"><span data-stu-id="58a36-136">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="58a36-137">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="58a36-137">UserNameOverTransport</span></span>|<span data-ttu-id="58a36-138">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="58a36-138">User name/password</span></span>|<span data-ttu-id="58a36-139">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-139">X509</span></span>|<span data-ttu-id="58a36-140">Transport</span><span class="sxs-lookup"><span data-stu-id="58a36-140">Transport</span></span>|  
|<span data-ttu-id="58a36-141">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="58a36-141">CertificateOverTransport</span></span>|<span data-ttu-id="58a36-142">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-142">X509</span></span>|<span data-ttu-id="58a36-143">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-143">X509</span></span>|<span data-ttu-id="58a36-144">Transport</span><span class="sxs-lookup"><span data-stu-id="58a36-144">Transport</span></span>|  
|<span data-ttu-id="58a36-145">KerberosOverTransport.</span><span class="sxs-lookup"><span data-stu-id="58a36-145">KerberosOverTransport</span></span>|<span data-ttu-id="58a36-146">Windows</span><span class="sxs-lookup"><span data-stu-id="58a36-146">Windows</span></span>|<span data-ttu-id="58a36-147">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-147">X509</span></span>|<span data-ttu-id="58a36-148">Transport</span><span class="sxs-lookup"><span data-stu-id="58a36-148">Transport</span></span>|  
|<span data-ttu-id="58a36-149">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="58a36-149">IssuedTokenOverTransport</span></span>|<span data-ttu-id="58a36-150">Im Verbund</span><span class="sxs-lookup"><span data-stu-id="58a36-150">Federated</span></span>|<span data-ttu-id="58a36-151">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-151">X509</span></span>|<span data-ttu-id="58a36-152">Transport</span><span class="sxs-lookup"><span data-stu-id="58a36-152">Transport</span></span>|  
|<span data-ttu-id="58a36-153">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="58a36-153">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="58a36-154">Windows Sspi wurde verhandelt</span><span class="sxs-lookup"><span data-stu-id="58a36-154">Windows Sspi Negotiated</span></span>|<span data-ttu-id="58a36-155">Windows Sspi wurde verhandelt</span><span class="sxs-lookup"><span data-stu-id="58a36-155">Windows Sspi Negotiated</span></span>|<span data-ttu-id="58a36-156">Transport</span><span class="sxs-lookup"><span data-stu-id="58a36-156">Transport</span></span>|  
|<span data-ttu-id="58a36-157">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="58a36-157">AnonymousForCertificate</span></span>|<span data-ttu-id="58a36-158">Keine</span><span class="sxs-lookup"><span data-stu-id="58a36-158">None</span></span>|<span data-ttu-id="58a36-159">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-159">X509</span></span>|<span data-ttu-id="58a36-160">`Message`</span><span class="sxs-lookup"><span data-stu-id="58a36-160">Message</span></span>|  
|<span data-ttu-id="58a36-161">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="58a36-161">UserNameForCertificate</span></span>|<span data-ttu-id="58a36-162">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="58a36-162">User name/password</span></span>|<span data-ttu-id="58a36-163">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-163">X509</span></span>|<span data-ttu-id="58a36-164">`Message`</span><span class="sxs-lookup"><span data-stu-id="58a36-164">Message</span></span>|  
|<span data-ttu-id="58a36-165">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="58a36-165">MutualCertificate</span></span>|<span data-ttu-id="58a36-166">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-166">X509</span></span>|<span data-ttu-id="58a36-167">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-167">X509</span></span>|<span data-ttu-id="58a36-168">`Message`</span><span class="sxs-lookup"><span data-stu-id="58a36-168">Message</span></span>|  
|<span data-ttu-id="58a36-169">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="58a36-169">MutualCertificateDuplex</span></span>|<span data-ttu-id="58a36-170">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-170">X509</span></span>|<span data-ttu-id="58a36-171">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-171">X509</span></span>|<span data-ttu-id="58a36-172">`Message`</span><span class="sxs-lookup"><span data-stu-id="58a36-172">Message</span></span>|  
|<span data-ttu-id="58a36-173">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="58a36-173">IssuedTokenForCertificate</span></span>|<span data-ttu-id="58a36-174">Im Verbund</span><span class="sxs-lookup"><span data-stu-id="58a36-174">Federated</span></span>|<span data-ttu-id="58a36-175">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-175">X509</span></span>|<span data-ttu-id="58a36-176">`Message`</span><span class="sxs-lookup"><span data-stu-id="58a36-176">Message</span></span>|  
|<span data-ttu-id="58a36-177">Kerberos</span><span class="sxs-lookup"><span data-stu-id="58a36-177">Kerberos</span></span>|<span data-ttu-id="58a36-178">Windows</span><span class="sxs-lookup"><span data-stu-id="58a36-178">Windows</span></span>|<span data-ttu-id="58a36-179">Windows</span><span class="sxs-lookup"><span data-stu-id="58a36-179">Windows</span></span>|<span data-ttu-id="58a36-180">`Message`</span><span class="sxs-lookup"><span data-stu-id="58a36-180">Message</span></span>|  
|<span data-ttu-id="58a36-181">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="58a36-181">IssuedToken</span></span>|<span data-ttu-id="58a36-182">Im Verbund</span><span class="sxs-lookup"><span data-stu-id="58a36-182">Federated</span></span>|<span data-ttu-id="58a36-183">Im Verbund</span><span class="sxs-lookup"><span data-stu-id="58a36-183">Federated</span></span>|<span data-ttu-id="58a36-184">`Message`</span><span class="sxs-lookup"><span data-stu-id="58a36-184">Message</span></span>|  
|<span data-ttu-id="58a36-185">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="58a36-185">SspiNegotiated</span></span>|<span data-ttu-id="58a36-186">Windows Sspi wurde verhandelt</span><span class="sxs-lookup"><span data-stu-id="58a36-186">Windows Sspi Negotiated</span></span>|<span data-ttu-id="58a36-187">Windows Sspi wurde verhandelt</span><span class="sxs-lookup"><span data-stu-id="58a36-187">Windows Sspi Negotiated</span></span>|<span data-ttu-id="58a36-188">`Message`</span><span class="sxs-lookup"><span data-stu-id="58a36-188">Message</span></span>|  
|<span data-ttu-id="58a36-189">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="58a36-189">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="58a36-190">Keine</span><span class="sxs-lookup"><span data-stu-id="58a36-190">None</span></span>|<span data-ttu-id="58a36-191">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="58a36-191">X509, TLS-Nego</span></span>|<span data-ttu-id="58a36-192">`Message`</span><span class="sxs-lookup"><span data-stu-id="58a36-192">Message</span></span>|  
|<span data-ttu-id="58a36-193">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="58a36-193">UserNameForSslNegotiated</span></span>|<span data-ttu-id="58a36-194">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="58a36-194">User name/password</span></span>|<span data-ttu-id="58a36-195">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="58a36-195">X509, TLS-Nego</span></span>|<span data-ttu-id="58a36-196">`Message`</span><span class="sxs-lookup"><span data-stu-id="58a36-196">Message</span></span>|  
|<span data-ttu-id="58a36-197">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="58a36-197">MutualSslNegotiated</span></span>|<span data-ttu-id="58a36-198">X509</span><span class="sxs-lookup"><span data-stu-id="58a36-198">X509</span></span>|<span data-ttu-id="58a36-199">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="58a36-199">X509, TLS-Nego</span></span>|<span data-ttu-id="58a36-200">`Message`</span><span class="sxs-lookup"><span data-stu-id="58a36-200">Message</span></span>|  
|<span data-ttu-id="58a36-201">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="58a36-201">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="58a36-202">Im Verbund</span><span class="sxs-lookup"><span data-stu-id="58a36-202">Federated</span></span>|<span data-ttu-id="58a36-203">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="58a36-203">X509, TLS-Nego</span></span>|<span data-ttu-id="58a36-204">`Message`</span><span class="sxs-lookup"><span data-stu-id="58a36-204">Message</span></span>|  
  
 <span data-ttu-id="58a36-205">Endpunkte, die solche Authentifizierungsmodi verwenden, können ihre Sicherheitsanforderungen über WS-SecurityPolicy (WS-SP) ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="58a36-205">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="58a36-206">Dieses Dokument beschreibt die Struktur der Sicherheitsheader und der Infrastrukturnachrichten für jeden Authentifizierungsmodus und bietet Richtlinien- und Nachrichtenbeispiele.</span><span class="sxs-lookup"><span data-stu-id="58a36-206">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 <span data-ttu-id="58a36-207">WCF nutzt WS-SecureConversation, um Unterstützung für sichere Sitzungen bereitzustellen, um den Austausch von mehreren Nachrichten zwischen Anwendungen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="58a36-207">WCF leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="58a36-208">Weitere Informationen zur Implementierung finden Sie unten unter "Sichere Sitzungen".</span><span class="sxs-lookup"><span data-stu-id="58a36-208">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="58a36-209">Zusätzlich zu den Authentifizierungs Modi bietet WCF Einstellungen zum Steuern allgemeiner Schutzmechanismen, die für die meisten Nachrichten Sicherheits basierten Authentifizierungs Modi gelten, z. b. die Reihenfolge der Signatur im Vergleich zu Verschlüsselungs Vorgängen, Algorithmussuites, Schlüssel Ableitung und Signatur Bestätigung.</span><span class="sxs-lookup"><span data-stu-id="58a36-209">In addition to authentication modes, WCF provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="58a36-210">Die folgenden XML-Präfixe und -Namespaces werden in diesem Dokument verwendet.</span><span class="sxs-lookup"><span data-stu-id="58a36-210">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="58a36-211">Präfix</span><span class="sxs-lookup"><span data-stu-id="58a36-211">Prefix</span></span>|<span data-ttu-id="58a36-212">Namespace</span><span class="sxs-lookup"><span data-stu-id="58a36-212">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="58a36-213">s</span><span class="sxs-lookup"><span data-stu-id="58a36-213">s</span></span>|`http://www.w3.org/2003/05/soap-envelope`|  
|<span data-ttu-id="58a36-214">sp</span><span class="sxs-lookup"><span data-stu-id="58a36-214">sp</span></span>|`http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702`|  
|<span data-ttu-id="58a36-215">a</span><span class="sxs-lookup"><span data-stu-id="58a36-215">a</span></span>|`http://www.w3.org/2005/08/addressing`|  
|<span data-ttu-id="58a36-216">wsse</span><span class="sxs-lookup"><span data-stu-id="58a36-216">wsse</span></span>|<span data-ttu-id="58a36-217">TBD – OASIS WSS 1,0 URI</span><span class="sxs-lookup"><span data-stu-id="58a36-217">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="58a36-218">wsse11</span><span class="sxs-lookup"><span data-stu-id="58a36-218">wsse11</span></span>|<span data-ttu-id="58a36-219">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="58a36-219">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="58a36-220">wsu</span><span class="sxs-lookup"><span data-stu-id="58a36-220">wsu</span></span>|`http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-utility-1.0.xsd`|  
|<span data-ttu-id="58a36-221">ds</span><span class="sxs-lookup"><span data-stu-id="58a36-221">ds</span></span>|<span data-ttu-id="58a36-222">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="58a36-222">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="58a36-223">wst</span><span class="sxs-lookup"><span data-stu-id="58a36-223">wst</span></span>|<span data-ttu-id="58a36-224">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="58a36-224">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="58a36-225">wssc</span><span class="sxs-lookup"><span data-stu-id="58a36-225">wssc</span></span>|<span data-ttu-id="58a36-226">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="58a36-226">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="58a36-227">wsaw</span><span class="sxs-lookup"><span data-stu-id="58a36-227">wsaw</span></span>|`http://www.w3.org/2006/05/addressing/wsdl`|  
|<span data-ttu-id="58a36-228">wsp</span><span class="sxs-lookup"><span data-stu-id="58a36-228">wsp</span></span>|`http://schemas.xmlsoap.org/ws/2004/09/policy`|  
|<span data-ttu-id="58a36-229">mssp</span><span class="sxs-lookup"><span data-stu-id="58a36-229">mssp</span></span>|`http://schemas.microsoft.com/ws/2005/07/securitypolicy`|  
  
## <a name="1-token-profiles"></a><span data-ttu-id="58a36-230">1. Tokenprofile</span><span class="sxs-lookup"><span data-stu-id="58a36-230">1. Token Profiles</span></span>  

 <span data-ttu-id="58a36-231">Webdienst-Sicherheitsspezifikationen stellen Anmeldeinformationen als Sicherheitstoken dar.</span><span class="sxs-lookup"><span data-stu-id="58a36-231">Web Services Security specifications represent credential as security tokens.</span></span> <span data-ttu-id="58a36-232">WCF unterstützt die folgenden Tokentypen:</span><span class="sxs-lookup"><span data-stu-id="58a36-232">WCF supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="58a36-233">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="58a36-233">1.1 UsernameToken</span></span>  

 <span data-ttu-id="58a36-234">WCF befolgt UsernameToken10-und UsernameToken11-Profile mit den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="58a36-234">WCF follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="58a36-235">Das R1101 PasswordType-Attribut auf Element UsernameToken\Password MUSS entweder weggelassen werden oder über den Wert #PasswordText (Standard) verfügen.</span><span class="sxs-lookup"><span data-stu-id="58a36-235">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="58a36-236">Man kann #PasswordDigest über Erweiterbarkeit implementieren.</span><span class="sxs-lookup"><span data-stu-id="58a36-236">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="58a36-237">Es wurde beobachtet, dass #PasswordDigest oft für einen Kennwortschutzmechanismus gehalten wurde, der sicher genug ist.</span><span class="sxs-lookup"><span data-stu-id="58a36-237">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="58a36-238">Aber #PasswordDigest kann nicht als Ersatz für eine Verschlüsselung von UsernameToken dienen.</span><span class="sxs-lookup"><span data-stu-id="58a36-238">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="58a36-239">Das primäre Ziel von #PasswordDigest ist ein Schutz vor Replay-Angriffen.</span><span class="sxs-lookup"><span data-stu-id="58a36-239">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="58a36-240">In WCF-Authentifizierungs Modi werden Wiedergabe-Angriffs Bedrohungen mithilfe von Nachrichten Signaturen behoben.</span><span class="sxs-lookup"><span data-stu-id="58a36-240">In WCF authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="58a36-241">B1102 WCF gibt nie Nonce aus und erstellte unter Elemente von UsernameToken.</span><span class="sxs-lookup"><span data-stu-id="58a36-241">B1102 WCF never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="58a36-242">Diese Unterelemente sollen die Replay-Erkennung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="58a36-242">These sub-elements are intended to help replay detection.</span></span> <span data-ttu-id="58a36-243">WCF verwendet stattdessen Nachrichten Signaturen.</span><span class="sxs-lookup"><span data-stu-id="58a36-243">WCF uses message signatures instead.</span></span>  
  
 <span data-ttu-id="58a36-244">OASIS WSS SOAP Message Security UsernameToken Profile&#160;1.1 (UsernameToken11) hat eine Schlüsselableitung der Kennwortfunktion eingeführt.</span><span class="sxs-lookup"><span data-stu-id="58a36-244">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="58a36-245">B1103 Das UsernameToken-Kennwort DARF NICHT für die Schlüsselableitung und daher nicht für kryptografische Vorgänge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58a36-245">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="58a36-246">Begründung: Kennwörter werden im Allgemeinen als zu schwach für die Verwendung in kryptografischen Vorgängen angesehen.</span><span class="sxs-lookup"><span data-stu-id="58a36-246">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="58a36-247">1.2 X509 Token</span><span class="sxs-lookup"><span data-stu-id="58a36-247">1.2 X509 Token</span></span>  

 <span data-ttu-id="58a36-248">WCF unterstützt X509v3-Zertifikate als Anmelde Informationstyp und folgt x509TokenProfile 1.0 und x509TokenProfile 1.1 mit den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="58a36-248">WCF supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="58a36-249">R1201 Das ValueType-Attribut auf dem BinarySecurityToken-Element muss den Wert #X509v3 besitzen, wenn es ein X509v3-Zertifikat enthält.</span><span class="sxs-lookup"><span data-stu-id="58a36-249">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="58a36-250">WSS X509 Token Profile 1.0 und 1.1 definieren auch #X509PKIPathv1 und #PKCS7 als Werttypen.</span><span class="sxs-lookup"><span data-stu-id="58a36-250">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> <span data-ttu-id="58a36-251">WCF unterstützt diese Typen nicht.</span><span class="sxs-lookup"><span data-stu-id="58a36-251">WCF does not support these types.</span></span>  
  
 <span data-ttu-id="58a36-252">R1202 Wenn eine SubjectKeyIdentifier (SKI)-Erweiterung in einem X509-Zertifikat vorliegt, sollte wsse:KeyIdentifier als externe Referenz für das Token verwendet werden, wobei das ValueType-Attribut #X509SubjectKeyIdentifier und sein Inhalt der base64-codierte Wert der SKI-Erweiterung des Zertifikats ist.</span><span class="sxs-lookup"><span data-stu-id="58a36-252">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="58a36-253">SKI-Verweise werden überall implementiert und haben sich als äußerst interoperabler Typ für externe Verweise erwiesen.</span><span class="sxs-lookup"><span data-stu-id="58a36-253">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="58a36-254">R1203 Ein externer Verweis auf das X509-Sicherheitstoken SOLLTE NICHT ds:X509IssuerSerial verwenden.</span><span class="sxs-lookup"><span data-stu-id="58a36-254">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="58a36-255">R1204 Wenn X509TokenProfile1.1 verwendet wird, SOLLTE eine externe Referenz auf das X509-Sicherheitstoken den Fingerabdruck, der von WS-Sicherheit&#160;1.1 eingeführt wird, verwenden.</span><span class="sxs-lookup"><span data-stu-id="58a36-255">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 <span data-ttu-id="58a36-256">WCF unterstützt X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="58a36-256">WCF supports X509IssuerSerial.</span></span> <span data-ttu-id="58a36-257">Es gibt jedoch Interoperabilitätsprobleme mit X509IssuerSerial: WCF verwendet eine Zeichenfolge, um zwei Werte von X509IssuerSerial zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="58a36-257">However there are interoperability issues with X509IssuerSerial: WCF uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="58a36-258">Wenn daher Komponenten des Antragsteller namens neu angeordnet und an einen WCF-Dienst gesendet werden, wird dieser nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="58a36-258">Therefore if one reorders components of the Subject Name and sends to an WCF service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="58a36-259">1.3 Kerberos-Token</span><span class="sxs-lookup"><span data-stu-id="58a36-259">1.3 Kerberos Token</span></span>  

 <span data-ttu-id="58a36-260">WCF unterstützt KerberosTokenProfile 1.1 zum Zweck der Windows-Authentifizierung mit den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="58a36-260">WCF supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="58a36-261">R1301 Ein Kerberos-Token muss den Wert eines GSS-ummantelten Kerberos&#160;v4&#160;AP_REQ tragen, gemäß der Definition in GSS_API und der Kerberos-Spezifikation, und muss das ValueType-Attribut mit dem Wert #GSS_Kerberosv5_AP_REQ besitzen.</span><span class="sxs-lookup"><span data-stu-id="58a36-261">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 <span data-ttu-id="58a36-262">WCF verwendet GSS als umschtes Kerberos-AP-REQ, nicht als Bare-AP-REQ.</span><span class="sxs-lookup"><span data-stu-id="58a36-262">WCF uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="58a36-263">Hierbei handelt es sich um eine empfohlene Vorgehensweise bezüglich der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="58a36-263">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="58a36-264">1.4 SAML v1.1 Token</span><span class="sxs-lookup"><span data-stu-id="58a36-264">1.4 SAML v1.1 Token</span></span>  

 <span data-ttu-id="58a36-265">WCF unterstützt WSS SAML-Tokenprofile 1,0 und 1,1 für SAML v 1.1-Token.</span><span class="sxs-lookup"><span data-stu-id="58a36-265">WCF supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="58a36-266">Es ist möglich, andere Versionen von SAML-Tokenformaten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="58a36-266">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="58a36-267">1.5 Sicherheitskontexttoken</span><span class="sxs-lookup"><span data-stu-id="58a36-267">1.5 Security Context Token</span></span>  

 <span data-ttu-id="58a36-268">WCF unterstützt das in WS-SecureConversation eingeführte Sicherheitskontext Token (SCT).</span><span class="sxs-lookup"><span data-stu-id="58a36-268">WCF supports the Security Context Token (SCT) introduced in WS-SecureConversation.</span></span> <span data-ttu-id="58a36-269">SCT wird verwendet, um einen Sicherheitskontext darzustellen, der in SecureConversation genauso etabliert ist wie in den Binärverhandlungsprotokollen TLS und SSPI (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="58a36-269">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="58a36-270">2. allgemeine Parameter für die Nachrichten Sicherheit</span><span class="sxs-lookup"><span data-stu-id="58a36-270">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="58a36-271">2.1 TimeStamp</span><span class="sxs-lookup"><span data-stu-id="58a36-271">2.1 TimeStamp</span></span>  

 <span data-ttu-id="58a36-272">Die <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A>-Eigenschaft der <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse steuert, ob ein Zeitstempel vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="58a36-272">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> <span data-ttu-id="58a36-273">WCF serialisiert immer wsse: Timestamp mit den Feldern wsse: created und wsse: abgelaufen.</span><span class="sxs-lookup"><span data-stu-id="58a36-273">WCF always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="58a36-274">Der wsse:TimeStamp wird immer signiert, wenn Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="58a36-274">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="58a36-275">2.2 Schutzreihenfolge</span><span class="sxs-lookup"><span data-stu-id="58a36-275">2.2 Protection Order</span></span>  

 <span data-ttu-id="58a36-276">WCF unterstützt die Nachrichten Schutz Reihenfolge "Sign Before verschlüsseln" und "Verschlüsselung vor dem Signieren" (Sicherheitsrichtlinie 1,2).</span><span class="sxs-lookup"><span data-stu-id="58a36-276">WCF supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.2).</span></span> <span data-ttu-id="58a36-277">"Sign Before Encrypt" wird u.&#160;a. aus den folgenden Gründen empfohlen: Mit "Encrypt Before Sign" geschützte Nachrichten sind Signaturersatzangriffen ausgesetzt, sofern der WS-Sicherheit&#160;1.1 SignatureConfirmation-Mechanismus nicht verwendet wird, und eine Signatur über verschlüsselten Inhalt erschwert die Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="58a36-277">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="58a36-278">2.3 Signaturschutz</span><span class="sxs-lookup"><span data-stu-id="58a36-278">2.3 Signature Protection</span></span>  

 <span data-ttu-id="58a36-279">Wenn Encrypt Before Sign verwendet wird, ist es empfehlenswert, die Signatur zu schützen, um Brute-Force-Angriffe zu verhindern, die versuchen, den verschlüsselten Inhalt oder den Signaturschlüssel zu erraten (besonders dann, wenn ein benutzerdefiniertes Token zusammen mit schwachen Schlüsselmaterialien verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="58a36-279">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="58a36-280">2.4 Algorithmussuites</span><span class="sxs-lookup"><span data-stu-id="58a36-280">2.4 Algorithm Suite</span></span>  

 <span data-ttu-id="58a36-281">WCF unterstützt alle in der Sicherheitsrichtlinie 1,2 aufgelisteten Algorithmussuites.</span><span class="sxs-lookup"><span data-stu-id="58a36-281">WCF supports all algorithm suites listed in Security Policy 1.2.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="58a36-282">2.5 Schlüsselableitung</span><span class="sxs-lookup"><span data-stu-id="58a36-282">2.5 Key Derivation</span></span>  

 <span data-ttu-id="58a36-283">WCF verwendet die "Schlüssel Ableitung für symmetrische Schlüssel", wie in WS-SecureConversation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58a36-283">WCF uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="58a36-284">2.6 Signaturbestätigung</span><span class="sxs-lookup"><span data-stu-id="58a36-284">2.6 Signature Confirmation</span></span>  

 <span data-ttu-id="58a36-285">Die Signaturbestätigung kann als Schutz gegen Angriffe von Mittelsmännern eingesetzt werden, um den Signatursatz zu schützen.</span><span class="sxs-lookup"><span data-stu-id="58a36-285">Signature confirmation can be used as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="58a36-286">2.7 Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="58a36-286">2.7 Security Header Layout</span></span>  

 <span data-ttu-id="58a36-287">Jeder Authentifizierungsmodus beschreibt ein bestimmtes Layout für den Sicherheitsheader.</span><span class="sxs-lookup"><span data-stu-id="58a36-287">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="58a36-288">Elemente innerhalb des Sicherheitsheaders sind teilweise geordnet.</span><span class="sxs-lookup"><span data-stu-id="58a36-288">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="58a36-289">Um die Reihenfolge der untergeordneten Sicherheitsheaderelemente zu definieren, definiert die WS-Sicherheitsrichtlinie die folgenden Sicherheitsheader-Layoutmodi:</span><span class="sxs-lookup"><span data-stu-id="58a36-289">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="58a36-290">Strict</span><span class="sxs-lookup"><span data-stu-id="58a36-290">Strict</span></span>|<span data-ttu-id="58a36-291">Dem Sicherheitsheader werden Elemente gemäß den durchnummerierten Layout-Regeln, die im Abschnitt&#160;7.7.1 der Sicherheitsrichtlinien beschrieben werden, und gemäß dem allgemeinen Prinzip der "Deklaration vor der Verwendung" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="58a36-291">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="58a36-292">Lax</span><span class="sxs-lookup"><span data-stu-id="58a36-292">Lax</span></span>|<span data-ttu-id="58a36-293">Die Elemente werden dem Sicherheitsheader in einer beliebigen Reihenfolge hinzugefügt, die der WSS: SOAP Message Security entspricht.</span><span class="sxs-lookup"><span data-stu-id="58a36-293">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="58a36-294">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="58a36-294">LaxTimestampFirst</span></span>|<span data-ttu-id="58a36-295">Ebenso wie Lax, nur dass das erste Element im Sicherheitsheader ein wsse:Timestamp sein muss</span><span class="sxs-lookup"><span data-stu-id="58a36-295">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="58a36-296">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="58a36-296">LaxTimestampLast</span></span>|<span data-ttu-id="58a36-297">Ebenso wie Lax, nur dass das letzte Element im Sicherheitsheader ein wsse:Timestamp sein muss</span><span class="sxs-lookup"><span data-stu-id="58a36-297">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 <span data-ttu-id="58a36-298">WCF unterstützt alle vier Modi für das Layout des Sicherheits Headers.</span><span class="sxs-lookup"><span data-stu-id="58a36-298">WCF supports all four modes for security header layout.</span></span> <span data-ttu-id="58a36-299">Sicherheitsheader-Struktur und Nachrichtenbeispiele für die Authentifizierungsmodi unten folgen dem "Strict"-Modus.</span><span class="sxs-lookup"><span data-stu-id="58a36-299">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="3-common-message-security-parameters"></a><span data-ttu-id="58a36-300">3. allgemeine Parameter für die Nachrichten Sicherheit</span><span class="sxs-lookup"><span data-stu-id="58a36-300">3. Common Message Security Parameters</span></span>  

 <span data-ttu-id="58a36-301">Dieser Abschnitt bietet Beispielrichtlinien für jeden Authentifizierungsmodus, zusammen mit Beispielen, die die Sicherheitsheader-Struktur in Nachrichten, die zwischen Client und Dienst ausgetauscht werden, zeigen.</span><span class="sxs-lookup"><span data-stu-id="58a36-301">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="31-transport-protection"></a><span data-ttu-id="58a36-302">3,1 Transport Schutz</span><span class="sxs-lookup"><span data-stu-id="58a36-302">3.1 Transport Protection</span></span>  

 <span data-ttu-id="58a36-303">WCF bietet fünf Authentifizierungs Modi, in denen der sichere Transport zum Schützen von Nachrichten verwendet wird. UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, issueddekenovertransport und SspiNegotiatedOverTransport.</span><span class="sxs-lookup"><span data-stu-id="58a36-303">WCF provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="58a36-304">Diese Authentifizierungsmodi werden mit der in der Sicherheitsrichtlinie beschriebenen Transportbindung erstellt.</span><span class="sxs-lookup"><span data-stu-id="58a36-304">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="58a36-305">Für den UserNameOverTransport-Authentifizierungsmodus ist das UsernameToken ein signiertes unterstützendes Token.</span><span class="sxs-lookup"><span data-stu-id="58a36-305">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="58a36-306">Für die anderen Authentifizierungsmodi wird das Token als signiertes unterzeichnendes Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58a36-306">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="58a36-307">Anhang&#160;C.1.2 und&#160;C.1.3 von SecurityPolicy beschreiben detailliert das Sicherheitsheader-Layout.</span><span class="sxs-lookup"><span data-stu-id="58a36-307">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="58a36-308">Die folgenden Beispielsicherheitsheader zeigen das "Strict"-Layout für einen gegebenen Authentifizierungsmodus an.</span><span class="sxs-lookup"><span data-stu-id="58a36-308">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="58a36-309">Der Wert der "Derived-Keys"-Eigenschaft für die Token ist in allen Fällen "false".</span><span class="sxs-lookup"><span data-stu-id="58a36-309">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="58a36-310">Die Werte der verschiedenen Eigenschaften der Transportbindung sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="58a36-310">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="58a36-311">Timestamp: true</span><span class="sxs-lookup"><span data-stu-id="58a36-311">Timestamp: true</span></span>  
  
 <span data-ttu-id="58a36-312">Sicherheitsheader-Layout: Strict</span><span class="sxs-lookup"><span data-stu-id="58a36-312">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="58a36-313">Algorithmussammlung: Basic256</span><span class="sxs-lookup"><span data-stu-id="58a36-313">Algorithm Suite: Basic256</span></span>  
  
#### <a name="311-usernameovertransport"></a><span data-ttu-id="58a36-314">3.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="58a36-314">3.1.1 UsernameOverTransport</span></span>  

 <span data-ttu-id="58a36-315">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein Benutzernamentoken, das auf der SOAP-Schicht als signiertes unterstützendes Token angezeigt wird, das immer vom Initiator an den Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="58a36-315">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="58a36-316">Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-316">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="58a36-317">Die verwendete Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="58a36-317">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="58a36-318">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-318">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="UserNameOverTransport_policy"><wsp:ExactlyOne><wsp:All><sp:TransportBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:TransportToken><wsp:Policy><sp:HttpsToken/></wsp:Policy></sp:TransportToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/></wsp:Policy></sp:TransportBinding><sp:SignedEncryptedSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:UsernameToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssUsernameToken10/></wsp:Policy></sp:UsernameToken></wsp:Policy></sp:SignedEncryptedSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
 <span data-ttu-id="58a36-319">Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="58a36-319">Security Header Layout</span></span>  
  
 <span data-ttu-id="58a36-320">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-320">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp><o:UsernameToken u:Id="uuid-b96fbb3a-e646-4403-9473-2e5ffc733ff8-1"> ... </o:UsernameToken></o:Security>  
```  
  
 <span data-ttu-id="58a36-321">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-321">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp></o:Security>  
```  
  
#### <a name="312-certificateovertransport"></a><span data-ttu-id="58a36-322">3.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="58a36-322">3.1.2 CertificateOverTransport</span></span>  

 <span data-ttu-id="58a36-323">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt wird, das immer vom Initiator an den Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="58a36-323">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="58a36-324">Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-324">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="58a36-325">Die verwendete Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="58a36-325">The binding used is a transport binding.</span></span> <span data-ttu-id="58a36-326">CertificateOverTransport signiert nur die SOAP-Header, nicht den SOAP-Text.</span><span class="sxs-lookup"><span data-stu-id="58a36-326">CertificateOverTransport only signs the SOAP headers, not the SOAP body.</span></span> <span data-ttu-id="58a36-327">Dies ist der vom TransportWithMessageCredentials-Sicherheitsmodus verwendete Authentifizierungsmodus.</span><span class="sxs-lookup"><span data-stu-id="58a36-327">This is the authentication mode used by the TransportWithMessageCredentials security mode.</span></span> <span data-ttu-id="58a36-328">Es werden lediglich die SOAP-Header signiert, da die Authentifizierung anhand von Nachrichtenanmeldeinformationen erfolgt.</span><span class="sxs-lookup"><span data-stu-id="58a36-328">Only the SOAP headers are signed because authentication is done by using message credentials.</span></span>  
  
 <span data-ttu-id="58a36-329">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-329">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="CertificateOverTransport_policy"><wsp:ExactlyOne><wsp:All><sp:TransportBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:TransportToken><wsp:Policy><sp:HttpsToken/></wsp:Policy></sp:TransportToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/></wsp:Policy></sp:TransportBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token><sp:SignedParts><sp:Header Name="To" Namespace="http://www.w3.org/2005/08/addressing"/></sp:SignedParts></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
 <span data-ttu-id="58a36-330">Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="58a36-330">Security Header Layout</span></span>  
  
 <span data-ttu-id="58a36-331">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-331">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature></o:Security>  
```  
  
 <span data-ttu-id="58a36-332">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-332">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp></o:Security>  
```  
  
#### <a name="313-issuedtokenovertransport"></a><span data-ttu-id="58a36-333">3.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="58a36-333">3.1.3 IssuedTokenOverTransport</span></span>  

 <span data-ttu-id="58a36-334">In diesem Authentifizierungsmodus unterstützt der Client den Dienst als solchen nicht, sondern präsentiert ein Token, das von einem Sicherheitstokendienst (Security Token Service, STS) ausgegeben wird, und einen freigegebenen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="58a36-334">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="58a36-335">Das ausgegebene Token wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt, das immer vom Initiator an den Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="58a36-335">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="58a36-336">Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-336">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="58a36-337">Die Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="58a36-337">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="58a36-338">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-338">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedTokenOverTransport_policy">
 <wsp:ExactlyOne>
  <wsp:All>
   <sp:TransportBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702">
    <wsp:Policy>
     <sp:TransportToken>
      <wsp:Policy>
       <sp:HttpsToken />
      </wsp:Policy>
     </sp:TransportToken>
     <sp:AlgorithmSuite>
      <wsp:Policy>
       <sp:Basic256 />
      </wsp:Policy>
     </sp:AlgorithmSuite>
     <sp:Layout>
      <wsp:Policy>
       <sp:Strict/>
      </wsp:Policy>
     </sp:Layout>
     <sp:IncludeTimestamp/>
    </wsp:Policy>
   </sp:TransportBinding>
   <sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702">
    <wsp:Policy>
     <sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient">
      <Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702">
       <Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address>
       <Metadata xmlns="http://www.w3.org/2005/08/addressing">
        <Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
         <wsx:MetadataSection xmlns="">
          <wsx:MetadataReference>
           <Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address>
           <Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity">
            <Dns> ...  </Dns>
           </Identity>
          </wsx:MetadataReference>
         </wsx:MetadataSection>
        </Metadata>
       </Metadata>
      </Issuer>
      <sp:RequestSecurityTokenTemplate>
       <trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType>
      </sp:RequestSecurityTokenTemplate>
      <wsp:Policy>
       <sp:RequireInternalReference/>
      </wsp:Policy>
     </sp:IssuedToken>
     <sp:SignedParts>
      <sp:Header Name="To" Namespace="http://www.w3.org/2005/08/addressing"/>
     </sp:SignedParts>
    </wsp:Policy>
   </sp:EndorsingSupportingTokens>
   <sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702">
    <wsp:Policy>
     <sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/>
     <sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/>
    </wsp:Policy>
   </sp:Wss11>
   <sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702">
    <wsp:Policy>
     <sp:MustSupportIssuedTokens/>
     <sp:RequireClientEntropy/>
     <sp:RequireServerEntropy/>
    </wsp:Policy>
   </sp:Trust13>
   <wsaw:UsingAddressing/>
  </wsp:All>
 </wsp:ExactlyOne>
</wsp:Policy>
```  
  
 <span data-ttu-id="58a36-339">Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="58a36-339">Security Header Layout</span></span>  
  
 <span data-ttu-id="58a36-340">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-340">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-67692bb6-85b7-4299-8587-3ce60086b0d2-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-fab7e1b2-8dc4-412b-bda9-b95a4f836815-16" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-341">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-341">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-fab7e1b2-8dc4-412b-bda9-b95a4f836815-21"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
#### <a name="314-kerberosovertransport"></a><span data-ttu-id="58a36-342">3.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="58a36-342">3.1.4 KerberosOverTransport</span></span>  

 <span data-ttu-id="58a36-343">Mit diesem Authentifizierungsmodus wird der Client mit einem Kerberos-Ticket dem Dienst gegenüber authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-343">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="58a36-344">Das Kerberos-Token wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58a36-344">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="58a36-345">Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-345">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="58a36-346">Die Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="58a36-346">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="58a36-347">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-347">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="KerberosOverTransport_policy"><wsp:ExactlyOne><wsp:All><sp:TransportBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:TransportToken><wsp:Policy><sp:HttpsToken/></wsp:Policy></sp:TransportToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic128/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/></wsp:Policy></sp:TransportBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:KerberosToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Once"><wsp:Policy><sp:WssGssKerberosV5ApReqToken11/></wsp:Policy></sp:KerberosToken><sp:SignedParts><sp:Header Name="To" Namespace="http://www.w3.org/2005/08/addressing"/></sp:SignedParts></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
 <span data-ttu-id="58a36-348">Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="58a36-348">Security Header Layout</span></span>  
  
 <span data-ttu-id="58a36-349">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-349">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature></o:Security>  
```  
  
 <span data-ttu-id="58a36-350">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-350">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp></o:Security>  
```  
  
#### <a name="315-sspinegotiatedovertransport"></a><span data-ttu-id="58a36-351">3.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="58a36-351">3.1.5 SspiNegotiatedOverTransport</span></span>  

 <span data-ttu-id="58a36-352">Bei diesem Modus wird ein Aushandlungsprotokoll verwendet, um Client- und Serverauthentifizierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58a36-352">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="58a36-353">Wenn möglich wird Kerberos verwendet, ansonsten NTLM.</span><span class="sxs-lookup"><span data-stu-id="58a36-353">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="58a36-354">Das resultierende SCT wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt, das immer vom Initiator an den Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="58a36-354">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="58a36-355">Der Dienst wird zusätzlich auf der Transportschicht über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-355">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="58a36-356">Die verwendete Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="58a36-356">The binding used is a transport binding.</span></span> <span data-ttu-id="58a36-357">"Spnetgo" (Aushandlung) beschreibt, wie WCF das binäre SSPI-Aushandlungs Protokoll mit WS-Trust verwendet.</span><span class="sxs-lookup"><span data-stu-id="58a36-357">"SPNEGO" (negotiation) describes how WCF uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="58a36-358">Die Sicherheitsheaderbeispiele in diesem Abschnitt gelten, nachdem der SCT durch den SPNEGO-Handshake eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="58a36-358">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="58a36-359">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-359">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="SspiNegotiatedOverTransport_policy"><wsp:ExactlyOne><wsp:All><sp:TransportBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:TransportToken><wsp:Policy><sp:HttpsToken/></wsp:Policy></sp:TransportToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/></wsp:Policy></sp:TransportBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:SpnegoContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></sp:SpnegoContextToken><sp:SignedParts><sp:Header Name="To" Namespace="http://www.w3.org/2005/08/addressing"/></sp:SignedParts></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples"></a><span data-ttu-id="58a36-360">Beispiele für Sicherheitsheader</span><span class="sxs-lookup"><span data-stu-id="58a36-360">Security Header Examples</span></span>  

 <span data-ttu-id="58a36-361">Sobald das Sicherheitskontexttoken einmal durch SPNEGO unter Verwendung der WS-Trust-Binäraushandlung eingeführt wurde, besitzen die Anwendungsnachrichten Sicherheitsheader mit der folgenden Struktur.</span><span class="sxs-lookup"><span data-stu-id="58a36-361">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="58a36-362">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-362">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-9a29d087-5dae-4d40-bf86-5746d9d30eca-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature></o:Security>  
```  
  
 <span data-ttu-id="58a36-363">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-363">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="_0"> ... </u:Timestamp></o:Security>  
```  
  
### <a name="32-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="58a36-364">3,2 Verwenden von X. 509-Zertifikaten für die Dienst Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="58a36-364">3.2 Using X.509 Certificates for Service Authentication</span></span>  

 <span data-ttu-id="58a36-365">In diesem Abschnitt werden die folgenden Authentifizierungsmodi beschrieben: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate und IssuedTokenForCertificate.</span><span class="sxs-lookup"><span data-stu-id="58a36-365">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="321-mutualcertificate-wss10"></a><span data-ttu-id="58a36-366">3.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="58a36-366">3.2.1 MutualCertificate WSS1.0</span></span>  

 <span data-ttu-id="58a36-367">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das auf der SOAP-Schicht als das Initiatortoken angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="58a36-367">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="58a36-368">Der Dienst wird ebenfalls über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-368">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="58a36-369">Sowohl die SOAP-Header als auch der SOAP-Text werden signiert.</span><span class="sxs-lookup"><span data-stu-id="58a36-369">Both the SOAP headers and the SOAP body are signed.</span></span> <span data-ttu-id="58a36-370">Ein symmetrischer Schlüssel wird erstellt und mit dem Transportzertifikat für den Empfänger verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="58a36-370">A symmetric key is created and is encrypted with the transport certificate for the recipient.</span></span>  
  
 <span data-ttu-id="58a36-371">Die verwendete Bindung ist eine asymmetrische Bindung mit den folgenden Eigenschaftswerten:</span><span class="sxs-lookup"><span data-stu-id="58a36-371">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="58a36-372">Initiator-Token: das X.509-Zertifikat des Clients, wobei der Inclusion-Modus auf .../IncludeToken/AlwaysToRecipient festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="58a36-372">Initiator Token: the client’s X.509 certificate, with inclusion mode set to .../IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="58a36-373">Empfängertoken: das X.509-Zertifikat des Servers, wobei der Inclusion-Modus auf .../IncludeToken/Never festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="58a36-373">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set .../IncludeToken/Never</span></span>  
  
 <span data-ttu-id="58a36-374">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="58a36-374">Token Protection: False</span></span>  
  
 <span data-ttu-id="58a36-375">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="58a36-375">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="58a36-376">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="58a36-376">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="58a36-377">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="58a36-377">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="58a36-378">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-378">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:AsymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:InitiatorToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:InitiatorToken><sp:RecipientToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:RecipientToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:AsymmetricBinding><sp:Wss10 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/></wsp:Policy></sp:Wss10><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-379">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-379">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-380">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-380">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-39cb393e-9da8-4d5d-b273-540ef614569b-1"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><e:EncryptedKey Id="_0" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><e:EncryptedData Id="_7" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-381">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-381">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"> <u:Timestamp u:Id="uuid-3d742930-70d3-4d7e-aa0a-8721128dc115-8"> ... </u:Timestamp><e:EncryptedKey Id="_0" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><e:EncryptedData Id="_5" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-382">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-382">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:AsymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:InitiatorToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:InitiatorToken><sp:RecipientToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:RecipientToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:AsymmetricBinding><sp:Wss10 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/></wsp:Policy></sp:Wss10><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-383">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-383">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-384">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-384">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-73da3e21-abff-4294-a910-e75303d280cc-1"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><e:EncryptedKey Id="_0" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="58a36-385">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-385">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-02f276b6-804f-480d-99e9-2e90fc76ab27-3"> ... </u:Timestamp><e:EncryptedKey Id="_0" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="322-mutualcertificateduplex"></a><span data-ttu-id="58a36-386">3.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="58a36-386">3.2.2 MutualCertificateDuplex</span></span>  

 <span data-ttu-id="58a36-387">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das auf der SOAP-Schicht als das Initiatortoken angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="58a36-387">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="58a36-388">Der Dienst wird ebenfalls über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-388">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="58a36-389">Die verwendete Bindung ist eine asymmetrische Bindung mit den folgenden Eigenschaftswerten:</span><span class="sxs-lookup"><span data-stu-id="58a36-389">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="58a36-390">Initiator-Token: das X.509-Zertifikat des Clients, wobei der Inclusion-Modus auf .../IncludeToken/AlwaysToRecipient festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="58a36-390">Initiator Token: Client’s X509 Certificate, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="58a36-391">Empfänger-Token: das X.509-Zertifikat des Servers, wobei der Inclusion-Modus auf .../IncludeToken/AlwaysToInitiator festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="58a36-391">Recipient Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="58a36-392">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="58a36-392">Token Protection: False</span></span>  
  
 <span data-ttu-id="58a36-393">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="58a36-393">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="58a36-394">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="58a36-394">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="58a36-395">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="58a36-395">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="58a36-396">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-396">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualCertificateDuplex_policy"><wsp:ExactlyOne><wsp:All><sp:AsymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:InitiatorToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:InitiatorToken><sp:RecipientToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToInitiator"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:RecipientToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:AsymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><cdp:CompositeDuplex xmlns:cdp="http://schemas.microsoft.com/net/2006/06/duplex"/><ow:OneWay xmlns:ow="http://schemas.microsoft.com/ws/2005/05/routing/policy"/><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-397">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-397">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-398">Anforderung und Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-398">Request and Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-4dec3da4-b572-4654-ba4d-4a2f84a87510-1"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><e:EncryptedKey Id="_0" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><e:EncryptedData Id="_7" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-399">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-399">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualCertificateDuplex_policy"><wsp:ExactlyOne><wsp:All><sp:AsymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:InitiatorToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:InitiatorToken><sp:RecipientToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToInitiator"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:RecipientToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:AsymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><cdp:CompositeDuplex xmlns:cdp="http://schemas.microsoft.com/net/2006/06/duplex"/><ow:OneWay xmlns:ow="http://schemas.microsoft.com/ws/2005/05/routing/policy"/><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-400">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-400">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-401">Anforderung und Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-401">Request and Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-b0e23feb-cd2d-4dc1-bad9-284bc45f3be3-1"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><e:EncryptedKey Id="_0" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="323-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="58a36-402">3.2.3 Verwenden von SymmetricBinding mit X.509-Dienstauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="58a36-402">3.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  

 <span data-ttu-id="58a36-403">"WSS10" bot lediglich eingeschränkten Support für Szenarien mit X509-Token.</span><span class="sxs-lookup"><span data-stu-id="58a36-403">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="58a36-404">Beispielsweise gab es keine Möglichkeit, Signatur- und Verschlüsselungsschutz für Nachrichten bereitzustellen, die nur Dienst-X509-Token verwenden.</span><span class="sxs-lookup"><span data-stu-id="58a36-404">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="58a36-405">"WSS11" hat die Verwendung von EncryptedKey als symmetrisches Token eingeführt.</span><span class="sxs-lookup"><span data-stu-id="58a36-405">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="58a36-406">Jetzt könnte ein temporärer Schlüssel, der für das X.509-Zertifikat verschlüsselt wurde, sowohl für den Anforderungs- als auch für den Antwortnachrichtenschutz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58a36-406">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="58a36-407">Die im Abschnitt 3,4 unten beschriebenen Authentifizierungs Modi verwenden dieses Muster.</span><span class="sxs-lookup"><span data-stu-id="58a36-407">The authentication modes described in the section 3.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="58a36-408">Die WS-Sicherheitsrichtlinie beschreibt dieses Muster unter Verwendung von SymmetricBinding mit dem Dienst-X509-Token als Schutztoken.</span><span class="sxs-lookup"><span data-stu-id="58a36-408">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="58a36-409">Die Authentifizierungsmodi AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 und IssuedTokenForCertificate verwenden alle eine ähnliche Instanz von sp:SymmetricBinding mit den folgenden Eigenschaftswerten:</span><span class="sxs-lookup"><span data-stu-id="58a36-409">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="58a36-410">Schutztoken: das X.509-Zertifikat des Servers, wobei der Einschlussmodus auf .../IncludeToken/Never festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="58a36-410">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="58a36-411">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="58a36-411">Token Protection: False</span></span>  
  
 <span data-ttu-id="58a36-412">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="58a36-412">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="58a36-413">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="58a36-413">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="58a36-414">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="58a36-414">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="58a36-415">Die oben erwähnten Authentifizierungsmodi unterscheiden sich nur durch die unterstützenden Token, die sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="58a36-415">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="58a36-416">AnonymousForCertificate besitzt keine unterstützenden Token, MutualCertificate WSS 1.1 besitzt das X509-Zertifikat des Clients als unterzeichnendes unterstützendes Token, UserNameForCertificate besitzt ein Benutzernamentoken als signiertes unterstützendes Token und IssuedTokenForCertificate besitzt das ausgestellte Token als unterzeichnendes unterstützendes Token.</span><span class="sxs-lookup"><span data-stu-id="58a36-416">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
#### <a name="324-anonymousforcertificate"></a><span data-ttu-id="58a36-417">3.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="58a36-417">3.2.4 AnonymousForCertificate</span></span>  

 <span data-ttu-id="58a36-418">Mit diesem Authentifizierungsmodus ist der Client anonym, und der Dienst wird mit einem X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-418">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="58a36-419">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung in 3.4.2.</span><span class="sxs-lookup"><span data-stu-id="58a36-419">The binding used is an instance of symmetric binding as described in 3.4.2.</span></span>  
  
 <span data-ttu-id="58a36-420">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-420">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="AnonymousforCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-421">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-421">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-422">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-422">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-4de2d2a1-6266-4a02-93e6-242a1ac2aeb3-2"> ... </u:Timestamp><e:EncryptedKey Id="uuid-4de2d2a1-6266-4a02-93e6-242a1ac2aeb3-1" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-423">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-423">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-b06cb481-3176-4c56-af35-c38252bb6c78-4"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_2" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><e:EncryptedData Id="_7" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-424">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-424">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="AnonymousforCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-425">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-425">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-426">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-426">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-562aac68-8cdd-45d5-bc03-df662e6ed048-2"> ... </u:Timestamp><e:EncryptedKey Id="uuid-562aac68-8cdd-45d5-bc03-df662e6ed048-1" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="58a36-427">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-427">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-15b48260-23da-424d-8dc4-8f4e150fb8cf-3"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><k:SignatureConfirmation u:Id="_2" Value="ALF+QNGmWn2k3LpWEDIzSBgTkvo=" xmlns:k="http://docs.oasis-open.org/wss/oasis-wss-wssecurity-secext-1.1.xsd"></k:SignatureConfirmation><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="325-usernameforcertificate"></a><span data-ttu-id="58a36-428">3.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="58a36-428">3.2.5 UserNameForCertificate</span></span>  

 <span data-ttu-id="58a36-429">Bei diesem Authentifizierungsmodus authentifiziert sich der Client dem Dienst gegenüber mit einem Benutzernamentoken, das auf der SOAP-Schicht als signiertes unterstützendes Token angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="58a36-429">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="58a36-430">Der Dienst wird über ein X.509-Zertifikat am Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-430">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="58a36-431">Die verwendete Bindung ist eine symmetrische Bindung, deren Schutztoken ein Schlüssel ist, der vom Client generiert und über den öffentlichen Schlüssel des Diensts verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="58a36-431">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="58a36-432">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-432">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="UserNameForCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:SignedEncryptedSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:UsernameToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssUsernameToken10/></wsp:Policy></sp:UsernameToken></wsp:Policy></sp:SignedEncryptedSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><http:BasicAuthentication xmlns:http="http://schemas.microsoft.com/ws/06/2004/policy/http"/><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-433">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-433">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-434">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-434">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-27196139-acb9-410f-a2c6-51d20d24278b-2"> ... </u:Timestamp><e:EncryptedKey Id="uuid-27196139-acb9-410f-a2c6-51d20d24278b-1" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_9" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-435">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-435">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-681226f7-126a-4806-b732-fcca097cd7a8-5"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-436">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-436">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="UserNameForCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:SignedEncryptedSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:UsernameToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssUsernameToken10/></wsp:Policy></sp:UsernameToken></wsp:Policy></sp:SignedEncryptedSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><http:BasicAuthentication xmlns:http="http://schemas.microsoft.com/ws/06/2004/policy/http"/><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-437">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-437">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-438">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-438">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-8276d8b7-74a0-4257-b8a5-e25350e7c2d4-2"> ... </u:Timestamp><e:EncryptedKey Id="uuid-8276d8b7-74a0-4257-b8a5-e25350e7c2d4-1" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="58a36-439">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-439">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-8a7ad353-f071-49dc-90dd-5ad2e9abd40a-4"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="326-mutualcertificate-wss-11"></a><span data-ttu-id="58a36-440">3.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="58a36-440">3.2.6 MutualCertificate (WSS 1.1)</span></span>  

 <span data-ttu-id="58a36-441">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="58a36-441">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="58a36-442">Der Dienst wird ebenfalls über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-442">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="58a36-443">Die verwendete Bindung ist eine symmetrische Bindung, deren Schutztoken ein Schlüssel ist, der vom Client generiert und über den öffentlichen Schlüssel des Diensts verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="58a36-443">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="58a36-444">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-444">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-445">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-445">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-446">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-446">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-75305d4e-f54f-4e36-9de9-45b6d2053c80-2"> ... </u:Timestamp><e:EncryptedKey Id="uuid-75305d4e-f54f-4e36-9de9-45b6d2053c80-1" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_2" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><o:BinarySecurityToken> ...</o:BinarySecurityToken><e:EncryptedData Id="_9" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><e:EncryptedData Id="_10" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-447">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-447">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-8c73fa91-f95b-40ff-b088-48118e6fadcf-5"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_3" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_9" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><e:EncryptedData Id="_10" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-448">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-448">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-449">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-449">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-450">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-450">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-0b940a9e-606f-43b9-b05d-a162043529bc-2"> ... </u:Timestamp><e:EncryptedKey Id="uuid-0b940a9e-606f-43b9-b05d-a162043529bc-1" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedKey><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><o:BinarySecurityToken> ... </o:BinarySecurityToken><Signature Id="_2" xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="58a36-451">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-451">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-67dacc31-4a50-4866-b673-ccc03e156337-3"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><k:SignatureConfirmation u:Id="_2" Value="mYyksUQKkK27Fd6hmgOiqFwvudk=" xmlns:k="http://docs.oasis-open.org/wss/oasis-wss-wssecurity-secext-1.1.xsd"></k:SignatureConfirmation><k:SignatureConfirmation u:Id="_3" Value="SreOZ4Rr2BcXjFQFvgN55ERypI/1/86hdWThE5lav0eYIxF1OCzQgZF+y7cQ82t+g3CRnLbE3c52DqMpY/HXlrdMct3m3rnpDH+fqdhNY4fE+M2v4zUMFR7uxDKWcEm9zZpmUvJCDfJRfKRaKjy5cTbccRKqSxw7HAqOYnqibA4=" xmlns:k="http://docs.oasis-open.org/wss/oasis-wss-wssecurity-secext-1.1.xsd"></k:SignatureConfirmation><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="327-issuedtokenforcertificate"></a><span data-ttu-id="58a36-452">3.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="58a36-452">3.2.7 IssuedTokenForCertificate</span></span>  

 <span data-ttu-id="58a36-453">In diesem Authentifizierungsmodus unterstützt der Client den Dienst als solchen nicht, sondern präsentiert ein Token, das von einem Sicherheitstokendienst (Security Token Service, STS) ausgegeben wird, und einen geteilten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="58a36-453">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="58a36-454">Das ausgestellte Token wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58a36-454">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="58a36-455">Der Dienst wird über ein X.509-Zertifikat am Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-455">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="58a36-456">Die verwendete Bindung ist eine symmetrische Bindung, deren Schutztoken ein Schlüssel ist, der vom Client generiert und über den öffentlichen Schlüssel des Diensts verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="58a36-456">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="58a36-457">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-457">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedTokenForCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address><Metadata xmlns="http://www.w3.org/2005/08/addressing"><Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><wsx:MetadataSection xmlns=""><wsx:MetadataReference><Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address><Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity"><Dns> ...  </Dns></Identity></wsx:MetadataReference></wsx:MetadataSection></Metadata></Metadata></Issuer><sp:RequestSecurityTokenTemplate><trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType></sp:RequestSecurityTokenTemplate><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireInternalReference/></wsp:Policy></sp:IssuedToken></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-458">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-458">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-459">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-459">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-1d2c03e6-0b69-4483-903a-6ef9b9d286ed-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-3f0f57fa-046d-40c0-919f-d0d7aa640b9f-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-460">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-460">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-3f0f57fa-046d-40c0-919f-d0d7aa640b9f-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-461">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-461">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-462">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-462">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedTokenForCertificate_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:X509Token sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Never"><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireThumbprintReference/><sp:WssX509V3Token10/></wsp:Policy></sp:X509Token></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address><Metadata xmlns="http://www.w3.org/2005/08/addressing"><Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><wsx:MetadataSection xmlns=""><wsx:MetadataReference><Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address><Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity"><Dns> ...  </Dns></Identity></wsx:MetadataReference></wsx:MetadataSection></Metadata></Metadata></Issuer><sp:RequestSecurityTokenTemplate><trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType></sp:RequestSecurityTokenTemplate><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireInternalReference/></wsp:Policy></sp:IssuedToken></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
 <span data-ttu-id="58a36-463">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-463">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-de1c51aa-2ecc-4e70-b6bd-9dca58331fa7-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-96c5e80a-9b87-4c6f-af77-752ca65cf607-16" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-464">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-464">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-96c5e80a-9b87-4c6f-af77-752ca65cf607-21"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
## <a name="33-kerberos"></a><span data-ttu-id="58a36-465">3,3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="58a36-465">3.3 Kerberos</span></span>  

 <span data-ttu-id="58a36-466">Mit diesem Authentifizierungsmodus wird der Client mit einem Kerberos-Ticket dem Dienst gegenüber authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-466">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="58a36-467">Dieses gleiche Ticket bietet auch Serverauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="58a36-467">That same ticket also provides server authentication.</span></span> <span data-ttu-id="58a36-468">Die verwendete Bindung ist eine symmetrische Bindung mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="58a36-468">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="58a36-469">Schutztoken: Kerberos-Ticket, Einschlussmodus ist auf .../IncludeToken/Once festgelegt</span><span class="sxs-lookup"><span data-stu-id="58a36-469">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="58a36-470">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="58a36-470">Token Protection: False</span></span>  
  
 <span data-ttu-id="58a36-471">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="58a36-471">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="58a36-472">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="58a36-472">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="58a36-473">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="58a36-473">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="58a36-474">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-474">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="Kerberos_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:KerberosToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Once"><wsp:Policy><sp:RequireDerivedKeys/><sp:WssGssKerberosV5ApReqToken11/></wsp:Policy></sp:KerberosToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic128/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-475">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-475">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-476">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-476">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-e8f6dc3b-407d-4387-bd33-97aedfd8bf13-2"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-477">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-477">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-7b03568e-66ae-49da-82ee-5d12d372876e-3"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-478">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-478">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="Kerberos_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:KerberosToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/Once"><wsp:Policy><sp:RequireDerivedKeys/><sp:WssGssKerberosV5ApReqToken11/></wsp:Policy></sp:KerberosToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic128/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-479">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-479">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-480">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-480">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-d29247f0-f220-4e81-9a8d-a15f5ac31072-2"> ... </u:Timestamp><o:BinarySecurityToken> ... </o:BinarySecurityToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="58a36-481">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-481">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-9025b930-4f15-42fe-8e78-35d3a3480177-2"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="34-issuedtoken"></a><span data-ttu-id="58a36-482">3,4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="58a36-482">3.4 IssuedToken</span></span>  

 <span data-ttu-id="58a36-483">In diesem Authentifizierungsmodus unterstützt der Client den Dienst als solchen nicht. Stattdessen präsentiert der Client ein Token, das von einem Security Token Service (STS) ausgegeben wird, und einen freigegebenen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="58a36-483">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="58a36-484">Der Dienst wird dem Client gegenüber nicht authentifiziert. Stattdessen verschlüsselt STS den geteilten Schlüssel als Teil des ausgestellten Tokens, sodass nur der Dienst den Schlüssel entschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="58a36-484">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="58a36-485">Die verwendete Bindung ist eine symmetrische Bindung mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="58a36-485">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="58a36-486">Schutztoken: ausgestelltes Token, Einschlussmodus ist auf .../IncludeToken/AlwaysToRecipient festgelegt</span><span class="sxs-lookup"><span data-stu-id="58a36-486">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="58a36-487">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="58a36-487">Token Protection: False</span></span>  
  
 <span data-ttu-id="58a36-488">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="58a36-488">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="58a36-489">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="58a36-489">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="58a36-490">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="58a36-490">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="58a36-491">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-491">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedToken_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address><Metadata xmlns="http://www.w3.org/2005/08/addressing"><Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><wsx:MetadataSection xmlns=""><wsx:MetadataReference><Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address><Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity"><Dns> ...  </Dns></Identity></wsx:MetadataReference></wsx:MetadataSection></Metadata></Metadata></Issuer><sp:RequestSecurityTokenTemplate><trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType></sp:RequestSecurityTokenTemplate><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireInternalReference/></wsp:Policy></sp:IssuedToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-492">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-492">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-493">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-493">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-61ce3989-bc38-4d67-8262-6232c9d49a26-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-7e2d2617-1c28-465a-be30-de4a78cfc0e2-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-494">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-494">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-7e2d2617-1c28-465a-be30-de4a78cfc0e2-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>
```  
  
 <span data-ttu-id="58a36-495">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-495">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedToken_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address><Metadata xmlns="http://www.w3.org/2005/08/addressing"><Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><wsx:MetadataSection xmlns=""><wsx:MetadataReference><Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address><Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity"><Dns> ...  </Dns></Identity></wsx:MetadataReference></wsx:MetadataSection></Metadata></Metadata></Issuer><sp:RequestSecurityTokenTemplate><trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType></sp:RequestSecurityTokenTemplate><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireInternalReference/></wsp:Policy></sp:IssuedToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-496">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-496">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-497">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-497">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-1dc8bdef-4202-4e08-8a5e-ab94da579dec-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-7e004f51-63a3-4069-9b03-6a1a311a3181-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-498">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-498">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-7e004f51-63a3-4069-9b03-6a1a311a3181-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> </c:DerivedKeyToken> ... <c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
### <a name="35-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="58a36-499">3,5 Verwenden von sslausgehandelt für die Dienst Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="58a36-499">3.5 Using SslNegotiated for Service Authentication</span></span>  

 <span data-ttu-id="58a36-500">Dieser Abschnitt beschreibt eine Gruppe von Authentifizierungsmodi, die eine symmetrische Bindung verwenden, deren Schutztoken ein Sicherheitskontexttoken über WS-SecureConversation (WS-SC) ist, dessen Schlüsselwert ausgeführt wird, indem das TLS-Protokoll über WS-Trust (WS-T) RST/RSTR-Nachrichten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="58a36-500">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="58a36-501">Genaue Informationen über die TLS-Handshake-Implementierung mit WS-Trust werden in TLSNEGO beschrieben.</span><span class="sxs-lookup"><span data-stu-id="58a36-501">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="58a36-502">In diesen Nachrichtenbeispielen wird davon ausgegangen, dass SCT bereits mit einem verbundenen Sicherheitskontext über einen Handshake etabliert ist.</span><span class="sxs-lookup"><span data-stu-id="58a36-502">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="58a36-503">Die verwendete Bindung ist eine symmetrische Bindung mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="58a36-503">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="58a36-504">Schutztoken: SslContextToken, Einschlussmodus ist auf .../IncludeToken/Never festgelegt</span><span class="sxs-lookup"><span data-stu-id="58a36-504">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="58a36-505">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="58a36-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="58a36-506">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="58a36-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="58a36-507">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="58a36-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="58a36-508">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="58a36-508">Encrypt Signature: True</span></span>  
  
#### <a name="351-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="58a36-509">3.5.1 Richtlinie für SslNegotiated-Dienstauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="58a36-509">3.5.1 Policy for SslNegotiated service authentication</span></span>  

 <span data-ttu-id="58a36-510">Die Richtlinien für alle Authentifizierungsmodi in diesem Abschnitt sind ähnlich und unterscheiden sich nur durch bestimmte signierte unterstützende oder ausstellende Token, die verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58a36-510">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
#### <a name="352-anonymousforsslnegotiated"></a><span data-ttu-id="58a36-511">3.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="58a36-511">3.5.2 AnonymousForSslNegotiated</span></span>  

 <span data-ttu-id="58a36-512">Mit diesem Authentifizierungsmodus ist der Client anonym, und der Dienst wird mit einem X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-512">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="58a36-513">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung in 3.5.1 oben.</span><span class="sxs-lookup"><span data-stu-id="58a36-513">The binding used is an instance of symmetric binding as described in 3.5.1 above.</span></span>  
  
 <span data-ttu-id="58a36-514">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-514">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="AnonymousForSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-515">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-515">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-516">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-516">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-f4b86ce2-4ba6-4c55-bac1-2e920fc6d5db-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-d21ec2b8-99f5-443c-a4c6-a4d40619187e-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-517">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-517">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-d21ec2b8-99f5-443c-a4c6-a4d40619187e-4"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-518">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-518">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="AnonymousForSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-519">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-519">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-520">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-520">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-c84b24b9-39e0-4cc3-99e2-cec088f1b9eb-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-df206ad9-1ee2-46d7-9fb4-6e4631c9762f-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="58a36-521">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-521">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-df206ad9-1ee2-46d7-9fb4-6e4631c9762f-3"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="353-usernameforsslnegotiated"></a><span data-ttu-id="58a36-522">3.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="58a36-522">3.5.3 UserNameForSslNegotiated</span></span>  

 <span data-ttu-id="58a36-523">Bei diesem Authentifizierungsmodus wird der Client über ein Benutzernamentoken authentifiziert, das auf der SOAP-Schicht als signiertes unterstützendes Token angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="58a36-523">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="58a36-524">Der Dienst wird über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-524">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="58a36-525">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung in 3.5.1.</span><span class="sxs-lookup"><span data-stu-id="58a36-525">The binding used is an instance of symmetric binding as described in 3.5.1.</span></span>  
  
 <span data-ttu-id="58a36-526">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-526">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="UserNameForSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:SignedEncryptedSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:UsernameToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssUsernameToken10/></wsp:Policy></sp:UsernameToken></wsp:Policy></sp:SignedEncryptedSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-527">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-527">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-528">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-528">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-3d1a12c3-e690-474a-a223-a346fc0329a9-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-137ea768-7d49-404b-87eb-f11d9c7154aa-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_9" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-529">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-529">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-137ea768-7d49-404b-87eb-f11d9c7154aa-5"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-530">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-530">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="UserNameForSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:SignedEncryptedSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:UsernameToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:WssUsernameToken10/></wsp:Policy></sp:UsernameToken></wsp:Policy></sp:SignedEncryptedSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-531">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-531">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-532">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-532">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-56e931e8-20c2-457f-a83e-8fcd6b92c258-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-83d053cb-03a0-4461-9616-86475cf083c4-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="58a36-533">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-533">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-83d053cb-03a0-4461-9616-86475cf083c4-4"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
#### <a name="354-issuedtokenforsslnegotiated"></a><span data-ttu-id="58a36-534">3.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="58a36-534">3.5.4 IssuedTokenForSslNegotiated</span></span>  

 <span data-ttu-id="58a36-535">In diesem Authentifizierungsmodus unterstützt der Client den Dienst als solchen nicht, sondern präsentiert ein Token, das von einem Sicherheitstokendienst (Security Token Service, STS) ausgegeben wird, und einen freigegebenen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="58a36-535">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="58a36-536">Das ausgestellte Token wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="58a36-536">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="58a36-537">Der Dienst wird über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-537">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="58a36-538">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung in 3.5.1 oben.</span><span class="sxs-lookup"><span data-stu-id="58a36-538">The binding used is an instance of symmetric binding as described in 3.5.1 above.</span></span>  
  
 <span data-ttu-id="58a36-539">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-539">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedTokenForSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address><Metadata xmlns="http://www.w3.org/2005/08/addressing"><Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><wsx:MetadataSection xmlns=""><wsx:MetadataReference><Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address><Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity"><Dns> ... </Dns></Identity></wsx:MetadataReference></wsx:MetadataSection></Metadata></Metadata></Issuer><sp:RequestSecurityTokenTemplate><trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType></sp:RequestSecurityTokenTemplate><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireInternalReference/></wsp:Policy></sp:IssuedToken></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-540">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-540">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-541">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-541">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-b19fb2e7-8f0c-45c1-b62c-45d6ff6d57e7-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-199509f9-7963-42b7-b340-7598ee261d5a-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-542">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-542">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-199509f9-7963-42b7-b340-7598ee261d5a-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-543">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-543">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="IssuedTokenForSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:EndorsingSupportingTokens xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:IssuedToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><Issuer xmlns="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><Address xmlns="http://www.w3.org/2005/08/addressing">http://www.w3.org/2005/08/addressing/anonymous</Address><Metadata xmlns="http://www.w3.org/2005/08/addressing"><Metadata xmlns="http://schemas.xmlsoap.org/ws/2004/09/mex" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"><wsx:MetadataSection xmlns=""><wsx:MetadataReference><Address xmlns="http://www.w3.org/2005/08/addressing"> ... </Address><Identity xmlns="http://schemas.xmlsoap.org/ws/2006/02/addressingidentity"><Dns> ... </Dns></Identity></wsx:MetadataReference></wsx:MetadataSection></Metadata></Metadata></Issuer><sp:RequestSecurityTokenTemplate><trust:KeyType xmlns:trust="http://docs.oasis-open.org/ws-sx/ws-trust/200512">http://docs.oasis-open.org/ws-sx/ws-trust/200512/SymmetricKey</trust:KeyType></sp:RequestSecurityTokenTemplate><wsp:Policy><sp:RequireDerivedKeys/><sp:RequireInternalReference/></wsp:Policy></sp:IssuedToken></wsp:Policy></sp:EndorsingSupportingTokens><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/><sp:RequireSignatureConfirmation/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-544">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-544">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-545">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-545">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-d75104d5-313e-440f-b112-db8aff57a5fe-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-e668caab-b7e4-4056-ac42-4015ae2a67a6-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-546">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-546">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-e668caab-b7e4-4056-ac42-4015ae2a67a6-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
#### <a name="355-mutualsslnegotiated"></a><span data-ttu-id="58a36-547">3.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="58a36-547">3.5.5 MutualSslNegotiated</span></span>  

 <span data-ttu-id="58a36-548">Bei diesem Authentifizierungsmodus werden sowohl der Client als auch der Dienst mit X.509-Zertifikaten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="58a36-548">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="58a36-549">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung in 3.5.1 oben.</span><span class="sxs-lookup"><span data-stu-id="58a36-549">The binding used is an instance of symmetric binding as described in 3.5.1 above.</span></span>  
  
 <span data-ttu-id="58a36-550">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-550">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><mssp:RequireClientCertificate/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-551">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-551">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-552">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-552">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-d1e6037e-8a64-494f-9447-07d3125b81b5-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-e4b73625-3011-4f6d-a6f9-4d682e860801-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-553">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-553">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-e4b73625-3011-4f6d-a6f9-4d682e860801-4"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-554">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-554">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="MutualSslNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><mssp:SslContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient" xmlns:mssp="http://schemas.microsoft.com/ws/2005/07/securitypolicy"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><mssp:RequireClientCertificate/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></mssp:SslContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-555">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-555">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-556">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-556">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-c2a6ab10-889a-4ee1-871d-05410c90fc10-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-ede0bd89-1f7e-4453-96ed-13e58c7ba8fe-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="58a36-557">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-557">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-ede0bd89-1f7e-4453-96ed-13e58c7ba8fe-3"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
### <a name="36-sspinegotiated"></a><span data-ttu-id="58a36-558">3,6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="58a36-558">3.6 SspiNegotiated</span></span>  

 <span data-ttu-id="58a36-559">Bei diesem Authentifizierungsmodus wird ein Aushandlungsprotokoll verwendet, um Client- und Serverauthentifizierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58a36-559">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="58a36-560">Wenn möglich wird Kerberos verwendet, ansonsten NTLM.</span><span class="sxs-lookup"><span data-stu-id="58a36-560">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="58a36-561">Die verwendete Bindung ist eine symmetrische Bindung mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="58a36-561">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="58a36-562">Schutztoken: SpnegoContextToken, Einschlussmodus ist auf .../IncludeToken/AlwaysToRecipient festgelegt</span><span class="sxs-lookup"><span data-stu-id="58a36-562">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="58a36-563">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="58a36-563">Token Protection: False</span></span>  
  
 <span data-ttu-id="58a36-564">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="58a36-564">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="58a36-565">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="58a36-565">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="58a36-566">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="58a36-566">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="58a36-567">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-567">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="SspiNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:SpnegoContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></sp:SpnegoContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-568">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-568">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-569">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-569">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-9a954fcb-4df2-4610-9800-f542f2b5130a-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-554d8cfc-e956-43db-9abb-afcafd024347-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-570">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-570">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-554d8cfc-e956-43db-9abb-afcafd024347-4"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>
```  
  
 <span data-ttu-id="58a36-571">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-571">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="SspiNegotiated_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:SpnegoContextToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireDerivedKeys/><sp:MustNotSendCancel/><sp:MustNotSendAmend/><sp:MustNotSendRenew/></wsp:Policy></sp:SpnegoContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-572">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-572">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-573">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-573">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-f1673773-f9a7-4b43-b13b-405e7dd4a6e3-4"> ... </u:Timestamp><sc:SecurityContextToken u:Id="uuid-e0aabc81-6942-4fe6-81bc-9def184565ea-1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:SecurityContextToken><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
 <span data-ttu-id="58a36-574">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-574">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-e0aabc81-6942-4fe6-81bc-9def184565ea-3"> ... </u:Timestamp><sc:DerivedKeyToken u:Id="_1" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><sc:DerivedKeyToken u:Id="_0" xmlns:sc="http://docs.oasis-open.org/ws-sx/ws-secureconversation/200512"> ... </sc:DerivedKeyToken><Signature xmlns="http://www.w3.org/2000/09/xmldsig#"> ... </Signature><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList></o:Security>  
```  
  
### <a name="37-secureconversation"></a><span data-ttu-id="58a36-575">3,7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="58a36-575">3.7 SecureConversation</span></span>  

 <span data-ttu-id="58a36-576">Die verwendete Bindung ist eine symmetrische Bindung, wobei das Schutztoken ein SCT über WS-SecureConversation (WS-SC) ist.</span><span class="sxs-lookup"><span data-stu-id="58a36-576">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="58a36-577">Das SCT wird über WS-Trust (WS-Trust) oder WS-SecureConversation (WS-SC) gemäß einer ummantelten Bindung ausgehandelt, die selbst eine symmetrische Bindung ist und ein Aushandlungsprotokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="58a36-577">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="58a36-578">Das Aushandlungsprotokoll verwendet Kerberos, um, falls möglich, Client- und Serverauthentifizierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="58a36-578">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="58a36-579">Wenn Kerberos nicht verwendet werden kann, greift es wieder auf NTLM zurück.</span><span class="sxs-lookup"><span data-stu-id="58a36-579">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="58a36-580">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-580">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="SecureConversation_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:SecureConversationToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireDerivedKeys/><sp:BootstrapPolicy><wsp:Policy><sp:SignedParts xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><sp:Body/><sp:Header Name="To" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="From" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="FaultTo" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="ReplyTo" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="MessageID" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="RelatesTo" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="Action" Namespace="http://www.w3.org/2005/08/addressing"/></sp:SignedParts><sp:EncryptedParts xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><sp:Body/></sp:EncryptedParts><sp:SymmetricBinding xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:SpnegoContextToken sp:IncludeToken="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireDerivedKeys/></wsp:Policy></sp:SpnegoContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust10 xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust10></wsp:Policy></sp:BootstrapPolicy><sp:MustNotSendAmend/></wsp:Policy></sp:SecureConversationToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="58a36-581">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="58a36-581">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  

 <span data-ttu-id="58a36-582">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-582">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-f01c6159-f159-454d-bd97-bbcc9b8e25d3-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-582920d7-14a7-4adc-8091-e1f92d7d8055-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-583">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-583">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-582920d7-14a7-4adc-8091-e1f92d7d8055-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-584">Policy</span><span class="sxs-lookup"><span data-stu-id="58a36-584">Policy</span></span>  
  
```xml  
<wsp:Policy wsu:Id="SecureConversation_policy"><wsp:ExactlyOne><wsp:All><sp:SymmetricBinding xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:SecureConversationToken sp:IncludeToken="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireDerivedKeys/><sp:BootstrapPolicy><wsp:Policy><sp:SignedParts xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><sp:Body/><sp:Header Name="To" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="From" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="FaultTo" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="ReplyTo" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="MessageID" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="RelatesTo" Namespace="http://www.w3.org/2005/08/addressing"/><sp:Header Name="Action" Namespace="http://www.w3.org/2005/08/addressing"/></sp:SignedParts><sp:EncryptedParts xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><sp:Body/></sp:EncryptedParts><sp:SymmetricBinding xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><wsp:Policy><sp:ProtectionToken><wsp:Policy><sp:SpnegoContextToken sp:IncludeToken="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient"><wsp:Policy><sp:RequireDerivedKeys/></wsp:Policy></sp:SpnegoContextToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptSignature/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust10 xmlns:sp="http://schemas.xmlsoap.org/ws/2005/07/securitypolicy"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust10></wsp:Policy></sp:BootstrapPolicy><sp:MustNotSendAmend/></wsp:Policy></sp:SecureConversationToken></wsp:Policy></sp:ProtectionToken><sp:AlgorithmSuite><wsp:Policy><sp:Basic256/></wsp:Policy></sp:AlgorithmSuite><sp:Layout><wsp:Policy><sp:Strict/></wsp:Policy></sp:Layout><sp:IncludeTimestamp/><sp:EncryptBeforeSigning/><sp:OnlySignEntireHeadersAndBody/></wsp:Policy></sp:SymmetricBinding><sp:Wss11 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportRefKeyIdentifier/><sp:MustSupportRefIssuerSerial/><sp:MustSupportRefThumbprint/><sp:MustSupportRefEncryptedKey/></wsp:Policy></sp:Wss11><sp:Trust13 xmlns:sp="http://docs.oasis-open.org/ws-sx/ws-securitypolicy/200702"><wsp:Policy><sp:MustSupportIssuedTokens/><sp:RequireClientEntropy/><sp:RequireServerEntropy/></wsp:Policy></sp:Trust13><wsaw:UsingAddressing/></wsp:All></wsp:ExactlyOne></wsp:Policy>  
```  
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="58a36-585">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="58a36-585">Security Header Examples: EncryptBeforeSign</span></span>  

 <span data-ttu-id="58a36-586">Anforderung</span><span class="sxs-lookup"><span data-stu-id="58a36-586">Request</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-d57e6342-1c68-4095-a0c1-41979088a944-5"> ... </u:Timestamp><c:SecurityContextToken u:Id="uuid-9b22407d-b914-4c41-9105-1cf8cf7c3fe5-1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:SecurityContextToken><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_8" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```  
  
 <span data-ttu-id="58a36-587">Antwort</span><span class="sxs-lookup"><span data-stu-id="58a36-587">Response</span></span>  
  
```xml  
<o:Security s:mustUnderstand="1" xmlns:o="http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-wssecurity-secext-1.0.xsd"><u:Timestamp u:Id="uuid-9b22407d-b914-4c41-9105-1cf8cf7c3fe5-6"> ... </u:Timestamp><c:DerivedKeyToken u:Id="_0" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><c:DerivedKeyToken u:Id="_1" xmlns:c="http://schemas.xmlsoap.org/ws/2005/02/sc"> ... </c:DerivedKeyToken><e:ReferenceList xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:ReferenceList><e:EncryptedData Id="_6" Type="http://www.w3.org/2001/04/xmlenc#Element" xmlns:e="http://www.w3.org/2001/04/xmlenc#"> ... </e:EncryptedData></o:Security>  
```
