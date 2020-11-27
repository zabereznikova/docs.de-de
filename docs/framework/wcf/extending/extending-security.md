---
title: Erweitern der Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: d91f4812dbccb7807be2e0780cccd1d0c38b1f40
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273060"
---
# <a name="extending-security"></a><span data-ttu-id="67a1c-102">Erweitern der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="67a1c-102">Extending Security</span></span>

<span data-ttu-id="67a1c-103">Wenn Sie neue Anspruchs Typen und benutzerdefinierte Token aufnehmen möchten, können Sie die Sicherheitsinfrastruktur von Windows Communication Foundation (WCF) erweitern.</span><span class="sxs-lookup"><span data-stu-id="67a1c-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="67a1c-104">Die Themen dieses Abschnitts erläutern die entsprechende Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="67a1c-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="67a1c-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="67a1c-105">In This Section</span></span>  
  
 [<span data-ttu-id="67a1c-106">Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="67a1c-106">Custom Credential and Credential Validation</span></span>](custom-credential-and-credential-validation.md)  
 <span data-ttu-id="67a1c-107">Erklärt die Verwendung des Identitätsmodells bei der Überprüfung von benutzerdefinierten Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="67a1c-107">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="67a1c-108">Benutzerdefinierte Token</span><span class="sxs-lookup"><span data-stu-id="67a1c-108">Custom Tokens</span></span>](custom-tokens.md)  
 <span data-ttu-id="67a1c-109">Bei ausgestellten Token aus einem Sicherheitstokendienst handelt es sich in der Regel um SAML-Token.</span><span class="sxs-lookup"><span data-stu-id="67a1c-109">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="67a1c-110">Dieses Thema erklärt das Erstellen eines benutzerdefinierten Tokentyps.</span><span class="sxs-lookup"><span data-stu-id="67a1c-110">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="67a1c-111">Benutzerdefinierte Autorisierung</span><span class="sxs-lookup"><span data-stu-id="67a1c-111">Custom Authorization</span></span>](custom-authorization.md)  
 <span data-ttu-id="67a1c-112">Erklärt das Implementieren einer benutzerdefinierten Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="67a1c-112">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="67a1c-113">Überschreiben der Identität eines Dienstes zur Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="67a1c-113">Overriding the Identity of a Service for Authentication</span></span>](overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="67a1c-114">Beschreibt das Überschreiben der Identität eines Dienstes zur Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="67a1c-114">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="67a1c-115">Vorgehensweise: Erstellen einer benutzerdefinierten Clientidentitätsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="67a1c-115">How to: Create a Custom Client Identity Verifier</span></span>](how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="67a1c-116">Veranschaulicht das Überprüfen einer benutzerdefinierten Endpunktidentität.</span><span class="sxs-lookup"><span data-stu-id="67a1c-116">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="67a1c-117">Vorgehensweise: Verwenden von separaten X.509-Zertifikaten zum Signieren und Verschlüsseln</span><span class="sxs-lookup"><span data-stu-id="67a1c-117">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="67a1c-118">Nachrichten werden in der Regel mit einem einzigen Zertifikat signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="67a1c-118">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="67a1c-119">Dieses Thema erklärt, wie Zertifikate bei Bedarf verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="67a1c-119">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="67a1c-120">Vorgehensweise: Ändern des Kryptografieanbieters für den privaten Schlüssel eines X.509-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="67a1c-120">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="67a1c-121">Erläutert, wie der Kryptografieanbieter geändert wird, mit dem der private Schlüssel eines X. 509-Zertifikats bereitgestellt wird, und wie der Anbieter in das Windows Communication Foundation-Framework (WCF) integriert wird.</span><span class="sxs-lookup"><span data-stu-id="67a1c-121">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="67a1c-122">Referenz</span><span class="sxs-lookup"><span data-stu-id="67a1c-122">Reference</span></span>  

 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="67a1c-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="67a1c-123">Related Sections</span></span>  

 [<span data-ttu-id="67a1c-124">Security</span><span class="sxs-lookup"><span data-stu-id="67a1c-124">Security</span></span>](../feature-details/security.md)  
  
 [<span data-ttu-id="67a1c-125">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="67a1c-125">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="67a1c-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="67a1c-126">See also</span></span>

- [<span data-ttu-id="67a1c-127">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="67a1c-127">Security Overview</span></span>](../feature-details/security-overview.md)
