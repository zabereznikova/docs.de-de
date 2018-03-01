---
title: CorValidatorModuleType-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3367f6928b5d7378b2686185ee3e03d0279cc11d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="64015-102">CorValidatorModuleType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="64015-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="64015-103">Gibt den Typ eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="64015-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64015-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="64015-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a><span data-ttu-id="64015-105">Member</span><span class="sxs-lookup"><span data-stu-id="64015-105">Members</span></span>  
  
|<span data-ttu-id="64015-106">Member</span><span class="sxs-lookup"><span data-stu-id="64015-106">Member</span></span>|<span data-ttu-id="64015-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64015-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="64015-108">Das Modul ist ein ungültiger Typ.</span><span class="sxs-lookup"><span data-stu-id="64015-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="64015-109">Der Minimalwert der der `CorValidatorModuleType` Enum.</span><span class="sxs-lookup"><span data-stu-id="64015-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="64015-110">Das Modul ist eine PE (portable Executable)-Datei.</span><span class="sxs-lookup"><span data-stu-id="64015-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="64015-111">Das Modul ist eine OBJ-Datei.</span><span class="sxs-lookup"><span data-stu-id="64015-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="64015-112">Das Modul ist eine Debugsitzung mit bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="64015-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="64015-113">Das Modul ist eine, die inkrementell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="64015-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="64015-114">Der Maximalwert der der `CorValidatorModuleType` Enum.</span><span class="sxs-lookup"><span data-stu-id="64015-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="64015-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="64015-115">Requirements</span></span>  
 <span data-ttu-id="64015-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64015-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64015-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="64015-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64015-118">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="64015-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="64015-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64015-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64015-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64015-120">See Also</span></span>  
 [<span data-ttu-id="64015-121">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="64015-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
