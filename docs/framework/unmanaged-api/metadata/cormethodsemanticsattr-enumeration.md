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
ms.openlocfilehash: de467c98dfa7ad3eac69502f2afe311b301e1ec5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444808"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="2e3ae-102">CorMethodSemanticsAttr-Enumeration</span><span class="sxs-lookup"><span data-stu-id="2e3ae-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="2e3ae-103">Enthält Werte, die die Beziehung zwischen einer Methode und einer zugeordneten Eigenschaft oder einem zugeordneten Ereignis beschreiben.</span><span class="sxs-lookup"><span data-stu-id="2e3ae-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e3ae-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e3ae-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="2e3ae-105">Member</span><span class="sxs-lookup"><span data-stu-id="2e3ae-105">Members</span></span>  
  
|<span data-ttu-id="2e3ae-106">Member</span><span class="sxs-lookup"><span data-stu-id="2e3ae-106">Member</span></span>|<span data-ttu-id="2e3ae-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e3ae-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="2e3ae-108">Gibt an, dass die Methode ist ein `set` -Accessor für eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2e3ae-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="2e3ae-109">Gibt an, dass die Methode ist ein `get` -Accessor für eine Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="2e3ae-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="2e3ae-110">Gibt an, dass die Methode eine Beziehung zu einer Eigenschaft oder ein Ereignis als diejenigen, die hier definiert.</span><span class="sxs-lookup"><span data-stu-id="2e3ae-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="2e3ae-111">Gibt an, dass die Methode Handlermethoden für ein Ereignis hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="2e3ae-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="2e3ae-112">Gibt an, dass die Methode Handlermethoden für ein Ereignis entfernt.</span><span class="sxs-lookup"><span data-stu-id="2e3ae-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="2e3ae-113">Gibt an, dass die Methode löst ein Ereignis aus.</span><span class="sxs-lookup"><span data-stu-id="2e3ae-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e3ae-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2e3ae-114">Requirements</span></span>  
 <span data-ttu-id="2e3ae-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e3ae-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e3ae-116">**Header:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="2e3ae-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="2e3ae-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e3ae-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e3ae-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e3ae-118">See Also</span></span>  
 [<span data-ttu-id="2e3ae-119">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="2e3ae-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
