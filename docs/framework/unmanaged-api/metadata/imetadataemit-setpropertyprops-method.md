---
title: IMetaDataEmit::SetPropertyProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetPropertyProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fe79846b9fd576941c706b48a7aed0667c264a3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="61f53-102">IMetaDataEmit::SetPropertyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="61f53-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="61f53-103">Legt die Funktionen, die in den Metadaten für eine Eigenschaft, die definiert, die durch einen vorherigen Aufruf von gespeicherten [DefineProperty-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span><span class="sxs-lookup"><span data-stu-id="61f53-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61f53-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="61f53-104">Syntax</span></span>  
  
```  
HRESULT SetPropertyProps (   
    [in]  mdProperty      pr,   
    [in]  DWORD           dwPropFlags,   
    [in]  DWORD           dwCPlusTypeFlag,   
    [in]  void const      *pValue,   
    [in]  ULONG           cchValue,   
    [in]  mdMethodDef     mdSetter,   
    [in]  mdMethodDef     mdGetter,   
    [in]  mdMethodDef     rmdOtherMethods[]   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61f53-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="61f53-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="61f53-106">[in] Das Token für die Eigenschaft geändert werden</span><span class="sxs-lookup"><span data-stu-id="61f53-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="61f53-107">[in] Die Eigenschaftenflags.</span><span class="sxs-lookup"><span data-stu-id="61f53-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="61f53-108">[in] Der Typ des Standardwerts für die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="61f53-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="61f53-109">[in] Der Standardwert für die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="61f53-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="61f53-110">[in] Die Anzahl von (Unicode-) Zeichen `pValue`.</span><span class="sxs-lookup"><span data-stu-id="61f53-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="61f53-111">[in] Die Methode, die den Wert der Eigenschaft festlegt.</span><span class="sxs-lookup"><span data-stu-id="61f53-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="61f53-112">[in] Die Methode, die den Eigenschaftswert abruft.</span><span class="sxs-lookup"><span data-stu-id="61f53-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="61f53-113">[in] Ein Array von anderen Methoden, die der Eigenschaft zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="61f53-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="61f53-114">Beenden Sie dieses Array mit einem `mdTokenNil` token.</span><span class="sxs-lookup"><span data-stu-id="61f53-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61f53-115">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="61f53-115">Requirements</span></span>  
 <span data-ttu-id="61f53-116">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61f53-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61f53-117">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="61f53-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61f53-118">**Bibliothek:** als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="61f53-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61f53-119">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61f53-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61f53-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="61f53-120">See Also</span></span>  
 [<span data-ttu-id="61f53-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61f53-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="61f53-122">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="61f53-122">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
