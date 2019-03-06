---
title: IMetaDataImport::GetParamProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ed9bae4fde96f0878e40ed73b81cc8776571ada5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57468057"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="90043-102">IMetaDataImport::GetParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="90043-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="90043-103">Ruft Metadatenwerte für den Parameter ab, auf den durch das angegebene ParamDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="90043-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90043-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="90043-104">Syntax</span></span>  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90043-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="90043-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="90043-106">[in] Ein ParamDef-Token, das die Parameter für die Metadaten zurückgegeben darstellt.</span><span class="sxs-lookup"><span data-stu-id="90043-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="90043-107">[out] Ein Zeiger auf ein MethodDef-Token, das die Methode, die den Parameter akzeptiert darstellt.</span><span class="sxs-lookup"><span data-stu-id="90043-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="90043-108">[out] Die Ordnungsposition des Parameters in der Argumentliste für die Methode.</span><span class="sxs-lookup"><span data-stu-id="90043-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="90043-109">[out] Ein Puffer, der den Namen des Parameters enthält.</span><span class="sxs-lookup"><span data-stu-id="90043-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="90043-110">[in] Die angeforderte Größe in Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="90043-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="90043-111">[out] Die zurückgegebene Größe in Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="90043-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="90043-112">[out] Ein Zeiger auf die Attributflags, die dem Parameter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="90043-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="90043-113">Dies ist eine Bitmaske der `CorParamAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="90043-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="90043-114">[out] Ein Zeiger auf ein Flag, der angibt, der Parameter ist, ein <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="90043-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="90043-115">[out] Ein Zeiger auf eine Konstante Zeichenfolge, die durch den Parameter zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="90043-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="90043-116">[out] Die Größe des `ppValue` in Breitzeichen oder NULL, wenn `ppValue` errichtet keine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="90043-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90043-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="90043-117">Remarks</span></span>

<span data-ttu-id="90043-118">Die Sequenzwerte `pulSequence` beginnen mit 1 für Parameter.</span><span class="sxs-lookup"><span data-stu-id="90043-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="90043-119">Ein Wert zurückgegeben hat eine Sequenznummer 0.</span><span class="sxs-lookup"><span data-stu-id="90043-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="90043-120">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="90043-120">Requirements</span></span>  
 <span data-ttu-id="90043-121">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90043-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90043-122">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="90043-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90043-123">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="90043-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90043-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90043-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90043-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90043-125">See also</span></span>
- [<span data-ttu-id="90043-126">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90043-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="90043-127">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="90043-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
