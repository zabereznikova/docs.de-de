---
title: MALLOC_TYPE-Enumeration
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695f69c8d9c3a295a705971743733339cf8aab13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765218"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="e7409-102">MALLOC_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e7409-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="e7409-103">Enthält Werte, die die Merkmale des Arbeitsspeichers angeben, die zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="e7409-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7409-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e7409-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="e7409-105">Member</span><span class="sxs-lookup"><span data-stu-id="e7409-105">Members</span></span>  
  
|<span data-ttu-id="e7409-106">Member</span><span class="sxs-lookup"><span data-stu-id="e7409-106">Member</span></span>|<span data-ttu-id="e7409-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e7409-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="e7409-108">Der zugeordnete Arbeitsspeicher kann es sich um eine ausführbare Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="e7409-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="e7409-109">Der belegte Arbeitsspeicher ist threadsicher.</span><span class="sxs-lookup"><span data-stu-id="e7409-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="e7409-110">Der Arbeitsspeicher kann, also von mehreren Threads ohne Synchronisierung zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e7409-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="e7409-111">Wenn dieses Flag nicht festgelegt ist, müssen die Aufrufe für das Objekt serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e7409-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e7409-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e7409-112">Requirements</span></span>  
 <span data-ttu-id="e7409-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7409-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7409-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e7409-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e7409-115">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e7409-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e7409-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7409-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7409-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e7409-117">See also</span></span>

- [<span data-ttu-id="e7409-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e7409-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
