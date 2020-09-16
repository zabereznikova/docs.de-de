---
title: Authentifizierung in WCF
description: Erfahren Sie mehr über verschiedene Mechanismen in WCF, die Authentifizierung bereitstellen, z. b. die Windows-Authentifizierung, X. 509-Zertifikate sowie Benutzername und Kennwort.
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: 414353b360992abea69d47de9efb22c3c77f4bf6
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558276"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="6f985-103">Authentifizierung in WCF</span><span class="sxs-lookup"><span data-stu-id="6f985-103">Authentication in WCF</span></span>
<span data-ttu-id="6f985-104">In den folgenden Themen werden verschiedene Mechanismen in Windows Communication Foundation (WCF) gezeigt, die die Authentifizierung bereitstellen, z. b. die Windows-Authentifizierung, X. 509-Zertifikate sowie Benutzername und Kenn Wörter.</span><span class="sxs-lookup"><span data-stu-id="6f985-104">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f985-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="6f985-105">In This Section</span></span>  
 [<span data-ttu-id="6f985-106">Vorgehensweise: Verwenden des ASP.NET-Mitgliedschaftsanbieters</span><span class="sxs-lookup"><span data-stu-id="6f985-106">How to: Use the ASP.NET Membership Provider</span></span>](how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="6f985-107">Zu den ASP.NET-Funktionen gehören eine Mitgliedschaft und ein Rollenanbieter, eine Datenbank, um Benutzernamen/Kennwort-Paare für die Authentifizierung zu speichern, sowie Benutzerrollen zur Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="6f985-107">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="6f985-108">In diesem Thema wird erläutert, wie WCF-Dienste dieselbe Datenbank verwenden können, um Benutzer zu authentifizieren und zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="6f985-108">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="6f985-109">Vorgehensweise: Verwenden eines benutzerdefinierten Benutzernamens und eines Kennwort-Validierungssteuerelements</span><span class="sxs-lookup"><span data-stu-id="6f985-109">How to: Use a Custom User Name and Password Validator</span></span>](how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="6f985-110">Veranschaulicht, wie ein benutzerdefiniertes Benutzernamen- und Kennwort-Validierungssteuerelement integriert wird.</span><span class="sxs-lookup"><span data-stu-id="6f985-110">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="6f985-111">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="6f985-111">Service Identity and Authentication</span></span>](service-identity-and-authentication.md)  
 <span data-ttu-id="6f985-112">Als zusätzliche Schutzmaßnahme kann ein Client den Dienst authentifizieren, indem er die erwartete *Identität* des Dienstanbieter angibt.</span><span class="sxs-lookup"><span data-stu-id="6f985-112">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="6f985-113">Wenn die erwartete Identität und die vom Dienst zurückgegebene Identität nicht übereinstimmen, schlägt die Authentifizierung fehl.</span><span class="sxs-lookup"><span data-stu-id="6f985-113">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="6f985-114">Sicherheitsaushandlung und Timeouts</span><span class="sxs-lookup"><span data-stu-id="6f985-114">Security Negotiation and Timeouts</span></span>](security-negotiation-and-timeouts.md)  
 <span data-ttu-id="6f985-115">Beschreibt die Verwendung der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A>-Eigenschaft in der <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6f985-115">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="6f985-116">Debuggen von Windows-Authentifizierungsfehlern</span><span class="sxs-lookup"><span data-stu-id="6f985-116">Debugging Windows Authentication Errors</span></span>](debugging-windows-authentication-errors.md)  
 <span data-ttu-id="6f985-117">Der Fokus liegt auf allgemeinen Problemen, die bei der Verwendung der Windows-Authentifizierung auftreten.</span><span class="sxs-lookup"><span data-stu-id="6f985-117">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="6f985-118">Referenz</span><span class="sxs-lookup"><span data-stu-id="6f985-118">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="6f985-119">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="6f985-119">Related Sections</span></span>  
 [<span data-ttu-id="6f985-120">Häufige Sicherheitsszenarien</span><span class="sxs-lookup"><span data-stu-id="6f985-120">Common Security Scenarios</span></span>](common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="6f985-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f985-121">See also</span></span>

- [<span data-ttu-id="6f985-122">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="6f985-122">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="6f985-123">[Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="6f985-123">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
