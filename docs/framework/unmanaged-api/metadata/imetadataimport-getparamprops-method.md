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
ms.openlocfilehash: a16621f4c9b06f049239dc4e2335d70a167dd756
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729264"
---
# <a name="imetadataimportgetparamprops-method"></a><span data-ttu-id="ce289-102">IMetaDataImport::GetParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="ce289-102">IMetaDataImport::GetParamProps Method</span></span>

<span data-ttu-id="ce289-103">Ruft Metadatenwerte für den Parameter ab, auf den durch das angegebene ParamDef-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ce289-103">Gets metadata values for the parameter referenced by the specified ParamDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce289-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce289-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ce289-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ce289-105">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="ce289-106">in Ein ParamDef-Token, das den Parameter darstellt, für den Metadaten zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="ce289-106">[in] A ParamDef token that represents the parameter to return metadata for.</span></span>  
  
 `pmd`  
 <span data-ttu-id="ce289-107">vorgenommen Ein Zeiger auf ein MethodDef-Token, das die Methode darstellt, die den-Parameter annimmt.</span><span class="sxs-lookup"><span data-stu-id="ce289-107">[out] A pointer to a MethodDef token representing the method that takes the parameter.</span></span>  
  
 `pulSequence`  
 <span data-ttu-id="ce289-108">vorgenommen Die Ordinalposition des Parameters in der Methoden Argumentliste.</span><span class="sxs-lookup"><span data-stu-id="ce289-108">[out] The ordinal position of the parameter in the method argument list.</span></span>  
  
 `szName`  
 <span data-ttu-id="ce289-109">vorgenommen Ein Puffer, der den Namen des Parameters enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="ce289-109">[out] A buffer to hold the name of the parameter.</span></span>  
  
 `cchName`  
 <span data-ttu-id="ce289-110">in Die angeforderte Größe in breit Zeichen von `szName` .</span><span class="sxs-lookup"><span data-stu-id="ce289-110">[in] The requested size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="ce289-111">vorgenommen Die zurückgegebene Größe in breit Zeichen von `szName` .</span><span class="sxs-lookup"><span data-stu-id="ce289-111">[out] The returned size in wide characters of `szName`.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="ce289-112">vorgenommen Ein Zeiger auf alle Attributflags, die dem-Parameter zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ce289-112">[out] A pointer to any attribute flags associated with the parameter.</span></span> <span data-ttu-id="ce289-113">Dies ist eine Bitmaske von `CorParamAttr` Werten.</span><span class="sxs-lookup"><span data-stu-id="ce289-113">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `pdwCPlusTypeFlag`  
 <span data-ttu-id="ce289-114">vorgenommen Ein Zeiger auf ein Flag, das angibt, dass der-Parameter ein ist <xref:System.ValueType> .</span><span class="sxs-lookup"><span data-stu-id="ce289-114">[out] A pointer to a flag specifying that the parameter is a <xref:System.ValueType>.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="ce289-115">vorgenommen Ein Zeiger auf eine Konstante Zeichenfolge, die vom-Parameter zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ce289-115">[out] A pointer to a constant string returned by the parameter.</span></span>  
  
 `pcchValue`  
 <span data-ttu-id="ce289-116">vorgenommen Die Größe von `ppValue` in breit Zeichen oder 0 (null), wenn `ppValue` keine Zeichenfolge enthält.</span><span class="sxs-lookup"><span data-stu-id="ce289-116">[out] The size of `ppValue` in wide characters, or zero if `ppValue` does not hold a string.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce289-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce289-117">Remarks</span></span>

<span data-ttu-id="ce289-118">Die Sequenzwerte in `pulSequence` beginnen mit 1 für Parameter.</span><span class="sxs-lookup"><span data-stu-id="ce289-118">The sequence values in `pulSequence` begin with 1 for parameters.</span></span> <span data-ttu-id="ce289-119">Ein Rückgabewert hat eine Sequenznummer von 0.</span><span class="sxs-lookup"><span data-stu-id="ce289-119">A return value has a sequence number of 0.</span></span>

## <a name="requirements"></a><span data-ttu-id="ce289-120">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ce289-120">Requirements</span></span>  

 <span data-ttu-id="ce289-121">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce289-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce289-122">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ce289-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ce289-123">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ce289-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ce289-124">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce289-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce289-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce289-125">See also</span></span>

- [<span data-ttu-id="ce289-126">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce289-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="ce289-127">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ce289-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
