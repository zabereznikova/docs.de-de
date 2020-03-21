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
ms.openlocfilehash: ebaab57b647250823443b48d9e45921036372d5e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176603"
---
# <a name="asm_display_flags-enumeration"></a><span data-ttu-id="78074-102">ASM_DISPLAY_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="78074-102">ASM_DISPLAY_FLAGS Enumeration</span></span>
<span data-ttu-id="78074-103">Gibt die Version, den Build, die Kultur, die Signatur usw. der Assembly an, deren Anzeigename von der [IAssemblyName::GetDisplayName-Methode](iassemblyname-getdisplayname-method.md) abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="78074-103">Indicates the version, build, culture, signature, and so on, of the assembly whose display name will be retrieved by the [IAssemblyName::GetDisplayName](iassemblyname-getdisplayname-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78074-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="78074-104">Syntax</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="78074-105">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="78074-105">Remarks</span></span>  
 <span data-ttu-id="78074-106">`ASM_DISPLAYF_FULL`spiegelt alle Änderungen wider, die an der Version des [IAssemblyName-Objekts](iassemblyname-interface.md) vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="78074-106">`ASM_DISPLAYF_FULL` reflects any changes made to the version of the [IAssemblyName](iassemblyname-interface.md) object.</span></span> <span data-ttu-id="78074-107">Gehen Sie nicht davon aus, dass der zurückgegebene Wert unveränderlich ist.</span><span class="sxs-lookup"><span data-stu-id="78074-107">Do not assume that the returned value is immutable.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="78074-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="78074-108">Requirements</span></span>  
 <span data-ttu-id="78074-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="78074-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78074-110">**Kopfzeile:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="78074-110">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="78074-111">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="78074-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="78074-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="78074-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78074-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="78074-113">See also</span></span>

- [<span data-ttu-id="78074-114">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="78074-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="78074-115">Fusionsenumerationen</span><span class="sxs-lookup"><span data-stu-id="78074-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
