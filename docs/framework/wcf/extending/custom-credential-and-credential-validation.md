---
title: Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 021a4e206a5abfb3508e8e548114de7e61dd2d04
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="81c33-102">Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="81c33-102">Custom Credential and Credential Validation</span></span>
<span data-ttu-id="81c33-103">Die Sicherheit in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] basiert auf dem Austausch von Anmeldeinformationen zwischen Diensten und Clients.</span><span class="sxs-lookup"><span data-stu-id="81c33-103">Security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="81c33-104">Die meisten Sicherheitsszenarien können durch die Verwendung allgemeiner Anmeldeinformationstypen wie Windows (Kerberos), Benutzerrname und Kennwörter sowie Zertifikate erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="81c33-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="81c33-105">Falls jedoch ein neuer Typ von Anmeldeinformationen erforderlich ist, wird in den Themen in diesem Abschnitt die Behandlung und Überprüfung neuer Typen erläutert.</span><span class="sxs-lookup"><span data-stu-id="81c33-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="81c33-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="81c33-106">In This Section</span></span>  
 [<span data-ttu-id="81c33-107">Vorgehensweise: erstellen ein Diensts, der ein benutzerdefiniertes Zertifikats-Validierungssteuerelement verwendet</span><span class="sxs-lookup"><span data-stu-id="81c33-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="81c33-108">Erläutert das Anpassen der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Validierung durch Erben von der <xref:System.IdentityModel.Selectors.X509CertificateValidator>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="81c33-108">Explains how to customize [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="81c33-109">Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="81c33-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="81c33-110">Veranschaulicht das Erweitern der <xref:System.ServiceModel.Description.ClientCredentials> und <xref:System.ServiceModel.Description.ServiceCredentials> Klassen für die Aufnahme neuer Anmeldeinformationstypen.</span><span class="sxs-lookup"><span data-stu-id="81c33-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="81c33-111">Dies ist das erste Thema in einer Reihe von Themen, die das Erstellen benutzerdefinierter Anmeldeinformationstypen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="81c33-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="81c33-112">Vorgehensweise: Erstellen Sie einen benutzerdefinierten Sicherheitstokenanbieter</span><span class="sxs-lookup"><span data-stu-id="81c33-112">How to: Create a Custom Security Token Provider</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="81c33-113">Erläutert das Erstellen eines Sicherheitstokenanbieters zur Behandlung neuer Anmeldeinformationstypen und zum Zurückgeben neuer Token für die Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="81c33-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="81c33-114">Dies ist das zweite Thema in der Reihe.</span><span class="sxs-lookup"><span data-stu-id="81c33-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="81c33-115">Vorgehensweise: erstellen ein benutzerdefinierten Sicherheitstokenauthentifizierers</span><span class="sxs-lookup"><span data-stu-id="81c33-115">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="81c33-116">Erläutert das Erstellen eines benutzerdefinierten Authentifizierers zum Authentifizieren eines neuen Anmeldeinformationstyps.</span><span class="sxs-lookup"><span data-stu-id="81c33-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="81c33-117">Dies ist das dritte Thema in der Reihe.</span><span class="sxs-lookup"><span data-stu-id="81c33-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="81c33-118">Verweis</span><span class="sxs-lookup"><span data-stu-id="81c33-118">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="81c33-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="81c33-119">Related Sections</span></span>  
 [<span data-ttu-id="81c33-120">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="81c33-120">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="81c33-121">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="81c33-121">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="81c33-122">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="81c33-122">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="81c33-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81c33-123">See Also</span></span>  
 [<span data-ttu-id="81c33-124">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="81c33-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
