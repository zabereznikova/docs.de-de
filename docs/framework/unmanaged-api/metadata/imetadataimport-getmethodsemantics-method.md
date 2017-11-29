---
title: IMetaDataImport::GetMethodSemantics-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetMethodSemantics
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetMethodSemantics
helpviewer_keywords:
- GetMethodSemantics method [.NET Framework metadata]
- IMetaDataImport::GetMethodSemantics method [.NET Framework metadata]
ms.assetid: 5e018eaa-d60e-4a0b-a2c5-8c36bd09d905
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f15aedb74fd7322031d213c5229f65d70f7cb771
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetmethodsemantics-method"></a><span data-ttu-id="ea46c-102">IMetaDataImport::GetMethodSemantics-Methode</span><span class="sxs-lookup"><span data-stu-id="ea46c-102">IMetaDataImport::GetMethodSemantics Method</span></span>
<span data-ttu-id="ea46c-103">Ruft Flags, die die Beziehung zwischen dem-Methode auf, die vom angegebenen MethodDef-Token und der gepaarten Eigenschaft verwiesen wird und das Ereignis verwiesen wird, vom angegebenen EventProp-token ab.</span><span class="sxs-lookup"><span data-stu-id="ea46c-103">Gets flags indicating the relationship between the method referenced by the specified MethodDef token and the paired property and event referenced by the specified EventProp token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea46c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ea46c-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSemantics (  
   [in]  mdMethodDef   mb,  
   [in]  mdToken       tkEventProp,  
   [out] DWORD         *pdwSemanticsFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ea46c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ea46c-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="ea46c-106">[in] Ein MethodDef-Token, das die Methode zum Abrufen der semantischen Rolleninformationen darstellt.</span><span class="sxs-lookup"><span data-stu-id="ea46c-106">[in] A MethodDef token representing the method to get the semantic role information for.</span></span>  
  
 `tkEventProp`  
 <span data-ttu-id="ea46c-107">[in] Ein Token, darstellt, die gepaarten Eigenschaft und das Ereignis für die Rolle "die Methode" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="ea46c-107">[in] A token representing the paired property and event for which to get the method's role.</span></span>  
  
 `pdwSemanticsFlags`  
 <span data-ttu-id="ea46c-108">[out] Ein Zeiger auf die zugeordnete Semantik-Flags.</span><span class="sxs-lookup"><span data-stu-id="ea46c-108">[out] A pointer to the associated semantics flags.</span></span> <span data-ttu-id="ea46c-109">Dieser Wert ist eine Bitmaske aus der [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) Enumeration.</span><span class="sxs-lookup"><span data-stu-id="ea46c-109">This value is a bitmask from the [CorMethodSemanticsAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodsemanticsattr-enumeration.md) enumeration.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea46c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ea46c-110">Remarks</span></span>  
 <span data-ttu-id="ea46c-111">Die [DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) Methode legt eine Methode Semantikflags fest.</span><span class="sxs-lookup"><span data-stu-id="ea46c-111">The [IMetaDataEmit::DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md) method sets a method's semantics flags.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ea46c-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ea46c-112">Requirements</span></span>  
 <span data-ttu-id="ea46c-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea46c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea46c-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ea46c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ea46c-115">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ea46c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ea46c-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ea46c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea46c-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ea46c-117">See Also</span></span>  
 [<span data-ttu-id="ea46c-118">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea46c-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="ea46c-119">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ea46c-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
