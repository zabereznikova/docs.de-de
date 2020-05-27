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
ms.openlocfilehash: 630fe4e79b369bfdefc19be72780f1893090895e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008455"
---
# <a name="malloc_type-enumeration"></a><span data-ttu-id="14b68-102">MALLOC_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="14b68-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="14b68-103">Enthält Werte, die die Merkmale des zugeordneten Arbeitsspeichers angeben.</span><span class="sxs-lookup"><span data-stu-id="14b68-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14b68-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="14b68-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="14b68-105">Member</span><span class="sxs-lookup"><span data-stu-id="14b68-105">Members</span></span>  
  
|<span data-ttu-id="14b68-106">Member</span><span class="sxs-lookup"><span data-stu-id="14b68-106">Member</span></span>|<span data-ttu-id="14b68-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="14b68-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="14b68-108">Der zugewiesene Arbeitsspeicher kann eine ausführbare Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="14b68-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="14b68-109">Der zugewiesene Arbeitsspeicher ist Thread sicher.</span><span class="sxs-lookup"><span data-stu-id="14b68-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="14b68-110">Das heißt, dass auf den Speicher durch mehrere Threads ohne Synchronisierung zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="14b68-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="14b68-111">Wenn dieses Flag nicht festgelegt ist, müssen Aufrufe für das-Objekt serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="14b68-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14b68-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="14b68-112">Requirements</span></span>  
 <span data-ttu-id="14b68-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14b68-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14b68-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="14b68-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="14b68-115">**Bibliothek:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="14b68-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="14b68-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14b68-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14b68-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14b68-117">See also</span></span>

- [<span data-ttu-id="14b68-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="14b68-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
