---
title: Erweitern der Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 94aefe80674c5b4ec6fcce6a41d9b68e093f4262
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33809400"
---
# <a name="extending-security"></a><span data-ttu-id="40ebe-102">Erweitern der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="40ebe-102">Extending Security</span></span>
<span data-ttu-id="40ebe-103">Um neue Anspruchstypen und benutzerdefinierte Token aufnehmen zu können, können Sie die Sicherheitsinfrastruktur von Windows Communication Foundation (WCF) erweitern.</span><span class="sxs-lookup"><span data-stu-id="40ebe-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="40ebe-104">Die Themen dieses Abschnitts erläutern die entsprechende Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="40ebe-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="40ebe-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="40ebe-105">In This Section</span></span>  
 [<span data-ttu-id="40ebe-106">Sicherheitsarchitektur</span><span class="sxs-lookup"><span data-stu-id="40ebe-106">Security Architecture</span></span>](http://msdn.microsoft.com/library/16593476-d36a-408d-808c-ae6fd483e28f)  
 <span data-ttu-id="40ebe-107">Führt Sie durch die Architektur des WCF-Sicherheitssystems.</span><span class="sxs-lookup"><span data-stu-id="40ebe-107">Walks through the architecture of the WCF security system.</span></span>  
  
 [<span data-ttu-id="40ebe-108">Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="40ebe-108">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="40ebe-109">Erklärt die Verwendung des Identitätsmodells bei der Überprüfung von benutzerdefinierten Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="40ebe-109">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="40ebe-110"> Benutzerdefinierte Token</span><span class="sxs-lookup"><span data-stu-id="40ebe-110">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="40ebe-111">Bei ausgestellten Token aus einem Sicherheitstokendienst handelt es sich in der Regel um SAML-Token.</span><span class="sxs-lookup"><span data-stu-id="40ebe-111">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="40ebe-112">Dieses Thema erklärt das Erstellen eines benutzerdefinierten Tokentyps.</span><span class="sxs-lookup"><span data-stu-id="40ebe-112">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="40ebe-113">Benutzerdefinierte Autorisierung</span><span class="sxs-lookup"><span data-stu-id="40ebe-113">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="40ebe-114">Erklärt das Implementieren einer benutzerdefinierten Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="40ebe-114">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="40ebe-115">Überschreiben der Identität eines Dienstes zur Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="40ebe-115">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="40ebe-116">Beschreibt das Überschreiben der Identität eines Dienstes zur Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="40ebe-116">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="40ebe-117">Vorgehensweise: Erstellen einer benutzerdefinierten Clientidentitätsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="40ebe-117">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="40ebe-118">Veranschaulicht das Überprüfen einer benutzerdefinierten Endpunktidentität.</span><span class="sxs-lookup"><span data-stu-id="40ebe-118">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="40ebe-119">Vorgehensweise: Verwenden von separaten X.509-Zertifikaten für Signieren und Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="40ebe-119">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="40ebe-120">Nachrichten werden in der Regel mit einem einzigen Zertifikat signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="40ebe-120">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="40ebe-121">Dieses Thema erklärt, wie Zertifikate bei Bedarf verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="40ebe-121">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="40ebe-122">Vorgehensweise: Ändern des Kryptografieanbieters für den privaten Schlüssel eines X.509-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="40ebe-122">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="40ebe-123">Erläutert, wie so ändern Sie den Kryptografieanbieter verwendet, um private Schlüssel eines x. 509-Zertifikats bereitzustellen und den Anbieter in der Windows Communication Foundation (WCF)-Framework zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="40ebe-123">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="40ebe-124">Referenz</span><span class="sxs-lookup"><span data-stu-id="40ebe-124">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="40ebe-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="40ebe-125">Related Sections</span></span>  
 [<span data-ttu-id="40ebe-126">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="40ebe-126">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="40ebe-127">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="40ebe-127">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="40ebe-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="40ebe-128">See Also</span></span>  
 [<span data-ttu-id="40ebe-129">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="40ebe-129">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
