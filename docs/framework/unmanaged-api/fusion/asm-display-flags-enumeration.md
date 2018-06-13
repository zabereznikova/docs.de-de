---
title: ASM_DISPLAY_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- ASM_DISPLAY_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_DISPLAY_FLAGS
helpviewer_keywords:
- ASM_DISPLAY_FLAGS enumeration [.NET Framework fusion]
ms.assetid: dbade6c9-9d26-4a79-9fd2-46108edd12d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9607aa99e1f1dbe0af3a868a32c70cd83d5e66a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429529"
---
# <a name="asmdisplayflags-enumeration"></a><span data-ttu-id="d1ad0-102">ASM_DISPLAY_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="d1ad0-102">ASM_DISPLAY_FLAGS Enumeration</span></span>
<span data-ttu-id="d1ad0-103">Gibt an, die Version, Build, Kultur, Signatur und usw., der die Assembly, deren Anzeigename abgerufen werden soll, indem, die [IAssemblyName:: GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="d1ad0-103">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1ad0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1ad0-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    ASM_DISPLAYF_VERSION                 = 0x01,  
    ASM_DISPLAYF_CULTURE                 = 0x02,  
    ASM_DISPLAYF_PUBLIC_KEY_TOKEN        = 0x04,  
    ASM_DISPLAYF_PUBLIC_KEY              = 0x08,  
    ASM_DISPLAYF_CUSTOM                  = 0x10,  
    ASM_DISPLAYF_PROCESSORARCHITECTURE   = 0x20,  
    ASM_DISPLAYF_LANGUAGEID              = 0x40,  
    ASM_DISPLAYF_RETARGET                = 0x80,  
    ASM_DISPLAYF_CONFIG_MASK             = 0x100,  
    ASM_DISPLAYF_MVID                    = 0x200,  
    ASM_DISPLAYF_FULL                    =   
                      ASM_DISPLAYF_VERSION           |   
                      ASM_DISPLAYF_CULTURE           |   
                      ASM_DISPLAYF_PUBLIC_KEY_TOKEN  |   
                      ASM_DISPLAYF_RETARGET          |   
                      ASM_DISPLAYF_PROCESSORARCHITECTURE  
  
} ASM_DISPLAY_FLAGS;  
```  
  
## <a name="remarks"></a><span data-ttu-id="d1ad0-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d1ad0-105">Remarks</span></span>  
 <span data-ttu-id="d1ad0-106">`ASM_DISPLAYF_FULL` Gibt alle Änderungen auf die Version von den [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="d1ad0-106">`ASM_DISPLAYF_FULL` reflects any changes made to the version of the [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span> <span data-ttu-id="d1ad0-107">Führen Sie Sie nicht davon gehen Sie aus, dass der zurückgegebene Wert unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d1ad0-107">Do not assume that the returned value is immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1ad0-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d1ad0-108">Requirements</span></span>  
 <span data-ttu-id="d1ad0-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1ad0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1ad0-110">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="d1ad0-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="d1ad0-111">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d1ad0-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d1ad0-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1ad0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1ad0-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1ad0-113">See Also</span></span>  
 [<span data-ttu-id="d1ad0-114">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d1ad0-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="d1ad0-115">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="d1ad0-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
