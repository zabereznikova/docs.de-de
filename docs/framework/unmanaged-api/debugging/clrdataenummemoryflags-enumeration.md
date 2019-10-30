---
title: CLRDataEnumMemoryFlags-Enumeration
ms.date: 03/30/2017
api_name:
- CLRDataEnumMemoryFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLRDataEnumMemoryFlags
helpviewer_keywords:
- CLRDataEnumMemoryFlags enumeration [.NET Framework debugging]
ms.assetid: e249f9fc-e24a-4506-903c-92781f6eab7c
topic_type:
- apiref
ms.openlocfilehash: 769e63ac6e23ae0264b79a1cd8d6e3cc1ac5a744
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132414"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="5ebba-102">CLRDataEnumMemoryFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5ebba-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="5ebba-103">Gibt an, welche Speicherbereiche ein Aufrufe der [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) -Methode einschließen sollte.</span><span class="sxs-lookup"><span data-stu-id="5ebba-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ebba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ebba-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="5ebba-105">Member</span><span class="sxs-lookup"><span data-stu-id="5ebba-105">Members</span></span>  
  
|<span data-ttu-id="5ebba-106">Member</span><span class="sxs-lookup"><span data-stu-id="5ebba-106">Member</span></span>|<span data-ttu-id="5ebba-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5ebba-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="5ebba-108">Ein Minidump, d. h. ein Speicher Abbild mit geringer Dichte.</span><span class="sxs-lookup"><span data-stu-id="5ebba-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="5ebba-109">Ein vollständiges Heap-Dump.</span><span class="sxs-lookup"><span data-stu-id="5ebba-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ebba-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ebba-110">Requirements</span></span>  
 <span data-ttu-id="5ebba-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ebba-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ebba-112">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="5ebba-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="5ebba-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ebba-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ebba-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ebba-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ebba-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ebba-115">See also</span></span>

- [<span data-ttu-id="5ebba-116">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="5ebba-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
