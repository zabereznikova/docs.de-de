---
title: ServiceAuthorizationBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: eb02a02557a88bf53ca1a8e5b30fe66d6995e545
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="serviceauthorizationbehavior"></a><span data-ttu-id="94897-102">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="94897-102">ServiceAuthorizationBehavior</span></span>
<span data-ttu-id="94897-103">ServiceAuthorizationBehavior</span><span class="sxs-lookup"><span data-stu-id="94897-103">ServiceAuthorizationBehavior</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94897-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94897-104">Syntax</span></span>  
  
```  
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="94897-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="94897-105">Methods</span></span>  
 <span data-ttu-id="94897-106">Die ServiceAuthorizationBehavior-Klasse definiert keine Methoden.</span><span class="sxs-lookup"><span data-stu-id="94897-106">The ServiceAuthorizationBehavior class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="94897-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="94897-107">Properties</span></span>  
 <span data-ttu-id="94897-108">Die ServiceAuthorizationBehavior-Klasse verfügt über folgende Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="94897-108">The ServiceAuthorizationBehavior class has the following properties:</span></span>  
  
### <a name="impersonatecallerforalloperations"></a><span data-ttu-id="94897-109">ImpersonateCallerForAllOperations</span><span class="sxs-lookup"><span data-stu-id="94897-109">ImpersonateCallerForAllOperations</span></span>  
 <span data-ttu-id="94897-110">Datentyp: Boolesch</span><span class="sxs-lookup"><span data-stu-id="94897-110">Data type: boolean</span></span>  
  
 <span data-ttu-id="94897-111">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="94897-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94897-112">Ein Wert, der kontrolliert, ob der Dienst versucht, mithilfe der Anmeldeinformationen der eingehenden Nachricht einen Identitätswechsel durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="94897-112">A value that controls whether the service attempts to impersonate using the credentials provided by the incoming message.</span></span>  
  
### <a name="principalpermissionmode"></a><span data-ttu-id="94897-113">PrincipalPermissionMode</span><span class="sxs-lookup"><span data-stu-id="94897-113">PrincipalPermissionMode</span></span>  
 <span data-ttu-id="94897-114">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="94897-114">Data type: string</span></span>  
  
 <span data-ttu-id="94897-115">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="94897-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94897-116">Ruft den Prinzipal ab, mit dem Vorgänge auf dem Server ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="94897-116">The principal used to carry out operations on the server.</span></span>  
  
### <a name="roleprovider"></a><span data-ttu-id="94897-117">RoleProvider</span><span class="sxs-lookup"><span data-stu-id="94897-117">RoleProvider</span></span>  
 <span data-ttu-id="94897-118">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="94897-118">Data type: string</span></span>  
  
 <span data-ttu-id="94897-119">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="94897-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94897-120">Der Name des ASP.NET-Rollenanbieters.</span><span class="sxs-lookup"><span data-stu-id="94897-120">The name of the ASP.NET role provider.</span></span>  
  
### <a name="serviceauthorizationmanager"></a><span data-ttu-id="94897-121">ServiceAuthorizationManager</span><span class="sxs-lookup"><span data-stu-id="94897-121">ServiceAuthorizationManager</span></span>  
 <span data-ttu-id="94897-122">Datentyp: string (Zeichenfolge)</span><span class="sxs-lookup"><span data-stu-id="94897-122">Data type: string</span></span>  
  
 <span data-ttu-id="94897-123">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="94897-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="94897-124">Der Autorisierungs-Manager für die benutzerdefinierte Autorisierung.</span><span class="sxs-lookup"><span data-stu-id="94897-124">The authorization manager used for custom authorization.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94897-125">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94897-125">Requirements</span></span>  
  
|<span data-ttu-id="94897-126">MOF</span><span class="sxs-lookup"><span data-stu-id="94897-126">MOF</span></span>|<span data-ttu-id="94897-127">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="94897-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="94897-128">Namespace</span><span class="sxs-lookup"><span data-stu-id="94897-128">Namespace</span></span>|<span data-ttu-id="94897-129">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="94897-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="94897-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94897-130">See Also</span></span>  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
