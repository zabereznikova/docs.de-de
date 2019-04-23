---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: 51555e3357b8c33a53261c4894d97798b0a05656
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2019
ms.locfileid: "59972835"
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="34f40-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="34f40-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="34f40-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="34f40-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34f40-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34f40-104">Syntax</span></span>  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="34f40-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="34f40-105">Methods</span></span>  
 <span data-ttu-id="34f40-106">Die ServiceAuthorizationBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="34f40-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="34f40-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="34f40-107">Properties</span></span>  
 <span data-ttu-id="34f40-108">Die ServiceAuthorizationBehavior-Klasse verfügt über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="34f40-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="34f40-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="34f40-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="34f40-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="34f40-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="34f40-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="34f40-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="34f40-112">Ein Wert, der kontrolliert, ob der Dienst versucht, mithilfe der Anmeldeinformationen der eingehenden Nachricht einen Identitätswechsel durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="34f40-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="34f40-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="34f40-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="34f40-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="34f40-114">Data type: string</span></span>  
  
 <span data-ttu-id="34f40-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="34f40-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="34f40-116">Ruft den Prinzipal ab, mit dem Vorgänge auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="34f40-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="34f40-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="34f40-117">RoleProvider</span></span>  
 <span data-ttu-id="34f40-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="34f40-118">Data type: string</span></span>  
  
 <span data-ttu-id="34f40-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="34f40-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="34f40-120">Der Name des ASP.NET-Rollenanbieters.</span><span class="sxs-lookup"><span data-stu-id="34f40-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="34f40-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="34f40-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="34f40-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="34f40-122">Data type: string</span></span>  
  
 <span data-ttu-id="34f40-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="34f40-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="34f40-124">Der Autorisierungs-Manager für die benutzerdefinierte Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="34f40-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34f40-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34f40-125">Requirements</span></span>  
  
|<span data-ttu-id="34f40-126">MOF</span><span class="sxs-lookup"><span data-stu-id="34f40-126">MOF</span></span>|<span data-ttu-id="34f40-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="34f40-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="34f40-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="34f40-128">Namespace</span></span>|<span data-ttu-id="34f40-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="34f40-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="34f40-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34f40-130">See also</span></span>

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
