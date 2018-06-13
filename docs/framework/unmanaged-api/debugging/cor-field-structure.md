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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0898936665b3b337f2fd4e4d53bcc9f6071469b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405358"
---
# <a name="corfield-structure"></a><span data-ttu-id="97441-102">COR_FIELD-Struktur</span><span class="sxs-lookup"><span data-stu-id="97441-102">COR_FIELD Structure</span></span>
<span data-ttu-id="97441-103">Bietet Informationen zu einem Feld in einem Objekt.</span><span class="sxs-lookup"><span data-stu-id="97441-103">Provides information about a field in an object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97441-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="97441-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD{  
    mdFieldDef token;  
    ULONG32 offset;  
    COR_TYPEID id;  
    CorElementType fieldType;  
} COR_FIELD;  
```  
  
## <a name="members"></a><span data-ttu-id="97441-105">Member</span><span class="sxs-lookup"><span data-stu-id="97441-105">Members</span></span>  
  
|<span data-ttu-id="97441-106">Member</span><span class="sxs-lookup"><span data-stu-id="97441-106">Member</span></span>|<span data-ttu-id="97441-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="97441-107">Description</span></span>|  
|------------|-----------------|  
|`token`|<span data-ttu-id="97441-108">Ein `mdFieldDef` Token, das zum Abrufen von Feldinformationen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="97441-108">An `mdFieldDef` token that can be used to get field information.</span></span>|  
|`offset`|<span data-ttu-id="97441-109">Der Offset in Bytes, die die Felddaten im-Objekt.</span><span class="sxs-lookup"><span data-stu-id="97441-109">The offset, in bytes, to the field data in the object.</span></span>|  
|`id`|<span data-ttu-id="97441-110">Ein [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) -Wert, der den Typ dieses Felds identifiziert.</span><span class="sxs-lookup"><span data-stu-id="97441-110">A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) value that identifies the type of this field.</span></span>|  
|`fieldType`|<span data-ttu-id="97441-111">Ein Wert der CorElementType-Enumeration, der den Typ des Felds angibt.</span><span class="sxs-lookup"><span data-stu-id="97441-111">A CorElementType enumeration value that indicates the type of the field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97441-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="97441-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97441-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="97441-113">Requirements</span></span>  
 <span data-ttu-id="97441-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97441-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97441-115">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97441-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97441-116">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97441-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97441-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97441-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97441-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="97441-118">See Also</span></span>  
 [<span data-ttu-id="97441-119">Debuggen von Strukturen</span><span class="sxs-lookup"><span data-stu-id="97441-119">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="97441-120">Debuggen</span><span class="sxs-lookup"><span data-stu-id="97441-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
