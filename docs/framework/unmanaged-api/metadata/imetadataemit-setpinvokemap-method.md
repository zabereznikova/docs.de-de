---
title: IMetaDataEmit::SetPinvokeMap-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: 4c68754bc44fe035fd8e7143c52895928beae395
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175589"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="b1ba2-102">IMetaDataEmit::SetPinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="b1ba2-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="b1ba2-103">Legt Features der PInvoke-Signatur einer Methode fest oder ändert diese, wie durch einen vorherigen Aufruf von [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)definiert.</span><span class="sxs-lookup"><span data-stu-id="b1ba2-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1ba2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1ba2-104">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b1ba2-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b1ba2-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="b1ba2-106">[in] Die `mdToken` Zuordnungsinformationen, auf die angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="b1ba2-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="b1ba2-107">[in] Flags, die von PInvoke für die Zuordnung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b1ba2-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="b1ba2-108">Dies ist eine `CorPinvokeMap` Bitmaske von Werten.</span><span class="sxs-lookup"><span data-stu-id="b1ba2-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="b1ba2-109">[in] Der Name des Zielexports in der systemeigenen DLL.</span><span class="sxs-lookup"><span data-stu-id="b1ba2-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="b1ba2-110">[in] Das `mdModuleRef` Token für die nicht verwaltete Ziel-DLL.</span><span class="sxs-lookup"><span data-stu-id="b1ba2-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1ba2-111">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="b1ba2-111">Requirements</span></span>  
 <span data-ttu-id="b1ba2-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1ba2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1ba2-113">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b1ba2-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b1ba2-114">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="b1ba2-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b1ba2-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b1ba2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1ba2-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1ba2-116">See also</span></span>

- [<span data-ttu-id="b1ba2-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1ba2-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b1ba2-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b1ba2-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
