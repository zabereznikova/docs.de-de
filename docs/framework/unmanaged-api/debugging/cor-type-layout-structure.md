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
ms.openlocfilehash: 6bd274b1eb14532629580e777288317186544912
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274164"
---
# <a name="cor_type_layout-structure"></a><span data-ttu-id="58c6f-102">COR_TYPE_LAYOUT-Struktur</span><span class="sxs-lookup"><span data-stu-id="58c6f-102">COR_TYPE_LAYOUT Structure</span></span>
<span data-ttu-id="58c6f-103">Bietet Informationen zum Layout eines Objekts im Speicher.</span><span class="sxs-lookup"><span data-stu-id="58c6f-103">Provides information about the layout of an object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58c6f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="58c6f-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_TYPE_LAYOUT {  
    COR_TYPEID parentID;  
    ULONG32 objectSize;  
    ULONG32 numFields;  
    ULONG32 boxOffset;  
    CorElementType type;  
} COR_TYPE_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="58c6f-105">Member</span><span class="sxs-lookup"><span data-stu-id="58c6f-105">Members</span></span>  
  
|<span data-ttu-id="58c6f-106">Member</span><span class="sxs-lookup"><span data-stu-id="58c6f-106">Member</span></span>|<span data-ttu-id="58c6f-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="58c6f-107">Description</span></span>|  
|------------|-----------------|  
|`parentID`|<span data-ttu-id="58c6f-108">Der Bezeichner des übergeordneten Typs für diesen Typ.</span><span class="sxs-lookup"><span data-stu-id="58c6f-108">The identifier of the parent type to this type.</span></span> <span data-ttu-id="58c6f-109">Dabei handelt es sich um <xref:System.Object?displayProperty=nameWithType>die NULL-Typ-ID (ttoken1 = 0, Token2 = 0), wenn die Typ-ID entspricht.</span><span class="sxs-lookup"><span data-stu-id="58c6f-109">This will be the NULL type id (token1= 0, token2 = 0) if the type id corresponds to <xref:System.Object?displayProperty=nameWithType>.</span></span>|  
|`objectSize`|<span data-ttu-id="58c6f-110">Die Basis Größe eines Objekts dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="58c6f-110">The base size of an object of this type.</span></span> <span data-ttu-id="58c6f-111">Dies ist die Gesamtgröße für Objekte, die keine Variablen groß sind.</span><span class="sxs-lookup"><span data-stu-id="58c6f-111">This is the total size for non-variable sized objects.</span></span>|  
|`numFields`|<span data-ttu-id="58c6f-112">Die Anzahl der Felder, die in Objekten dieses Typs enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="58c6f-112">The number of fields included in objects of this type.</span></span>|  
|`boxOffset`|<span data-ttu-id="58c6f-113">Wenn dieser Typ ein Boxing ist, der Anfangs Offset der Felder eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="58c6f-113">If this type is boxed, the beginning offset of an object's fields.</span></span> <span data-ttu-id="58c6f-114">Dieses Feld ist nur für Werttypen, z. b. primitive und Strukturen, gültig.</span><span class="sxs-lookup"><span data-stu-id="58c6f-114">This field is valid only for value types such as primitives and structures.</span></span>|  
|`type`|<span data-ttu-id="58c6f-115">Der CorElementType, zu dem dieser Typ gehört.</span><span class="sxs-lookup"><span data-stu-id="58c6f-115">The CorElementType to which this type belongs.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="58c6f-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="58c6f-116">Remarks</span></span>  
 <span data-ttu-id="58c6f-117">Wenn `numFields` größer als 0 (null) ist, können Sie die [ICorDebugProcess5:: gettypeer Fields](icordebugprocess5-gettypefields-method.md) -Methode aufrufen, um Informationen zu den Feldern in diesem Typ zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="58c6f-117">If `numFields` is greater than zero, you can call the [ICorDebugProcess5::GetTypeFields](icordebugprocess5-gettypefields-method.md) method to obtain information about the fields in this type.</span></span> <span data-ttu-id="58c6f-118">Wenn `type` , `ELEMENT_TYPE_STRING` oderist`ELEMENT_TYPE_SZARRAY`, ist die Größe von Objekten dieses Typs variabel, und Sie können die [COR_TYPEID](cor-typeid-structure.md) -Struktur an die [ICorDebugProcess5:: getarraylayout](icordebugprocess5-getarraylayout-method.md) -Methode übergeben. `ELEMENT_TYPE_ARRAY`</span><span class="sxs-lookup"><span data-stu-id="58c6f-118">If `type` is `ELEMENT_TYPE_STRING`, `ELEMENT_TYPE_ARRAY`, or `ELEMENT_TYPE_SZARRAY`, the size of objects of this type is variable, and you can pass the [COR_TYPEID](cor-typeid-structure.md) structure to the [ICorDebugProcess5::GetArrayLayout](icordebugprocess5-getarraylayout-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58c6f-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="58c6f-119">Requirements</span></span>  
 <span data-ttu-id="58c6f-120">**Formen** Weitere Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58c6f-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58c6f-121">**Header:** Cordebug. idl, Cordebug. h</span><span class="sxs-lookup"><span data-stu-id="58c6f-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="58c6f-122">**Fern** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58c6f-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58c6f-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58c6f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58c6f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58c6f-124">See also</span></span>

- [<span data-ttu-id="58c6f-125">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="58c6f-125">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="58c6f-126">Debuggen</span><span class="sxs-lookup"><span data-stu-id="58c6f-126">Debugging</span></span>](index.md)
