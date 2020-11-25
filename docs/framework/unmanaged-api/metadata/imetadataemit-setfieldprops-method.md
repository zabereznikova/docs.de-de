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
ms.openlocfilehash: 0f98fb64b43822c437c39df2f3c51a222ef386b9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730395"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="84271-102">IMetaDataEmit::SetFieldProps-Methode</span><span class="sxs-lookup"><span data-stu-id="84271-102">IMetaDataEmit::SetFieldProps Method</span></span>

<span data-ttu-id="84271-103">Legt den Standardwert für das Feld fest, auf das durch das angegebene Feld Token verwiesen wird, oder aktualisiert dieses.</span><span class="sxs-lookup"><span data-stu-id="84271-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84271-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="84271-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84271-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="84271-105">Parameters</span></span>  

 `fd`  
 <span data-ttu-id="84271-106">in Das Token für das Zielfeld.</span><span class="sxs-lookup"><span data-stu-id="84271-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="84271-107">in Feld Attribute.</span><span class="sxs-lookup"><span data-stu-id="84271-107">[in] Field attributes.</span></span> <span data-ttu-id="84271-108">Dies ist eine Bitmaske von `CorFieldAttr` Werten.</span><span class="sxs-lookup"><span data-stu-id="84271-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="84271-109">in Der `ELEMENT_TYPE_` *\** für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="84271-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="84271-110">Dies ist ein- `CorElementType` Wert.</span><span class="sxs-lookup"><span data-stu-id="84271-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="84271-111">Wenn keine Konstante definiert ist, legen Sie diesen Wert auf fest `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="84271-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="84271-112">in Der Konstante Wert für das Feld.</span><span class="sxs-lookup"><span data-stu-id="84271-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="84271-113">in Die Größe von in Unicode-Zeichen `pValue` .</span><span class="sxs-lookup"><span data-stu-id="84271-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84271-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="84271-114">Requirements</span></span>  

 <span data-ttu-id="84271-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84271-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84271-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="84271-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="84271-117">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="84271-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84271-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84271-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84271-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="84271-119">See also</span></span>

- [<span data-ttu-id="84271-120">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84271-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="84271-121">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="84271-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
