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
ms.openlocfilehash: 479cb25ad8e1c263d3539a4203ac5bea781eb931
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009376"
---
# <a name="imetadataemitdefineproperty-method"></a><span data-ttu-id="5f6f0-102">IMetaDataEmit::DefineProperty-Methode</span><span class="sxs-lookup"><span data-stu-id="5f6f0-102">IMetaDataEmit::DefineProperty Method</span></span>
<span data-ttu-id="5f6f0-103">Erstellt eine Eigenschafts Definition für den angegebenen Typ mit dem angegebenen `get` und den `set` Methoden Accessoren und ruft ein Token für diese Eigenschafts Definition ab.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-103">Creates a property definition for the specified type, with the specified `get` and `set` method accessors, and gets a token to that property definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f6f0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f6f0-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="5f6f0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5f6f0-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="5f6f0-106">in Das Token für die Klasse oder Schnittstelle, für die die Eigenschaft definiert wird.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-106">[in] The token for class or interface on which the property is being defined.</span></span>  
  
 `szProperty`  
 <span data-ttu-id="5f6f0-107">[in] Der Name der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-107">[in] The name of the property.</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="5f6f0-108">in Die Eigenschaftenflags.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-108">[in] The property flags.</span></span>  
  
 `pvSig`  
 <span data-ttu-id="5f6f0-109">in Die Eigenschaften Signatur.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-109">[in] The property signature.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="5f6f0-110">in Die Anzahl von Bytes in `pvSig` .</span><span class="sxs-lookup"><span data-stu-id="5f6f0-110">[in] The count of bytes in `pvSig`.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="5f6f0-111">in Der Typ des Standardwerts der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-111">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5f6f0-112">in Der Standardwert für die-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-112">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="5f6f0-113">in Die Anzahl von (Unicode-) Zeichen in `pValue` .</span><span class="sxs-lookup"><span data-stu-id="5f6f0-113">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="5f6f0-114">in Die Methode, die den Eigenschafts Wert festlegt.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-114">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="5f6f0-115">in Die Methode, die den Eigenschafts Wert abruft.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-115">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="5f6f0-116">in Ein Array von anderen Methoden, die der-Eigenschaft zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-116">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="5f6f0-117">Beenden Sie das Array mit einem `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="5f6f0-117">Terminate the array with an `mdTokenNil`.</span></span>  
  
 `pmdProp`  
 <span data-ttu-id="5f6f0-118">vorgenommen Das `mdProperty` zugewiesene Token.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-118">[out] The `mdProperty` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f6f0-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5f6f0-119">Requirements</span></span>  
 <span data-ttu-id="5f6f0-120">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f6f0-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f6f0-121">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5f6f0-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5f6f0-122">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="5f6f0-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5f6f0-123">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f6f0-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f6f0-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f6f0-124">See also</span></span>

- [<span data-ttu-id="5f6f0-125">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f6f0-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="5f6f0-126">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5f6f0-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
