---
title: IMetaDataEmit::SetParamProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b7cfba90edab44a0053fdfc759417ee7f074401
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132031"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="dc0c7-102">IMetaDataEmit::SetParamProps-Methode</span><span class="sxs-lookup"><span data-stu-id="dc0c7-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="dc0c7-103">Legt fest oder ändert Sie Features eines Methodenparameters, die von einem vorherigen Aufruf von definiert wurde [DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span><span class="sxs-lookup"><span data-stu-id="dc0c7-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc0c7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc0c7-104">Syntax</span></span>  
  
```  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc0c7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dc0c7-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="dc0c7-106">[in] Das Token für den Target-Parameter.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="dc0c7-107">[in] Der Name des Parameters im Unicode-Format.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="dc0c7-108">[in] Die Flags für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="dc0c7-109">[in] Die ELEMENT_TYPE_ \* für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="dc0c7-110">[in] Der Konstante Wert für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="dc0c7-111">[in] Die Größe in Zeichen (Unicode) der `pValue`.</span><span class="sxs-lookup"><span data-stu-id="dc0c7-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc0c7-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="dc0c7-112">Requirements</span></span>  
 <span data-ttu-id="dc0c7-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dc0c7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc0c7-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dc0c7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc0c7-115">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="dc0c7-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dc0c7-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc0c7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc0c7-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc0c7-117">See also</span></span>

- [<span data-ttu-id="dc0c7-118">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc0c7-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="dc0c7-119">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dc0c7-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
