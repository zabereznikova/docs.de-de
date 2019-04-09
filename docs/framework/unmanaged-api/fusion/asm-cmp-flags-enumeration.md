---
title: ASM_CMP_FLAGS-Enumeration
ms.date: 03/30/2017
api_name:
- ASM_CMP_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- ASM_CMP_FLAGS
helpviewer_keywords:
- ASM_CMP_FLAGS enumeration [.NET Framework fusion]
ms.assetid: 4d1e6700-d4be-4fbd-8796-bfb4c07abbc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a37355365f337527bbc9254cae6e6f3d3f2f604
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216846"
---
# <a name="asmcmpflags-enumeration"></a><span data-ttu-id="7c790-102">ASM_CMP_FLAGS-Enumeration</span><span class="sxs-lookup"><span data-stu-id="7c790-102">ASM_CMP_FLAGS Enumeration</span></span>
<span data-ttu-id="7c790-103">Gibt an, die Version, Build, Kultur, Signatur und So weiter, der zwei Assemblys, die durch verglichen werden die [IAssemblyName:: IsEqual](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="7c790-103">Indicates the version, build, culture, signature, and so on, of two assemblies to be compared by the [IAssemblyName::IsEqual](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-isequal-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c790-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7c790-104">Syntax</span></span>  
  
```  
typedef enum {  
  
    ASM_CMPF_NAME                   = 0x1,  
    ASM_CMPF_MAJOR_VERSION          = 0x2,  
    ASM_CMPF_MINOR_VERSION          = 0x4,  
    ASM_CMPF_BUILD_NUMBER           = 0x8,  
    ASM_CMPF_REVISION_NUMBER        = 0x10,  
  
    ASM_CMPF_VERSION                =   
                 ASM_CMPF_MAJOR_VERSION |   
                 ASM_CMPF_MINOR_VERSION |   
                 ASM_CMPF_BUILD_NUMBER  |   
                 ASM_CMPF_REVISION_NUMBER,  
  
    ASM_CMPF_PUBLIC_KEY_TOKEN       = 0x20,  
    ASM_CMPF_CULTURE                = 0x40,  
    ASM_CMPF_CUSTOM                 = 0x80,  
    ASM_CMPF_DEFAULT                = 0x100,  
    ASM_CMPF_RETARGET               = 0x200,  
    ASM_CMPF_ARCHITECTURE           = 0x400,  
    ASM_CMPF_CONFIG_MASK            = 0x800,  
    ASM_CMPF_MVID                   = 0x1000,  
    ASM_CMPF_SIGNATURE              = 0x2000,  
  
    ASM_CMPF_IL_ALL                 =   
                 ASM_CMPF_NAME             |   
                 ASM_CMPF_VERSION          |   
                 ASM_CMPF_PUBLIC_KEY_TOKEN |   
                 ASM_CMPF_CULTURE,  
  
    ASM_CMPF_IL_NO_VERSION          =   
                 ASM_CMPF_NAME             |   
                 ASM_CMPF_PUBLIC_KEY_TOKEN |   
                 ASM_CMPF_CULTURE  
  
} ASM_CMP_FLAGS;  
```  
  
## <a name="requirements"></a><span data-ttu-id="7c790-105">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="7c790-105">Requirements</span></span>  
 <span data-ttu-id="7c790-106">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c790-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c790-107">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="7c790-107">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="7c790-108">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="7c790-108">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7c790-109">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="7c790-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7c790-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7c790-110">See also</span></span>

- [<span data-ttu-id="7c790-111">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7c790-111">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="7c790-112">Fusionsenumerationen</span><span class="sxs-lookup"><span data-stu-id="7c790-112">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
