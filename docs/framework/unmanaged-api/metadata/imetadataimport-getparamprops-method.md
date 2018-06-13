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
ms.openlocfilehash: 95850448504fd863f2726a7fb7574436476a6dc5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449324"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="e43ec-102">IMetaDataImport::GetParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="e43ec-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="e43ec-103">Ruft Metadatenwerte für den Parameter ab, auf den durch das angegebene ParamDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="e43ec-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e43ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e43ec-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="e43ec-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="e43ec-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="e43ec-106">[in] Ein ParamDef-Token, die Metadaten für die zurückzugebenden Parameters darstellt.</span><span class="sxs-lookup"><span data-stu-id="e43ec-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="e43ec-107">[out] Ein Zeiger auf ein MethodDef-Token, das die Methode, die den Parameter akzeptiert darstellt.</span><span class="sxs-lookup"><span data-stu-id="e43ec-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="e43ec-108">[out] Die Ordnungsposition des Parameters in der Argumentliste der Methode.</span><span class="sxs-lookup"><span data-stu-id="e43ec-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="e43ec-109">[out] Ein Puffer, der den Namen des Parameters enthält.</span><span class="sxs-lookup"><span data-stu-id="e43ec-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="e43ec-110">[in] Die angeforderte Größe in Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="e43ec-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="e43ec-111">[out] Die zurückgegebene Größe in Breitzeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="e43ec-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="e43ec-112">[out] Ein Zeiger auf Attributflags, die dem Parameter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="e43ec-112">[out] A pointer to any attribute flags associated with the parameter.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="e43ec-113">[out] Ein Zeiger auf ein Flag, das angibt, die der Parameter ist ein <xref:System.ValueType>.</span><span class="sxs-lookup"><span data-stu-id="e43ec-113">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="e43ec-114">[out] Ein Zeiger auf eine Konstante Zeichenfolge, die durch den Parameter zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e43ec-114">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="e43ec-115">[out] Die Größe des `ppValue` in Breitzeichen oder 0 (null), wenn `ppValue` errichtet keine Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e43ec-115">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e43ec-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e43ec-116">Requirements</span></span>  
 <span data-ttu-id="e43ec-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e43ec-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e43ec-118">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="e43ec-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e43ec-119">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e43ec-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e43ec-120">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e43ec-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e43ec-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e43ec-121">See Also</span></span>  
 [<span data-ttu-id="e43ec-122">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e43ec-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="e43ec-123">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="e43ec-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
