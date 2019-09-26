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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67b85917be590bdba7ed3f10972ad39b731dbcdd
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274240"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="3460e-102">CLRDataEnumMemoryFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3460e-102">CLRDataEnumMemoryFlags Enumeration</span></span>
<span data-ttu-id="3460e-103">Gibt an, welche Speicherbereiche ein Aufrufe der [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) -Methode einschließen sollte.</span><span class="sxs-lookup"><span data-stu-id="3460e-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3460e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3460e-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="3460e-105">Member</span><span class="sxs-lookup"><span data-stu-id="3460e-105">Members</span></span>  
  
|<span data-ttu-id="3460e-106">Member</span><span class="sxs-lookup"><span data-stu-id="3460e-106">Member</span></span>|<span data-ttu-id="3460e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3460e-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="3460e-108">Ein Minidump, d. h. ein Speicher Abbild mit geringer Dichte.</span><span class="sxs-lookup"><span data-stu-id="3460e-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="3460e-109">Ein vollständiges Heap-Dump.</span><span class="sxs-lookup"><span data-stu-id="3460e-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3460e-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3460e-110">Requirements</span></span>  
 <span data-ttu-id="3460e-111">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3460e-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3460e-112">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="3460e-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="3460e-113">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3460e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3460e-114">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3460e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3460e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3460e-115">See also</span></span>

- [<span data-ttu-id="3460e-116">Debuggen von Enumerationen</span><span class="sxs-lookup"><span data-stu-id="3460e-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
