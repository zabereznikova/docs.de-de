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
ms.openlocfilehash: efc627619d9abf9cfa6010e1c0ca709989b9cad3
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445462"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="5ee24-102">IMetaDataEmit::SetFieldProps-Methode</span><span class="sxs-lookup"><span data-stu-id="5ee24-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="5ee24-103">Sets or updates the default value for the field referenced by the specified field token.</span><span class="sxs-lookup"><span data-stu-id="5ee24-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ee24-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5ee24-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ee24-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5ee24-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="5ee24-106">[in] The token for the target field.</span><span class="sxs-lookup"><span data-stu-id="5ee24-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="5ee24-107">[in] Field attributes.</span><span class="sxs-lookup"><span data-stu-id="5ee24-107">[in] Field attributes.</span></span> <span data-ttu-id="5ee24-108">This is a bitmask of `CorFieldAttr` values.</span><span class="sxs-lookup"><span data-stu-id="5ee24-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="5ee24-109">[in] The `ELEMENT_TYPE_` *\** for the constant value.</span><span class="sxs-lookup"><span data-stu-id="5ee24-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="5ee24-110">This is a `CorElementType` value.</span><span class="sxs-lookup"><span data-stu-id="5ee24-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="5ee24-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span><span class="sxs-lookup"><span data-stu-id="5ee24-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5ee24-112">[in] The constant value for the field.</span><span class="sxs-lookup"><span data-stu-id="5ee24-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="5ee24-113">[in] The size, in Unicode characters, of `pValue`.</span><span class="sxs-lookup"><span data-stu-id="5ee24-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ee24-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ee24-114">Requirements</span></span>  
 <span data-ttu-id="5ee24-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ee24-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ee24-116">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5ee24-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ee24-117">**Library:** Used as a resource in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ee24-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5ee24-118">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ee24-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee24-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ee24-119">See also</span></span>

- [<span data-ttu-id="5ee24-120">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ee24-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5ee24-121">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5ee24-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
