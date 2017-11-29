---
title: Erweitern der Sicherheit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
caps.latest.revision: "23"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: a3950b156ede806382bbe4e013db5d94a8b20a23
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="extending-security"></a><span data-ttu-id="a12fb-102">Erweitern der Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a12fb-102">Extending Security</span></span>
<span data-ttu-id="a12fb-103">Wenn Sie neue Anspruchstypen und benutzerdefinierte Token aufnehmen möchten, können Sie die Sicherheitsinfrastruktur von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] erweitern.</span><span class="sxs-lookup"><span data-stu-id="a12fb-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="a12fb-104">Die Themen dieses Abschnitts erläutern die entsprechende Vorgehensweise.</span><span class="sxs-lookup"><span data-stu-id="a12fb-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a12fb-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="a12fb-105">In This Section</span></span>  
 [<span data-ttu-id="a12fb-106">Sicherheitsarchitektur</span><span class="sxs-lookup"><span data-stu-id="a12fb-106">Security Architecture</span></span>](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)  
 <span data-ttu-id="a12fb-107">Veranschaulicht die Architektur des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Sicherheitssystems.</span><span class="sxs-lookup"><span data-stu-id="a12fb-107">Walks through the architecture of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security system.</span></span>  
  
 [<span data-ttu-id="a12fb-108">Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="a12fb-108">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="a12fb-109">Erklärt die Verwendung des Identitätsmodells bei der Überprüfung von benutzerdefinierten Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="a12fb-109">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="a12fb-110">Benutzerdefinierte Token</span><span class="sxs-lookup"><span data-stu-id="a12fb-110">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="a12fb-111">Bei ausgestellten Token aus einem Sicherheitstokendienst handelt es sich in der Regel um SAML-Token.</span><span class="sxs-lookup"><span data-stu-id="a12fb-111">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="a12fb-112">Dieses Thema erklärt das Erstellen eines benutzerdefinierten Tokentyps.</span><span class="sxs-lookup"><span data-stu-id="a12fb-112">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="a12fb-113">Benutzerdefinierte Autorisierung</span><span class="sxs-lookup"><span data-stu-id="a12fb-113">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="a12fb-114">Erklärt das Implementieren einer benutzerdefinierten Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="a12fb-114">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="a12fb-115">Überschreiben der Identität eines Dienstes zur Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="a12fb-115">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="a12fb-116">Beschreibt das Überschreiben der Identität eines Dienstes zur Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="a12fb-116">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="a12fb-117">Vorgehensweise: Erstellen einer benutzerdefinierten Clientidentitätsüberprüfung</span><span class="sxs-lookup"><span data-stu-id="a12fb-117">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="a12fb-118">Veranschaulicht das Überprüfen einer benutzerdefinierten Endpunktidentität.</span><span class="sxs-lookup"><span data-stu-id="a12fb-118">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="a12fb-119">Vorgehensweise: Verwenden von separaten x. 509-Zertifikate für die Signierung und Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="a12fb-119">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="a12fb-120">Nachrichten werden in der Regel mit einem einzigen Zertifikat signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="a12fb-120">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="a12fb-121">Dieses Thema erklärt, wie Zertifikate bei Bedarf verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a12fb-121">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="a12fb-122">Vorgehensweise: Ändern des Kryptografieanbieters für den privaten Schlüssel ein x. 509-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="a12fb-122">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="a12fb-123">Erläutert, wie Sie den Kryptografieanbieter ändern, mit dessen Hilfe der private Schlüssel eines X.509-Zertifikats bereitgestellt wird, und wie Sie den Anbieter in das [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Sicherheitsframework integrieren.</span><span class="sxs-lookup"><span data-stu-id="a12fb-123">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a12fb-124">Verweis</span><span class="sxs-lookup"><span data-stu-id="a12fb-124">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="a12fb-125">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="a12fb-125">Related Sections</span></span>  
 [<span data-ttu-id="a12fb-126">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="a12fb-126">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="a12fb-127">Einfache WCF-Programmierung</span><span class="sxs-lookup"><span data-stu-id="a12fb-127">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="a12fb-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a12fb-128">See Also</span></span>  
 [<span data-ttu-id="a12fb-129">Sicherheit (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="a12fb-129">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
