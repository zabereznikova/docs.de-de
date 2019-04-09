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
ms.openlocfilehash: 14eee096c25967d321e4693b260501827d944a80
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59154179"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="52fc2-102">CorValidatorModuleType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="52fc2-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="52fc2-103">Gibt den Typ eines Moduls.</span><span class="sxs-lookup"><span data-stu-id="52fc2-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52fc2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="52fc2-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="52fc2-105">Member</span><span class="sxs-lookup"><span data-stu-id="52fc2-105">Members</span></span>  
  
|<span data-ttu-id="52fc2-106">Member</span><span class="sxs-lookup"><span data-stu-id="52fc2-106">Member</span></span>|<span data-ttu-id="52fc2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="52fc2-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="52fc2-108">Das Modul ist ein ungültiger Typ.</span><span class="sxs-lookup"><span data-stu-id="52fc2-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="52fc2-109">Der minimale Wert des der `CorValidatorModuleType` Enum.</span><span class="sxs-lookup"><span data-stu-id="52fc2-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="52fc2-110">Das Modul ist eine Datei (portable Executable)-Datei.</span><span class="sxs-lookup"><span data-stu-id="52fc2-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="52fc2-111">Das Modul ist eine OBJ-Datei.</span><span class="sxs-lookup"><span data-stu-id="52fc2-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="52fc2-112">Das Modul ist eine Debugsitzung mit bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="52fc2-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="52fc2-113">Das Modul ist ein, die inkrementell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="52fc2-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="52fc2-114">Der maximale Wert, der die `CorValidatorModuleType` Enum.</span><span class="sxs-lookup"><span data-stu-id="52fc2-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="52fc2-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="52fc2-115">Requirements</span></span>  
 <span data-ttu-id="52fc2-116">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52fc2-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52fc2-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="52fc2-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="52fc2-118">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="52fc2-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="52fc2-119">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="52fc2-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="52fc2-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="52fc2-120">See also</span></span>

- [<span data-ttu-id="52fc2-121">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="52fc2-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
