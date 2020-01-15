---
title: Authentifizierung in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: abe7aff025207ad8bdf8657daba3584e6a1b2e7f
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964695"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="62d62-102">Authentifizierung in WCF</span><span class="sxs-lookup"><span data-stu-id="62d62-102">Authentication in WCF</span></span>
<span data-ttu-id="62d62-103">In den folgenden Themen werden verschiedene Mechanismen in Windows Communication Foundation (WCF) gezeigt, die die Authentifizierung bereitstellen, z. b. die Windows-Authentifizierung, X. 509-Zertifikate sowie Benutzername und Kenn Wörter.</span><span class="sxs-lookup"><span data-stu-id="62d62-103">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="62d62-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="62d62-104">In This Section</span></span>  
 [<span data-ttu-id="62d62-105">Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="62d62-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="62d62-106">Zu den ASP.NET-Funktionen gehören eine Mitgliedschaft und ein Rollenanbieter, eine Datenbank, um Benutzernamen/Kennwort-Paare für die Authentifizierung zu speichern, sowie Benutzerrollen zur Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="62d62-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="62d62-107">In diesem Thema wird erläutert, wie WCF-Dienste dieselbe Datenbank verwenden können, um Benutzer zu authentifizieren und zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="62d62-107">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="62d62-108">Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungssteuerelements</span><span class="sxs-lookup"><span data-stu-id="62d62-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="62d62-109">Veranschaulicht, wie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement integriert wird.</span><span class="sxs-lookup"><span data-stu-id="62d62-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="62d62-110">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="62d62-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="62d62-111">Als zusätzliche Schutzmaßnahme kann ein Client den Dienst authentifizieren, indem er die erwartete *Identität* des Dienstanbieter angibt.</span><span class="sxs-lookup"><span data-stu-id="62d62-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="62d62-112">Wenn die erwartete Identität und die vom Dienst zurückgegebene Identität nicht übereinstimmen, schlägt die Authentifizierung fehl.</span><span class="sxs-lookup"><span data-stu-id="62d62-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="62d62-113">Sicherheitsaushandlung und Timeouts</span><span class="sxs-lookup"><span data-stu-id="62d62-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="62d62-114">Beschreibt die Verwendung der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft in der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="62d62-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="62d62-115">Debuggen von Windows-Authentifizierungsfehlern</span><span class="sxs-lookup"><span data-stu-id="62d62-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="62d62-116">Der Fokus liegt auf allgemeinen Problemen, die bei der Verwendung der Windows-Authentifizierung auftreten.</span><span class="sxs-lookup"><span data-stu-id="62d62-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="62d62-117">Referenz</span><span class="sxs-lookup"><span data-stu-id="62d62-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="62d62-118">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="62d62-118">Related Sections</span></span>  
 [<span data-ttu-id="62d62-119">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="62d62-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="62d62-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62d62-120">See also</span></span>

- [<span data-ttu-id="62d62-121">Übersicht über die Sicherheit</span><span class="sxs-lookup"><span data-stu-id="62d62-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="62d62-122">[Sicherheitsmodell für Windows Server-App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="62d62-122">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
