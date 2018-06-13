---
title: CorValidatorModuleType-Enumeration
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 97e9ae5a7c35b4f9b6e2b4ca7e754b5b7480dfa6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444138"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="92976-102">CorValidatorModuleType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="92976-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="92976-103">Gibt den Typ eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="92976-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92976-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="92976-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="92976-105">Member</span><span class="sxs-lookup"><span data-stu-id="92976-105">Members</span></span>  
  
|<span data-ttu-id="92976-106">Member</span><span class="sxs-lookup"><span data-stu-id="92976-106">Member</span></span>|<span data-ttu-id="92976-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="92976-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="92976-108">Das Modul ist ein ungültiger Typ.</span><span class="sxs-lookup"><span data-stu-id="92976-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="92976-109">Der Minimalwert der der `CorValidatorModuleType` Enum.</span><span class="sxs-lookup"><span data-stu-id="92976-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="92976-110">Das Modul ist eine PE (portable Executable)-Datei.</span><span class="sxs-lookup"><span data-stu-id="92976-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="92976-111">Das Modul ist eine OBJ-Datei.</span><span class="sxs-lookup"><span data-stu-id="92976-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="92976-112">Das Modul ist eine Debugsitzung mit bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="92976-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="92976-113">Das Modul ist eine, die inkrementell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="92976-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="92976-114">Der Maximalwert der der `CorValidatorModuleType` Enum.</span><span class="sxs-lookup"><span data-stu-id="92976-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="92976-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="92976-115">Requirements</span></span>  
 <span data-ttu-id="92976-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92976-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92976-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="92976-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="92976-118">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="92976-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="92976-119">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92976-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92976-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="92976-120">See Also</span></span>  
 [<span data-ttu-id="92976-121">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="92976-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
