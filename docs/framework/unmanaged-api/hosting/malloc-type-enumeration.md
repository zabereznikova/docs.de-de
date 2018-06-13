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
ms.openlocfilehash: 2c5e970a1677b1e43821cce9985e32ebd0726686
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442539"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="e6b1e-102">MALLOC_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e6b1e-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="e6b1e-103">Enthält Werte, die die Merkmale des Arbeitsspeichers angeben, die zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="e6b1e-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6b1e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e6b1e-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="e6b1e-105">Member</span><span class="sxs-lookup"><span data-stu-id="e6b1e-105">Members</span></span>  
  
|<span data-ttu-id="e6b1e-106">Member</span><span class="sxs-lookup"><span data-stu-id="e6b1e-106">Member</span></span>|<span data-ttu-id="e6b1e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e6b1e-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="e6b1e-108">Der belegte Arbeitsspeicher kann eine ausführbare Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="e6b1e-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="e6b1e-109">Der belegte Arbeitsspeicher ist threadsicher.</span><span class="sxs-lookup"><span data-stu-id="e6b1e-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="e6b1e-110">Der Arbeitsspeicher kann also durch mehrere Threads ohne Synchronisierung zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="e6b1e-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="e6b1e-111">Wenn dieses Flag nicht festgelegt ist, müssen für das Objekt serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e6b1e-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6b1e-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e6b1e-112">Requirements</span></span>  
 <span data-ttu-id="e6b1e-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6b1e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6b1e-114">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e6b1e-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e6b1e-115">**Bibliothek:** "Mscoree.dll"</span><span class="sxs-lookup"><span data-stu-id="e6b1e-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e6b1e-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e6b1e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6b1e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6b1e-117">See Also</span></span>  
 [<span data-ttu-id="e6b1e-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="e6b1e-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
