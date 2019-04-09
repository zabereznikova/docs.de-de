---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: 51555e3357b8c33a53261c4894d97798b0a05656
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102933"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="f6a9a-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="f6a9a-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="f6a9a-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="f6a9a-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f6a9a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6a9a-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f6a9a-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f6a9a-105">Methods</span></span>  
 <span data-ttu-id="f6a9a-106">Die ServiceAuthorizationBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="f6a9a-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f6a9a-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f6a9a-107">Properties</span></span>  
 <span data-ttu-id="f6a9a-108">Die ServiceAuthorizationBehavior-Klasse verfügt über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f6a9a-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="f6a9a-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="f6a9a-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="f6a9a-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="f6a9a-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="f6a9a-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f6a9a-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6a9a-112">Ein Wert, der kontrolliert, ob der Dienst versucht, mithilfe der Anmeldeinformationen der eingehenden Nachricht einen Identitätswechsel durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f6a9a-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="f6a9a-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="f6a9a-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="f6a9a-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f6a9a-114">Data type: string</span></span>  
  
 <span data-ttu-id="f6a9a-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f6a9a-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6a9a-116">Ruft den Prinzipal ab, mit dem Vorgänge auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f6a9a-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="f6a9a-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="f6a9a-117">RoleProvider</span></span>  
 <span data-ttu-id="f6a9a-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f6a9a-118">Data type: string</span></span>  
  
 <span data-ttu-id="f6a9a-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f6a9a-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6a9a-120">Der Name des ASP.NET-Rollenanbieters.</span><span class="sxs-lookup"><span data-stu-id="f6a9a-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="f6a9a-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="f6a9a-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="f6a9a-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="f6a9a-122">Data type: string</span></span>  
  
 <span data-ttu-id="f6a9a-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f6a9a-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f6a9a-124">Der Autorisierungs-Manager für die benutzerdefinierte Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="f6a9a-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f6a9a-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f6a9a-125">Requirements</span></span>  
  
|<span data-ttu-id="f6a9a-126">MOF</span><span class="sxs-lookup"><span data-stu-id="f6a9a-126">MOF</span></span>|<span data-ttu-id="f6a9a-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f6a9a-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f6a9a-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="f6a9a-128">Namespace</span></span>|<span data-ttu-id="f6a9a-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f6a9a-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f6a9a-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6a9a-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
