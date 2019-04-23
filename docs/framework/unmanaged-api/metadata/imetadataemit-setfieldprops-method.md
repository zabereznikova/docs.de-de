---
title: IMetaDataEmit::SetFieldProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 94ba607669b4b1ca68294470cf1cc4fb27464d28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59097654"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="13d1d-102">IMetaDataEmit::SetFieldProps-Methode</span><span class="sxs-lookup"><span data-stu-id="13d1d-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="13d1d-103">Legt fest oder aktualisiert den Standardwert für das Feld auf die durch das angegebene Feld-Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="13d1d-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13d1d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="13d1d-104">Syntax</span></span>  
  
```  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13d1d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="13d1d-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="13d1d-106">[in] Das Token für das Feld "Ziel".</span><span class="sxs-lookup"><span data-stu-id="13d1d-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="13d1d-107">[in] Feldattribute.</span><span class="sxs-lookup"><span data-stu-id="13d1d-107">[in] Field attributes.</span></span> <span data-ttu-id="13d1d-108">Dies ist eine Bitmaske der `CorFieldAttr` Werte.</span><span class="sxs-lookup"><span data-stu-id="13d1d-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="13d1d-109">[in] Die `ELEMENT_TYPE_` *\** für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="13d1d-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="13d1d-110">Dies ist eine `CorElementType` Wert.</span><span class="sxs-lookup"><span data-stu-id="13d1d-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="13d1d-111">Wenn eine Konstante nicht definiert ist, legen Sie diesen Wert auf `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="13d1d-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="13d1d-112">[in] Der Konstante Wert für das Feld.</span><span class="sxs-lookup"><span data-stu-id="13d1d-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="13d1d-113">[in] Die Größe in Unicode-Zeichen von `pValue`.</span><span class="sxs-lookup"><span data-stu-id="13d1d-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13d1d-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="13d1d-114">Requirements</span></span>  
 <span data-ttu-id="13d1d-115">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13d1d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13d1d-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13d1d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13d1d-117">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="13d1d-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13d1d-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13d1d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13d1d-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="13d1d-119">See also</span></span>

- [<span data-ttu-id="13d1d-120">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13d1d-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="13d1d-121">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="13d1d-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
