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
ms.openlocfilehash: 2fb7f11677870f7d53439f1867f167fabe70b22a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723843"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="10ded-102">CorValidatorModuleType-Enumeration</span><span class="sxs-lookup"><span data-stu-id="10ded-102">CorValidatorModuleType Enumeration</span></span>

<span data-ttu-id="10ded-103">Gibt den Typ eines Moduls an.</span><span class="sxs-lookup"><span data-stu-id="10ded-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10ded-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="10ded-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="10ded-105">Member</span><span class="sxs-lookup"><span data-stu-id="10ded-105">Members</span></span>  
  
|<span data-ttu-id="10ded-106">Member</span><span class="sxs-lookup"><span data-stu-id="10ded-106">Member</span></span>|<span data-ttu-id="10ded-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="10ded-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="10ded-108">Das Modul ist ein ungültiger Typ.</span><span class="sxs-lookup"><span data-stu-id="10ded-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="10ded-109">Der minimale Wert der Enumeration `CorValidatorModuleType` .</span><span class="sxs-lookup"><span data-stu-id="10ded-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="10ded-110">Das Modul ist eine portable ausführbare Datei (PE).</span><span class="sxs-lookup"><span data-stu-id="10ded-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="10ded-111">Das Modul ist eine OBJ-Datei.</span><span class="sxs-lookup"><span data-stu-id="10ded-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="10ded-112">Das Modul ist eine Debugger-Sitzung zum Bearbeiten und fortfahren.</span><span class="sxs-lookup"><span data-stu-id="10ded-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="10ded-113">Dabei handelt es sich um ein Modul, das inkrementell erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="10ded-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="10ded-114">Der maximale Wert der Enumeration `CorValidatorModuleType` .</span><span class="sxs-lookup"><span data-stu-id="10ded-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="10ded-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="10ded-115">Requirements</span></span>  

 <span data-ttu-id="10ded-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10ded-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10ded-117">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="10ded-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="10ded-118">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="10ded-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="10ded-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10ded-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10ded-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10ded-120">See also</span></span>

- [<span data-ttu-id="10ded-121">Metadatenenumerationen</span><span class="sxs-lookup"><span data-stu-id="10ded-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
