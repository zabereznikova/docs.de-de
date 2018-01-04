---
title: Sicherheitsprotokolle, Version&#160;1.0
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ee3402d2-1076-410b-a3cb-fae0372bd7af
caps.latest.revision: "4"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ba5ce91f4cb3edd93698f7c0ba028186afdb8111
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="security-protocols-version-10"></a><span data-ttu-id="8aeaf-102">Sicherheitsprotokolle, Version&#160;1.0</span><span class="sxs-lookup"><span data-stu-id="8aeaf-102">Security Protocols version 1.0</span></span>
<span data-ttu-id="8aeaf-103">Die Webdienste-Sicherheitsprotokolle bieten Webdiensten Sicherheitsmechanismen, die alle vorhandenen Nachrichtensicherheitsanforderungen eines Unternehmens abdecken.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-103">The Web Services Security Protocols provide Web services security mechanisms that cover all existing enterprise messaging security requirements.</span></span> <span data-ttu-id="8aeaf-104">In diesem Abschnitt werden die Details von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], Version &#160;1.0, (implementiert im <xref:System.ServiceModel.Channels.SecurityBindingElement>) der folgenden Webdienste-Sicherheitsprotokolle beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-104">This section describes the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] version 1.0 details (implemented in the <xref:System.ServiceModel.Channels.SecurityBindingElement>) for the following Web services security protocols.</span></span>  
  
|<span data-ttu-id="8aeaf-105">Spezifikation/Dokument</span><span class="sxs-lookup"><span data-stu-id="8aeaf-105">Specification/Document</span></span>|<span data-ttu-id="8aeaf-106">Link</span><span class="sxs-lookup"><span data-stu-id="8aeaf-106">Link</span></span>|  
|-|-|  
|<span data-ttu-id="8aeaf-107">WSS: SOAP-Nachrichtensicherheit 1,0</span><span class="sxs-lookup"><span data-stu-id="8aeaf-107">WSS: SOAP Message Security 1.0</span></span>|<span data-ttu-id="8aeaf-108">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-108">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf</span></span>|  
|<span data-ttu-id="8aeaf-109">WSS: Username Token Profile 1.0</span><span class="sxs-lookup"><span data-stu-id="8aeaf-109">WSS: Username Token Profile 1.0</span></span>|<span data-ttu-id="8aeaf-110">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-110">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="8aeaf-111">WSS: X509 Token Profile 1,0</span><span class="sxs-lookup"><span data-stu-id="8aeaf-111">WSS: X509 Token Profile 1.0</span></span>|<span data-ttu-id="8aeaf-112">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-112">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="8aeaf-113">WSS: SAML 1.1 Token Profile 1,0</span><span class="sxs-lookup"><span data-stu-id="8aeaf-113">WSS: SAML 1.1 Token Profile 1.0</span></span>|<span data-ttu-id="8aeaf-114">http://docs.oasis-open.org/wss/oasis-wss-sam1-token-profile-1.0.pdf (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-114">http://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="8aeaf-115">WSS: SOAP-Nachrichtensicherheit 1.1</span><span class="sxs-lookup"><span data-stu-id="8aeaf-115">WSS: SOAP Message Security 1.1</span></span>|<span data-ttu-id="8aeaf-116">http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-116">http://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf</span></span>|  
|<span data-ttu-id="8aeaf-117">WSS: Username Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="8aeaf-117">WSS Username Token Profile 1.1</span></span>|<span data-ttu-id="8aeaf-118">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-118">http://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf</span></span>|  
|<span data-ttu-id="8aeaf-119">WSS: X.509 Token Profile 1,1</span><span class="sxs-lookup"><span data-stu-id="8aeaf-119">WSS: X.509 Token Profile 1.1</span></span>|<span data-ttu-id="8aeaf-120">http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-120">http://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf</span></span>|  
|<span data-ttu-id="8aeaf-121">WSS: Kerberos Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="8aeaf-121">WSS: Kerberos Token Profile 1.1</span></span>|<span data-ttu-id="8aeaf-122">http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-122">http://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf</span></span>|  
|<span data-ttu-id="8aeaf-123">WSS: SAML 1.1 Token Profile 1.1</span><span class="sxs-lookup"><span data-stu-id="8aeaf-123">WSS: SAML 1.1 Token Profile 1.1</span></span>|<span data-ttu-id="8aeaf-124">http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-124">http://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf</span></span>|  
|<span data-ttu-id="8aeaf-125">WS-Secure Conversation</span><span class="sxs-lookup"><span data-stu-id="8aeaf-125">WS-Secure Conversation</span></span>|<span data-ttu-id="8aeaf-126">http://msdn.microsoft.com/ws/2005/02/ws-secure-conversation/ (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-126">http://msdn.microsoft.com/ws/2005/02/ws-secure-conversation/</span></span>|  
|<span data-ttu-id="8aeaf-127">WS-Trust</span><span class="sxs-lookup"><span data-stu-id="8aeaf-127">WS-Trust</span></span>|<span data-ttu-id="8aeaf-128">http://msdn.microsoft.com/ws/2005/02/ws-trust/ (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-128">http://msdn.microsoft.com/ws/2005/02/ws-trust/</span></span>|  
|<span data-ttu-id="8aeaf-129">Anwendungshinweis:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-129">Application Note:</span></span><br /><br /> <span data-ttu-id="8aeaf-130">Verwenden von WS-Trust für TLS Handshake</span><span class="sxs-lookup"><span data-stu-id="8aeaf-130">Using WS-Trust for TLS Handshake</span></span>|<span data-ttu-id="8aeaf-131">Wird veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="8aeaf-131">To be published</span></span>|  
|<span data-ttu-id="8aeaf-132">Anwendungshinweis:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-132">Application Note:</span></span><br /><br /> <span data-ttu-id="8aeaf-133">Verwenden von WS-Trust für SPNEGO</span><span class="sxs-lookup"><span data-stu-id="8aeaf-133">Using WS-Trust for SPNEGO</span></span>|<span data-ttu-id="8aeaf-134">Wird veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="8aeaf-134">To be published</span></span>|  
|<span data-ttu-id="8aeaf-135">Anwendungshinweis:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-135">Application Note:</span></span><br /><br /> <span data-ttu-id="8aeaf-136">Webdienste-Adressierungsendpunktverweise und -identität</span><span class="sxs-lookup"><span data-stu-id="8aeaf-136">Web Services Addressing Endpoint References And Identity</span></span>|<span data-ttu-id="8aeaf-137">Wird veröffentlicht</span><span class="sxs-lookup"><span data-stu-id="8aeaf-137">To be published</span></span>|  
|<span data-ttu-id="8aeaf-138">WS-SecurityPolicy 1.1</span><span class="sxs-lookup"><span data-stu-id="8aeaf-138">WS-SecurityPolicy 1.1</span></span><br /><br /> <span data-ttu-id="8aeaf-139">(2005/07)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-139">(2005/07)</span></span>|<span data-ttu-id="8aeaf-140">http://msdn.microsoft.com/ws/2005/07/ws-security-policy/ (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-140">http://msdn.microsoft.com/ws/2005/07/ws-security-policy/</span></span><br /><br /> <span data-ttu-id="8aeaf-141">Wurde gemäß den an das OASIS WS-SX Technical Committee (http://www.oasis-open.org/archives/ws-sx/200512/msg00017.html) übermittelten Fehlerberichten geändert</span><span class="sxs-lookup"><span data-stu-id="8aeaf-141">as amended by errata submitted to OASIS WS-SX Technical Committee http://www.oasis-open.org/archives/ws-sx/200512/msg00017.html</span></span>|  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-142">, Version 1, bietet 17 Authentifizierungsmodi, die als Basis für die Webdienste-Sicherheitskonfiguration verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-142">, version 1, provides 17 authentication modes that can be used as the basis for Web services security configuration.</span></span> <span data-ttu-id="8aeaf-143">Jeder Modus wird für einen allgemeinen Satz von Bereitstellungsanforderungen optimiert, z.&#160;B.:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-143">Each mode is optimized for a common set of deployment requirements, such as:</span></span>  
  
-   <span data-ttu-id="8aeaf-144">Anmeldeinformationen, die zum Authentifizieren von Client und Dienst verwendet werden</span><span class="sxs-lookup"><span data-stu-id="8aeaf-144">Credentials used to authenticate client and service.</span></span>  
  
-   <span data-ttu-id="8aeaf-145">Nachrichten- oder Transportsicherheitsschutzmechanismen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-145">Message or transport security protection mechanisms.</span></span>  
  
-   <span data-ttu-id="8aeaf-146">Nachrichtenaustauschmuster</span><span class="sxs-lookup"><span data-stu-id="8aeaf-146">Message exchange patterns.</span></span>  
  
|<span data-ttu-id="8aeaf-147">Authentifizierungsmodus</span><span class="sxs-lookup"><span data-stu-id="8aeaf-147">Authentication Mode</span></span>|<span data-ttu-id="8aeaf-148">Clientauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-148">Client Authentication</span></span>|<span data-ttu-id="8aeaf-149">Serverauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-149">Server Authentication</span></span>|<span data-ttu-id="8aeaf-150">Modus</span><span class="sxs-lookup"><span data-stu-id="8aeaf-150">Mode</span></span>|  
|-------------------------|---------------------------|---------------------------|----------|  
|<span data-ttu-id="8aeaf-151">UserNameOverTransport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-151">UserNameOverTransport</span></span>|<span data-ttu-id="8aeaf-152">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-152">User name/password</span></span>|<span data-ttu-id="8aeaf-153">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-153">X509</span></span>|<span data-ttu-id="8aeaf-154">Transport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-154">Transport</span></span>|  
|<span data-ttu-id="8aeaf-155">CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-155">CertificateOverTransport</span></span>|<span data-ttu-id="8aeaf-156">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-156">X509</span></span>|<span data-ttu-id="8aeaf-157">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-157">X509</span></span>|<span data-ttu-id="8aeaf-158">Transport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-158">Transport</span></span>|  
|<span data-ttu-id="8aeaf-159">KerberosOverTransport.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-159">KerberosOverTransport</span></span>|<span data-ttu-id="8aeaf-160">Windows</span><span class="sxs-lookup"><span data-stu-id="8aeaf-160">Windows</span></span>|<span data-ttu-id="8aeaf-161">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-161">X509</span></span>|<span data-ttu-id="8aeaf-162">Transport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-162">Transport</span></span>|  
|<span data-ttu-id="8aeaf-163">IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-163">IssuedTokenOverTransport</span></span>|<span data-ttu-id="8aeaf-164">Verbunden</span><span class="sxs-lookup"><span data-stu-id="8aeaf-164">Federated</span></span>|<span data-ttu-id="8aeaf-165">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-165">X509</span></span>|<span data-ttu-id="8aeaf-166">Transport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-166">Transport</span></span>|  
|<span data-ttu-id="8aeaf-167">SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-167">SspiNegotiatedOverTransport</span></span>|<span data-ttu-id="8aeaf-168">Windows Sspi wurde verhandelt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-168">Windows Sspi Negotiated</span></span>|<span data-ttu-id="8aeaf-169">Windows Sspi wurde verhandelt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-169">Windows Sspi Negotiated</span></span>|<span data-ttu-id="8aeaf-170">Transport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-170">Transport</span></span>|  
|<span data-ttu-id="8aeaf-171">AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="8aeaf-171">AnonymousForCertificate</span></span>|<span data-ttu-id="8aeaf-172">Keine</span><span class="sxs-lookup"><span data-stu-id="8aeaf-172">None</span></span>|<span data-ttu-id="8aeaf-173">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-173">X509</span></span>|<span data-ttu-id="8aeaf-174">Meldung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-174">Message</span></span>|  
|<span data-ttu-id="8aeaf-175">UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="8aeaf-175">UserNameForCertificate</span></span>|<span data-ttu-id="8aeaf-176">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-176">User name/password</span></span>|<span data-ttu-id="8aeaf-177">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-177">X509</span></span>|<span data-ttu-id="8aeaf-178">Meldung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-178">Message</span></span>|  
|<span data-ttu-id="8aeaf-179">MutualCertificate</span><span class="sxs-lookup"><span data-stu-id="8aeaf-179">MutualCertificate</span></span>|<span data-ttu-id="8aeaf-180">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-180">X509</span></span>|<span data-ttu-id="8aeaf-181">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-181">X509</span></span>|<span data-ttu-id="8aeaf-182">Meldung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-182">Message</span></span>|  
|<span data-ttu-id="8aeaf-183">MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="8aeaf-183">MutualCertificateDuplex</span></span>|<span data-ttu-id="8aeaf-184">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-184">X509</span></span>|<span data-ttu-id="8aeaf-185">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-185">X509</span></span>|<span data-ttu-id="8aeaf-186">Meldung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-186">Message</span></span>|  
|<span data-ttu-id="8aeaf-187">IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="8aeaf-187">IssuedTokenForCertificate</span></span>|<span data-ttu-id="8aeaf-188">Verbunden</span><span class="sxs-lookup"><span data-stu-id="8aeaf-188">Federated</span></span>|<span data-ttu-id="8aeaf-189">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-189">X509</span></span>|<span data-ttu-id="8aeaf-190">Meldung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-190">Message</span></span>|  
|<span data-ttu-id="8aeaf-191">Kerberos</span><span class="sxs-lookup"><span data-stu-id="8aeaf-191">Kerberos</span></span>|<span data-ttu-id="8aeaf-192">Windows</span><span class="sxs-lookup"><span data-stu-id="8aeaf-192">Windows</span></span>|<span data-ttu-id="8aeaf-193">Windows</span><span class="sxs-lookup"><span data-stu-id="8aeaf-193">Windows</span></span>|<span data-ttu-id="8aeaf-194">Meldung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-194">Message</span></span>|  
|<span data-ttu-id="8aeaf-195">IssuedToken</span><span class="sxs-lookup"><span data-stu-id="8aeaf-195">IssuedToken</span></span>|<span data-ttu-id="8aeaf-196">Verbunden</span><span class="sxs-lookup"><span data-stu-id="8aeaf-196">Federated</span></span>|<span data-ttu-id="8aeaf-197">Verbunden</span><span class="sxs-lookup"><span data-stu-id="8aeaf-197">Federated</span></span>|<span data-ttu-id="8aeaf-198">Meldung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-198">Message</span></span>|  
|<span data-ttu-id="8aeaf-199">SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="8aeaf-199">SspiNegotiated</span></span>|<span data-ttu-id="8aeaf-200">Windows Sspi wurde verhandelt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-200">Windows Sspi Negotiated</span></span>|<span data-ttu-id="8aeaf-201">Windows Sspi wurde verhandelt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-201">Windows Sspi Negotiated</span></span>|<span data-ttu-id="8aeaf-202">Meldung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-202">Message</span></span>|  
|<span data-ttu-id="8aeaf-203">AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="8aeaf-203">AnonymousForSslNegotiated</span></span>|<span data-ttu-id="8aeaf-204">Keine</span><span class="sxs-lookup"><span data-stu-id="8aeaf-204">None</span></span>|<span data-ttu-id="8aeaf-205">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="8aeaf-205">X509, TLS-Nego</span></span>|<span data-ttu-id="8aeaf-206">Meldung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-206">Message</span></span>|  
|<span data-ttu-id="8aeaf-207">UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="8aeaf-207">UserNameForSslNegotiated</span></span>|<span data-ttu-id="8aeaf-208">Benutzername/Kennwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-208">User name/password</span></span>|<span data-ttu-id="8aeaf-209">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="8aeaf-209">X509, TLS-Nego</span></span>|<span data-ttu-id="8aeaf-210">Meldung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-210">Message</span></span>|  
|<span data-ttu-id="8aeaf-211">MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="8aeaf-211">MutualSslNegotiated</span></span>|<span data-ttu-id="8aeaf-212">X509</span><span class="sxs-lookup"><span data-stu-id="8aeaf-212">X509</span></span>|<span data-ttu-id="8aeaf-213">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="8aeaf-213">X509, TLS-Nego</span></span>|<span data-ttu-id="8aeaf-214">Meldung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-214">Message</span></span>|  
|<span data-ttu-id="8aeaf-215">IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="8aeaf-215">IssuedTokenForSslNegotiated</span></span>|<span data-ttu-id="8aeaf-216">Verbunden</span><span class="sxs-lookup"><span data-stu-id="8aeaf-216">Federated</span></span>|<span data-ttu-id="8aeaf-217">X509, TLS-Nego</span><span class="sxs-lookup"><span data-stu-id="8aeaf-217">X509, TLS-Nego</span></span>|<span data-ttu-id="8aeaf-218">Meldung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-218">Message</span></span>|  
  
 <span data-ttu-id="8aeaf-219">Endpunkte, die solche Authentifizierungsmodi verwenden, können ihre Sicherheitsanforderungen über WS-SecurityPolicy (WS-SP) ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-219">Endpoints using such authentication modes can express their security requirements using WS-SecurityPolicy (WS-SP).</span></span> <span data-ttu-id="8aeaf-220">Dieses Dokument beschreibt die Struktur der Sicherheitsheader und der Infrastrukturnachrichten für jeden Authentifizierungsmodus und bietet Richtlinien- und Nachrichtenbeispiele.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-220">This document describes the structure of security header and infrastructure messages for each authentication mode and provides examples of policies and messages.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-221"> setzt WS-SecureConversation ein, um sicheren Sitzungssupport für den Schutz eines mehrteiligen Nachrichtenaustauschs zwischen Anwendungen zu bieten.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-221"> leverages WS-SecureConversation to provide secure sessions support to protect multi-message exchanges between applications.</span></span>  <span data-ttu-id="8aeaf-222">Weitere Informationen zur Implementierung finden Sie unten unter "Sichere Sitzungen".</span><span class="sxs-lookup"><span data-stu-id="8aeaf-222">See "Secure Sessions" below for implementation details.</span></span>  
  
 <span data-ttu-id="8aeaf-223">Zusätzlich zu den Authentifizierungsmodi bietet [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Einstellungen zum Kontrollieren der benutzerdefinierten Schutzmechanismen, die für die meisten auf Nachrichtensicherheit basierenden Authentifizierungsmodi gelten, z. B.: Reihenfolge von Signatur gg. Verschlüsselungsvorgängen, Algorithmussuites, Schlüsselableitung und Signaturbestätigung.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-223">In addition to authentication modes, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] provides settings to control common protection mechanisms that apply to most message security-based authentication modes, for example: order of signature versus encryption operations, algorithm suites, key derivation, and signature confirmation.</span></span>  
  
 <span data-ttu-id="8aeaf-224">Die folgenden XML-Präfixe und -Namespaces werden in diesem Dokument verwendet.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-224">The following prefixes and namespaces are used in this document.</span></span>  
  
|<span data-ttu-id="8aeaf-225">Präfix</span><span class="sxs-lookup"><span data-stu-id="8aeaf-225">Prefix</span></span>|<span data-ttu-id="8aeaf-226">Namespace</span><span class="sxs-lookup"><span data-stu-id="8aeaf-226">Namespace</span></span>|  
|------------|---------------|  
|<span data-ttu-id="8aeaf-227">s</span><span class="sxs-lookup"><span data-stu-id="8aeaf-227">s</span></span>|<span data-ttu-id="8aeaf-228">http://www.w3.org/2003/05/soap-envelope</span><span class="sxs-lookup"><span data-stu-id="8aeaf-228">http://www.w3.org/2003/05/soap-envelope</span></span>|  
|<span data-ttu-id="8aeaf-229">sp</span><span class="sxs-lookup"><span data-stu-id="8aeaf-229">sp</span></span>|<span data-ttu-id="8aeaf-230">http://schemas.xmlsoap.org/ws/2005/07/securitypolicy</span><span class="sxs-lookup"><span data-stu-id="8aeaf-230">http://schemas.xmlsoap.org/ws/2005/07/securitypolicy</span></span>|  
|<span data-ttu-id="8aeaf-231">a</span><span class="sxs-lookup"><span data-stu-id="8aeaf-231">a</span></span>|<span data-ttu-id="8aeaf-232">http://www.w3.org/2005/08/addressing (möglicherweise in englischer Sprache)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-232">http://www.w3.org/2005/08/addressing</span></span>|  
|<span data-ttu-id="8aeaf-233">wsse</span><span class="sxs-lookup"><span data-stu-id="8aeaf-233">wsse</span></span>|<span data-ttu-id="8aeaf-234">TBD – OASIS WSS 1,0 URI</span><span class="sxs-lookup"><span data-stu-id="8aeaf-234">TBD – OASIS WSS 1.0 URI</span></span>|  
|<span data-ttu-id="8aeaf-235">wsse11</span><span class="sxs-lookup"><span data-stu-id="8aeaf-235">wsse11</span></span>|<span data-ttu-id="8aeaf-236">TBD – OASIS WSS 1.1 URI</span><span class="sxs-lookup"><span data-stu-id="8aeaf-236">TBD – OASIS WSS 1.1 URI</span></span>|  
|<span data-ttu-id="8aeaf-237">wsu</span><span class="sxs-lookup"><span data-stu-id="8aeaf-237">wsu</span></span>|<span data-ttu-id="8aeaf-238">TBD – OASIS WSS 1.0 Utility URI</span><span class="sxs-lookup"><span data-stu-id="8aeaf-238">TBD – OASIS WSS 1.0 Utility URI</span></span>|  
|<span data-ttu-id="8aeaf-239">ds</span><span class="sxs-lookup"><span data-stu-id="8aeaf-239">ds</span></span>|<span data-ttu-id="8aeaf-240">TBD – W3C XMLDSig URI</span><span class="sxs-lookup"><span data-stu-id="8aeaf-240">TBD – W3C XMLDSig URI</span></span>|  
|<span data-ttu-id="8aeaf-241">wst</span><span class="sxs-lookup"><span data-stu-id="8aeaf-241">wst</span></span>|<span data-ttu-id="8aeaf-242">TBD – WS-Trust 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="8aeaf-242">TBD – WS-Trust 2005/02 URI</span></span>|  
|<span data-ttu-id="8aeaf-243">wssc</span><span class="sxs-lookup"><span data-stu-id="8aeaf-243">wssc</span></span>|<span data-ttu-id="8aeaf-244">TBD – WS-SecureConversation 2005/02 URI</span><span class="sxs-lookup"><span data-stu-id="8aeaf-244">TBD – WS-SecureConversation 2005/02 URI</span></span>|  
|<span data-ttu-id="8aeaf-245">wsaw</span><span class="sxs-lookup"><span data-stu-id="8aeaf-245">wsaw</span></span>|<span data-ttu-id="8aeaf-246">TBD – WS-Addressing-Richtliniennamespace</span><span class="sxs-lookup"><span data-stu-id="8aeaf-246">TBD - WS-Addressing policy namespace</span></span>|  
|<span data-ttu-id="8aeaf-247">wsp</span><span class="sxs-lookup"><span data-stu-id="8aeaf-247">wsp</span></span>|<span data-ttu-id="8aeaf-248">http://schemas.xmlsoap.org/ws/2004/09/policy</span><span class="sxs-lookup"><span data-stu-id="8aeaf-248">http://schemas.xmlsoap.org/ws/2004/09/policy</span></span>|  
|<span data-ttu-id="8aeaf-249">mssp</span><span class="sxs-lookup"><span data-stu-id="8aeaf-249">mssp</span></span>|<span data-ttu-id="8aeaf-250">http://schemas.microsoft.com/ws/2005/07/securitypolicy</span><span class="sxs-lookup"><span data-stu-id="8aeaf-250">http://schemas.microsoft.com/ws/2005/07/securitypolicy</span></span>|  
  
## <a name="1-token-profiles"></a><span data-ttu-id="8aeaf-251">1. Tokenprofile</span><span class="sxs-lookup"><span data-stu-id="8aeaf-251">1. Token Profiles</span></span>  
 <span data-ttu-id="8aeaf-252">Webdienst-Sicherheitsspezifikationen stellen Anmeldeinformationen als Sicherheitstoken dar.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-252">Web Services Security specifications represent credential as security tokens.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-253"> unterstützt die folgenden Tokentypen:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-253"> supports the following token types:</span></span>  
  
### <a name="11-usernametoken"></a><span data-ttu-id="8aeaf-254">1.1 UsernameToken</span><span class="sxs-lookup"><span data-stu-id="8aeaf-254">1.1 UsernameToken</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-255"> befolgt UsernameToken10- und UsernameToken11-Profile mit den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-255"> follows UsernameToken10 and UsernameToken11 profiles with the following constraints:</span></span>  
  
 <span data-ttu-id="8aeaf-256">Das R1101 PasswordType-Attribut auf Element UsernameToken\Password MUSS entweder weggelassen werden oder über den Wert #PasswordText (Standard) verfügen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-256">R1101 PasswordType attribute on UsernameToken\Password element MUST be either omitted or have value #PasswordText (default).</span></span>  
  
 <span data-ttu-id="8aeaf-257">Man kann #PasswordDigest über Erweiterbarkeit implementieren.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-257">One can implement the #PasswordDigest using extensibility.</span></span> <span data-ttu-id="8aeaf-258">Es wurde beobachtet, dass #PasswordDigest oft für einen Kennwortschutzmechanismus gehalten wurde, der sicher genug ist.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-258">It has been observed that #PasswordDigest was often mistaken to be a secure enough password protection mechanism.</span></span> <span data-ttu-id="8aeaf-259">Aber #PasswordDigest kann nicht als Ersatz für eine Verschlüsselung von UsernameToken dienen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-259">But #PasswordDigest cannot serve as a substitute for encryption of the UsernameToken.</span></span> <span data-ttu-id="8aeaf-260">Das primäre Ziel von #PasswordDigest ist ein Schutz vor Replay-Angriffen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-260">The primary goal of #PasswordDigest is protection against replay attacks.</span></span> <span data-ttu-id="8aeaf-261">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Authentifizierungsmodi werden Replay-Angriffsbedrohungen durch die Nutzung von Nachrichtensignaturen verringert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-261">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] authentication modes, replay attack threats are mitigated by using message signatures.</span></span>  
  
 <span data-ttu-id="8aeaf-262">B1102 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] gibt nie die Unterelemente "Nonce" und "Created" von "UsernameToken" aus.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-262">B1102 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] never emits Nonce and Created sub-elements of the UsernameToken.</span></span>  
  
 <span data-ttu-id="8aeaf-263">Diese Unterelemente sollen die Replay-Erkennung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-263">These sub-elements are intended to help replay detection.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-264"> verwendet stattdessen Nachrichtensignaturen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-264"> uses message signatures instead.</span></span>  
  
 <span data-ttu-id="8aeaf-265">OASIS WSS SOAP Message Security UsernameToken Profile&#160;1.1 (UsernameToken11) hat eine Schlüsselableitung der Kennwortfunktion eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-265">OASIS WSS SOAP Message Security UsernameToken Profile 1.1 (UsernameToken11) introduced key derivation from password feature.</span></span>  
  
 <span data-ttu-id="8aeaf-266">B1103 Das UsernameToken-Kennwort DARF NICHT für die Schlüsselableitung und daher nicht für kryptografische Vorgänge verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-266">B1103 UsernameToken password MUST not be used for key derivation and therefore for cryptographic operations.</span></span>  
  
 <span data-ttu-id="8aeaf-267">Begründung: Kennwörter werden im Allgemeinen als zu schwach für die Verwendung in kryptografischen Vorgängen angesehen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-267">Rationale: passwords are generally considered too weak to be used for cryptographic operations.</span></span>  
  
### <a name="12-x509-token"></a><span data-ttu-id="8aeaf-268">1.2 X509 Token</span><span class="sxs-lookup"><span data-stu-id="8aeaf-268">1.2 X509 Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-269"> unterstützt X509v3-Zertifikate als Anmeldeinformationstyp und folgt X509TokenProfile1.0 und X509TokenProfile1.1 mit den folgenden Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-269"> supports X509v3 certificates as a credential type and follows X509TokenProfile1.0 and X509TokenProfile1.1 with the following constraints:</span></span>  
  
 <span data-ttu-id="8aeaf-270">R1201 Das ValueType-Attribut auf dem BinarySecurityToken-Element muss den Wert #X509v3 besitzen, wenn es ein X509v3-Zertifikat enthält.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-270">R1201 The ValueType attribute on the BinarySecurityToken element must have value #X509v3 when it contains an X509v3 certificate.</span></span>  
  
 <span data-ttu-id="8aeaf-271">WSS X509 Token Profile 1.0 und 1.1 definieren auch #X509PKIPathv1 und #PKCS7 als Werttypen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-271">WSS X509 Token Profile 1.0 and 1.1 define also #X509PKIPathv1 and #PKCS7 as value types.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-272"> unterstützt diese Typen nicht.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-272"> does not support these types.</span></span>  
  
 <span data-ttu-id="8aeaf-273">R1202 Wenn eine SubjectKeyIdentifier (SKI)-Erweiterung in einem X509-Zertifikat vorliegt, sollte wsse:KeyIdentifier als externe Referenz für das Token verwendet werden, wobei das ValueType-Attribut #X509SubjectKeyIdentifier und sein Inhalt der base64-codierte Wert der SKI-Erweiterung des Zertifikats ist.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-273">R1202 If a SubjectKeyIdentifier (SKI) extension is present in an X509 certificate, wsse:KeyIdentifier should be used for external references to the token, with the ValueType attribute as #X509SubjectKeyIdentifier and its content the base64-encoded value of certificate's SKI extension.</span></span>  
  
 <span data-ttu-id="8aeaf-274">SKI-Verweise werden überall implementiert und haben sich als äußerst interoperabler Typ für externe Verweise erwiesen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-274">SKI references are widely implemented and proven to be a highly interoperable external reference type.</span></span>  
  
 <span data-ttu-id="8aeaf-275">R1203 Ein externer Verweis auf das X509-Sicherheitstoken SOLLTE NICHT ds:X509IssuerSerial verwenden.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-275">R1203 An external Reference to X509 Security Token SHOULD NOT use ds:X509IssuerSerial.</span></span>  
  
 <span data-ttu-id="8aeaf-276">R1204 Wenn X509TokenProfile1.1 verwendet wird, SOLLTE eine externe Referenz auf das X509-Sicherheitstoken den Fingerabdruck, der von WS-Sicherheit&#160;1.1 eingeführt wird, verwenden.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-276">R1204 If X509TokenProfile1.1 is in use, an external reference to X509 Security Token SHOULD use the thumbprint introduced by WS-Security 1.1.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-277"> unterstützt X509IssuerSerial.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-277"> supports X509IssuerSerial.</span></span> <span data-ttu-id="8aeaf-278">Es gibt jedoch Interoperabilitätsprobleme mit X509IssuerSerial: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet eine Zeichenfolge, um zwei Werte von X509IssuerSerial zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-278">However There are interoperability issues with X509IssuerSerial: [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses a string to compare two values of X509IssuerSerial.</span></span> <span data-ttu-id="8aeaf-279">Beim Neuordnen von Komponenten des Betreffsnamens und dem Senden eines Verweises auf ein Zertifikat an einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst wird er möglicherweise nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-279">Therefore if one reorders components of the Subject Name and sends to an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service a reference to a certificate, it may not be found.</span></span>  
  
### <a name="13-kerberos-token"></a><span data-ttu-id="8aeaf-280">1.3 Kerberos-Token</span><span class="sxs-lookup"><span data-stu-id="8aeaf-280">1.3 Kerberos Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-281"> unterstützt mit den folgenden Einschränkungen KerberosTokenProfile1.1 für den Zweck der Windows-Authentifizierung:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-281"> supports KerberosTokenProfile1.1 for the purpose of Windows authentication with the following constraints:</span></span>  
  
 <span data-ttu-id="8aeaf-282">R1301 Ein Kerberos-Token muss den Wert eines GSS-ummantelten Kerberos&#160;v4&#160;AP_REQ tragen, gemäß der Definition in GSS_API und der Kerberos-Spezifikation, und muss das ValueType-Attribut mit dem Wert #GSS_Kerberosv5_AP_REQ besitzen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-282">R1301 A Kerberos Token must carry the value of a GSS wrapped Kerberos v4 AP_REQ as defined in GSS_API and the Kerberos specification, and must have the ValueType attribute with the value #GSS_Kerberosv5_AP_REQ.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-283"> verwendet einen GSS-ummantelten Kerberos AP-REQ und keinen reinen AP-REQ.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-283"> uses GSS wrapped Kerberos AP-REQ, not a bare AP-REQ.</span></span> <span data-ttu-id="8aeaf-284">Hierbei handelt es sich um eine empfohlene Vorgehensweise bezüglich der Sicherheit.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-284">This is a security best practice.</span></span>  
  
### <a name="14-saml-v11-token"></a><span data-ttu-id="8aeaf-285">1.4 SAML v1.1 Token</span><span class="sxs-lookup"><span data-stu-id="8aeaf-285">1.4 SAML v1.1 Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-286"> unterstützt WSS SAML Token-Profile&#160;1.0 und&#160;1.1 für SAML-v1.1-Token.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-286"> supports WSS SAML Token profiles 1.0 and 1.1 for SAML v1.1 tokens.</span></span> <span data-ttu-id="8aeaf-287">Es ist möglich, andere Versionen von SAML-Tokenformaten zu implementieren.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-287">It is possible to implement other versions of SAML token formats.</span></span>  
  
### <a name="15-security-context-token"></a><span data-ttu-id="8aeaf-288">1.5 Sicherheitskontexttoken</span><span class="sxs-lookup"><span data-stu-id="8aeaf-288">1.5 Security Context Token</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-289"> unterstützt das in WS-SecureCoversation eingeführte Sicherheitskontexttoken (SCT).</span><span class="sxs-lookup"><span data-stu-id="8aeaf-289"> supports the Security Context Token (SCT) introduced in WS-SecureCoversation.</span></span> <span data-ttu-id="8aeaf-290">SCT wird verwendet, um einen Sicherheitskontext darzustellen, der in SecureConversation genauso etabliert ist wie in den Binärverhandlungsprotokollen TLS und SSPI (siehe unten).</span><span class="sxs-lookup"><span data-stu-id="8aeaf-290">SCT is used to represent a security context established in SecureConversation as well as the binary negotiation protocols TLS and SSPI, described below.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="8aeaf-291">2. Allgemeine Nachrichtensicherheitsparameter</span><span class="sxs-lookup"><span data-stu-id="8aeaf-291">2. Common Message Security Parameters</span></span>  
  
### <a name="21-timestamp"></a><span data-ttu-id="8aeaf-292">2.1 TimeStamp</span><span class="sxs-lookup"><span data-stu-id="8aeaf-292">2.1 TimeStamp</span></span>  
 <span data-ttu-id="8aeaf-293">Die <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A>-Eigenschaft der <xref:System.ServiceModel.Channels.SecurityBindingElement>-Klasse steuert, ob ein Zeitstempel vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-293">Timestamp presence is controlled using the <xref:System.ServiceModel.Channels.SecurityBindingElement.IncludeTimestamp%2A> property of the <xref:System.ServiceModel.Channels.SecurityBindingElement> class.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-294"> serialisiert wsse:TimeStamp immer mit dem wsse:Created-Feld und dem wsse:Expires-Feld.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-294"> always serializes wsse:TimeStamp with wsse:Created and wsse:Expires fields.</span></span> <span data-ttu-id="8aeaf-295">Der wsse:TimeStamp wird immer signiert, wenn Signatur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-295">The wsse:TimeStamp is always signed when signing is used.</span></span>  
  
### <a name="22-protection-order"></a><span data-ttu-id="8aeaf-296">2.2 Schutzreihenfolge</span><span class="sxs-lookup"><span data-stu-id="8aeaf-296">2.2 Protection Order</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-297"> unterstützt die Nachrichtenschutzreihenfolgen "Sign Before Encrypt" und "Encrypt Before Sign" (Sicherheitsrichtlinie&#160;1.1).</span><span class="sxs-lookup"><span data-stu-id="8aeaf-297"> supports the message protection order "Sign Before Encrypt" and "Encrypt Before Sign" (Security Policy 1.1).</span></span> <span data-ttu-id="8aeaf-298">"Sign Before Encrypt" wird u.&#160;a. aus den folgenden Gründen empfohlen: Mit "Encrypt Before Sign" geschützte Nachrichten sind Signaturersatzangriffen ausgesetzt, sofern der WS-Sicherheit&#160;1.1 SignatureConfirmation-Mechanismus nicht verwendet wird, und eine Signatur über verschlüsselten Inhalt erschwert die Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-298">"Sign Before Encrypt" is recommended for reasons including: messages protected with Encrypt Before Sign are open to signature substitution attacks unless the WS-Security 1.1 SignatureConfirmation mechanism is used, and a signature over encrypted content makes auditing harder.</span></span>  
  
### <a name="23-signature-protection"></a><span data-ttu-id="8aeaf-299">2.3 Signaturschutz</span><span class="sxs-lookup"><span data-stu-id="8aeaf-299">2.3 Signature Protection</span></span>  
 <span data-ttu-id="8aeaf-300">Wenn Encrypt Before Sign verwendet wird, ist es empfehlenswert, die Signatur zu schützen, um Brute-Force-Angriffe zu verhindern, die versuchen, den verschlüsselten Inhalt oder den Signaturschlüssel zu erraten (besonders dann, wenn ein benutzerdefiniertes Token zusammen mit schwachen Schlüsselmaterialien verwendet wird).</span><span class="sxs-lookup"><span data-stu-id="8aeaf-300">When Encrypt Before Sign is used, it is recommended to protect the signature to prevent brute force attacks for guessing the encrypted content or the signing key (especially when a custom token is used with weak key material).</span></span>  
  
### <a name="24-algorithm-suite"></a><span data-ttu-id="8aeaf-301">2.4 Algorithmussuites</span><span class="sxs-lookup"><span data-stu-id="8aeaf-301">2.4 Algorithm Suite</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-302"> unterstützt alle in der Sicherheitsrichtlinie&#160;1.1 aufgeführten Algorithmussuites.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-302"> supports all algorithm suites listed in Security Policy 1.1.</span></span>  
  
### <a name="25-key-derivation"></a><span data-ttu-id="8aeaf-303">2.5 Schlüsselableitung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-303">2.5 Key Derivation</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-304"> verwendet die "Schlüsselableitung für symmetrische Schlüssel" gemäß ihrer Beschreibung in WS-SecureConversation.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-304"> uses "Key Derivation for symmetric keys" as described in WS-SecureConversation.</span></span>  
  
### <a name="26-signature-confirmation"></a><span data-ttu-id="8aeaf-305">2.6 Signaturbestätigung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-305">2.6 Signature Confirmation</span></span>  
 <span data-ttu-id="8aeaf-306">Signaturbestätigung kann als Schutz gegen Angriffe von Mittelsmännern eingesetzt werden, um den Signatursatz zu schützen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-306">Signature confirmation can be as protection from middle man attacks to protect the set of signatures.</span></span>  
  
### <a name="27-security-header-layout"></a><span data-ttu-id="8aeaf-307">2.7 Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="8aeaf-307">2.7 Security Header Layout</span></span>  
 <span data-ttu-id="8aeaf-308">Jeder Authentifizierungsmodus beschreibt ein bestimmtes Layout für den Sicherheitsheader.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-308">Each authentication mode describes a certain layout for the security header.</span></span> <span data-ttu-id="8aeaf-309">Elemente innerhalb des Sicherheitsheaders sind teilweise geordnet.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-309">Elements within the security header are semi-ordered.</span></span> <span data-ttu-id="8aeaf-310">Um die Reihenfolge der untergeordneten Sicherheitsheaderelemente zu definieren, definiert die WS-Sicherheitsrichtlinie die folgenden Sicherheitsheader-Layoutmodi:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-310">To define the order of security header child elements, WS-Security Policy defines the following security header layout modes:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="8aeaf-311">Strict</span><span class="sxs-lookup"><span data-stu-id="8aeaf-311">Strict</span></span>|<span data-ttu-id="8aeaf-312">Dem Sicherheitsheader werden Elemente gemäß den durchnummerierten Layout-Regeln, die im Abschnitt&#160;7.7.1 der Sicherheitsrichtlinien beschrieben werden, und gemäß dem allgemeinen Prinzip der "Deklaration vor der Verwendung" hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-312">Items are added to the security header following the numbered layout rules described in Security Policy section 7.7.1 according to a general principle of "declare before use".</span></span>|  
|<span data-ttu-id="8aeaf-313">Lax</span><span class="sxs-lookup"><span data-stu-id="8aeaf-313">Lax</span></span>|<span data-ttu-id="8aeaf-314">Die Elemente werden dem Sicherheitsheader in einer beliebigen Reihenfolge hinzugefügt, die der WSS: SOAP Message Security entspricht.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-314">Items are added to the security header in any order that conforms to WSS: SOAP Message Security.</span></span>|  
|<span data-ttu-id="8aeaf-315">LaxTimestampFirst</span><span class="sxs-lookup"><span data-stu-id="8aeaf-315">LaxTimestampFirst</span></span>|<span data-ttu-id="8aeaf-316">Ebenso wie Lax, nur dass das erste Element im Sicherheitsheader ein wsse:Timestamp sein muss</span><span class="sxs-lookup"><span data-stu-id="8aeaf-316">Same as Lax except that the first item in the security header must be a wsse:Timestamp</span></span>|  
|<span data-ttu-id="8aeaf-317">LaxTimestampLast</span><span class="sxs-lookup"><span data-stu-id="8aeaf-317">LaxTimestampLast</span></span>|<span data-ttu-id="8aeaf-318">Ebenso wie Lax, nur dass das letzte Element im Sicherheitsheader ein wsse:Timestamp sein muss</span><span class="sxs-lookup"><span data-stu-id="8aeaf-318">Same as lax except that the last item in the security header must be a wsse:Timestamp</span></span>|  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-319"> unterstützt alle vier Modi für das Sicherheitsheader-Layout.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-319"> supports all four modes for security header layout.</span></span> <span data-ttu-id="8aeaf-320">Sicherheitsheader-Struktur und Nachrichtenbeispiele für die Authentifizierungsmodi unten folgen dem "Strict"-Modus.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-320">Security header structure and message examples for authentication modes below follow the "Strict" mode.</span></span>  
  
## <a name="2-common-message-security-parameters"></a><span data-ttu-id="8aeaf-321">2. Allgemeine Nachrichtensicherheitsparameter</span><span class="sxs-lookup"><span data-stu-id="8aeaf-321">2. Common Message Security Parameters</span></span>  
 <span data-ttu-id="8aeaf-322">Dieser Abschnitt bietet Beispielrichtlinien für jeden Authentifizierungsmodus, zusammen mit Beispielen, die die Sicherheitsheader-Struktur in Nachrichten, die zwischen Client und Dienst ausgetauscht werden, zeigen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-322">This section provides example policies for each authentication mode along with examples showing security header structure in messages exchanged by client and service.</span></span>  
  
### <a name="61-transport-protection"></a><span data-ttu-id="8aeaf-323">6.1 Transportschutz</span><span class="sxs-lookup"><span data-stu-id="8aeaf-323">6.1 Transport Protection</span></span>  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="8aeaf-324"> stellt fünf Authentifizierungsmodi bereit, die sicheren Transport verwenden, um Nachrichten zu schützen: UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport und SspiNegotiatedOverTransport.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-324"> provides five authentication modes that use secure transport to protect messages; UserNameOverTransport, CertificateOverTransport, KerberosOverTransport, IssuedTokenOverTransport and SspiNegotiatedOverTransport.</span></span>  
  
 <span data-ttu-id="8aeaf-325">Diese Authentifizierungsmodi werden mit der in der Sicherheitsrichtlinie beschriebenen Transportbindung erstellt.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-325">These authentication modes are constructed using the transport binding described in SecurityPolicy.</span></span> <span data-ttu-id="8aeaf-326">Für den UserNameOverTransport-Authentifizierungsmodus ist das UsernameToken ein signiertes unterstützendes Token.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-326">For the UserNameOverTransport authentication mode the UsernameToken is a signed supporting token.</span></span> <span data-ttu-id="8aeaf-327">Für die anderen Authentifizierungsmodi wird das Token als signiertes unterzeichnendes Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-327">For the other authentication modes the token appears as a signed endorsing token.</span></span> <span data-ttu-id="8aeaf-328">Anhang&#160;C.1.2 und&#160;C.1.3 von SecurityPolicy beschreiben detailliert das Sicherheitsheader-Layout.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-328">Appendix C.1.2 and C.1.3 of SecurityPolicy describe the security header layout in detail.</span></span> <span data-ttu-id="8aeaf-329">Die folgenden Beispielsicherheitsheader zeigen das "Strict"-Layout für einen gegebenen Authentifizierungsmodus an.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-329">The following example security headers show the Strict layout for a given authentication mode.</span></span>  
  
 <span data-ttu-id="8aeaf-330">Der Wert der "Derived-Keys"-Eigenschaft für die Token ist in allen Fällen "false".</span><span class="sxs-lookup"><span data-stu-id="8aeaf-330">The value of the "Derived Keys" property for the tokens in all cases is "false".</span></span>  
  
 <span data-ttu-id="8aeaf-331">Die Werte der verschiedenen Eigenschaften der Transportbindung sind wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-331">The values of the various properties of the transport binding are as follows:</span></span>  
  
 <span data-ttu-id="8aeaf-332">Timestamp: true</span><span class="sxs-lookup"><span data-stu-id="8aeaf-332">Timestamp: true</span></span>  
  
 <span data-ttu-id="8aeaf-333">Sicherheitsheader-Layout: Strict</span><span class="sxs-lookup"><span data-stu-id="8aeaf-333">Security Header Layout: Strict</span></span>  
  
 <span data-ttu-id="8aeaf-334">Algorithmussuite: Basic256</span><span class="sxs-lookup"><span data-stu-id="8aeaf-334">Algorithm Suite: Basic256</span></span>  
  
#### <a name="611-usernameovertransport"></a><span data-ttu-id="8aeaf-335">6.1.1 UsernameOverTransport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-335">6.1.1 UsernameOverTransport</span></span>  
 <span data-ttu-id="8aeaf-336">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein Benutzernamentoken, das auf der SOAP-Schicht als signiertes unterstützendes Token angezeigt wird, das immer vom Initiator an den Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-336">With this authentication mode, the client authenticates with a Username Token which appears at the SOAP layer as a signed supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="8aeaf-337">Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-337">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="8aeaf-338">Die verwendete Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-338">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="8aeaf-339">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-339">Policy</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-340">Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="8aeaf-340">Security Header Layout</span></span>  
  
 <span data-ttu-id="8aeaf-341">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-341">Request</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
  <wsse:UsernameToken ... >  
  ...  
  </wsse:UsernameToken>  
</wsse:Security>  
```  
  
 <span data-ttu-id="8aeaf-342">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-342">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="612-certificateovertransport"></a><span data-ttu-id="8aeaf-343">6.1.2 CertificateOverTransport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-343">6.1.2 CertificateOverTransport</span></span>  
 <span data-ttu-id="8aeaf-344">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt wird, das immer vom Initiator an den Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-344">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="8aeaf-345">Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-345">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="8aeaf-346">Die verwendete Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-346">The binding used is a transport binding.</span></span>  
  
 <span data-ttu-id="8aeaf-347">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-347">Policy</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-348">Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="8aeaf-348">Security Header Layout</span></span>  
  
 <span data-ttu-id="8aeaf-349">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-349">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-350">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-350">Response</span></span>  
  
```xml  
<o:Security>  
  <u:Timestamp u:Id="_0">  
  ...  
  </u:Timestamp>  
</o:Security>  
```  
  
#### <a name="613-issuedtokenovertransport"></a><span data-ttu-id="8aeaf-351">6.1.3 IssuedTokenOverTransport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-351">6.1.3 IssuedTokenOverTransport</span></span>  
 <span data-ttu-id="8aeaf-352">In diesem Authentifizierungsmodus unterstützt der Client den Dienst als solchen nicht, sondern präsentiert ein Token, das von einem Sicherheitstokendienst (Security Token Service, STS) ausgegeben wird, und einen freigegebenen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-352">With this authentication mode the client does not authenticate to the service, as such, but rather presents a token issued by a Security Token Service (STS) and proves knowledge of a shared key.</span></span> <span data-ttu-id="8aeaf-353">Das ausgegebene Token wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt, das immer vom Initiator an den Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-353">The issued token appears at the SOAP layer as an endorsing supporting token that is always sent from the initiator to the recipient.</span></span> <span data-ttu-id="8aeaf-354">Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-354">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="8aeaf-355">Die Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-355">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="8aeaf-356">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-356">Policy</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-357">Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="8aeaf-357">Security Header Layout</span></span>  
  
 <span data-ttu-id="8aeaf-358">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-358">Request</span></span>  
  
```xml  
<wsse:Security s:mustUnderstand="1" >  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
  <saml:Assertion ...>  
  ...  
  </saml:Assertion>  
  <ds:Signature>  
  ...  
  </ds:Signature>  
</wsse:Security>  
```  
  
 <span data-ttu-id="8aeaf-359">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-359">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="614-kerberosovertransport"></a><span data-ttu-id="8aeaf-360">6.1.4 KerberosOverTransport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-360">6.1.4 KerberosOverTransport</span></span>  
 <span data-ttu-id="8aeaf-361">Mit diesem Authentifizierungsmodus wird der Client mit einem Kerberos-Ticket dem Dienst gegenüber authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-361">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="8aeaf-362">Das Kerberos-Token wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-362">The Kerberos token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="8aeaf-363">Der Dienst wird über ein X.509-Zertifikat auf der Transportschicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-363">The service is authenticated using an X.509 certificate at the transport layer.</span></span> <span data-ttu-id="8aeaf-364">Die Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-364">The binding is a transport binding.</span></span>  
  
 <span data-ttu-id="8aeaf-365">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-365">Policy</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-366">Sicherheitsheader-Layout</span><span class="sxs-lookup"><span data-stu-id="8aeaf-366">Security Header Layout</span></span>  
  
 <span data-ttu-id="8aeaf-367">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-367">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-368">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-368">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp>  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
#### <a name="615-sspinegotiatedovertransport"></a><span data-ttu-id="8aeaf-369">6.1.5 SspiNegotiatedOverTransport</span><span class="sxs-lookup"><span data-stu-id="8aeaf-369">6.1.5 SspiNegotiatedOverTransport</span></span>  
 <span data-ttu-id="8aeaf-370">Bei diesem Modus wird ein Aushandlungsprotokoll verwendet, um Client- und Serverauthentifizierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-370">With this mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="8aeaf-371">Wenn möglich wird Kerberos verwendet, ansonsten NTLM.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-371">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="8aeaf-372">Das resultierende SCT wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt, das immer vom Initiator an den Empfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-372">The resulting SCT appears at the SOAP layer as an endorsing supporting token that is always sent from initiator to recipient.</span></span> <span data-ttu-id="8aeaf-373">Der Dienst wird zusätzlich auf der Transportschicht über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-373">The service is additionally authenticated at the transport layer by an X.509 certificate.</span></span> <span data-ttu-id="8aeaf-374">Die verwendete Bindung ist eine Transportbindung.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-374">The binding used is a transport binding.</span></span> <span data-ttu-id="8aeaf-375">"SPNEGO" (Aushandlung) beschreibt, wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] das binäre SSPI-Aushandlungsprotokoll zusammen mit WS-Trust verwendet.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-375">"SPNEGO" (negotiation) describes how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses SSPI binary negotiation protocol with WS-Trust.</span></span> <span data-ttu-id="8aeaf-376">Die Sicherheitsheaderbeispiele in diesem Abschnitt gelten, nachdem der SCT durch den SPNEGO-Handshake eingeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-376">Security header examples in this section are after the SCT has been established through the SPNEGO handshake.</span></span>  
  
 <span data-ttu-id="8aeaf-377">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-377">Policy</span></span>  
  
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
  
### <a name="security-header-examples"></a><span data-ttu-id="8aeaf-378">Beispiele für Sicherheitsheader</span><span class="sxs-lookup"><span data-stu-id="8aeaf-378">Security Header Examples</span></span>  
 <span data-ttu-id="8aeaf-379">Sobald das Sicherheitskontexttoken einmal durch SPNEGO unter Verwendung der WS-Trust-Binäraushandlung eingeführt wurde, besitzen die Anwendungsnachrichten Sicherheitsheader mit der folgenden Struktur.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-379">Once the Security Context Token is established through SPNEGO handshake using WS-Trust Binary Negotiation, the application messages have security headers with the following structure.</span></span>  
  
 <span data-ttu-id="8aeaf-380">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-380">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-381">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-381">Response</span></span>  
  
```xml  
<wsse:Security>  
  <wsu:Timestamp u:Id="_0">  
  ...  
  </wsu:Timestamp>  
</wsse:Security>  
```  
  
### <a name="62-using-x509-certificates-for-service-authentication"></a><span data-ttu-id="8aeaf-382">6.2 Verwenden von X.509-Zertifikaten zur Dienstauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-382">6.2 Using X.509 Certificates for Service Authentication</span></span>  
 <span data-ttu-id="8aeaf-383">In diesem Abschnitt werden die folgenden Authentifizierungsmodi beschrieben: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate und IssuedTokenForCertificate.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-383">This section describes the following authentication modes: MutualCertificate WSS1.0, Mutual CertificateDuplex, MutualCertificate WSS1.1, AnonymousForCertificate, UserNameForCertificate and IssuedTokenForCertificate.</span></span>  
  
#### <a name="621-mutualcertificate-wss10"></a><span data-ttu-id="8aeaf-384">6.2.1 MutualCertificate WSS1.0</span><span class="sxs-lookup"><span data-stu-id="8aeaf-384">6.2.1 MutualCertificate WSS1.0</span></span>  
 <span data-ttu-id="8aeaf-385">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das auf der SOAP-Schicht als das Initiatortoken angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-385">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="8aeaf-386">Der Dienst wird ebenfalls über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-386">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="8aeaf-387">Die verwendete Bindung ist eine asymmetrische Bindung mit den folgenden Eigenschaftswerten:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-387">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="8aeaf-388">Initiator-Token: das X.509-Zertifikat des Clients, wobei der Inclusion-Modus auf .../IncludeToken/AlwaysToRecipient festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="8aeaf-388">Initiator Token: the client’s X.509 certificate, with inclusion mode set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="8aeaf-389">Empfängertoken: das X.509-Zertifikat des Servers, wobei der Inclusion-Modus auf .../IncludeToken/Never festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="8aeaf-389">Recipient Token: Server’s X.509 Certificate, with inclusion mode is set …/IncludeToken/Never</span></span>  
  
 <span data-ttu-id="8aeaf-390">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="8aeaf-390">Token Protection: False</span></span>  
  
 <span data-ttu-id="8aeaf-391">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-391">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="8aeaf-392">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-392">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="8aeaf-393">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-393">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="8aeaf-394">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-394">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-395">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-395">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-396">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-396">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-397">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-397">Response</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-398">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-398">Security Header Examples: EncryptBeforeSign</span></span>  
  
 <span data-ttu-id="8aeaf-399">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-399">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-400">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-400">Response</span></span>  
  
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
  
#### <a name="622-mutualcertificateduplex"></a><span data-ttu-id="8aeaf-401">6.2.2 MutualCertificateDuplex</span><span class="sxs-lookup"><span data-stu-id="8aeaf-401">6.2.2 MutualCertificateDuplex</span></span>  
 <span data-ttu-id="8aeaf-402">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das auf der SOAP-Schicht als das Initiatortoken angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-402">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as the initiator token.</span></span> <span data-ttu-id="8aeaf-403">Der Dienst wird ebenfalls über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-403">The service is also authenticated using an X.509 certificate.</span></span>  
  
 <span data-ttu-id="8aeaf-404">Die verwendete Bindung ist eine asymmetrische Bindung mit den folgenden Eigenschaftswerten:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-404">The binding used is an asymmetric binding with the following property values:</span></span>  
  
 <span data-ttu-id="8aeaf-405">Initiator-Token: das X.509-Zertifikat des Clients, wobei der Inclusion-Modus auf .../IncludeToken/AlwaysToRecipient festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="8aeaf-405">Initiator Token: Client’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToRecipient</span></span>  
  
 <span data-ttu-id="8aeaf-406">Empfänger-Token: das X.509-Zertifikat des Servers, wobei der Inclusion-Modus auf .../IncludeToken/AlwaysToInitiator festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="8aeaf-406">Recipient Token: Server’s X509 Certificate, inclusion mode is set to …/IncludeToken/AlwaysToInitiator</span></span>  
  
 <span data-ttu-id="8aeaf-407">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="8aeaf-407">Token Protection: False</span></span>  
  
 <span data-ttu-id="8aeaf-408">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-408">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="8aeaf-409">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-409">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="8aeaf-410">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-410">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="8aeaf-411">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-411">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-412">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-412">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-413">Anforderung und Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-413">Request and Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-414">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-414">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-415">Anforderung und Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-415">Request and Response</span></span>  
  
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
  
#### <a name="623-using-symmetricbinding-with-x509-service-authentication"></a><span data-ttu-id="8aeaf-416">6.2.3 Verwenden von SymmetricBinding mit X.509-Dienstauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-416">6.2.3 Using SymmetricBinding with X.509 Service Authentication</span></span>  
 <span data-ttu-id="8aeaf-417">"WSS10" bot lediglich eingeschränkten Support für Szenarien mit X509-Token.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-417">"WSS10" provided limited support for scenarios with X509 tokens.</span></span> <span data-ttu-id="8aeaf-418">Beispielsweise gab es keine Möglichkeit, Signatur- und Verschlüsselungsschutz für Nachrichten bereitzustellen, die nur Dienst-X509-Token verwenden.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-418">For example, there was no way to provide signature and encryption protection for messages using only service X509 token.</span></span> <span data-ttu-id="8aeaf-419">"WSS11" hat die Verwendung von EncryptedKey als symmetrisches Token eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-419">"WSS11" introduced the usage of EncryptedKey as a symmetric token.</span></span> <span data-ttu-id="8aeaf-420">Jetzt könnte ein temporärer Schlüssel, der für das X.509-Zertifikat verschlüsselt wurde, sowohl für den Anforderungs- als auch für den Antwortnachrichtenschutz verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-420">Now a temporary key encrypted for the service's X.509 certificate could be used for both request and response messages protection.</span></span> <span data-ttu-id="8aeaf-421">Die unten in Abschnitt&#160;6.4 beschriebenen Authentifizierungsmodi verwenden dieses Muster.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-421">The authentication modes described in the section 6.4 below use this pattern.</span></span>  
  
 <span data-ttu-id="8aeaf-422">Die WS-Sicherheitsrichtlinie beschreibt dieses Muster unter Verwendung von SymmetricBinding mit dem Dienst-X509-Token als Schutztoken.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-422">WS-SecurityPolicy describes this pattern using SymmetricBinding with Service X509 token as the protection token.</span></span>  
  
 <span data-ttu-id="8aeaf-423">Die Authentifizierungsmodi AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 und IssuedTokenForCertificate verwenden alle eine ähnliche Instanz von sp:SymmetricBinding mit den folgenden Eigenschaftswerten:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-423">Authentication modes AnonymousForCertificate, UsernameForCertificate, MutualCertificate WSS11 and IssuedTokenForCertificate all use a similar instance of sp:SymmetricBinding with the following property values:</span></span>  
  
 <span data-ttu-id="8aeaf-424">Schutztoken: das X.509-Zertifikat des Servers, wobei der Einschlussmodus auf .../IncludeToken/Never festgelegt ist</span><span class="sxs-lookup"><span data-stu-id="8aeaf-424">Protection Token: Server’s X509 Certificate, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="8aeaf-425">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="8aeaf-425">Token Protection: False</span></span>  
  
 <span data-ttu-id="8aeaf-426">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-426">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="8aeaf-427">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-427">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="8aeaf-428">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-428">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="8aeaf-429">Die oben erwähnten Authentifizierungsmodi unterscheiden sich nur durch die unterstützenden Token, die sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-429">The above authentication modes only differ by the supporting tokens they use.</span></span> <span data-ttu-id="8aeaf-430">AnonymousForCertificate besitzt keine unterstützenden Token, MutualCertificate WSS 1.1 besitzt das X509-Zertifikat des Clients als unterzeichnendes unterstützendes Token, UserNameForCertificate besitzt ein Benutzernamentoken als signiertes unterstützendes Token und IssuedTokenForCertificate besitzt das ausgestellte Token als unterzeichnendes unterstützendes Token.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-430">AnonymousForCertificate does not have any supporting tokens, MutualCertificate WSS 1.1 has the client’s X509 certificate as an endorsing supporting tokens, UserNameForCertificate has a UserName Token as a signed supporting token and IssuedTokenForCertificate has the issued token as an endorsing supporting token.</span></span>  
  
 <span data-ttu-id="8aeaf-431">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-431">Policy</span></span>  
  
 <span data-ttu-id="8aeaf-432">Symmetrische Bindung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-432">Symmetric Binding</span></span>  
  
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
  
#### <a name="624-anonymousforcertificate"></a><span data-ttu-id="8aeaf-433">6.2.4 AnonymousForCertificate</span><span class="sxs-lookup"><span data-stu-id="8aeaf-433">6.2.4 AnonymousForCertificate</span></span>  
 <span data-ttu-id="8aeaf-434">Mit diesem Authentifizierungsmodus ist der Client anonym, und der Dienst wird mit einem X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-434">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="8aeaf-435">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung im Abschnitt&#160;6.4.2.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-435">The binding used is an instance of symmetric binding as described in 6.4.2.</span></span>  
  
 <span data-ttu-id="8aeaf-436">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-436">Policy</span></span>  
  
 <span data-ttu-id="8aeaf-437">Weitere Informationen zu den Bindungen finden Sie unter "Richtlinie" im Abschnitt&#160;6.2.3.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-437">See "Policy" in 6.2.3 above for binding details</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-438">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-438">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-439">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-439">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-440">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-440">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-441">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-441">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-442">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-442">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-443">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-443">Response</span></span>  
  
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
  
#### <a name="625-usernameforcertificate"></a><span data-ttu-id="8aeaf-444">6.2.5 UserNameForCertificate</span><span class="sxs-lookup"><span data-stu-id="8aeaf-444">6.2.5 UserNameForCertificate</span></span>  
 <span data-ttu-id="8aeaf-445">Bei diesem Authentifizierungsmodus authentifiziert sich der Client dem Dienst gegenüber mit einem Benutzernamentoken, das auf der SOAP-Schicht als signiertes unterstützendes Token angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-445">With this authentication mode the client authenticates to the service using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="8aeaf-446">Der Dienst wird über ein X.509-Zertifikat am Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-446">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="8aeaf-447">Die verwendete Bindung ist eine symmetrische Bindung, deren Schutztoken ein Schlüssel ist, der vom Client generiert und über den öffentlichen Schlüssel des Diensts verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-447">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="8aeaf-448">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-448">Policy</span></span>  
  
 <span data-ttu-id="8aeaf-449">Weitere Informationen zu den Bindungen finden Sie unter "Richtlinie" im Abschnitt&#160;6.2.3.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-449">See "Policy" in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="8aeaf-450">Signiertes unterstützendes Token</span><span class="sxs-lookup"><span data-stu-id="8aeaf-450">Signed Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-451">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-451">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-452">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-452">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-453">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-453">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-454">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-454">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-455">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-455">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-456">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-456">Response</span></span>  
  
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
  
#### <a name="626-mutualcertificate-wss-11"></a><span data-ttu-id="8aeaf-457">6.2.6 MutualCertificate (WSS 1.1)</span><span class="sxs-lookup"><span data-stu-id="8aeaf-457">6.2.6 MutualCertificate (WSS 1.1)</span></span>  
 <span data-ttu-id="8aeaf-458">Bei diesem Authentifizierungsmodus authentifiziert sich der Client über ein X.509-Zertifikat, das auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-458">With this authentication mode the client authenticates using an X.509 certificate which appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="8aeaf-459">Der Dienst wird ebenfalls über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-459">The service is also authenticated using an X.509 certificate.</span></span> <span data-ttu-id="8aeaf-460">Die verwendete Bindung ist eine symmetrische Bindung, deren Schutztoken ein Schlüssel ist, der vom Client generiert und über den öffentlichen Schlüssel des Diensts verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-460">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="8aeaf-461">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-461">Policy</span></span>  
  
 <span data-ttu-id="8aeaf-462">Weitere Informationen zu den Bindungen finden Sie unter "Richtlinie" im Abschnitt&#160;6.2.3.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-462">See Policy in 6.2.3 for binding details</span></span>  
  
 <span data-ttu-id="8aeaf-463">Ausstellendes unterstützendes Token</span><span class="sxs-lookup"><span data-stu-id="8aeaf-463">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-464">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-464">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-465">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-465">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-466">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-466">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-467">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-467">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-468">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-468">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-469">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-469">Response</span></span>  
  
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
  
#### <a name="627-issuedtokenforcertificate"></a><span data-ttu-id="8aeaf-470">6.2.7 IssuedTokenForCertificate</span><span class="sxs-lookup"><span data-stu-id="8aeaf-470">6.2.7 IssuedTokenForCertificate</span></span>  
 <span data-ttu-id="8aeaf-471">In diesem Authentifizierungsmodus unterstützt der Client den Dienst als solchen nicht, sondern präsentiert ein Token, das von einem Sicherheitstokendienst (Security Token Service, STS) ausgegeben wird, und einen geteilten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-471">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by a STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="8aeaf-472">Das ausgestellte Token wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-472">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="8aeaf-473">Der Dienst wird über ein X.509-Zertifikat am Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-473">The service authenticates to the client using an X.509 certificate.</span></span> <span data-ttu-id="8aeaf-474">Die verwendete Bindung ist eine symmetrische Bindung, deren Schutztoken ein Schlüssel ist, der vom Client generiert und über den öffentlichen Schlüssel des Diensts verschlüsselt wurde.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-474">The binding used is a symmetric binding with the protection token being a key generated by the client, encrypted with the public key of the service.</span></span>  
  
 <span data-ttu-id="8aeaf-475">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-475">Policy</span></span>  
  
 <span data-ttu-id="8aeaf-476">Weitere Informationen zu den Bindungen finden Sie unter "Richtlinie" im Abschnitt&#160;6.2.3.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-476">See Policy in 6.2.3 above for binding details</span></span>  
  
 <span data-ttu-id="8aeaf-477">Ausstellendes unterstützendes Token</span><span class="sxs-lookup"><span data-stu-id="8aeaf-477">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-478">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-478">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-479">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-479">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-480">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-480">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-481">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-481">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-482">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-482">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-483">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-483">Response</span></span>  
  
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
  
## <a name="63-kerberos"></a><span data-ttu-id="8aeaf-484">6.3 Kerberos</span><span class="sxs-lookup"><span data-stu-id="8aeaf-484">6.3 Kerberos</span></span>  
 <span data-ttu-id="8aeaf-485">Mit diesem Authentifizierungsmodus wird der Client mit einem Kerberos-Ticket dem Dienst gegenüber authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-485">With this authentication mode the client authenticates to the service using a Kerberos ticket.</span></span> <span data-ttu-id="8aeaf-486">Dieses gleiche Ticket bietet auch Serverauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-486">That same ticket also provides server authentication.</span></span> <span data-ttu-id="8aeaf-487">Die verwendete Bindung ist eine symmetrische Bindung mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-487">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="8aeaf-488">Schutztoken: Kerberos-Ticket, Einschlussmodus ist auf .../IncludeToken/Once festgelegt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-488">Protection Token: Kerberos Ticket, inclusion mode is set to .../IncludeToken/Once</span></span>  
<span data-ttu-id="8aeaf-489">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="8aeaf-489">Token Protection: False</span></span>  
  
 <span data-ttu-id="8aeaf-490">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-490">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="8aeaf-491">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-491">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="8aeaf-492">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-492">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="8aeaf-493">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-493">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-494">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-494">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-495">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-495">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-496">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-496">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-497">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-497">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-498">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-498">Request</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
 <span data-ttu-id="8aeaf-499">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-499">Response</span></span>  
  
```xml  
<wsse:Security>  
TBD  
</wsse:Security>  
```  
  
#### <a name="64-issuedtoken"></a><span data-ttu-id="8aeaf-500">6.4 IssuedToken</span><span class="sxs-lookup"><span data-stu-id="8aeaf-500">6.4 IssuedToken</span></span>  
 <span data-ttu-id="8aeaf-501">In diesem Authentifizierungsmodus unterstützt der Client den Dienst als solchen nicht. Stattdessen präsentiert der Client ein Token, das von einem Security Token Service (STS) ausgegeben wird, und einen freigegebenen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-501">With this authentication mode the client does not authenticate to the service, as such, rather the client presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="8aeaf-502">Der Dienst wird dem Client gegenüber nicht authentifiziert. Stattdessen verschlüsselt STS den geteilten Schlüssel als Teil des ausgestellten Tokens, sodass nur der Dienst den Schlüssel entschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-502">The service is not authenticated to the client, as such, instead the STS encrypts the shared key as part of the issued token such that only the service can decrypt the key.</span></span> <span data-ttu-id="8aeaf-503">Die verwendete Bindung ist eine symmetrische Bindung mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-503">The binding used is as symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="8aeaf-504">Schutztoken: ausgestelltes Token, Einschlussmodus ist auf .../IncludeToken/AlwaysToRecipient festgelegt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-504">Protection Token: Issued Token, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="8aeaf-505">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="8aeaf-505">Token Protection: False</span></span>  
  
 <span data-ttu-id="8aeaf-506">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-506">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="8aeaf-507">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-507">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="8aeaf-508">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-508">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="8aeaf-509">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-509">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-510">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-510">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-511">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-511">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-512">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-512">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-513">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-513">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-514">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-514">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-515">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-515">Response</span></span>  
  
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
  
### <a name="65-using-sslnegotiated-for-service-authentication"></a><span data-ttu-id="8aeaf-516">6.5 Verwenden von SslNegotiated zur Dienstauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-516">6.5 Using SslNegotiated for Service Authentication</span></span>  
 <span data-ttu-id="8aeaf-517">Dieser Abschnitt beschreibt eine Gruppe von Authentifizierungsmodi, die eine symmetrische Bindung verwenden, deren Schutztoken ein Sicherheitskontexttoken über WS-SecureConversation (WS-SC) ist, dessen Schlüsselwert ausgeführt wird, indem das TLS-Protokoll über WS-Trust (WS-T) RST/RSTR-Nachrichten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-517">This section describes a group of authentication modes that use a symmetric binding with the protection token being a Security Context Token per WS-SecureConversation (WS-SC) whose key value is negotiated by executing the TLS protocol over WS-Trust (WS-T) RST/RSTR messages.</span></span> <span data-ttu-id="8aeaf-518">Genaue Informationen über die TLS-Handshake-Implementierung mit WS-Trust werden in TLSNEGO beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-518">Details of the TLS handshake implementation using WS-Trust are described in TLSNEGO.</span></span> <span data-ttu-id="8aeaf-519">In diesen Nachrichtenbeispielen wird davon ausgegangen, dass SCT bereits mit einem verbundenen Sicherheitskontext über einen Handshake etabliert ist.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-519">Here in the message examples we will assume that SCT with an associated security context is already established through a handshake.</span></span>  
  
 <span data-ttu-id="8aeaf-520">Die verwendete Bindung ist eine symmetrische Bindung mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-520">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="8aeaf-521">Schutztoken: SslContextToken, Einschlussmodus ist auf .../IncludeToken/Never festgelegt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-521">Protection Token: SslContextToken, inclusion mode is set to .../IncludeToken/Never</span></span>  
<span data-ttu-id="8aeaf-522">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="8aeaf-522">Token Protection: False</span></span>  
  
 <span data-ttu-id="8aeaf-523">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-523">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="8aeaf-524">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-524">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="8aeaf-525">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-525">Encrypt Signature: True</span></span>  
  
#### <a name="651-policy-for-sslnegotiated-service-authentication"></a><span data-ttu-id="8aeaf-526">6.5.1 Richtlinie für SslNegotiated-Dienstauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-526">6.5.1 Policy for SslNegotiated service authentication</span></span>  
 <span data-ttu-id="8aeaf-527">Die Richtlinien für alle Authentifizierungsmodi in diesem Abschnitt sind ähnlich und unterscheiden sich nur durch bestimmte signierte unterstützende oder ausstellende Token, die verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-527">Policy for all authentication modes in this section are similar and differ only by specific signed supporting or endorsing tokens used.</span></span>  
  
```xml  
<wsp:Policy wsu:Id='SslNegotiated_policy' >  
  <wsp:ExactlyOne>  
    <wsp:All>  
      <sp:SymmetricBinding>  
        <wsp:Policy>  
          <sp:ProtectionToken>  
            <wsp:Policy>  
              <mssp:SslContextToken sp:IncludeToken='http://schemas.xmlsoap.org/ws/2005/07/securitypolicy/IncludeToken/AlwaysToRecipient' />  
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
  
#### <a name="652-anonymousforsslnegotiated"></a><span data-ttu-id="8aeaf-528">6.5.2 AnonymousForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="8aeaf-528">6.5.2 AnonymousForSslNegotiated</span></span>  
 <span data-ttu-id="8aeaf-529">Mit diesem Authentifizierungsmodus ist der Client anonym, und der Dienst wird mit einem X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-529">With this authentication mode the client is anonymous and the service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="8aeaf-530">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung in&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-530">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="8aeaf-531">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-531">Policy</span></span>  
  
 <span data-ttu-id="8aeaf-532">Weitere Informationen zu den Bindungen finden Sie unter "Richtlinie" im Abschnitt&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-532">See Policy in 6.5.1 above for binding details.</span></span>  
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-533">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-533">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-534">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-534">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-535">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-535">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-536">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-536">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-537">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-537">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-538">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-538">Response</span></span>  
  
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
  
#### <a name="653-usernameforsslnegotiated"></a><span data-ttu-id="8aeaf-539">6.5.3 UserNameForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="8aeaf-539">6.5.3 UserNameForSslNegotiated</span></span>  
 <span data-ttu-id="8aeaf-540">Bei diesem Authentifizierungsmodus wird der Client über ein Benutzernamentoken authentifiziert, das auf der SOAP-Schicht als signiertes unterstützendes Token angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-540">With this authentication mode the client is authenticates using a Username Token which appears at the SOAP layer as a signed supporting token.</span></span> <span data-ttu-id="8aeaf-541">Der Dienst wird über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-541">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="8aeaf-542">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung im Abschnitt&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-542">The binding used is an instance of symmetric binding as described in 6.5.1.</span></span>  
  
 <span data-ttu-id="8aeaf-543">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-543">Policy</span></span>  
  
 <span data-ttu-id="8aeaf-544">Weitere Informationen zu den Bindungen finden Sie im Abschnitt&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-544">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="8aeaf-545">Signiertes unterstützendes Token</span><span class="sxs-lookup"><span data-stu-id="8aeaf-545">Signed Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-546">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-546">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-547">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-547">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-548">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-548">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-549">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-549">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-550">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-550">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-551">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-551">Response</span></span>  
  
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
  
#### <a name="654-issuedtokenforsslnegotiated"></a><span data-ttu-id="8aeaf-552">6.5.4 IssuedTokenForSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="8aeaf-552">6.5.4 IssuedTokenForSslNegotiated</span></span>  
 <span data-ttu-id="8aeaf-553">In diesem Authentifizierungsmodus unterstützt der Client den Dienst als solchen nicht, sondern präsentiert ein Token, das von einem Sicherheitstokendienst (Security Token Service, STS) ausgegeben wird, und einen freigegebenen Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-553">With this authentication mode the client does not authenticate to the service, as such, but instead presents a token issued by an STS and proves knowledge of a shared key.</span></span> <span data-ttu-id="8aeaf-554">Das ausgestellte Token wird auf der SOAP-Schicht als ausstellendes unterstützendes Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-554">The issued token appears at the SOAP layer as an endorsing supporting token.</span></span> <span data-ttu-id="8aeaf-555">Der Dienst wird über ein X.509-Zertifikat authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-555">The service is authenticated using an X.509 certificate.</span></span> <span data-ttu-id="8aeaf-556">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung in&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-556">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="8aeaf-557">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-557">Policy</span></span>  
  
 <span data-ttu-id="8aeaf-558">Weitere Informationen zu den Bindungen finden Sie im Abschnitt&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-558">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="8aeaf-559">Ausstellendes unterstützendes Token</span><span class="sxs-lookup"><span data-stu-id="8aeaf-559">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-560">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-560">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-561">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-561">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-562">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-562">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-563">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-563">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-564">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-564">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-565">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-565">Response</span></span>  
  
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
  
#### <a name="655-mutualsslnegotiated"></a><span data-ttu-id="8aeaf-566">6.5.5 MutualSslNegotiated</span><span class="sxs-lookup"><span data-stu-id="8aeaf-566">6.5.5 MutualSslNegotiated</span></span>  
 <span data-ttu-id="8aeaf-567">Bei diesem Authentifizierungsmodus werden sowohl der Client als auch der Dienst mit X.509-Zertifikaten authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-567">With this authentication mode the client and the service authenticate using X.509 certificates.</span></span> <span data-ttu-id="8aeaf-568">Die verwendete Bindung ist eine Instanz einer symmetrischen Bindung gemäß der Beschreibung in&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-568">The binding used is an instance of symmetric binding as described in 6.5.1 above.</span></span>  
  
 <span data-ttu-id="8aeaf-569">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-569">Policy</span></span>  
  
 <span data-ttu-id="8aeaf-570">Weitere Informationen zu den Bindungen finden Sie im Abschnitt&#160;6.5.1.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-570">See section 6.5.1 above for binding details</span></span>  
  
 <span data-ttu-id="8aeaf-571">Ausstellendes unterstützendes Token</span><span class="sxs-lookup"><span data-stu-id="8aeaf-571">Endorsing Supporting Token</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-572">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-572">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-573">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-573">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-574">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-574">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-575">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-575">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-576">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-576">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-577">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-577">Response</span></span>  
  
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
  
### <a name="66-sspinegotiated"></a><span data-ttu-id="8aeaf-578">6.6 SspiNegotiated</span><span class="sxs-lookup"><span data-stu-id="8aeaf-578">6.6 SspiNegotiated</span></span>  
 <span data-ttu-id="8aeaf-579">Bei diesem Authentifizierungsmodus wird ein Aushandlungsprotokoll verwendet, um Client- und Serverauthentifizierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-579">With this authentication mode a negotiation protocol is used to perform client and server authentication.</span></span> <span data-ttu-id="8aeaf-580">Wenn möglich wird Kerberos verwendet, ansonsten NTLM.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-580">Kerberos is used if possible, otherwise NTLM.</span></span> <span data-ttu-id="8aeaf-581">Die verwendete Bindung ist eine symmetrische Bindung mit den folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="8aeaf-581">The binding used is a symmetric binding with the following properties;</span></span>  
  
 <span data-ttu-id="8aeaf-582">Schutztoken: SpnegoContextToken, Einschlussmodus ist auf .../IncludeToken/AlwaysToRecipient festgelegt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-582">Protection Token: SpnegoContextToken, inclusion mode is set to .../IncludeToken/AlwaysToRecipient</span></span>  
<span data-ttu-id="8aeaf-583">Tokenschutz: False</span><span class="sxs-lookup"><span data-stu-id="8aeaf-583">Token Protection: False</span></span>  
  
 <span data-ttu-id="8aeaf-584">Ganze Header- und Textsignaturen: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-584">Entire Header And Body Signatures: True</span></span>  
  
 <span data-ttu-id="8aeaf-585">Schutzreihenfolge: SignBeforeEncrypt</span><span class="sxs-lookup"><span data-stu-id="8aeaf-585">Protection Order: SignBeforeEncrypt</span></span>  
  
 <span data-ttu-id="8aeaf-586">Signaturverschlüsselung: True</span><span class="sxs-lookup"><span data-stu-id="8aeaf-586">Encrypt Signature: True</span></span>  
  
 <span data-ttu-id="8aeaf-587">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-587">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-588">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-588">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-589">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-589">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-590">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-590">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-591">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-591">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-592">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-592">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-593">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-593">Response</span></span>  
  
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
  
### <a name="67-secureconversation"></a><span data-ttu-id="8aeaf-594">6.7 SecureConversation</span><span class="sxs-lookup"><span data-stu-id="8aeaf-594">6.7 SecureConversation</span></span>  
 <span data-ttu-id="8aeaf-595">Die verwendete Bindung ist eine symmetrische Bindung, wobei das Schutztoken ein SCT über WS-SecureConversation (WS-SC) ist.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-595">The binding used is a symmetric binding with the protection token being a SCT per WS-SecureConversation (WS-SC).</span></span> <span data-ttu-id="8aeaf-596">Das SCT wird über WS-Trust (WS-Trust) oder WS-SecureConversation (WS-SC) gemäß einer ummantelten Bindung ausgehandelt, die selbst eine symmetrische Bindung ist und ein Aushandlungsprotokoll verwendet.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-596">The SCT is negotiated using WS-Trust (WS-Trust) or WS-SecureConversation (WS-SC) according to a nested binding, which is itself a symmetric binding that uses a negotiation protocol.</span></span> <span data-ttu-id="8aeaf-597">Das Aushandlungsprotokoll verwendet Kerberos, um, falls möglich, Client- und Serverauthentifizierung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-597">The negotiation protocol will use Kerberos to perform client and server authentication if possible.</span></span> <span data-ttu-id="8aeaf-598">Wenn Kerberos nicht verwendet werden kann, greift es wieder auf NTLM zurück.</span><span class="sxs-lookup"><span data-stu-id="8aeaf-598">If Kerberos cannot be used, it will fall back to NTLM.</span></span>  
  
 <span data-ttu-id="8aeaf-599">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="8aeaf-599">Policy</span></span>  
  
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
  
### <a name="security-header-examples-signbeforeencrypt-encryptsignature"></a><span data-ttu-id="8aeaf-600">Sicherheitsheaderbeispiele: SignBeforeEncrypt, EncryptSignature</span><span class="sxs-lookup"><span data-stu-id="8aeaf-600">Security Header Examples: SignBeforeEncrypt, EncryptSignature</span></span>  
 <span data-ttu-id="8aeaf-601">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-601">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-602">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-602">Response</span></span>  
  
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
  
### <a name="security-header-examples-encryptbeforesign"></a><span data-ttu-id="8aeaf-603">Sicherheitsheaderbeispiele: EncryptBeforeSign</span><span class="sxs-lookup"><span data-stu-id="8aeaf-603">Security Header Examples: EncryptBeforeSign</span></span>  
 <span data-ttu-id="8aeaf-604">Anforderung</span><span class="sxs-lookup"><span data-stu-id="8aeaf-604">Request</span></span>  
  
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
  
 <span data-ttu-id="8aeaf-605">Antwort</span><span class="sxs-lookup"><span data-stu-id="8aeaf-605">Response</span></span>  
  
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
