---
title: ServiceAppDomain
ms.date: 03/30/2017
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
ms.openlocfilehash: aef0a0da9d107b92d9d3017968d5554205a6fd71
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33485667"
---
# <a name="serviceappdomain"></a><span data-ttu-id="c9638-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="c9638-102">ServiceAppDomain</span></span>
<span data-ttu-id="c9638-103">Ordnet einer Anwendungsdomäne einen Dienst zu.</span><span class="sxs-lookup"><span data-stu-id="c9638-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9638-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c9638-104">Syntax</span></span>  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c9638-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="c9638-105">Methods</span></span>  
 <span data-ttu-id="c9638-106">Mit der ServiceAppDomain-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="c9638-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c9638-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="c9638-107">Properties</span></span>  
 <span data-ttu-id="c9638-108">Die ServiceAppDomain-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="c9638-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="c9638-109">ref</span><span class="sxs-lookup"><span data-stu-id="c9638-109">ref</span></span>  
 <span data-ttu-id="c9638-110">Datentyp: Dienst</span><span class="sxs-lookup"><span data-stu-id="c9638-110">Data type: Service</span></span>  
<span data-ttu-id="c9638-111">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="c9638-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="c9638-112">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c9638-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9638-113">Der Dienst dieser Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="c9638-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="c9638-114">ref</span><span class="sxs-lookup"><span data-stu-id="c9638-114">ref</span></span>  
 <span data-ttu-id="c9638-115">Datentyp: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="c9638-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="c9638-116">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="c9638-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="c9638-117">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="c9638-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c9638-118">Enthält Eigenschaften der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="c9638-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9638-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c9638-119">Requirements</span></span>  
  
|<span data-ttu-id="c9638-120">MOF</span><span class="sxs-lookup"><span data-stu-id="c9638-120">MOF</span></span>|<span data-ttu-id="c9638-121">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c9638-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c9638-122">Namespace</span><span class="sxs-lookup"><span data-stu-id="c9638-122">Namespace</span></span>|<span data-ttu-id="c9638-123">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c9638-123">Defined in root\ServiceModel</span></span>|
