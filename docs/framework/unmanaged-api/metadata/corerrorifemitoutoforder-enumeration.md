---
title: CorErrorIfEmitOutOfOrder-Enumeration
ms.date: 03/30/2017
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
ms.openlocfilehash: 1d1b0cbb8be33f285b63e7353da973455e0fd752
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718851"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="e091c-102">CorErrorIfEmitOutOfOrder-Enumeration</span><span class="sxs-lookup"><span data-stu-id="e091c-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>

<span data-ttu-id="e091c-103">Enthält Flagwerte, die die Bedingungen angeben, bei denen eine Fehlermeldung generiert werden soll, wenn Metadaten nicht in der richtigen Reihenfolge ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="e091c-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e091c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e091c-104">Syntax</span></span>  
  
```cpp  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a><span data-ttu-id="e091c-105">Member</span><span class="sxs-lookup"><span data-stu-id="e091c-105">Members</span></span>  
  
|<span data-ttu-id="e091c-106">Member</span><span class="sxs-lookup"><span data-stu-id="e091c-106">Member</span></span>|<span data-ttu-id="e091c-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e091c-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="e091c-108">Gibt das Standardverhalten an, das keine Fehlermeldungen generiert.</span><span class="sxs-lookup"><span data-stu-id="e091c-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="e091c-109">Gibt an, dass der Compiler keine Fehlermeldungen generieren soll.</span><span class="sxs-lookup"><span data-stu-id="e091c-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="e091c-110">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Feld, eine Eigenschaft, ein Ereignis, eine Methode oder ein Parameter nicht in der richtigen Reihenfolge ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e091c-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="e091c-111">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Methode nicht in der richtigen Reihenfolge ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e091c-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="e091c-112">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Feld nicht in der richtigen Reihenfolge ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e091c-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="e091c-113">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Parameter nicht in der richtigen Reihenfolge ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e091c-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="e091c-114">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Eigenschaft nicht in der richtigen Reihenfolge ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e091c-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="e091c-115">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Ereignis außerhalb der Reihenfolge ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="e091c-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e091c-116">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="e091c-116">Requirements</span></span>  

 <span data-ttu-id="e091c-117">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e091c-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e091c-118">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="e091c-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="e091c-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e091c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e091c-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e091c-120">See also</span></span>

- [<span data-ttu-id="e091c-121">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="e091c-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
