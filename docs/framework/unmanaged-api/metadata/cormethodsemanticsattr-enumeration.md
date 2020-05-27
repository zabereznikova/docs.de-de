---
title: CorMethodSemanticsAttr-Enumeration
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 1572c206f4a5a5fe0fd189ca84d0bcda2249c6d4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007649"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="77052-102">CorMethodSemanticsAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="77052-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="77052-103">Enthält Werte, die die Beziehung zwischen einer Methode und einer zugeordneten Eigenschaft oder einem zugeordneten Ereignis beschreiben.</span><span class="sxs-lookup"><span data-stu-id="77052-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77052-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="77052-104">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="77052-105">Member</span><span class="sxs-lookup"><span data-stu-id="77052-105">Members</span></span>  
  
|<span data-ttu-id="77052-106">Member</span><span class="sxs-lookup"><span data-stu-id="77052-106">Member</span></span>|<span data-ttu-id="77052-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="77052-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="77052-108">Gibt an, dass die Methode ein- `set` Accessor für eine Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="77052-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="77052-109">Gibt an, dass die Methode ein- `get` Accessor für eine Eigenschaft ist.</span><span class="sxs-lookup"><span data-stu-id="77052-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="77052-110">Gibt an, dass die Methode eine Beziehung zu einer Eigenschaft oder einem Ereignis aufweist, das nicht hier definiert ist.</span><span class="sxs-lookup"><span data-stu-id="77052-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="77052-111">Gibt an, dass die Methode Handlermethoden für ein Ereignis hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="77052-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="77052-112">Gibt an, dass die Methode Handlermethoden für ein Ereignis entfernt.</span><span class="sxs-lookup"><span data-stu-id="77052-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="77052-113">Gibt an, dass die Methode ein Ereignis auslöst.</span><span class="sxs-lookup"><span data-stu-id="77052-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="77052-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="77052-114">Requirements</span></span>  
 <span data-ttu-id="77052-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77052-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77052-116">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="77052-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="77052-117">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77052-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77052-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="77052-118">See also</span></span>

- [<span data-ttu-id="77052-119">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="77052-119">Metadata Enumerations</span></span>](metadata-enumerations.md)
