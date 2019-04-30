---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: 05be495dbfe87e7dd14b0cfbb38b30c6f8278e6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61957072"
---
# <a name="serviceappdomain"></a><span data-ttu-id="f8a36-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="f8a36-102">ServiceAppDomain</span></span>
<span data-ttu-id="f8a36-103">Ordnet einer Anwendungsdomäne einen Dienst zu.</span><span class="sxs-lookup"><span data-stu-id="f8a36-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8a36-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f8a36-104">Syntax</span></span>  
  
```csharp
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="f8a36-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="f8a36-105">Methods</span></span>  
 <span data-ttu-id="f8a36-106">Mit der ServiceAppDomain-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="f8a36-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f8a36-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="f8a36-107">Properties</span></span>  
 <span data-ttu-id="f8a36-108">Die ServiceAppDomain-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="f8a36-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="f8a36-109">ref</span><span class="sxs-lookup"><span data-stu-id="f8a36-109">ref</span></span>  
 <span data-ttu-id="f8a36-110">Datentyp: Dienst</span><span class="sxs-lookup"><span data-stu-id="f8a36-110">Data type: Service</span></span>  
<span data-ttu-id="f8a36-111">Qualifizierer: Key</span><span class="sxs-lookup"><span data-stu-id="f8a36-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="f8a36-112">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f8a36-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f8a36-113">Der Dienst dieser Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="f8a36-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="f8a36-114">ref</span><span class="sxs-lookup"><span data-stu-id="f8a36-114">ref</span></span>  
 <span data-ttu-id="f8a36-115">Datentyp: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="f8a36-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="f8a36-116">Qualifizierer: Key</span><span class="sxs-lookup"><span data-stu-id="f8a36-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="f8a36-117">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="f8a36-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f8a36-118">Enthält Eigenschaften der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="f8a36-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8a36-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f8a36-119">Requirements</span></span>  
  
|<span data-ttu-id="f8a36-120">MOF</span><span class="sxs-lookup"><span data-stu-id="f8a36-120">MOF</span></span>|<span data-ttu-id="f8a36-121">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f8a36-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f8a36-122">Namespace</span><span class="sxs-lookup"><span data-stu-id="f8a36-122">Namespace</span></span>|<span data-ttu-id="f8a36-123">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f8a36-123">Defined in root\ServiceModel</span></span>|
