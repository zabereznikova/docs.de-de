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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ed2c818ce9e11ff6eca26ac1c6f13b19668551b7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485329"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="1a848-102">IMetaDataEmit::SetPinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="1a848-102">IMetaDataEmit::SetPinvokeMap Method</span></span>
<span data-ttu-id="1a848-103">Legt fest oder ändert Sie Features von PInvoke-Signatur einer Methode, gemäß einem vorherigen Aufruf von [IMetaDataEmit:: DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span><span class="sxs-lookup"><span data-stu-id="1a848-103">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a848-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1a848-104">Syntax</span></span>  
  
```  
HRESULT SetPinvokeMap (   
    [in]  mdToken      tk,   
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,   
    [in]  mdModuleRef  mrImportDLL   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1a848-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1a848-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="1a848-106">[in] Die `mdToken` für die Zuordnung Informationen gilt.</span><span class="sxs-lookup"><span data-stu-id="1a848-106">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="1a848-107">[in] Flags, die von PInvoke verwendet, um die Zuordnung vornehmen.</span><span class="sxs-lookup"><span data-stu-id="1a848-107">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="1a848-108">Dies ist eine Bitmaske der `CorPinvokeMap` Werte.</span><span class="sxs-lookup"><span data-stu-id="1a848-108">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="1a848-109">[in] Der Name des Ziels in der systemeigenen DLL exportieren.</span><span class="sxs-lookup"><span data-stu-id="1a848-109">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="1a848-110">[in] Die `mdModuleRef` token für das Ziel nicht verwalteten DLL.</span><span class="sxs-lookup"><span data-stu-id="1a848-110">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1a848-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1a848-111">Requirements</span></span>  
 <span data-ttu-id="1a848-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a848-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a848-113">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1a848-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1a848-114">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="1a848-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1a848-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a848-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a848-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a848-116">See also</span></span>
- [<span data-ttu-id="1a848-117">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a848-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1a848-118">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1a848-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
