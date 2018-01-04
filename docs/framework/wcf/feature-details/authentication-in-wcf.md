---
title: Authentifizierung in WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 432ed9debeffad82125b567508ed46b46d4b8821
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="cd460-102">Authentifizierung in WCF</span><span class="sxs-lookup"><span data-stu-id="cd460-102">Authentication in WCF</span></span>
<span data-ttu-id="cd460-103">Die folgenden Themen beschreiben eine Anzahl unterschiedlicher Mechanismen in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], die eine Authentifizierung ermöglichen, z. B. die Windows-Authentifizierung, X.509-Zertifikate sowie Benutzername und Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="cd460-103">The following topics show a number of different mechanisms in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cd460-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cd460-104">In This Section</span></span>  
 [<span data-ttu-id="cd460-105">Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="cd460-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="cd460-106">Zu den ASP.NET-Funktionen gehören eine Mitgliedschaft und ein Rollenanbieter, eine Datenbank, um Benutzernamen/Kennwort-Paare für die Authentifizierung zu speichern, sowie Benutzerrollen zur Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="cd460-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="cd460-107">In diesem Thema wird erläutert, wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste die gleiche Datenbank verwenden können, um Benutzer zu authentifizieren und zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="cd460-107">This topic explains how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="cd460-108">Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungssteuerelements</span><span class="sxs-lookup"><span data-stu-id="cd460-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="cd460-109">Veranschaulicht, wie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement integriert wird.</span><span class="sxs-lookup"><span data-stu-id="cd460-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="cd460-110">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="cd460-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="cd460-111">Als zusätzliche Schutzvorrichtung, kann ein Client den Dienst authentifizieren, durch Angeben der erwarteten *Identität* des Diensts.</span><span class="sxs-lookup"><span data-stu-id="cd460-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="cd460-112">Wenn die erwartete Identität und die vom Dienst zurückgegebene Identität nicht übereinstimmen, schlägt die Authentifizierung fehl.</span><span class="sxs-lookup"><span data-stu-id="cd460-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="cd460-113">Sicherheitsaushandlung und Timeouts</span><span class="sxs-lookup"><span data-stu-id="cd460-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="cd460-114">Beschreibt die Verwendung der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft in der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="cd460-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="cd460-115">Debuggen von Windows-Authentifizierungsfehlern</span><span class="sxs-lookup"><span data-stu-id="cd460-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="cd460-116">Der Fokus liegt auf allgemeinen Problemen, die bei der Verwendung der Windows-Authentifizierung auftreten.</span><span class="sxs-lookup"><span data-stu-id="cd460-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="cd460-117">Verweis</span><span class="sxs-lookup"><span data-stu-id="cd460-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="cd460-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="cd460-118">Related Sections</span></span>  
 [<span data-ttu-id="cd460-119">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="cd460-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="cd460-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cd460-120">See Also</span></span>  
 [<span data-ttu-id="cd460-121">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="cd460-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="cd460-122">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="cd460-122">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
