---
title: COR_TYPE_LAYOUT-Struktur
ms.date: 03/30/2017
api_name:
- COR_TYPE_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPE_LAYOUT
helpviewer_keywords:
- COR_TYPE_LAYOUT structure [.NET Framework debugging]
ms.assetid: 43a7addd-f25a-4049-9907-abec3eb17af2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7efb2c3e8033b8bd8fa736a29b2ab9b3bedebeaa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59109641"
---
# <a name="cortypelayout-structure"></a><span data-ttu-id="d1335-102">COR_TYPE_LAYOUT-Struktur</span><span class="sxs-lookup"><span data-stu-id="d1335-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="d1335-103">Bietet Informationen zum Layout eines Objekts im Speicher.</span><span class="sxs-lookup"><span data-stu-id="d1335-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1335-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1335-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="d1335-105">Member</span><span class="sxs-lookup"><span data-stu-id="d1335-105">Members</span></span>  
  
|<span data-ttu-id="d1335-106">Member</span><span class="sxs-lookup"><span data-stu-id="d1335-106">Member</span></span>|<span data-ttu-id="d1335-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1335-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="d1335-108">Der Bezeichner des übergeordneten Typs auf diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="d1335-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="d1335-109">Dadurch werden die NULL-Typ-Id (ttoken1 = 0 "," token2 = 0) Wenn die Typ-Id entspricht <xref:System.Object?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d1335-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="d1335-110">Die Grundgröße eines Objekts dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="d1335-110">The base size of an object of this type.</span></span> <span data-ttu-id="d1335-111">Dies ist die Gesamtgröße für große Objekte nicht-Variable.</span><span class="sxs-lookup"><span data-stu-id="d1335-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="d1335-112">Die Anzahl der Felder, die in der Objekte dieses Typs enthalten.</span><span class="sxs-lookup"><span data-stu-id="d1335-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="d1335-113">Wenn dieser Typ geschachtelt ist, offset am Anfang der Felder eines Objekts aus.</span><span class="sxs-lookup"><span data-stu-id="d1335-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="d1335-114">Dieses Feld gilt nur für Werttypen wie z. B. primitive Typen und Strukturen.</span><span class="sxs-lookup"><span data-stu-id="d1335-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="d1335-115">Die CorElementType, zu dem dieser Typ gehört.</span><span class="sxs-lookup"><span data-stu-id="d1335-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1335-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d1335-116">Remarks</span></span>  
 <span data-ttu-id="d1335-117">Wenn `numFields` ist größer als 0 (null), rufen Sie die [icordebugprocess5:: Gettypefields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) Methode zum Abrufen von Informationen zu den Feldern in dieser Art.</span><span class="sxs-lookup"><span data-stu-id="d1335-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="d1335-118">Wenn `type` ist `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, oder `ELEMENT_TYPE_SZARRAY`, die Größe der Objekte dieses Typs ist, Variablen und können Sie übergeben die [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) -Struktur in der [icordebugprocess5:: Getarraylayout ](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="d1335-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1335-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1335-119">Requirements</span></span>  
 <span data-ttu-id="d1335-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1335-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1335-121">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1335-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1335-122">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1335-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1335-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1335-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1335-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1335-124">See also</span></span>

- [<span data-ttu-id="d1335-125">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="d1335-125">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="d1335-126">Debuggen</span><span class="sxs-lookup"><span data-stu-id="d1335-126">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
