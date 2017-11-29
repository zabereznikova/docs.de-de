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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6fbd4a322153bd9f560b6c039f586100770a0216
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="16027-102">Authentifizierung in WCF</span><span class="sxs-lookup"><span data-stu-id="16027-102">Authentication in WCF</span></span>
<span data-ttu-id="16027-103">Die folgenden Themen beschreiben eine Anzahl unterschiedlicher Mechanismen in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], die eine Authentifizierung ermöglichen, z. B. die Windows-Authentifizierung, X.509-Zertifikate sowie Benutzername und Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="16027-103">The following topics show a number of different mechanisms in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16027-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="16027-104">In This Section</span></span>  
 [<span data-ttu-id="16027-105">Vorgehensweise: Verwenden Sie den ASP.NET-Mitgliedschaftsanbieter</span><span class="sxs-lookup"><span data-stu-id="16027-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="16027-106">Zu den ASP.NET-Funktionen gehören eine Mitgliedschaft und ein Rollenanbieter, eine Datenbank, um Benutzernamen/Kennwort-Paare für die Authentifizierung zu speichern, sowie Benutzerrollen zur Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="16027-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="16027-107">In diesem Thema wird erläutert, wie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste die gleiche Datenbank verwenden können, um Benutzer zu authentifizieren und zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="16027-107">This topic explains how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="16027-108">Vorgehensweise: Verwenden Sie einen benutzerdefinierten Benutzernamen und Kennwort-Validierungssteuerelement</span><span class="sxs-lookup"><span data-stu-id="16027-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="16027-109">Veranschaulicht, wie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement integriert wird.</span><span class="sxs-lookup"><span data-stu-id="16027-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="16027-110">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="16027-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="16027-111">Als zusätzliche Schutzvorrichtung, kann ein Client den Dienst authentifizieren, durch Angeben der erwarteten *Identität* des Diensts.</span><span class="sxs-lookup"><span data-stu-id="16027-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="16027-112">Wenn die erwartete Identität und die vom Dienst zurückgegebene Identität nicht übereinstimmen, schlägt die Authentifizierung fehl.</span><span class="sxs-lookup"><span data-stu-id="16027-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="16027-113">Sicherheitsaushandlung und Timeouts</span><span class="sxs-lookup"><span data-stu-id="16027-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="16027-114">Beschreibt die Verwendung der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft in der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="16027-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="16027-115">Debuggen von Windows-Authentifizierungsfehlern</span><span class="sxs-lookup"><span data-stu-id="16027-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="16027-116">Der Fokus liegt auf allgemeinen Problemen, die bei der Verwendung der Windows-Authentifizierung auftreten.</span><span class="sxs-lookup"><span data-stu-id="16027-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="16027-117">Verweis</span><span class="sxs-lookup"><span data-stu-id="16027-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="16027-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="16027-118">Related Sections</span></span>  
 [<span data-ttu-id="16027-119">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="16027-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="16027-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16027-120">See Also</span></span>  
 [<span data-ttu-id="16027-121">Sicherheit (Übersicht)</span><span class="sxs-lookup"><span data-stu-id="16027-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="16027-122">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="16027-122">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
