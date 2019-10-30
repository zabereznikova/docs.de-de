---
title: COR_FIELD-Struktur
ms.date: 03/30/2017
api_name:
- COR_FIELD
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_FIELD
helpviewer_keywords:
- COR_FIELD structure [.NET Framework debugging]
ms.assetid: c0822423-a9df-4961-950d-50dcc152f863
topic_type:
- apiref
ms.openlocfilehash: 78e34d9d33d34047e3ebd2effb4894bc7b709585
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132355"
---
# <a name="cor_field-structure"></a><span data-ttu-id="b0bd2-102">COR_FIELD-Struktur</span><span class="sxs-lookup"><span data-stu-id="b0bd2-102">COR_FIELD Structure</span></span>
<span data-ttu-id="b0bd2-103">Bietet Informationen zu einem Feld in einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="b0bd2-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0bd2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b0bd2-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="b0bd2-105">Member</span><span class="sxs-lookup"><span data-stu-id="b0bd2-105">Members</span></span>  
  
|<span data-ttu-id="b0bd2-106">Member</span><span class="sxs-lookup"><span data-stu-id="b0bd2-106">Member</span></span>|<span data-ttu-id="b0bd2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b0bd2-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="b0bd2-108">Ein `mdFieldDef` Token, das verwendet werden kann, um Feldinformationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b0bd2-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="b0bd2-109">Der Offset in Bytes für die Felddaten im-Objekt.</span><span class="sxs-lookup"><span data-stu-id="b0bd2-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="b0bd2-110">Ein [COR_TYPEID](cor-typeid-structure.md) -Wert, der den Typ dieses Felds angibt.</span><span class="sxs-lookup"><span data-stu-id="b0bd2-110">A [COR_TYPEID](cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="b0bd2-111">Ein CorElementType-Enumerationswert, der den Typ des Felds angibt.</span><span class="sxs-lookup"><span data-stu-id="b0bd2-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0bd2-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b0bd2-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0bd2-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b0bd2-113">Requirements</span></span>  
 <span data-ttu-id="b0bd2-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0bd2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0bd2-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b0bd2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b0bd2-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b0bd2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b0bd2-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0bd2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0bd2-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0bd2-118">See also</span></span>

- [<span data-ttu-id="b0bd2-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="b0bd2-119">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="b0bd2-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="b0bd2-120">Debugging</span></span>](index.md)
