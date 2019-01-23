---
title: Authentifizierung in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: 22bfd7edf0ca0e9eb57e63c168c783f25782d607
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523921"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="79858-102">Authentifizierung in WCF</span><span class="sxs-lookup"><span data-stu-id="79858-102">Authentication in WCF</span></span>
<span data-ttu-id="79858-103">Die folgenden Themen zeigen eine Reihe von verschiedenen Mechanismen in Windows Communication Foundation (WCF), die Authentifizierung, z. B. bereitstellen, Windows-Authentifizierung, x. 509-Zertifikate und Benutzernamen und Kennwörter.</span><span class="sxs-lookup"><span data-stu-id="79858-103">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="79858-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="79858-104">In This Section</span></span>  
 [<span data-ttu-id="79858-105">Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="79858-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="79858-106">Zu den ASP.NET-Funktionen gehören eine Mitgliedschaft und ein Rollenanbieter, eine Datenbank, um Benutzernamen/Kennwort-Paare für die Authentifizierung zu speichern, sowie Benutzerrollen zur Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="79858-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="79858-107">In diesem Thema wird erläutert, wie WCF-Dienste verwenden können die gleiche Datenbank zu authentifizieren und Autorisieren von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="79858-107">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="79858-108">Vorgehensweise: Verwenden Sie einen benutzerdefinierten Benutzernamen und das Kennwort-Validierungssteuerelement</span><span class="sxs-lookup"><span data-stu-id="79858-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="79858-109">Veranschaulicht, wie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement integriert wird.</span><span class="sxs-lookup"><span data-stu-id="79858-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="79858-110">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="79858-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="79858-111">Als zusätzliche Schutzvorrichtung, kann ein Client den Dienst authentifizieren, durch die Angabe der erwarteten *Identität* des Diensts.</span><span class="sxs-lookup"><span data-stu-id="79858-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="79858-112">Wenn die erwartete Identität und die vom Dienst zurückgegebene Identität nicht übereinstimmen, schlägt die Authentifizierung fehl.</span><span class="sxs-lookup"><span data-stu-id="79858-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="79858-113">Sicherheitsaushandlung und Timeouts</span><span class="sxs-lookup"><span data-stu-id="79858-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="79858-114">Beschreibt die Verwendung der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft in der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="79858-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="79858-115">Debuggen von Windows-Authentifizierungsfehlern</span><span class="sxs-lookup"><span data-stu-id="79858-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="79858-116">Der Fokus liegt auf allgemeinen Problemen, die bei der Verwendung der Windows-Authentifizierung auftreten.</span><span class="sxs-lookup"><span data-stu-id="79858-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="79858-117">Referenz</span><span class="sxs-lookup"><span data-stu-id="79858-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="79858-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="79858-118">Related Sections</span></span>  
 [<span data-ttu-id="79858-119">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="79858-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="79858-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79858-120">See also</span></span>
- [<span data-ttu-id="79858-121">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="79858-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="79858-122">Sicherheitsmodell für Windows Server AppFabric</span><span class="sxs-lookup"><span data-stu-id="79858-122">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
