---
title: IAssemblyName::GetDisplayName-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyName.GetDisplayName
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 810192848e15a200a4b2eb33eaf60ddbd7c7c607
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="94b50-102">IAssemblyName::GetDisplayName-Methode</span><span class="sxs-lookup"><span data-stu-id="94b50-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="94b50-103">Ruft den lesbaren Namen der Assembly verwiesen wird, von diesem [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) Objekt.</span><span class="sxs-lookup"><span data-stu-id="94b50-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94b50-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="94b50-104">Syntax</span></span>  
  
```  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="94b50-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="94b50-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="94b50-106">[out] Der Zeichenfolgenpuffer mit dem Namen der Assembly, auf die verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="94b50-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="94b50-107">[in, out] Die Größe des `szDisplayName` in Breitzeichen, einschließlich eines null-Abschlusszeichens.</span><span class="sxs-lookup"><span data-stu-id="94b50-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="94b50-108">[in] Eine bitweise Kombination von [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) Werte, die die Funktionen von beeinflussen `szDisplayName`.</span><span class="sxs-lookup"><span data-stu-id="94b50-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94b50-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="94b50-109">Requirements</span></span>  
 <span data-ttu-id="94b50-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="94b50-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94b50-111">**Header:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="94b50-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="94b50-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94b50-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94b50-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="94b50-113">See Also</span></span>  
 [<span data-ttu-id="94b50-114">IAssemblyName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="94b50-114">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="94b50-115">Fusion-Enumerationen</span><span class="sxs-lookup"><span data-stu-id="94b50-115">Fusion Enumerations</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
