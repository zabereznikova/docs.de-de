---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: c916d0820a1eae333384deab7b0619abfbdc8167
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2018
ms.locfileid: "49415379"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="7b8cd-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="7b8cd-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="7b8cd-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="7b8cd-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b8cd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7b8cd-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="7b8cd-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="7b8cd-105">Methods</span></span>  
 <span data-ttu-id="7b8cd-106">Die ServiceAuthorizationBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="7b8cd-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="7b8cd-107">Properties</span></span>  
 <span data-ttu-id="7b8cd-108">Die ServiceAuthorizationBehavior-Klasse verfügt über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="7b8cd-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="7b8cd-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="7b8cd-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="7b8cd-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="7b8cd-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="7b8cd-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7b8cd-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b8cd-112">Ein Wert, der kontrolliert, ob der Dienst versucht, mithilfe der Anmeldeinformationen der eingehenden Nachricht einen Identitätswechsel durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="7b8cd-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="7b8cd-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="7b8cd-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7b8cd-114">Data type: string</span></span>  
  
 <span data-ttu-id="7b8cd-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7b8cd-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b8cd-116">Ruft den Prinzipal ab, mit dem Vorgänge auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="7b8cd-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="7b8cd-117">RoleProvider</span></span>  
 <span data-ttu-id="7b8cd-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7b8cd-118">Data type: string</span></span>  
  
 <span data-ttu-id="7b8cd-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7b8cd-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b8cd-120">Der Name des ASP.NET-Rollenanbieters.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="7b8cd-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="7b8cd-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="7b8cd-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="7b8cd-122">Data type: string</span></span>  
  
 <span data-ttu-id="7b8cd-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="7b8cd-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b8cd-124">Der Autorisierungs-Manager für die benutzerdefinierte Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b8cd-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7b8cd-125">Requirements</span></span>  
  
|<span data-ttu-id="7b8cd-126">MOF</span><span class="sxs-lookup"><span data-stu-id="7b8cd-126">MOF</span></span>|<span data-ttu-id="7b8cd-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="7b8cd-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7b8cd-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="7b8cd-128">Namespace</span></span>|<span data-ttu-id="7b8cd-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="7b8cd-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="7b8cd-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b8cd-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
