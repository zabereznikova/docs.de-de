---
title: Autorisierung in WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 67da01508fbb8f14b6405b79445bdef297e63288
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96247485"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="af9eb-102">Autorisierung in WCF</span><span class="sxs-lookup"><span data-stu-id="af9eb-102">Authorization in WCF</span></span>

<span data-ttu-id="af9eb-103">Autorisierung ist der Prozess, Zugriff und Rechte für Ressourcen zu steuern, z. B. Dienste oder Dateien.</span><span class="sxs-lookup"><span data-stu-id="af9eb-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="af9eb-104">In den Themen in diesem Abschnitt wird erläutert, wie Sie diese grundlegende Aufgabe in Windows Communication Foundation (WCF) auf unterschiedlichste Weise ausführen.</span><span class="sxs-lookup"><span data-stu-id="af9eb-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="af9eb-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="af9eb-105">In This Section</span></span>  

 [<span data-ttu-id="af9eb-106">Zugriffssteuerungsmechanismen</span><span class="sxs-lookup"><span data-stu-id="af9eb-106">Access Control Mechanisms</span></span>](access-control-mechanisms.md)  
 <span data-ttu-id="af9eb-107">Bietet eine kurze Übersicht über die Autorisierungs Mechanismen in WCF und empfohlene Verwendungsmöglichkeiten.</span><span class="sxs-lookup"><span data-stu-id="af9eb-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="af9eb-108">Vorgehensweise: Einschränken des Zugriffs mit der PrincipalPermissionAttribute-Klasse</span><span class="sxs-lookup"><span data-stu-id="af9eb-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="af9eb-109">Zeigt den Prozess zum Zugriff auf einen Dienst mit dem <xref:System.Security.Permissions.PrincipalPermissionAttribute> an.</span><span class="sxs-lookup"><span data-stu-id="af9eb-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="af9eb-110">Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="af9eb-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="af9eb-111">Führt Sie durch die Konfiguration eines Dienstanbieters, um die Verwendung der Rollen Anbieter Funktion von ASP.net zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="af9eb-111">Walks through the configuration of a service to enable it to use the role provider feature of ASP.NET.</span></span>  
  
 [<span data-ttu-id="af9eb-112">Vorgehensweise: Verwenden des Rollenanbieters für den ASP.NET-Autorisierungs-Manager bei einem Dienst</span><span class="sxs-lookup"><span data-stu-id="af9eb-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 <span data-ttu-id="af9eb-113">ASP.net kann den Autorisierungs-Manager verwenden, um die Autorisierung für eine Website zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="af9eb-113">ASP.NET can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="af9eb-114">WCF kann die Kombination von ASP.net/Authorization Manager auch für die Autorisierung von Clients nutzen.</span><span class="sxs-lookup"><span data-stu-id="af9eb-114">WCF can similarly leverage the ASP.NET/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="af9eb-115">Verwalten von Ansprüchen und Autorisierung mit dem Identitätsmodell</span><span class="sxs-lookup"><span data-stu-id="af9eb-115">Managing Claims and Authorization with the Identity Model</span></span>](managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="af9eb-116">Erläutert die Grundlagen des Verwendens der Identitätsmodellinfrastruktur für auf Ansprüche basierende Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="af9eb-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="af9eb-117">Delegierung und Identitätswechsel</span><span class="sxs-lookup"><span data-stu-id="af9eb-117">Delegation and Impersonation</span></span>](delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="af9eb-118">Erläutert den Unterschied zwischen Delegierung und Identitätswechsel.</span><span class="sxs-lookup"><span data-stu-id="af9eb-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="af9eb-119">Referenz</span><span class="sxs-lookup"><span data-stu-id="af9eb-119">Reference</span></span>  

 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="af9eb-120">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="af9eb-120">Related Sections</span></span>  

 [<span data-ttu-id="af9eb-121">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="af9eb-121">Authentication</span></span>](authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="af9eb-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="af9eb-122">See also</span></span>

- [<span data-ttu-id="af9eb-123">Sicherheitsübersicht</span><span class="sxs-lookup"><span data-stu-id="af9eb-123">Security Overview</span></span>](security-overview.md)
- <span data-ttu-id="af9eb-124">[Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="af9eb-124">[Security Model for Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
