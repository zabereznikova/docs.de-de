---
title: IMetaDataEmit::SetClassLayout-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
ms.openlocfilehash: e855868d18fc6cffdd5d92cfa401606caf45b76c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177560"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="7ec48-102">IMetaDataEmit::SetClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="7ec48-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="7ec48-103">Schließt das Layout von Feldern für eine Klasse ab, die durch einen vorherigen Aufruf der [DefineTypeDef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7ec48-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ec48-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7ec48-104">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ec48-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7ec48-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="7ec48-106">[in] Ein `mdTypeDef` Token, das die zu legende Klasse angibt.</span><span class="sxs-lookup"><span data-stu-id="7ec48-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="7ec48-107">[in] Die Packungsgröße: 1, 2, 4, 8 oder 16 Bytes.</span><span class="sxs-lookup"><span data-stu-id="7ec48-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="7ec48-108">Die Verpackungsgröße ist die Anzahl der Bytes zwischen benachbarten Feldern.</span><span class="sxs-lookup"><span data-stu-id="7ec48-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="7ec48-109">[in] Ein Array [von COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) Strukturen, von denen jede ein Feld der Klasse und den Offset des Felds innerhalb der Klasse angibt.</span><span class="sxs-lookup"><span data-stu-id="7ec48-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="7ec48-110">Beenden Sie `mdTokenNil`das Array mit .</span><span class="sxs-lookup"><span data-stu-id="7ec48-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="7ec48-111">[in] Die Größe der Klasse in Bytes.</span><span class="sxs-lookup"><span data-stu-id="7ec48-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ec48-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7ec48-112">Remarks</span></span>  
 <span data-ttu-id="7ec48-113">Die Klasse wird zunächst definiert, indem die [IMetaDataEmit::DefineTypeDef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) aufgerufen und eines von drei Layouts für die Felder der Klasse angegeben wird: automatisch, sequenziell oder explizit.</span><span class="sxs-lookup"><span data-stu-id="7ec48-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="7ec48-114">Normalerweise würden Sie das automatische Layout verwenden und die Laufzeit den besten Weg zum Layout der Felder auswählen lassen.</span><span class="sxs-lookup"><span data-stu-id="7ec48-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="7ec48-115">Möglicherweise möchten Sie jedoch, dass die Felder entsprechend der Anordnung angeordnet sind, die nicht verwalteter Code verwendet.</span><span class="sxs-lookup"><span data-stu-id="7ec48-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="7ec48-116">Wählen Sie in diesem Fall entweder `SetClassLayout` sequenzielles oder explizites Layout aus, und rufen Sie auf, um das Layout der Felder abzuschließen:</span><span class="sxs-lookup"><span data-stu-id="7ec48-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="7ec48-117">Sequenzielles Layout: Geben Sie die Verpackungsgröße an.</span><span class="sxs-lookup"><span data-stu-id="7ec48-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="7ec48-118">Ein Feld wird entweder an seiner natürlichen Größe oder der Verpackungsgröße ausgerichtet, je nachdem, was zu dem kleineren Versatz des Feldes führt.</span><span class="sxs-lookup"><span data-stu-id="7ec48-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="7ec48-119">Legen `rFieldOffsets` `ulClassSize` Sie fest und auf Null.</span><span class="sxs-lookup"><span data-stu-id="7ec48-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="7ec48-120">Explizites Layout: Geben Sie entweder den Versatz jedes Feldes an, oder geben Sie die Klassengröße und die Verpackungsgröße an.</span><span class="sxs-lookup"><span data-stu-id="7ec48-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ec48-121">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="7ec48-121">Requirements</span></span>  
 <span data-ttu-id="7ec48-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ec48-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ec48-123">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7ec48-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ec48-124">**Bibliothek:** Wird als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="7ec48-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7ec48-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ec48-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ec48-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ec48-126">See also</span></span>

- [<span data-ttu-id="7ec48-127">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ec48-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="7ec48-128">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7ec48-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
