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
ms.openlocfilehash: 29f2401e2e3faccae05ca5249fcd7d9e89aacb46
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007610"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="4af25-102">CorNativeLinkType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="4af25-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="4af25-103">Stellt Werte bereit, die den im systemeigenen Code verknüpften Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="4af25-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4af25-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4af25-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="4af25-105">Member</span><span class="sxs-lookup"><span data-stu-id="4af25-105">Members</span></span>  
  
|<span data-ttu-id="4af25-106">Member</span><span class="sxs-lookup"><span data-stu-id="4af25-106">Member</span></span>|<span data-ttu-id="4af25-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4af25-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="4af25-108">Gibt an, dass keines der Schlüsselwörter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4af25-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="4af25-109">Gibt an, dass ein ANSI-Schlüsselwort angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4af25-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="4af25-110">Gibt an, dass ein Unicode-Schlüsselwort angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="4af25-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="4af25-111">Gibt an, dass ein Auto-Schlüsselwort angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4af25-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="4af25-112">Gibt an, dass ein OLE-Schlüsselwort angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4af25-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="4af25-113">Wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="4af25-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4af25-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4af25-114">Requirements</span></span>  
 <span data-ttu-id="4af25-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4af25-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4af25-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4af25-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4af25-117">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4af25-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4af25-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4af25-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4af25-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4af25-119">See also</span></span>

- [<span data-ttu-id="4af25-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="4af25-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
