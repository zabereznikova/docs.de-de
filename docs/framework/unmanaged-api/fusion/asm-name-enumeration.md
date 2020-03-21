---
title: ASM_NAME-Enumeration
ms.date: 03/30/2017
api_name:
- ASM_NAME
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_NAME
helpviewer_keywords:
- ASM_NAME enumeration [.NET Framework fusion]
ms.assetid: c8b65b19-d777-428f-bc0c-0d84c78a37bc
topic_type:
- apiref
ms.openlocfilehash: fb77fe470829570d5abe291249eb7ef9023e6b14
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178313"
---
# <a name="asm_name-enumeration"></a><span data-ttu-id="053c8-102">ASM_NAME-Enumeration</span><span class="sxs-lookup"><span data-stu-id="053c8-102">ASM_NAME Enumeration</span></span>
<span data-ttu-id="053c8-103">Gibt die Version, den Build, die Kultur, die Signatur usw. der Assembly an, deren Eigenschaften von [IAssemblyName-Methoden](iassemblyname-interface.md) abgerufen oder festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="053c8-103">Indicates the version, build, culture, signature, and so on, of the assembly whose properties will be retrieved or set by [IAssemblyName](iassemblyname-interface.md) methods.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="053c8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="053c8-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
  
    ASM_NAME_PUBLIC_KEY = 0,  
    ASM_NAME_PUBLIC_KEY_TOKEN,  
    ASM_NAME_HASH_VALUE,  
    ASM_NAME_NAME,  
    ASM_NAME_MAJOR_VERSION,  
    ASM_NAME_MINOR_VERSION,  
    ASM_NAME_BUILD_NUMBER,  
    ASM_NAME_REVISION_NUMBER,  
    ASM_NAME_CULTURE,  
    ASM_NAME_PROCESSOR_ID_ARRAY,  
    ASM_NAME_OSINFO_ARRAY,  
    ASM_NAME_HASH_ALGID,  
    ASM_NAME_ALIAS,  
    ASM_NAME_CODEBASE_URL,  
    ASM_NAME_CODEBASE_LASTMOD,  
    ASM_NAME_NULL_PUBLIC_KEY,  
    ASM_NAME_NULL_PUBLIC_KEY_TOKEN,  
    ASM_NAME_CUSTOM,  
    ASM_NAME_NULL_CUSTOM,
    ASM_NAME_MVID,  
    ASM_NAME_FILE_MAJOR_VERSION,  
    ASM_NAME_FILE_MINOR_VERSION,  
    ASM_NAME_FILE_BUILD_NUMBER,  
    ASM_NAME_FILE_REVISION_NUMBER,  
    ASM_NAME_RETARGET,  
    ASM_NAME_SIGNATURE_BLOB,  
    ASM_NAME_CONFIG_MASK,  
    ASM_NAME_ARCHITECTURE,  
    ASM_NAME_MAX_PARAMS  
  
} ASM_NAME;  
```  
  
## <a name="requirements"></a><span data-ttu-id="053c8-105">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="053c8-105">Requirements</span></span>  
 <span data-ttu-id="053c8-106">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="053c8-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="053c8-107">**Kopfzeile:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="053c8-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="053c8-108">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="053c8-108">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="053c8-109">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="053c8-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053c8-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="053c8-110">See also</span></span>

- [<span data-ttu-id="053c8-111">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="053c8-111">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="053c8-112">Fusionsenumerationen</span><span class="sxs-lookup"><span data-stu-id="053c8-112">Fusion Enumerations</span></span>](fusion-enumerations.md)
