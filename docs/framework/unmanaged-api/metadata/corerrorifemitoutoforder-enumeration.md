---
title: CorErrorIfEmitOutOfOrder-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorErrorIfEmitOutOfOrder
api_location: mscoree.dll
api_type: COM
f1_keywords: CorErrorIfEmitOutOfOrder
helpviewer_keywords: CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c049d78d8ba67ec5f08fc2beb584fef4987c9e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="be6e1-102">CorErrorIfEmitOutOfOrder-Enumeration</span><span class="sxs-lookup"><span data-stu-id="be6e1-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="be6e1-103">Enthält Flagwerte, die die Bedingungen angeben, bei denen eine Fehlermeldung generiert werden soll, wenn Metadaten nicht in der richtigen Reihenfolge ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be6e1-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be6e1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="be6e1-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="be6e1-105">Member</span><span class="sxs-lookup"><span data-stu-id="be6e1-105">Members</span></span>  
  
|<span data-ttu-id="be6e1-106">Member</span><span class="sxs-lookup"><span data-stu-id="be6e1-106">Member</span></span>|<span data-ttu-id="be6e1-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="be6e1-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="be6e1-108">Gibt an, das Standardverhalten, bei das keine Fehlermeldungen generiert.</span><span class="sxs-lookup"><span data-stu-id="be6e1-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="be6e1-109">Gibt an, dass der Compiler keine Fehlermeldungen generiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="be6e1-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="be6e1-110">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Feld, Eigenschaft, Ereignis, eine Methode oder Parameter wird nicht in der richtigen Reihenfolge ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="be6e1-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="be6e1-111">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Methode außerhalb der Reihenfolge ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be6e1-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="be6e1-112">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Feld außerhalb der Reihenfolge ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be6e1-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="be6e1-113">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Parameter außerhalb der Reihenfolge ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be6e1-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="be6e1-114">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Eigenschaft außerhalb der Reihenfolge ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be6e1-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="be6e1-115">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Ereignis nicht in der richtigen Reihenfolge ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="be6e1-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be6e1-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="be6e1-116">Requirements</span></span>  
 <span data-ttu-id="be6e1-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be6e1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be6e1-118">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="be6e1-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="be6e1-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be6e1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be6e1-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be6e1-120">See Also</span></span>  
 [<span data-ttu-id="be6e1-121">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="be6e1-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
