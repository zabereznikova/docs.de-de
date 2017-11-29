---
title: ServiceAppDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f28e5186-a66d-46c1-abe9-b50e07f8cb4f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 36048f56c3b54447a112e6f0a457624062ce965a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="serviceappdomain"></a><span data-ttu-id="5e02f-102">ServiceAppDomain</span><span class="sxs-lookup"><span data-stu-id="5e02f-102">ServiceAppDomain</span></span>
<span data-ttu-id="5e02f-103">Ordnet einer Anwendungsdomäne einen Dienst zu.</span><span class="sxs-lookup"><span data-stu-id="5e02f-103">Maps a service to an application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e02f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e02f-104">Syntax</span></span>  
  
```  
class ServiceAppDomain  
{  
  Service ref;  
  AppDomainInfo ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="5e02f-105">Methoden</span><span class="sxs-lookup"><span data-stu-id="5e02f-105">Methods</span></span>  
 <span data-ttu-id="5e02f-106">Mit der ServiceAppDomain-Klasse werden keine Methoden definiert.</span><span class="sxs-lookup"><span data-stu-id="5e02f-106">The ServiceAppDomain class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5e02f-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5e02f-107">Properties</span></span>  
 <span data-ttu-id="5e02f-108">Die ServiceAppDomain-Klasse verfügt über die folgenden Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="5e02f-108">The ServiceAppDomain class has the following properties:</span></span>  
  
### <a name="ref"></a><span data-ttu-id="5e02f-109">ref</span><span class="sxs-lookup"><span data-stu-id="5e02f-109">ref</span></span>  
 <span data-ttu-id="5e02f-110">Datentyp: Dienst</span><span class="sxs-lookup"><span data-stu-id="5e02f-110">Data type: Service</span></span>  
<span data-ttu-id="5e02f-111">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="5e02f-111">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="5e02f-112">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="5e02f-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5e02f-113">Der Dienst dieser Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="5e02f-113">The service of this application domain.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="5e02f-114">ref</span><span class="sxs-lookup"><span data-stu-id="5e02f-114">ref</span></span>  
 <span data-ttu-id="5e02f-115">Datentyp: AppDomainInfo</span><span class="sxs-lookup"><span data-stu-id="5e02f-115">Data type: AppDomainInfo</span></span>  
<span data-ttu-id="5e02f-116">Qualifizierer: Schlüssel</span><span class="sxs-lookup"><span data-stu-id="5e02f-116">Qualifiers: Key</span></span>  
  
 <span data-ttu-id="5e02f-117">Zugriffstyp: Schreibgeschützt</span><span class="sxs-lookup"><span data-stu-id="5e02f-117">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5e02f-118">Enthält Eigenschaften der Anwendungsdomäne.</span><span class="sxs-lookup"><span data-stu-id="5e02f-118">Contains properties of the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e02f-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5e02f-119">Requirements</span></span>  
  
|<span data-ttu-id="5e02f-120">MOF</span><span class="sxs-lookup"><span data-stu-id="5e02f-120">MOF</span></span>|<span data-ttu-id="5e02f-121">Deklariert in Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="5e02f-121">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5e02f-122">Namespace</span><span class="sxs-lookup"><span data-stu-id="5e02f-122">Namespace</span></span>|<span data-ttu-id="5e02f-123">Definiert in root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="5e02f-123">Defined in root\ServiceModel</span></span>|
