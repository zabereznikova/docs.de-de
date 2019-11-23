---
title: IMetaDataImport::GetPinvokeMap-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
ms.openlocfilehash: c458fef77b49f522ca21dd5487731f4d43588cea
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437097"
---
# <a name="imetadataimportgetpinvokemap-method"></a><span data-ttu-id="e5aa1-102">IMetaDataImport::GetPinvokeMap-Methode</span><span class="sxs-lookup"><span data-stu-id="e5aa1-102">IMetaDataImport::GetPinvokeMap Method</span></span>
<span data-ttu-id="e5aa1-103">Ruft ein ModuleRef-Token zum Darstellen der Zielassembly eines PInvoke-Aufrufs ab.</span><span class="sxs-lookup"><span data-stu-id="e5aa1-103">Gets a ModuleRef token to represent the target assembly of a PInvoke call.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5aa1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e5aa1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5aa1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e5aa1-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e5aa1-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span><span class="sxs-lookup"><span data-stu-id="e5aa1-106">[in] A FieldDef or MethodDef token to get the PInvoke mapping metadata for.</span></span>  
  
 `pdwMappingFlags`  
 <span data-ttu-id="e5aa1-107">[out] A pointer to flags used for mapping.</span><span class="sxs-lookup"><span data-stu-id="e5aa1-107">[out] A pointer to flags used for mapping.</span></span> <span data-ttu-id="e5aa1-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span><span class="sxs-lookup"><span data-stu-id="e5aa1-108">This value is a bitmask from the [CorPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/corpinvokemap-enumeration.md) enumeration.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="e5aa1-109">[out] The name of the unmanaged target DLL.</span><span class="sxs-lookup"><span data-stu-id="e5aa1-109">[out] The name of the unmanaged target DLL.</span></span>  
  
 `cchImportName`  
 <span data-ttu-id="e5aa1-110">[in] The size in wide characters of `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="e5aa1-110">[in] The size in wide characters of `szImportName`.</span></span>  
  
 `pchImportName`  
 <span data-ttu-id="e5aa1-111">[out] The number of wide characters returned in `szImportName`.</span><span class="sxs-lookup"><span data-stu-id="e5aa1-111">[out] The number of wide characters returned in `szImportName`.</span></span>  
  
 `pmrImportDLL`  
 <span data-ttu-id="e5aa1-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span><span class="sxs-lookup"><span data-stu-id="e5aa1-112">[out] A pointer to a ModuleRef token that represents the unmanaged target object library.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5aa1-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e5aa1-113">Requirements</span></span>  
 <span data-ttu-id="e5aa1-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e5aa1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5aa1-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e5aa1-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5aa1-116">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e5aa1-116">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e5aa1-117">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5aa1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5aa1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5aa1-118">See also</span></span>

- [<span data-ttu-id="e5aa1-119">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5aa1-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="e5aa1-120">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e5aa1-120">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
