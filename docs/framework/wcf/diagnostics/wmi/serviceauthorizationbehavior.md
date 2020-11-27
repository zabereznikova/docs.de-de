---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: d3625865484568746888ef0638d9a8501e610bef
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96273203"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="b1a60-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="b1a60-102">ServiceAuthorizationBehavior</span></span>

<span data-ttu-id="b1a60-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="b1a60-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1a60-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1a60-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="b1a60-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="b1a60-105">Methods</span></span>  

 <span data-ttu-id="b1a60-106">Die ServiceAuthorizationBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="b1a60-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="b1a60-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="b1a60-107">Properties</span></span>  

 <span data-ttu-id="b1a60-108">Die ServiceAuthorizationBehavior-Klasse verfügt über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="b1a60-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="b1a60-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="b1a60-109">ImpersonateCallerForAllOperations</span></span>  

 <span data-ttu-id="b1a60-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="b1a60-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="b1a60-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b1a60-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1a60-112">Ein Wert, der kontrolliert, ob der Dienst versucht, mithilfe der Anmeldeinformationen der eingehenden Nachricht einen Identitätswechsel durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="b1a60-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="b1a60-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="b1a60-113">PrincipalPermissionMode</span></span>  

 <span data-ttu-id="b1a60-114">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="b1a60-114">Data type: string</span></span>  
  
 <span data-ttu-id="b1a60-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b1a60-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1a60-116">Ruft den Prinzipal ab, mit dem Vorgänge auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b1a60-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="b1a60-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="b1a60-117">RoleProvider</span></span>  

 <span data-ttu-id="b1a60-118">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="b1a60-118">Data type: string</span></span>  
  
 <span data-ttu-id="b1a60-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b1a60-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1a60-120">Der Name des ASP.NET-Rollenanbieters.</span><span class="sxs-lookup"><span data-stu-id="b1a60-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="b1a60-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="b1a60-121">ServiceAuthorizationManager</span></span>  

 <span data-ttu-id="b1a60-122">Datentyp: String</span><span class="sxs-lookup"><span data-stu-id="b1a60-122">Data type: string</span></span>  
  
 <span data-ttu-id="b1a60-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="b1a60-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="b1a60-124">Der Autorisierungs-Manager für die benutzerdefinierte Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="b1a60-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1a60-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b1a60-125">Requirements</span></span>  
  
|<span data-ttu-id="b1a60-126">MOF</span><span class="sxs-lookup"><span data-stu-id="b1a60-126">MOF</span></span>|<span data-ttu-id="b1a60-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="b1a60-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="b1a60-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="b1a60-128">Namespace</span></span>|<span data-ttu-id="b1a60-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="b1a60-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="b1a60-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1a60-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
