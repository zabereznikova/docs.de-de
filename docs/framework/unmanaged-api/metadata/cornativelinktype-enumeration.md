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
ms.openlocfilehash: 66d650adb39a9c7dade0936ec671ae5a8b4aeecd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045468"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="33676-102">CorNativeLinkType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="33676-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="33676-103">Stellt Werte bereit, die den im systemeigenen Code verknüpften Typ angeben.</span><span class="sxs-lookup"><span data-stu-id="33676-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33676-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="33676-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="33676-105">Member</span><span class="sxs-lookup"><span data-stu-id="33676-105">Members</span></span>  
  
|<span data-ttu-id="33676-106">Member</span><span class="sxs-lookup"><span data-stu-id="33676-106">Member</span></span>|<span data-ttu-id="33676-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="33676-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="33676-108">Gibt an, dass keines der Schlüsselwörter angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="33676-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="33676-109">Gibt an, dass ein ANSI-Schlüsselwort angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="33676-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="33676-110">Gibt an, dass ein Unicode-Schlüsselwort angegeben wird</span><span class="sxs-lookup"><span data-stu-id="33676-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="33676-111">Gibt an, dass ein Schlüsselwort "Auto" angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="33676-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="33676-112">Gibt an, dass ein OLE-Schlüsselwort angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="33676-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="33676-113">Nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="33676-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="33676-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="33676-114">Requirements</span></span>  
 <span data-ttu-id="33676-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="33676-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33676-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="33676-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33676-117">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="33676-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33676-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33676-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33676-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="33676-119">See also</span></span>

- [<span data-ttu-id="33676-120">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="33676-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
