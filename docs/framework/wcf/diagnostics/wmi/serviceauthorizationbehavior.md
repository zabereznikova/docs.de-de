---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: e03f83927ec5aef7f916b2262c9c8cff1db68ac9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33486472"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="eee70-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="eee70-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="eee70-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="eee70-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eee70-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eee70-104">Syntax</span></span>  
  
```  
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="eee70-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="eee70-105">Methods</span></span>  
 <span data-ttu-id="eee70-106">Die ServiceAuthorizationBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="eee70-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="eee70-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="eee70-107">Properties</span></span>  
 <span data-ttu-id="eee70-108">Die ServiceAuthorizationBehavior-Klasse verfügt über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="eee70-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="eee70-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="eee70-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="eee70-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="eee70-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="eee70-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="eee70-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eee70-112">Ein Wert, der kontrolliert, ob der Dienst versucht, mithilfe der Anmeldeinformationen der eingehenden Nachricht einen Identitätswechsel durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="eee70-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="eee70-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="eee70-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="eee70-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="eee70-114">Data type: string</span></span>  
  
 <span data-ttu-id="eee70-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="eee70-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eee70-116">Ruft den Prinzipal ab, mit dem Vorgänge auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="eee70-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="eee70-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="eee70-117">RoleProvider</span></span>  
 <span data-ttu-id="eee70-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="eee70-118">Data type: string</span></span>  
  
 <span data-ttu-id="eee70-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="eee70-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eee70-120">Der Name des ASP.NET-Rollenanbieters.</span><span class="sxs-lookup"><span data-stu-id="eee70-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="eee70-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="eee70-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="eee70-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="eee70-122">Data type: string</span></span>  
  
 <span data-ttu-id="eee70-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="eee70-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="eee70-124">Der Autorisierungs-Manager für die benutzerdefinierte Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="eee70-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eee70-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eee70-125">Requirements</span></span>  
  
|<span data-ttu-id="eee70-126">MOF</span><span class="sxs-lookup"><span data-stu-id="eee70-126">MOF</span></span>|<span data-ttu-id="eee70-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="eee70-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="eee70-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="eee70-128">Namespace</span></span>|<span data-ttu-id="eee70-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="eee70-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="eee70-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eee70-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
