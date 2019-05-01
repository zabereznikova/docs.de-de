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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5e36cb91c3ef741badb04b54e2b62158ecf6ced1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045629"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="0fa3b-102">CorMethodSemanticsAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="0fa3b-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="0fa3b-103">Enthält Werte, die die Beziehung zwischen einer Methode und einer zugeordneten Eigenschaft oder einem zugeordneten Ereignis beschreiben.</span><span class="sxs-lookup"><span data-stu-id="0fa3b-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fa3b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0fa3b-104">Syntax</span></span>  
  
```  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="0fa3b-105">Member</span><span class="sxs-lookup"><span data-stu-id="0fa3b-105">Members</span></span>  
  
|<span data-ttu-id="0fa3b-106">Member</span><span class="sxs-lookup"><span data-stu-id="0fa3b-106">Member</span></span>|<span data-ttu-id="0fa3b-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0fa3b-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="0fa3b-108">Gibt an, dass die Methode ist eine `set` Accessor für eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0fa3b-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="0fa3b-109">Gibt an, dass die Methode ist eine `get` Accessor für eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="0fa3b-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="0fa3b-110">Gibt an, dass die Methode eine Beziehung auf eine Eigenschaft oder ein Ereignis als die hier definiert.</span><span class="sxs-lookup"><span data-stu-id="0fa3b-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="0fa3b-111">Gibt an, dass die Methode Handlermethoden für ein Ereignis hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0fa3b-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="0fa3b-112">Gibt an, dass die Methode Handlermethoden für ein Ereignis entfernt.</span><span class="sxs-lookup"><span data-stu-id="0fa3b-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="0fa3b-113">Gibt an, dass die Methode löst ein Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="0fa3b-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0fa3b-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0fa3b-114">Requirements</span></span>  
 <span data-ttu-id="0fa3b-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fa3b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fa3b-116">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="0fa3b-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="0fa3b-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fa3b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa3b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fa3b-118">See also</span></span>

- [<span data-ttu-id="0fa3b-119">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="0fa3b-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
