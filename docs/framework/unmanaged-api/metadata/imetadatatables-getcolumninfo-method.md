---
title: IMetaDataTables::GetColumnInfo-Methode
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
ms.openlocfilehash: 854d3ad28cc00c03e903b9e1d2ce3863e3ceef17
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436093"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="44e0e-102">IMetaDataTables::GetColumnInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="44e0e-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="44e0e-103">Ruft Daten über die angegebene Spalte in der angegebenen Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="44e0e-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e0e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="44e0e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumnInfo (   
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="44e0e-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="44e0e-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="44e0e-106">in Der Index der gewünschten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="44e0e-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="44e0e-107">in Der Index der gewünschten Spalte.</span><span class="sxs-lookup"><span data-stu-id="44e0e-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="44e0e-108">vorgenommen Ein Zeiger auf den Offset der Spalte in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="44e0e-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="44e0e-109">vorgenommen Ein Zeiger auf die Größe der Spalte in Bytes.</span><span class="sxs-lookup"><span data-stu-id="44e0e-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="44e0e-110">vorgenommen Ein Zeiger auf den Typ der Werte in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="44e0e-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="44e0e-111">vorgenommen Ein Zeiger auf einen Zeiger auf den Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="44e0e-111">[out] A pointer to a pointer to the column name.</span></span>  
 
## <a name="remarks"></a><span data-ttu-id="44e0e-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="44e0e-112">Remarks</span></span>

<span data-ttu-id="44e0e-113">Der zurückgegebene Spaltentyp liegt innerhalb eines Wertebereichs:</span><span class="sxs-lookup"><span data-stu-id="44e0e-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="44e0e-114">pType</span><span class="sxs-lookup"><span data-stu-id="44e0e-114">pType</span></span>                    | <span data-ttu-id="44e0e-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="44e0e-115">Description</span></span>   | <span data-ttu-id="44e0e-116">Hilfsfunktion</span><span class="sxs-lookup"><span data-stu-id="44e0e-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="44e0e-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="44e0e-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="44e0e-118">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="44e0e-118">(0..63)</span></span>   | <span data-ttu-id="44e0e-119">Gesagt</span><span class="sxs-lookup"><span data-stu-id="44e0e-119">Rid</span></span>           | <span data-ttu-id="44e0e-120">**Isridtype**</span><span class="sxs-lookup"><span data-stu-id="44e0e-120">**IsRidType**</span></span><br><span data-ttu-id="44e0e-121">**Isridortoken**</span><span class="sxs-lookup"><span data-stu-id="44e0e-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="44e0e-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="44e0e-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="44e0e-123">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="44e0e-123">(64..95)</span></span> | <span data-ttu-id="44e0e-124">Codiertes Token</span><span class="sxs-lookup"><span data-stu-id="44e0e-124">Coded token</span></span> | <span data-ttu-id="44e0e-125">**Iscodeddekentype**</span><span class="sxs-lookup"><span data-stu-id="44e0e-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="44e0e-126">**Isridortoken**</span><span class="sxs-lookup"><span data-stu-id="44e0e-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="44e0e-127">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="44e0e-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="44e0e-128">Int16</span><span class="sxs-lookup"><span data-stu-id="44e0e-128">Int16</span></span>         | <span data-ttu-id="44e0e-129">**Isfixedtype**</span><span class="sxs-lookup"><span data-stu-id="44e0e-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="44e0e-130">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="44e0e-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="44e0e-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="44e0e-131">UInt16</span></span>        | <span data-ttu-id="44e0e-132">**Isfixedtype**</span><span class="sxs-lookup"><span data-stu-id="44e0e-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="44e0e-133">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="44e0e-133">`iLONG` (98)</span></span>             | <span data-ttu-id="44e0e-134">Int32</span><span class="sxs-lookup"><span data-stu-id="44e0e-134">Int32</span></span>         | <span data-ttu-id="44e0e-135">**Isfixedtype**</span><span class="sxs-lookup"><span data-stu-id="44e0e-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="44e0e-136">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="44e0e-136">`iULONG` (99)</span></span>            | <span data-ttu-id="44e0e-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="44e0e-137">UInt32</span></span>        | <span data-ttu-id="44e0e-138">**Isfixedtype**</span><span class="sxs-lookup"><span data-stu-id="44e0e-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="44e0e-139">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="44e0e-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="44e0e-140">Byte</span><span class="sxs-lookup"><span data-stu-id="44e0e-140">Byte</span></span>          | <span data-ttu-id="44e0e-141">**Isfixedtype**</span><span class="sxs-lookup"><span data-stu-id="44e0e-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="44e0e-142">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="44e0e-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="44e0e-143">String</span><span class="sxs-lookup"><span data-stu-id="44e0e-143">String</span></span>        | <span data-ttu-id="44e0e-144">**Isheaptype**</span><span class="sxs-lookup"><span data-stu-id="44e0e-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="44e0e-145">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="44e0e-145">`iGUID` (102)</span></span>            | <span data-ttu-id="44e0e-146">Guid</span><span class="sxs-lookup"><span data-stu-id="44e0e-146">Guid</span></span>          | <span data-ttu-id="44e0e-147">**Isheaptype**</span><span class="sxs-lookup"><span data-stu-id="44e0e-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="44e0e-148">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="44e0e-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="44e0e-149">Blob</span><span class="sxs-lookup"><span data-stu-id="44e0e-149">Blob</span></span>          | <span data-ttu-id="44e0e-150">**Isheaptype**</span><span class="sxs-lookup"><span data-stu-id="44e0e-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="44e0e-151">Werte, die im *Heap* gespeichert sind (d. h. `IsHeapType == true`), können mithilfe von gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="44e0e-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="44e0e-152">`iSTRING`: **IMetadataTables. GetString**</span><span class="sxs-lookup"><span data-stu-id="44e0e-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="44e0e-153">`iGUID`: **IMetadataTables. GetGuid**</span><span class="sxs-lookup"><span data-stu-id="44e0e-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="44e0e-154">`iBLOB`: **IMetadataTables. getBlob**</span><span class="sxs-lookup"><span data-stu-id="44e0e-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44e0e-155">Um die in der obigen Tabelle definierten Konstanten zu verwenden, schließen Sie die-Direktive `#define _DEFINE_META_DATA_META_CONSTANTS` ein, die von der *Cor. h* -Header Datei bereitgestellt wird</span><span class="sxs-lookup"><span data-stu-id="44e0e-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="44e0e-156">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="44e0e-156">Requirements</span></span>  
 <span data-ttu-id="44e0e-157">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44e0e-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44e0e-158">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="44e0e-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44e0e-159">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="44e0e-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44e0e-160">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44e0e-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e0e-161">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="44e0e-161">See also</span></span>

- [<span data-ttu-id="44e0e-162">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44e0e-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="44e0e-163">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="44e0e-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
