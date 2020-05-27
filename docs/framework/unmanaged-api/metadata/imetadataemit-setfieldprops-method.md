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
ms.openlocfilehash: 220556ec130c7bff7c413405820c4fee0582b051
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008013"
---
# <a name="imetadataemitsetfieldprops-method"></a><span data-ttu-id="c86ca-102">IMetaDataEmit::SetFieldProps-Methode</span><span class="sxs-lookup"><span data-stu-id="c86ca-102">IMetaDataEmit::SetFieldProps Method</span></span>
<span data-ttu-id="c86ca-103">Legt den Standardwert für das Feld fest, auf das durch das angegebene Feld Token verwiesen wird, oder aktualisiert dieses.</span><span class="sxs-lookup"><span data-stu-id="c86ca-103">Sets or updates the default value for the field referenced by the specified field token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c86ca-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c86ca-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c86ca-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c86ca-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="c86ca-106">in Das Token für das Zielfeld.</span><span class="sxs-lookup"><span data-stu-id="c86ca-106">[in] The token for the target field.</span></span>  
  
 `dwFieldFlags`  
 <span data-ttu-id="c86ca-107">in Feld Attribute.</span><span class="sxs-lookup"><span data-stu-id="c86ca-107">[in] Field attributes.</span></span> <span data-ttu-id="c86ca-108">Dies ist eine Bitmaske von `CorFieldAttr` Werten.</span><span class="sxs-lookup"><span data-stu-id="c86ca-108">This is a bitmask of `CorFieldAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="c86ca-109">in Der `ELEMENT_TYPE_` *\** für den konstanten Wert.</span><span class="sxs-lookup"><span data-stu-id="c86ca-109">[in] The `ELEMENT_TYPE_`*\** for the constant value.</span></span> <span data-ttu-id="c86ca-110">Dies ist ein- `CorElementType` Wert.</span><span class="sxs-lookup"><span data-stu-id="c86ca-110">This is a `CorElementType` value.</span></span> <span data-ttu-id="c86ca-111">Wenn keine Konstante definiert ist, legen Sie diesen Wert auf fest `ELEMENT_TYPE_END` .</span><span class="sxs-lookup"><span data-stu-id="c86ca-111">If a constant is not being defined, set this value to `ELEMENT_TYPE_END`.</span></span>  
  
 `pValue`  
 <span data-ttu-id="c86ca-112">in Der Konstante Wert für das Feld.</span><span class="sxs-lookup"><span data-stu-id="c86ca-112">[in] The constant value for the field.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="c86ca-113">in Die Größe von in Unicode-Zeichen `pValue` .</span><span class="sxs-lookup"><span data-stu-id="c86ca-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c86ca-114">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c86ca-114">Requirements</span></span>  
 <span data-ttu-id="c86ca-115">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c86ca-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c86ca-116">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c86ca-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c86ca-117">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="c86ca-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c86ca-118">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c86ca-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c86ca-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c86ca-119">See also</span></span>

- [<span data-ttu-id="c86ca-120">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c86ca-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c86ca-121">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c86ca-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
