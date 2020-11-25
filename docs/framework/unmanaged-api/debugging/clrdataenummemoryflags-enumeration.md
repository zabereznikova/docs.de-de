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
ms.openlocfilehash: 9a82162023fa05e85fc9bbeb16961f2aafd9a4ec
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729797"
---
# <a name="clrdataenummemoryflags-enumeration"></a><span data-ttu-id="cf676-102">CLRDataEnumMemoryFlags-Enumeration</span><span class="sxs-lookup"><span data-stu-id="cf676-102">CLRDataEnumMemoryFlags Enumeration</span></span>

<span data-ttu-id="cf676-103">Gibt an, welche Speicherbereiche ein Aufrufe der [ICLRDataEnumMemoryRegions:: EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) -Methode einschließen sollte.</span><span class="sxs-lookup"><span data-stu-id="cf676-103">Indicates which memory regions a call to the [ICLRDataEnumMemoryRegions::EnumMemoryRegions](iclrdataenummemoryregions-enummemoryregions-method.md) method should include.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cf676-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="cf676-104">Syntax</span></span>  
  
```cpp  
typedef enum CLRDataEnumMemoryFlags {  
    CLRDATA_ENUM_MEM_DEFAULT  = 0x0,  
    CLRDATA_ENUM_MEM_MINI     = CLRDATA_ENUM_MEM_DEFAULT,  
    CLRDATA_ENUM_MEM_HEAP     = 0x1  
} CLRDataEnumMemoryFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="cf676-105">Member</span><span class="sxs-lookup"><span data-stu-id="cf676-105">Members</span></span>  
  
|<span data-ttu-id="cf676-106">Member</span><span class="sxs-lookup"><span data-stu-id="cf676-106">Member</span></span>|<span data-ttu-id="cf676-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cf676-107">Description</span></span>|  
|------------|-----------------|  
|`CLRDATA_ENUM_MEM_DEFAULT`|<span data-ttu-id="cf676-108">Ein Minidump, d. h. ein Speicher Abbild mit geringer Dichte.</span><span class="sxs-lookup"><span data-stu-id="cf676-108">A minidump, that is, a sparse memory dump.</span></span>|  
|`CLRDATA_ENUM_MEM_HEAP`|<span data-ttu-id="cf676-109">Ein vollständiges Heap-Dump.</span><span class="sxs-lookup"><span data-stu-id="cf676-109">A full heap dump.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cf676-110">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="cf676-110">Requirements</span></span>  

 <span data-ttu-id="cf676-111">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cf676-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cf676-112">**Header:** Clrdata. idl, Clrdata. h</span><span class="sxs-lookup"><span data-stu-id="cf676-112">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="cf676-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cf676-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cf676-114">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cf676-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf676-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cf676-115">See also</span></span>

- [<span data-ttu-id="cf676-116">Debugenumerationen</span><span class="sxs-lookup"><span data-stu-id="cf676-116">Debugging Enumerations</span></span>](debugging-enumerations.md)
