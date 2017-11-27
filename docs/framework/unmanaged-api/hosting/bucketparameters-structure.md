---
title: BucketParameters-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: BucketParameters
api_location: mscoree.dll
api_type: COM
f1_keywords: BucketParameters
helpviewer_keywords: BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7626ce6b2b6278be7cd9989718c13f7c98e4ace3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="81b0c-102">BucketParameters-Struktur</span><span class="sxs-lookup"><span data-stu-id="81b0c-102">BucketParameters Structure</span></span>
<span data-ttu-id="81b0c-103">Speichert den Typnamen des ein Ereignis und die Parameter für die aktuelle Ausnahme, die dem Ereignis zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="81b0c-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81b0c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="81b0c-104">Syntax</span></span>  
  
```  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="81b0c-105">Member</span><span class="sxs-lookup"><span data-stu-id="81b0c-105">Members</span></span>  
  
|<span data-ttu-id="81b0c-106">Member</span><span class="sxs-lookup"><span data-stu-id="81b0c-106">Member</span></span>|<span data-ttu-id="81b0c-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81b0c-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="81b0c-108">`true`, wenn Sie der Rest dieser Struktur gültig ist. andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="81b0c-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="81b0c-109">Der Name des Ereignistyps.</span><span class="sxs-lookup"><span data-stu-id="81b0c-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="81b0c-110">Ein Array von Zeichenfolgen, von denen jedes einen Parameter für die aktuelle Ausnahme, die das Ereignis angibt.</span><span class="sxs-lookup"><span data-stu-id="81b0c-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81b0c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="81b0c-111">Requirements</span></span>  
 <span data-ttu-id="81b0c-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81b0c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81b0c-113">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="81b0c-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="81b0c-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81b0c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b0c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81b0c-115">See Also</span></span>  
 [<span data-ttu-id="81b0c-116">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="81b0c-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
