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
ms.openlocfilehash: f11b374ed0ecbfc137c43fb641ae691237604691
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431519"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="6f674-102">IMetaDataEmit::DefineProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="6f674-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="6f674-103">Erstellt eine Eigenschafts Definition für den angegebenen Typ mit dem angegebenen `get` und `set` Methodenaccessoren und ruft ein Token für diese Eigenschafts Definition ab.</span><span class="sxs-lookup"><span data-stu-id="6f674-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f674-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f674-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="6f674-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6f674-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="6f674-106">in Das Token für die Klasse oder Schnittstelle, für die die Eigenschaft definiert wird.</span><span class="sxs-lookup"><span data-stu-id="6f674-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="6f674-107">in Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6f674-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="6f674-108">in Die Eigenschaftenflags.</span><span class="sxs-lookup"><span data-stu-id="6f674-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="6f674-109">in Die Eigenschaften Signatur.</span><span class="sxs-lookup"><span data-stu-id="6f674-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="6f674-110">in Die Anzahl der Bytes in `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="6f674-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="6f674-111">in Der Typ des Standardwerts der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6f674-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="6f674-112">in Der Standardwert für die-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="6f674-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="6f674-113">in Die Anzahl von (Unicode-) Zeichen in `pValue`.</span><span class="sxs-lookup"><span data-stu-id="6f674-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="6f674-114">in Die Methode, die den Eigenschafts Wert festlegt.</span><span class="sxs-lookup"><span data-stu-id="6f674-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="6f674-115">in Die Methode, die den Eigenschafts Wert abruft.</span><span class="sxs-lookup"><span data-stu-id="6f674-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="6f674-116">in Ein Array von anderen Methoden, die der-Eigenschaft zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="6f674-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="6f674-117">Beenden Sie das Array mit einem `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="6f674-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="6f674-118">vorgenommen Das zugewiesene `mdProperty` Token.</span><span class="sxs-lookup"><span data-stu-id="6f674-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f674-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6f674-119">Requirements</span></span>  
 <span data-ttu-id="6f674-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f674-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f674-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6f674-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6f674-122">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f674-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6f674-123">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f674-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f674-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6f674-124">See also</span></span>

- [<span data-ttu-id="6f674-125">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f674-125">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="6f674-126">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6f674-126">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
