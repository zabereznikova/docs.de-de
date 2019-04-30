---
title: BucketParameters-Struktur
ms.date: 03/30/2017
api_name:
- BucketParameters
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- BucketParameters
helpviewer_keywords:
- BucketParameters structure [.NET Framework hosting]
ms.assetid: 9432487e-f276-45d6-9a13-9a68024dbd46
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5998ce684726b2386d8f1e05eb7eaeccf455747c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946761"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="f0ef7-102">BucketParameters-Struktur</span><span class="sxs-lookup"><span data-stu-id="f0ef7-102">BucketParameters Structure</span></span>
<span data-ttu-id="f0ef7-103">Speichert den Typnamen eines Ereignisses und die Parameter für die aktuelle Ausnahme, die dem Ereignis zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f0ef7-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ef7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0ef7-104">Syntax</span></span>  
  
```  
typedef struct _BucketParameters {  
    BOOL  fInited;                    
    WCHAR pszEventTypeName[255];      
    WCHAR pszParams[10][255];         
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="f0ef7-105">Member</span><span class="sxs-lookup"><span data-stu-id="f0ef7-105">Members</span></span>  
  
|<span data-ttu-id="f0ef7-106">Member</span><span class="sxs-lookup"><span data-stu-id="f0ef7-106">Member</span></span>|<span data-ttu-id="f0ef7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f0ef7-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="f0ef7-108">`true`, wenn der Rest dieser Struktur gültig ist. andernfalls `false`.</span><span class="sxs-lookup"><span data-stu-id="f0ef7-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="f0ef7-109">Der Name des Ereignistyps.</span><span class="sxs-lookup"><span data-stu-id="f0ef7-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="f0ef7-110">Ein Array von Zeichenfolgen, von denen jede einen Parameter für die aktuelle Ausnahme, die dem Ereignis zugeordnete angibt.</span><span class="sxs-lookup"><span data-stu-id="f0ef7-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f0ef7-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f0ef7-111">Requirements</span></span>  
 <span data-ttu-id="f0ef7-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0ef7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0ef7-113">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="f0ef7-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f0ef7-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0ef7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ef7-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f0ef7-115">See also</span></span>

- [<span data-ttu-id="f0ef7-116">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="f0ef7-116">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
