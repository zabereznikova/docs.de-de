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
ms.openlocfilehash: fe58a519d0feac0da49e7778247da1ef538f8b83
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730031"
---
# <a name="malloc_type-enumeration"></a><span data-ttu-id="f5e4f-102">MALLOC_TYPE-Enumeration</span><span class="sxs-lookup"><span data-stu-id="f5e4f-102">MALLOC_TYPE Enumeration</span></span>

<span data-ttu-id="f5e4f-103">Enthält Werte, die die Merkmale des zugeordneten Arbeitsspeichers angeben.</span><span class="sxs-lookup"><span data-stu-id="f5e4f-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5e4f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5e4f-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="f5e4f-105">Member</span><span class="sxs-lookup"><span data-stu-id="f5e4f-105">Members</span></span>  
  
|<span data-ttu-id="f5e4f-106">Member</span><span class="sxs-lookup"><span data-stu-id="f5e4f-106">Member</span></span>|<span data-ttu-id="f5e4f-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="f5e4f-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="f5e4f-108">Der zugewiesene Arbeitsspeicher kann eine ausführbare Datei enthalten.</span><span class="sxs-lookup"><span data-stu-id="f5e4f-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="f5e4f-109">Der zugewiesene Arbeitsspeicher ist Thread sicher.</span><span class="sxs-lookup"><span data-stu-id="f5e4f-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="f5e4f-110">Das heißt, dass auf den Speicher durch mehrere Threads ohne Synchronisierung zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f5e4f-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="f5e4f-111">Wenn dieses Flag nicht festgelegt ist, müssen Aufrufe für das-Objekt serialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="f5e4f-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f5e4f-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f5e4f-112">Requirements</span></span>  

 <span data-ttu-id="f5e4f-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5e4f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5e4f-114">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f5e4f-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f5e4f-115">**Bibliothek:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f5e4f-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f5e4f-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f5e4f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5e4f-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5e4f-117">See also</span></span>

- [<span data-ttu-id="f5e4f-118">Hosten von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="f5e4f-118">Hosting Enumerations</span></span>](hosting-enumerations.md)
