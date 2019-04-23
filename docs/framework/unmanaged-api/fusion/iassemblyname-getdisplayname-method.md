---
title: IAssemblyName::GetDisplayName-Methode
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 323c883b4010f3ddd4c575e5d5fc40a3419e57c2
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59214363"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="24f7b-102">IAssemblyName::GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="24f7b-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="24f7b-103">Ruft den lesbaren Namen der Assembly verwiesen wird, von diesem [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="24f7b-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24f7b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24f7b-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="24f7b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="24f7b-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="24f7b-106">[out] Der Puffer mit dem Namen der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="24f7b-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="24f7b-107">[in, out] Die Größe des `szDisplayName` in Breitzeichen, einschließlich eines null-Abschlusszeichens.</span><span class="sxs-lookup"><span data-stu-id="24f7b-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="24f7b-108">[in] Eine bitweise Kombination von [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) Werte, die die Features von beeinflussen `szDisplayName`.</span><span class="sxs-lookup"><span data-stu-id="24f7b-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24f7b-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24f7b-109">Requirements</span></span>  
 <span data-ttu-id="24f7b-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24f7b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24f7b-111">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="24f7b-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="24f7b-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24f7b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24f7b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24f7b-113">See also</span></span>

- [<span data-ttu-id="24f7b-114">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24f7b-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="24f7b-115">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="24f7b-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
