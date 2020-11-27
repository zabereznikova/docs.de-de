---
title: Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: 5f2909bb088a5f3d3203fe3c9e24b2df3450aa3f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257827"
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="dad0d-102">Benutzerdefinierte Anmeldeinformationen und Validierung der Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="dad0d-102">Custom Credential and Credential Validation</span></span>

<span data-ttu-id="dad0d-103">Die Sicherheit in Windows Communication Foundation (WCF) basiert auf dem Austausch von Anmelde Informationen zwischen Diensten und Clients.</span><span class="sxs-lookup"><span data-stu-id="dad0d-103">Security in Windows Communication Foundation (WCF) is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="dad0d-104">Die meisten Sicherheitsszenarien können durch die Verwendung allgemeiner Anmeldeinformationstypen wie Windows (Kerberos), Benutzerrname und Kennwörter sowie Zertifikate erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="dad0d-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="dad0d-105">Falls jedoch ein neuer Typ von Anmeldeinformationen erforderlich ist, wird in den Themen in diesem Abschnitt die Behandlung und Überprüfung neuer Typen erläutert.</span><span class="sxs-lookup"><span data-stu-id="dad0d-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dad0d-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dad0d-106">In This Section</span></span>  

 [<span data-ttu-id="dad0d-107">Vorgehensweise: Erstellen eines Diensts, der ein benutzerdefiniertes Zertifikatsvalidierungssteuerelement verwendet</span><span class="sxs-lookup"><span data-stu-id="dad0d-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="dad0d-108">Erläutert, wie Sie die WCF-Validierung anpassen, indem Sie von der- <xref:System.IdentityModel.Selectors.X509CertificateValidator> Klasse erben.</span><span class="sxs-lookup"><span data-stu-id="dad0d-108">Explains how to customize WCF validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="dad0d-109">Exemplarische Vorgehensweise: Erstellen von benutzerdefinierten Client- und Dienstanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="dad0d-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="dad0d-110">Veranschaulicht, wie die <xref:System.ServiceModel.Description.ClientCredentials> Klassen und erweitert werden <xref:System.ServiceModel.Description.ServiceCredentials> , um neue Anmelde Informationstypen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="dad0d-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="dad0d-111">Dies ist das erste Thema in einer Reihe von Themen, die das Erstellen benutzerdefinierter Anmeldeinformationstypen ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="dad0d-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="dad0d-112">Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenanbieters</span><span class="sxs-lookup"><span data-stu-id="dad0d-112">How to: Create a Custom Security Token Provider</span></span>](how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="dad0d-113">Erläutert das Erstellen eines Sicherheitstokenanbieters zur Behandlung neuer Anmeldeinformationstypen und zum Zurückgeben neuer Token für die Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="dad0d-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="dad0d-114">Dies ist das zweite Thema in der Reihe.</span><span class="sxs-lookup"><span data-stu-id="dad0d-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="dad0d-115">Vorgehensweise: Erstellen eines benutzerdefinierten Sicherheitstokenauthentifizierers</span><span class="sxs-lookup"><span data-stu-id="dad0d-115">How to: Create a Custom Security Token Authenticator</span></span>](how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="dad0d-116">Erläutert das Erstellen eines benutzerdefinierten Authentifizierers zum Authentifizieren eines neuen Anmeldeinformationstyps.</span><span class="sxs-lookup"><span data-stu-id="dad0d-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="dad0d-117">Dies ist das dritte Thema in der Reihe.</span><span class="sxs-lookup"><span data-stu-id="dad0d-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dad0d-118">Referenz</span><span class="sxs-lookup"><span data-stu-id="dad0d-118">Reference</span></span>  

 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="dad0d-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="dad0d-119">Related Sections</span></span>  

 [<span data-ttu-id="dad0d-120">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="dad0d-120">Authentication</span></span>](../feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="dad0d-121">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="dad0d-121">Federation and Issued Tokens</span></span>](../feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="dad0d-122">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="dad0d-122">Authorization</span></span>](../feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="dad0d-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dad0d-123">See also</span></span>

- [<span data-ttu-id="dad0d-124">Security</span><span class="sxs-lookup"><span data-stu-id="dad0d-124">Security</span></span>](../feature-details/security.md)
