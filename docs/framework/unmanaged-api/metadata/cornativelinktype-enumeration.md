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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0f946179fc31adebc8e8fc67c394e0b55a876f49
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54641329"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="13cd5-102">CorNativeLinkType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="13cd5-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="13cd5-103">Stellt Werte bereit, die den im nativen Code verknüpften Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="13cd5-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13cd5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13cd5-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="13cd5-105">Member</span><span class="sxs-lookup"><span data-stu-id="13cd5-105">Members</span></span>  
  
|<span data-ttu-id="13cd5-106">Member</span><span class="sxs-lookup"><span data-stu-id="13cd5-106">Member</span></span>|<span data-ttu-id="13cd5-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="13cd5-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="13cd5-108">Gibt an, dass keines der Schlüsselwörter angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="13cd5-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="13cd5-109">Gibt an, dass ein ANSI-Schlüsselwort angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="13cd5-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="13cd5-110">Gibt an, dass ein Unicode-Schlüsselwort angegeben wird</span><span class="sxs-lookup"><span data-stu-id="13cd5-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="13cd5-111">Gibt an, dass ein Schlüsselwort "Auto" angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="13cd5-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="13cd5-112">Gibt an, dass ein OLE-Schlüsselwort angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="13cd5-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="13cd5-113">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="13cd5-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13cd5-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13cd5-114">Requirements</span></span>  
 <span data-ttu-id="13cd5-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13cd5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13cd5-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13cd5-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13cd5-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="13cd5-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13cd5-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13cd5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13cd5-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13cd5-119">See also</span></span>
- [<span data-ttu-id="13cd5-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="13cd5-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
