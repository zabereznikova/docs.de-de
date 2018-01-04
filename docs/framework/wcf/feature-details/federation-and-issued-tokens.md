---
title: Verbund und ausgestellte Token
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 017d3e51022ad9980dc8f058415697c80a2a6b35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="af110-102">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="af110-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="af110-103">Mit [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] können Sie Clients erstellen, die sicher mit Diensten kommunizieren, die den WS-Verbund und die WS-Trust-Spezifikationen implementieren.</span><span class="sxs-lookup"><span data-stu-id="af110-103">With [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="af110-104">Die Spezifikationen verwenden XML, SOAP und Web Services Description Language (WSDL), um Mechanismen zu bieten, die Authentifizierung und Autorisierung über verschiedene Vertrauensbereiche hinweg zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="af110-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af110-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="af110-105">In This Section</span></span>  
 [<span data-ttu-id="af110-106">Verbund</span><span class="sxs-lookup"><span data-stu-id="af110-106">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 <span data-ttu-id="af110-107">Bietet einen Überblick über den Verbund.</span><span class="sxs-lookup"><span data-stu-id="af110-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="af110-108">Verbund und Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="af110-108">Federation and Trust</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 <span data-ttu-id="af110-109">Führt die Entwurfsprobleme auf, die beim Erstellen von Verbunddiensten oder -clients berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="af110-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="af110-110">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="af110-110">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 <span data-ttu-id="af110-111">Beschreibt die Grundlagen der Erstellung eines Verbundclients mit [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="af110-111">Describes the basics of creating a federated client with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="af110-112">Vorgehensweise: Konfigurieren von Anmeldeinformationen für einen Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="af110-112">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="af110-113">Beschreibt die Schritte beim Erstellen eines Verbunddiensts.</span><span class="sxs-lookup"><span data-stu-id="af110-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="af110-114">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="af110-114">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="af110-115">Beschreibt, wie man Clients und Dienste konfiguriert, die `WSFederationHttpBinding` verwenden.</span><span class="sxs-lookup"><span data-stu-id="af110-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="af110-116">Vorgehensweise: Erstellen eines Sicherheitstokendiensts</span><span class="sxs-lookup"><span data-stu-id="af110-116">How to: Create a Security Token Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 <span data-ttu-id="af110-117">Beschreibt die Schritte beim Erstellen eines Sicherheitstokendiensts.</span><span class="sxs-lookup"><span data-stu-id="af110-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="af110-118">SAML-Token (Security Assertions Markup Language) und Ansprüche.</span><span class="sxs-lookup"><span data-stu-id="af110-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 <span data-ttu-id="af110-119">Beschreibt Security Assertions Markup Language (SAML)-Token, die erweiterbar sind und es ermöglichen, Rich Claim-Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="af110-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="af110-120">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="af110-120">How to: Configure a Local Issuer</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="af110-121">Beschreibt, wie ein lokaler Aussteller von Sicherheitstoken erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="af110-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="af110-122">Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="af110-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="af110-123">Beschreibt, wie Sicherheitssitzungen auf `WSFederationHttpBinding` deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="af110-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="af110-124">Sichere Sitzungen müssen deaktiviert werden, wenn eine Webfarm erstellt wird, die eine Sitzung für jeden Client erfordert.</span><span class="sxs-lookup"><span data-stu-id="af110-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="af110-125">Verweis</span><span class="sxs-lookup"><span data-stu-id="af110-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="af110-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af110-126">See Also</span></span>  
 [<span data-ttu-id="af110-127">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="af110-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="af110-128"> Benutzerdefinierte Token</span><span class="sxs-lookup"><span data-stu-id="af110-128">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 [<span data-ttu-id="af110-129">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="af110-129">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
