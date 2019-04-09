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
ms.openlocfilehash: cbcff46b1932f3293fba4fda922e78f3b9ac37b0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59148849"
---
# <a name="asmdisplayflags-enumeration"></a><span data-ttu-id="3bfd1-102">ASM_DISPLAY_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="3bfd1-102">ASM_DISPLAY_FLAGS Enumeration</span></span>
<span data-ttu-id="3bfd1-103">Gibt an, die Version, Build, Kultur, Signatur und So weiter, der die Assembly, deren Anzeigename abgerufen werden soll, indem, die [IAssemblyName:: GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="3bfd1-103">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-getdisplayname-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bfd1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bfd1-104">Syntax</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="3bfd1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3bfd1-105">Remarks</span></span>  
 `ASM_DISPLAYF_FULL` <span data-ttu-id="3bfd1-106">Gibt alle Änderungen, die auf die Version von der [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="3bfd1-106">reflects any changes made to the version of the [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span> <span data-ttu-id="3bfd1-107">Führen Sie Sie nicht davon gehen Sie aus, dass der zurückgegebene Wert unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3bfd1-107">Do not assume that the returned value is immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bfd1-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3bfd1-108">Requirements</span></span>  
 <span data-ttu-id="3bfd1-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bfd1-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bfd1-110">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="3bfd1-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3bfd1-111">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3bfd1-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="3bfd1-112">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="3bfd1-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3bfd1-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bfd1-113">See also</span></span>

- [<span data-ttu-id="3bfd1-114">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3bfd1-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="3bfd1-115">Fusionsenumerationen</span><span class="sxs-lookup"><span data-stu-id="3bfd1-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
