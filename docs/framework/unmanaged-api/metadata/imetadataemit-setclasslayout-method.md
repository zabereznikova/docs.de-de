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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2dc1664551683066a33fb52e16e4909506601f2a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54588690"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="0fe46-102">IMetaDataEmit::SetClassLayout-Methode</span><span class="sxs-lookup"><span data-stu-id="0fe46-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="0fe46-103">Schließt das Layout der Felder für eine Klasse, die von einem vorherigen Aufruf von definiert wurde [DefineTypeDef-Methode](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span><span class="sxs-lookup"><span data-stu-id="0fe46-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fe46-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0fe46-104">Syntax</span></span>  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0fe46-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0fe46-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="0fe46-106">[in] Ein `mdTypeDef` Token, das die Klasse angeordnet werden, gibt.</span><span class="sxs-lookup"><span data-stu-id="0fe46-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="0fe46-107">[in] Die Komprimierungsgröße ist: 1, 2, 4, 8 oder 16 Bytes.</span><span class="sxs-lookup"><span data-stu-id="0fe46-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="0fe46-108">Die Komprimierungsgröße ist die Anzahl von Bytes zwischen angrenzenden Feldern.</span><span class="sxs-lookup"><span data-stu-id="0fe46-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="0fe46-109">[in] Ein Array von [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) Strukturen, von denen jeder gibt an, ein Feld der Klasse und das Feld des in der Klasse.</span><span class="sxs-lookup"><span data-stu-id="0fe46-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="0fe46-110">Beenden Sie das Array mit `mdTokenNil`.</span><span class="sxs-lookup"><span data-stu-id="0fe46-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="0fe46-111">[in] Die Größe in Bytes der-Klasse.</span><span class="sxs-lookup"><span data-stu-id="0fe46-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0fe46-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0fe46-112">Remarks</span></span>  
 <span data-ttu-id="0fe46-113">Die Klasse wird zuerst definiert, durch den Aufruf der [IMetaDataEmit:: DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) -Methode, und geben eine der drei Layouts für die Felder der Klasse: automatische, sequenziellen oder explizit.</span><span class="sxs-lookup"><span data-stu-id="0fe46-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="0fe46-114">Normalerweise würden Sie verwenden des automatischen Layouts und die Runtime, die die beste Möglichkeit, das Layout der Felder auswählen können.</span><span class="sxs-lookup"><span data-stu-id="0fe46-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="0fe46-115">Allerdings sollten Sie die Felder entsprechend der Anordnung, die von nicht Code verwaltetem angeordnet.</span><span class="sxs-lookup"><span data-stu-id="0fe46-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="0fe46-116">In diesem Fall wählen Sie entweder sequenzielles oder explizites Layout und Aufruf `SetClassLayout` das Layout der Felder abgeschlossen:</span><span class="sxs-lookup"><span data-stu-id="0fe46-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
-   <span data-ttu-id="0fe46-117">Sequenzielles Layout: Geben Sie die Komprimierungsgröße ist.</span><span class="sxs-lookup"><span data-stu-id="0fe46-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="0fe46-118">Ein Feld wird entsprechend ihrer natürlichen Größe oder die Komprimierungsgröße ist, welche Ergebnisse in der kleineren Offset des Felds ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="0fe46-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="0fe46-119">Legen Sie `rFieldOffsets` und `ulClassSize` 0 (null).</span><span class="sxs-lookup"><span data-stu-id="0fe46-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
-   <span data-ttu-id="0fe46-120">Explizites Layout: Geben Sie den Offset der einzelnen Felder oder geben Sie die Klassengröße und die Komprimierungsgröße ist.</span><span class="sxs-lookup"><span data-stu-id="0fe46-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fe46-121">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0fe46-121">Requirements</span></span>  
 <span data-ttu-id="0fe46-122">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fe46-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fe46-123">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0fe46-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0fe46-124">**Bibliothek:** Als Ressource in MSCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="0fe46-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0fe46-125">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fe46-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe46-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fe46-126">See also</span></span>
- [<span data-ttu-id="0fe46-127">IMetaDataEmit-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0fe46-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="0fe46-128">IMetaDataEmit2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0fe46-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
