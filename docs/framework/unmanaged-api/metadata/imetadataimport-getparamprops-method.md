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
ms.openlocfilehash: bb73ccdd9eee4b5a655a56b5d6757e0c6003fbc9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437129"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="0f105-102">IMetaDataImport::GetParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="0f105-102">IMetaDataImport::GetParamProps Method</span></span>
<span data-ttu-id="0f105-103">Ruft Metadatenwerte für den Parameter ab, auf den durch das angegebene ParamDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="0f105-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f105-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0f105-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="0f105-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0f105-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="0f105-106">in Ein ParamDef-Token, das den Parameter darstellt, für den Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0f105-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="0f105-107">vorgenommen Ein Zeiger auf ein MethodDef-Token, das die Methode darstellt, die den-Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="0f105-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="0f105-108">vorgenommen Die Ordinalposition des Parameters in der Methoden Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="0f105-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="0f105-109">vorgenommen Ein Puffer, der den Namen des Parameters enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="0f105-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="0f105-110">in Die angeforderte Größe in breit Zeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="0f105-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="0f105-111">vorgenommen Die zurückgegebene Größe in breit Zeichen `szName`.</span><span class="sxs-lookup"><span data-stu-id="0f105-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="0f105-112">vorgenommen Ein Zeiger auf alle Attributflags, die dem-Parameter zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0f105-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="0f105-113">Dies ist eine Bitmaske von `CorParamAttr` Werten.</span><span class="sxs-lookup"><span data-stu-id="0f105-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="0f105-114">vorgenommen Ein Zeiger auf ein Flag, das angibt, dass der Parameter eine <xref:System.ValueType>ist.</span><span class="sxs-lookup"><span data-stu-id="0f105-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="0f105-115">vorgenommen Ein Zeiger auf eine Konstante Zeichenfolge, die vom-Parameter zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0f105-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="0f105-116">vorgenommen Die Größe der `ppValue` in breit Zeichen oder 0 (null), wenn `ppValue` keine Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="0f105-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f105-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0f105-117">Remarks</span></span>

<span data-ttu-id="0f105-118">Die Sequenzwerte in `pulSequence` mit 1 für Parameter beginnen.</span><span class="sxs-lookup"><span data-stu-id="0f105-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="0f105-119">Ein Rückgabewert hat eine Sequenznummer von 0.</span><span class="sxs-lookup"><span data-stu-id="0f105-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f105-120">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0f105-120">Requirements</span></span>  
 <span data-ttu-id="0f105-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f105-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f105-122">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0f105-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0f105-123">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="0f105-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0f105-124">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f105-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f105-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f105-125">See also</span></span>

- [<span data-ttu-id="0f105-126">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f105-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="0f105-127">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0f105-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
