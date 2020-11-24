---
title: CorNativeLinkType-Enumeration
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
ms.openlocfilehash: c155373f7da47e904c94a44efa2fba42309d4218
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671355"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="24fb5-102">CorNativeLinkType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="24fb5-102">CorNativeLinkType Enumeration</span></span>

<span data-ttu-id="24fb5-103">Stellt Werte bereit, die den im systemeigenen Code verknüpften Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="24fb5-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24fb5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24fb5-104">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="24fb5-105">Member</span><span class="sxs-lookup"><span data-stu-id="24fb5-105">Members</span></span>  
  
|<span data-ttu-id="24fb5-106">Member</span><span class="sxs-lookup"><span data-stu-id="24fb5-106">Member</span></span>|<span data-ttu-id="24fb5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="24fb5-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="24fb5-108">Gibt an, dass keines der Schlüsselwörter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="24fb5-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="24fb5-109">Gibt an, dass ein ANSI-Schlüsselwort angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="24fb5-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="24fb5-110">Gibt an, dass ein Unicode-Schlüsselwort angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="24fb5-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="24fb5-111">Gibt an, dass ein Auto-Schlüsselwort angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="24fb5-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="24fb5-112">Gibt an, dass ein OLE-Schlüsselwort angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="24fb5-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="24fb5-113">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="24fb5-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24fb5-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="24fb5-114">Requirements</span></span>  

 <span data-ttu-id="24fb5-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24fb5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24fb5-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="24fb5-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="24fb5-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="24fb5-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="24fb5-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24fb5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24fb5-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="24fb5-119">See also</span></span>

- [<span data-ttu-id="24fb5-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="24fb5-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
