---
title: IMetaDataEmit::SetPropertyProps-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: b5af877c26c20bf64a27618bf24a7bce5b410419
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007779"
---
# <a name="imetadataemitsetpropertyprops-method"></a><span data-ttu-id="3442f-102">IMetaDataEmit::SetPropertyProps-Methode</span><span class="sxs-lookup"><span data-stu-id="3442f-102">IMetaDataEmit::SetPropertyProps Method</span></span>
<span data-ttu-id="3442f-103">Legt die in den Metadaten gespeicherten Features für eine Eigenschaft fest, die durch einen vorherigen-Befehl der [DefineProperty-Methode](imetadataemit-defineproperty-method.md)definiert wird.</span><span class="sxs-lookup"><span data-stu-id="3442f-103">Sets the features stored in metadata for a property defined by a prior call to [DefineProperty Method](imetadataemit-defineproperty-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3442f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3442f-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="3442f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3442f-105">Parameters</span></span>  
 `pr`  
 <span data-ttu-id="3442f-106">in Das Token für die Eigenschaft, die geändert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3442f-106">[in] The token for the property to be changed</span></span>  
  
 `dwPropFlags`  
 <span data-ttu-id="3442f-107">in Eigenschaftenflags.</span><span class="sxs-lookup"><span data-stu-id="3442f-107">[in] Property flags.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="3442f-108">in Der Typ des Standardwerts der Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3442f-108">[in] The type of the property's default value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="3442f-109">in Der Standardwert für die-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="3442f-109">[in] The default value for the property.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="3442f-110">in Die Anzahl von (Unicode-) Zeichen in `pValue` .</span><span class="sxs-lookup"><span data-stu-id="3442f-110">[in] The count of (Unicode) characters in `pValue`.</span></span>  
  
 `mdSetter`  
 <span data-ttu-id="3442f-111">in Die Methode, die den Eigenschafts Wert festlegt.</span><span class="sxs-lookup"><span data-stu-id="3442f-111">[in] The method that sets the property value.</span></span>  
  
 `mdGetter`  
 <span data-ttu-id="3442f-112">in Die Methode, die den Eigenschafts Wert abruft.</span><span class="sxs-lookup"><span data-stu-id="3442f-112">[in] The method that gets the property value.</span></span>  
  
 `rmdOtherMethods[]`  
 <span data-ttu-id="3442f-113">in Ein Array von anderen Methoden, die der-Eigenschaft zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="3442f-113">[in] An array of other methods associated with the property.</span></span> <span data-ttu-id="3442f-114">Beenden Sie dieses Array mit einem `mdTokenNil` Token.</span><span class="sxs-lookup"><span data-stu-id="3442f-114">Terminate this array with an `mdTokenNil` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3442f-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3442f-115">Requirements</span></span>  
 <span data-ttu-id="3442f-116">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3442f-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3442f-117">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3442f-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3442f-118">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="3442f-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3442f-119">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3442f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3442f-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3442f-120">See also</span></span>

- [<span data-ttu-id="3442f-121">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3442f-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="3442f-122">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3442f-122">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
