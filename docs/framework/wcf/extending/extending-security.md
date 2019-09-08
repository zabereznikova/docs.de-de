---
title: Erweitern der Sicherheit
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 45216493a3afa23f24a085964a2c43e19b197d4b
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70797122"
---
# <a name="extending-security"></a><span data-ttu-id="8cf9d-102">Erweitern der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8cf9d-102">Extending Security</span></span>
<span data-ttu-id="8cf9d-103">Wenn Sie neue Anspruchs Typen und benutzerdefinierte Token aufnehmen möchten, können Sie die Sicherheitsinfrastruktur von Windows Communication Foundation (WCF) erweitern.</span><span class="sxs-lookup"><span data-stu-id="8cf9d-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="8cf9d-104">Die Themen dieses Abschnitts erläutern die entsprechende Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="8cf9d-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8cf9d-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="8cf9d-105">In This Section</span></span>  
  
 [<span data-ttu-id="8cf9d-106">Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="8cf9d-106">Custom Credential and Credential Validation</span></span>](custom-credential-and-credential-validation.md)  
 <span data-ttu-id="8cf9d-107">Erklärt die Verwendung des Identitätsmodells bei der Überprüfung von benutzerdefinierten Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="8cf9d-107">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="8cf9d-108"> Benutzerdefinierte Token</span><span class="sxs-lookup"><span data-stu-id="8cf9d-108">Custom Tokens</span></span>](custom-tokens.md)  
 <span data-ttu-id="8cf9d-109">Bei ausgestellten Token aus einem Sicherheitstokendienst handelt es sich in der Regel um SAML-Token.</span><span class="sxs-lookup"><span data-stu-id="8cf9d-109">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="8cf9d-110">Dieses Thema erklärt das Erstellen eines benutzerdefinierten Tokentyps.</span><span class="sxs-lookup"><span data-stu-id="8cf9d-110">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="8cf9d-111">Benutzerdefinierte Autorisierung</span><span class="sxs-lookup"><span data-stu-id="8cf9d-111">Custom Authorization</span></span>](custom-authorization.md)  
 <span data-ttu-id="8cf9d-112">Erklärt das Implementieren einer benutzerdefinierten Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="8cf9d-112">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="8cf9d-113">Überschreiben der Identität eines Dienstes zur Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="8cf9d-113">Overriding the Identity of a Service for Authentication</span></span>](overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="8cf9d-114">Beschreibt das Überschreiben der Identität eines Dienstes zur Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="8cf9d-114">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="8cf9d-115">Vorgehensweise: Erstellen einer benutzerdefinierten Client Identitätsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="8cf9d-115">How to: Create a Custom Client Identity Verifier</span></span>](how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="8cf9d-116">Veranschaulicht das Überprüfen einer benutzerdefinierten Endpunktidentität.</span><span class="sxs-lookup"><span data-stu-id="8cf9d-116">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="8cf9d-117">Vorgehensweise: Verwenden von separaten X. 509-Zertifikaten zum Signieren und verschlüsseln</span><span class="sxs-lookup"><span data-stu-id="8cf9d-117">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="8cf9d-118">Nachrichten werden in der Regel mit einem einzigen Zertifikat signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="8cf9d-118">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="8cf9d-119">Dieses Thema erklärt, wie Zertifikate bei Bedarf verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8cf9d-119">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="8cf9d-120">Vorgehensweise: Ändern des Kryptografieanbieters für den privaten Schlüssel eines X. 509-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="8cf9d-120">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="8cf9d-121">Erläutert, wie der Kryptografieanbieter geändert wird, mit dem der private Schlüssel eines X. 509-Zertifikats bereitgestellt wird, und wie der Anbieter in das Windows Communication Foundation-Framework (WCF) integriert wird.</span><span class="sxs-lookup"><span data-stu-id="8cf9d-121">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the Windows Communication Foundation (WCF) framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="8cf9d-122">Referenz</span><span class="sxs-lookup"><span data-stu-id="8cf9d-122">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="8cf9d-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="8cf9d-123">Related Sections</span></span>  
 [<span data-ttu-id="8cf9d-124">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8cf9d-124">Security</span></span>](../feature-details/security.md)  
  
 [<span data-ttu-id="8cf9d-125">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="8cf9d-125">Basic WCF Programming</span></span>](../basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="8cf9d-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8cf9d-126">See also</span></span>

- [<span data-ttu-id="8cf9d-127">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8cf9d-127">Security Overview</span></span>](../feature-details/security-overview.md)
