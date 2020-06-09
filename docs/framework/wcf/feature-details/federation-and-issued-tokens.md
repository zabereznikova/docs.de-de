---
title: Verbund und ausgestellte Token
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: aeffc1e2a7b61dfd9406b9f06678064533ea61ec
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595504"
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="63977-102">Verbund und ausgestellte Token</span><span class="sxs-lookup"><span data-stu-id="63977-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="63977-103">Mit Windows Communication Foundation (WCF) können Sie Clients erstellen, die sicher mit Diensten kommunizieren, die die WS-Verbund-und WS-Trust-Spezifikationen implementieren.</span><span class="sxs-lookup"><span data-stu-id="63977-103">With Windows Communication Foundation (WCF), you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="63977-104">Die Spezifikationen verwenden XML, SOAP und Web Services Description Language (WSDL), um Mechanismen zu bieten, die Authentifizierung und Autorisierung über verschiedene Vertrauensbereiche hinweg zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="63977-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="63977-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="63977-105">In This Section</span></span>  
 [<span data-ttu-id="63977-106">Verbund</span><span class="sxs-lookup"><span data-stu-id="63977-106">Federation</span></span>](federation.md)  
 <span data-ttu-id="63977-107">Bietet einen Überblick über den Verbund.</span><span class="sxs-lookup"><span data-stu-id="63977-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="63977-108">Verbund und Vertrauenswürdigkeit</span><span class="sxs-lookup"><span data-stu-id="63977-108">Federation and Trust</span></span>](federation-and-trust.md)  
 <span data-ttu-id="63977-109">Führt die Entwurfsprobleme auf, die beim Erstellen von Verbunddiensten oder -clients berücksichtigt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="63977-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="63977-110">Vorgehensweise: Erstellen eines Verbundclients</span><span class="sxs-lookup"><span data-stu-id="63977-110">How to: Create a Federated Client</span></span>](how-to-create-a-federated-client.md)  
 <span data-ttu-id="63977-111">Beschreibt die Grundlagen der Erstellung eines Verbund Clients mit WCF.</span><span class="sxs-lookup"><span data-stu-id="63977-111">Describes the basics of creating a federated client with WCF.</span></span>  
  
 [<span data-ttu-id="63977-112">Vorgehensweise: Konfigurieren von Anmeldeinformationen auf einem Verbunddienst</span><span class="sxs-lookup"><span data-stu-id="63977-112">How to: Configure Credentials on a Federation Service</span></span>](how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="63977-113">Beschreibt die Schritte beim Erstellen eines Verbunddiensts.</span><span class="sxs-lookup"><span data-stu-id="63977-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="63977-114">Vorgehensweise: Erstellen einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="63977-114">How to: Create a WSFederationHttpBinding</span></span>](how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="63977-115">Beschreibt, wie man Clients und Dienste konfiguriert, die `WSFederationHttpBinding` verwenden.</span><span class="sxs-lookup"><span data-stu-id="63977-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="63977-116">Vorgehensweise: Erstellen eines Sicherheitstokendiensts</span><span class="sxs-lookup"><span data-stu-id="63977-116">How to: Create a Security Token Service</span></span>](how-to-create-a-security-token-service.md)  
 <span data-ttu-id="63977-117">Beschreibt die Schritte beim Erstellen eines Sicherheitstokendiensts.</span><span class="sxs-lookup"><span data-stu-id="63977-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="63977-118">SAML-Token (Security Assertions Markup Language) und Ansprüche</span><span class="sxs-lookup"><span data-stu-id="63977-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](saml-tokens-and-claims.md)  
 <span data-ttu-id="63977-119">Beschreibt Security Assertions Markup Language (SAML)-Token, die erweiterbar sind und es ermöglichen, Rich Claim-Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="63977-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="63977-120">Vorgehensweise: Konfigurieren eines lokalen Ausstellers</span><span class="sxs-lookup"><span data-stu-id="63977-120">How to: Configure a Local Issuer</span></span>](how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="63977-121">Beschreibt, wie ein lokaler Aussteller von Sicherheitstoken erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="63977-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="63977-122">Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="63977-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="63977-123">Beschreibt, wie Sicherheitssitzungen auf `WSFederationHttpBinding` deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="63977-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="63977-124">Sichere Sitzungen müssen deaktiviert werden, wenn eine Webfarm erstellt wird, die eine Sitzung für jeden Client erfordert.</span><span class="sxs-lookup"><span data-stu-id="63977-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="63977-125">Referenz</span><span class="sxs-lookup"><span data-stu-id="63977-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="63977-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63977-126">See also</span></span>

- [<span data-ttu-id="63977-127">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="63977-127">Authorization</span></span>](authorization-in-wcf.md)
- [<span data-ttu-id="63977-128">Benutzerdefinierte Token</span><span class="sxs-lookup"><span data-stu-id="63977-128">Custom Tokens</span></span>](../extending/custom-tokens.md)
- <span data-ttu-id="63977-129">[Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="63977-129">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
