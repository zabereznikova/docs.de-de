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
ms.openlocfilehash: 5214298c6ad9594548ab45ed583cb5b14ce1f30d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441765"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="db725-102">IMetaDataEmit::SetClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="db725-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="db725-103">Schließt das Layout der Felder für eine Klasse ab, die durch einen vorherigen-Rückruf der [DefineTypeDef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="db725-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db725-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="db725-104">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db725-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="db725-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="db725-106">in Ein `mdTypeDef` Token, das die Klasse angibt, die angelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="db725-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="db725-107">in Die Komprimierungs Größe: 1, 2, 4, 8 oder 16 Bytes.</span><span class="sxs-lookup"><span data-stu-id="db725-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="db725-108">Bei der Komprimierungs Größe handelt es sich um die Anzahl von Bytes zwischen angrenzenden Feldern.</span><span class="sxs-lookup"><span data-stu-id="db725-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="db725-109">in Ein Array von [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) Strukturen, von denen jede ein Feld der Klasse und den Offset des Felds innerhalb der Klasse angibt.</span><span class="sxs-lookup"><span data-stu-id="db725-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="db725-110">Beenden Sie das Array mit `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="db725-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="db725-111">in Die Größe (in Bytes) der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="db725-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db725-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="db725-112">Remarks</span></span>  
 <span data-ttu-id="db725-113">Die-Klasse wird anfänglich durch Aufrufen der [IMetaDataEmit::D efinetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) -Methode definiert, wobei eines von drei Layouts für die Felder der-Klasse angegeben wird: automatisch, sequenziell oder explizit.</span><span class="sxs-lookup"><span data-stu-id="db725-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="db725-114">Normalerweise verwenden Sie das automatische Layout und lassen die Common Language Runtime die beste Möglichkeit zum Anordnen der Felder auswählen.</span><span class="sxs-lookup"><span data-stu-id="db725-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="db725-115">Möglicherweise möchten Sie jedoch, dass die Felder entsprechend der von nicht verwaltetem Code verwendeten Anordnung angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="db725-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="db725-116">Wählen Sie in diesem Fall entweder ein sequenzielles oder explizites Layout aus, und nennen Sie `SetClassLayout`, um das Layout der Felder abzuschließen:</span><span class="sxs-lookup"><span data-stu-id="db725-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="db725-117">Sequenzielles Layout: Geben Sie die Verpackungsgröße an.</span><span class="sxs-lookup"><span data-stu-id="db725-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="db725-118">Ein Feld wird entweder nach seiner natürlichen Größe oder der Komprimierungs Größe ausgerichtet, je nachdem, was zu einem kleineren Offset des Felds führt.</span><span class="sxs-lookup"><span data-stu-id="db725-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="db725-119">Legen Sie `rFieldOffsets` und `ulClassSize` auf 0 (null) fest.</span><span class="sxs-lookup"><span data-stu-id="db725-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="db725-120">Explizites Layout: Geben Sie entweder den Offset jedes Felds an, oder geben Sie die Klassengröße und die Komprimierungs Größe an.</span><span class="sxs-lookup"><span data-stu-id="db725-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db725-121">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="db725-121">Requirements</span></span>  
 <span data-ttu-id="db725-122">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db725-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db725-123">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="db725-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="db725-124">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="db725-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="db725-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db725-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db725-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="db725-126">See also</span></span>

- [<span data-ttu-id="db725-127">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db725-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="db725-128">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="db725-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
