---
title: IMetaDataEmit::DefineProperty-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1b80833892fc1c0290e94f5de7d9b081529c6a37
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085024"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="9152f-102">IMetaDataEmit::DefineProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="9152f-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="9152f-103">Erstellt eine Eigenschaftsdefinition für den angegebenen Typ, mit dem angegebenen `get` und `set` Methodenaccessoren, und ruft ein Token auf diese Eigenschaftsdefinition ab.</span><span class="sxs-lookup"><span data-stu-id="9152f-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9152f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9152f-104">Syntax</span></span>  
  
```  
HRESULT DefineProperty (   
    [in]  mdTypeDef          td,   
    [in]  LPCWSTR            szProperty,   
    [in]  DWORD              dwPropFlags,   
    [in]  PCCOR_SIGNATURE    pvSig,   
    [in]  ULONG              cbSig,   
    [in]  DWORD              dwCPlusTypeFlag,   
    [in]  void const         *pValue,   
    [in]  ULONG              cchValue,   
    [in]  mdMethodDef        mdSetter,   
    [in]  mdMethodDef        mdGetter,   
    [in]  mdMethodDef        rmdOtherMethods[],   
    [out] mdProperty         *pmdProp   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9152f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9152f-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="9152f-106">[in] Das Token für die Klasse oder Schnittstelle, die auf dem die Eigenschaft definiert wird.</span><span class="sxs-lookup"><span data-stu-id="9152f-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="9152f-107">[in] Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9152f-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="9152f-108">[in] Die Eigenschaftenflags.</span><span class="sxs-lookup"><span data-stu-id="9152f-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="9152f-109">[in] Die Eigenschaftensignatur.</span><span class="sxs-lookup"><span data-stu-id="9152f-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="9152f-110">[in] Die Anzahl der Bytes im `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="9152f-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="9152f-111">[in] Der Typ der Standardwert der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9152f-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="9152f-112">[in] Der Standardwert für die Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="9152f-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="9152f-113">[in] Die Anzahl von (Unicode-) Zeichen in `pValue`.</span><span class="sxs-lookup"><span data-stu-id="9152f-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="9152f-114">[in] Die Methode, die den Wert der Eigenschaft festlegt.</span><span class="sxs-lookup"><span data-stu-id="9152f-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="9152f-115">[in] Die Methode, die den Wert der Eigenschaft abruft.</span><span class="sxs-lookup"><span data-stu-id="9152f-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="9152f-116">[in] Ein Array von anderen Methoden der Eigenschaft zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="9152f-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="9152f-117">Beenden Sie das Array mit einem `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="9152f-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="9152f-118">[out] Die `mdProperty` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="9152f-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9152f-119">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9152f-119">Requirements</span></span>  
 <span data-ttu-id="9152f-120">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9152f-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9152f-121">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9152f-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9152f-122">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="9152f-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9152f-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9152f-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9152f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9152f-124">See also</span></span>

- [<span data-ttu-id="9152f-125">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9152f-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="9152f-126">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9152f-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
