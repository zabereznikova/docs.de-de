---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: 58eb2a9fd9017aaf9966644180936f5871e086d1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54613895"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="9cf5a-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="9cf5a-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="9cf5a-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="9cf5a-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cf5a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9cf5a-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="9cf5a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="9cf5a-105">Methods</span></span>  
 <span data-ttu-id="9cf5a-106">Die ServiceAuthorizationBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="9cf5a-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="9cf5a-107">Properties</span></span>  
 <span data-ttu-id="9cf5a-108">Die ServiceAuthorizationBehavior-Klasse verfügt über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="9cf5a-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="9cf5a-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="9cf5a-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="9cf5a-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="9cf5a-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="9cf5a-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9cf5a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9cf5a-112">Ein Wert, der kontrolliert, ob der Dienst versucht, mithilfe der Anmeldeinformationen der eingehenden Nachricht einen Identitätswechsel durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="9cf5a-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="9cf5a-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="9cf5a-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9cf5a-114">Data type: string</span></span>  
  
 <span data-ttu-id="9cf5a-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9cf5a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9cf5a-116">Ruft den Prinzipal ab, mit dem Vorgänge auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="9cf5a-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="9cf5a-117">RoleProvider</span></span>  
 <span data-ttu-id="9cf5a-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9cf5a-118">Data type: string</span></span>  
  
 <span data-ttu-id="9cf5a-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9cf5a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9cf5a-120">Der Name des ASP.NET-Rollenanbieters.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="9cf5a-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="9cf5a-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="9cf5a-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="9cf5a-122">Data type: string</span></span>  
  
 <span data-ttu-id="9cf5a-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="9cf5a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="9cf5a-124">Der Autorisierungs-Manager für die benutzerdefinierte Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cf5a-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9cf5a-125">Requirements</span></span>  
  
|<span data-ttu-id="9cf5a-126">MOF</span><span class="sxs-lookup"><span data-stu-id="9cf5a-126">MOF</span></span>|<span data-ttu-id="9cf5a-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="9cf5a-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="9cf5a-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="9cf5a-128">Namespace</span></span>|<span data-ttu-id="9cf5a-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="9cf5a-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9cf5a-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9cf5a-130">See also</span></span>
- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
