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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 628ca1b555d80319312450d784981cfed1bda947
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160445"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="4f446-102">CorErrorIfEmitOutOfOrder-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4f446-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="4f446-103">Enthält Flagwerte, die die Bedingungen angeben, bei denen eine Fehlermeldung generiert werden soll, wenn Metadaten nicht in der richtigen Reihenfolge ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4f446-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f446-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f446-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="4f446-105">Member</span><span class="sxs-lookup"><span data-stu-id="4f446-105">Members</span></span>  
  
|<span data-ttu-id="4f446-106">Member</span><span class="sxs-lookup"><span data-stu-id="4f446-106">Member</span></span>|<span data-ttu-id="4f446-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f446-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="4f446-108">Gibt an, das Standardverhalten, das keine Fehlermeldungen generiert.</span><span class="sxs-lookup"><span data-stu-id="4f446-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="4f446-109">Gibt an, dass der Compiler keine Fehlermeldungen generiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4f446-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="4f446-110">Gibt an, dass der Compiler sollte eine Fehlermeldung generiert, wenn ein Feld, Eigenschaft, Ereignis, eine Methode oder Parameter wird außerhalb der Reihenfolge ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="4f446-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="4f446-111">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Methode außerhalb der Reihenfolge ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4f446-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="4f446-112">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Feld außerhalb der Reihenfolge ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4f446-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="4f446-113">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Parameter außerhalb der Reihenfolge ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4f446-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="4f446-114">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn eine Eigenschaft außerhalb der Reihenfolge ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4f446-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="4f446-115">Gibt an, dass der Compiler eine Fehlermeldung generieren soll, wenn ein Ereignis außerhalb der Reihenfolge ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4f446-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f446-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4f446-116">Requirements</span></span>  
 <span data-ttu-id="4f446-117">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f446-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f446-118">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="4f446-118">**Header:** CorHdr.h</span></span>  
  
 **<span data-ttu-id="4f446-119">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="4f446-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4f446-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f446-120">See also</span></span>

- [<span data-ttu-id="4f446-121">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="4f446-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
