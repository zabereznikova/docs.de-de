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
ms.openlocfilehash: 1eefd1ee5597ded269c56c05eec118b11294dd8a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732135"
---
# <a name="asm_display_flags-enumeration"></a><span data-ttu-id="5bd09-102">ASM_DISPLAY_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="5bd09-102">ASM_DISPLAY_FLAGS Enumeration</span></span>

<span data-ttu-id="5bd09-103">Gibt die Version, den Build, die Kultur, die Signatur usw. der Assembly an, deren Anzeige Name von der [IAssemblyName:: GetDisplayName](iassemblyname-getdisplayname-method.md) -Methode abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5bd09-103">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](iassemblyname-getdisplayname-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bd09-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5bd09-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="remarks"></a><span data-ttu-id="5bd09-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5bd09-105">Remarks</span></span>  

 <span data-ttu-id="5bd09-106">`ASM_DISPLAYF_FULL` spiegelt alle Änderungen wider, die an der Version des [IAssemblyName](iassemblyname-interface.md) -Objekts vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="5bd09-106">`ASM_DISPLAYF_FULL` reflects any changes made to the version of the [IAssemblyName](iassemblyname-interface.md) object.</span></span> <span data-ttu-id="5bd09-107">Gehen Sie nicht davon aus, dass der zurückgegebene Wert unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="5bd09-107">Do not assume that the returned value is immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bd09-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5bd09-108">Requirements</span></span>  

 <span data-ttu-id="5bd09-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bd09-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bd09-110">**Header:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="5bd09-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="5bd09-111">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="5bd09-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5bd09-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bd09-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bd09-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5bd09-113">See also</span></span>

- [<span data-ttu-id="5bd09-114">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5bd09-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="5bd09-115">Fusionsenumerationen</span><span class="sxs-lookup"><span data-stu-id="5bd09-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
