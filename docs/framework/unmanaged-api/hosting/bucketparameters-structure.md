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
ms.openlocfilehash: 8b54cb30ec96ad0fb7851af6f2d465fe771886ac
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95677853"
---
# <a name="bucketparameters-structure"></a><span data-ttu-id="b7ff9-102">BucketParameters-Struktur</span><span class="sxs-lookup"><span data-stu-id="b7ff9-102">BucketParameters Structure</span></span>

<span data-ttu-id="b7ff9-103">Speichert den Typnamen eines Ereignisses und die Parameter für die aktuelle Ausnahme, die dem Ereignis zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b7ff9-103">Stores the type name of an event and the parameters for the current exception that is associated with the event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7ff9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7ff9-104">Syntax</span></span>  
  
```cpp  
typedef struct _BucketParameters {  
    BOOL  fInited;
    WCHAR pszEventTypeName[255];
    WCHAR pszParams[10][255];
} BucketParameters;  
```  
  
## <a name="members"></a><span data-ttu-id="b7ff9-105">Member</span><span class="sxs-lookup"><span data-stu-id="b7ff9-105">Members</span></span>  
  
|<span data-ttu-id="b7ff9-106">Member</span><span class="sxs-lookup"><span data-stu-id="b7ff9-106">Member</span></span>|<span data-ttu-id="b7ff9-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b7ff9-107">Description</span></span>|  
|------------|-----------------|  
|`fInited`|<span data-ttu-id="b7ff9-108">`true`, wenn der Rest dieser-Struktur gültig ist. andernfalls `false` .</span><span class="sxs-lookup"><span data-stu-id="b7ff9-108">`true`, if the rest of this structure is valid; otherwise, `false`.</span></span>|  
|`pszEventTypeName`|<span data-ttu-id="b7ff9-109">Der Name des Ereignis Typs.</span><span class="sxs-lookup"><span data-stu-id="b7ff9-109">Name of the event type.</span></span>|  
|`pszParams`|<span data-ttu-id="b7ff9-110">Ein Array von Zeichen folgen, von denen jede einen Parameter für die aktuelle Ausnahme angibt, die dem Ereignis zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b7ff9-110">An array of strings, each of which specifies a parameter for the current exception associated with the event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b7ff9-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b7ff9-111">Requirements</span></span>  

 <span data-ttu-id="b7ff9-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7ff9-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7ff9-113">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="b7ff9-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="b7ff9-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7ff9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7ff9-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7ff9-115">See also</span></span>

- [<span data-ttu-id="b7ff9-116">Hosten von Strukturen</span><span class="sxs-lookup"><span data-stu-id="b7ff9-116">Hosting Structures</span></span>](hosting-structures.md)
