---
title: CorRefToDefCheck-Enumeration
ms.date: 03/30/2017
api_name:
- CorRefToDefCheck
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRefToDefCheck
helpviewer_keywords:
- CorRefToDefCheck enumeration [.NET Framework metadata]
ms.assetid: f9a80f1a-55af-4459-b095-8441aae16119
topic_type:
- apiref
ms.openlocfilehash: e7ce604acddb88d5a15844cbce2622b21e364cc1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95706111"
---
# <a name="correftodefcheck-enumeration"></a><span data-ttu-id="9a6c7-102">CorRefToDefCheck-Enumeration</span><span class="sxs-lookup"><span data-stu-id="9a6c7-102">CorRefToDefCheck Enumeration</span></span>

<span data-ttu-id="9a6c7-103">Gibt Flags an, mit denen gesteuert wird, welche Elemente, auf die verwiesen wird, zur Optimierung des Codes in ihre Definitionen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-103">Specifies flags to control which referenced items are converted to their definitions in order to optimize the code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a6c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9a6c7-104">Syntax</span></span>  
  
```cpp  
typedef enum CorRefToDefCheck {  
    MDRefToDefDefault           = 0x00000003,  
    MDRefToDefAll               = 0xffffffff,  
    MDRefToDefNone              = 0x00000000,  
    MDTypeRefToDef              = 0x00000001,  
    MDMemberRefToDef            = 0x00000002  
} CorRefToDefCheck;  
```  
  
## <a name="members"></a><span data-ttu-id="9a6c7-105">Member</span><span class="sxs-lookup"><span data-stu-id="9a6c7-105">Members</span></span>  
  
|<span data-ttu-id="9a6c7-106">Member</span><span class="sxs-lookup"><span data-stu-id="9a6c7-106">Member</span></span>|<span data-ttu-id="9a6c7-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="9a6c7-107">Description</span></span>|  
|------------|-----------------|  
|`MDRefToDefDefault`|<span data-ttu-id="9a6c7-108">Gibt an, dass Typverweise und Element Verweise in Definitionen konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-108">Specifies that type references and member references should be converted to definitions.</span></span> <span data-ttu-id="9a6c7-109">Dies ist der Standardwert ( `MDTypeRefToDef` &#124; `MDMemberRefToDef` ).</span><span class="sxs-lookup"><span data-stu-id="9a6c7-109">This is the default value (`MDTypeRefToDef` &#124; `MDMemberRefToDef`).</span></span>|  
|`MDRefToDefAll`|<span data-ttu-id="9a6c7-110">Gibt an, dass alle referenzierten Elemente in Definitionen konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-110">Specifies that all referenced items should be converted to definitions.</span></span>|  
|`MDRefToDefNone`|<span data-ttu-id="9a6c7-111">Gibt an, dass keine referenzierten Elemente in Definitionen konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-111">Specifies that no referenced items should be converted to definitions.</span></span>|  
|`MDTypeRefToDef`|<span data-ttu-id="9a6c7-112">Gibt an, dass nur Typverweise in Typdefinitionen konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-112">Specifies that only type references should be converted to type definitions.</span></span>|  
|`MDMemberRefToDef`|<span data-ttu-id="9a6c7-113">Gibt an, dass nur Member-Verweise in Definitionen konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-113">Specifies that only member references should be converted to definitions.</span></span> <span data-ttu-id="9a6c7-114">Das heißt, dass Element Verweise entweder in Methoden Definitionen oder Feld Definitionen konvertiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="9a6c7-114">That is, member references should be converted to either method definitions or field definitions.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a6c7-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="9a6c7-115">Requirements</span></span>  

 <span data-ttu-id="9a6c7-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a6c7-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a6c7-117">**Header:** Corhdr. h</span><span class="sxs-lookup"><span data-stu-id="9a6c7-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="9a6c7-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a6c7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6c7-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9a6c7-119">See also</span></span>

- [<span data-ttu-id="9a6c7-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="9a6c7-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
