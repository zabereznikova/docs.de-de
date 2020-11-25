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
ms.openlocfilehash: 227d9ab67ab3091508232be3018ca520a6b5dcc6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95711051"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="ab7da-102">IMetaDataTables::GetColumnInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="ab7da-102">IMetaDataTables::GetColumnInfo Method</span></span>

<span data-ttu-id="ab7da-103">Ruft Daten über die angegebene Spalte in der angegebenen Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="ab7da-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ab7da-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab7da-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ab7da-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="ab7da-105">Parameters</span></span>

=======

 `ixTbl`  
 <span data-ttu-id="ab7da-106">in Der Index der gewünschten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ab7da-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="ab7da-107">in Der Index der gewünschten Spalte.</span><span class="sxs-lookup"><span data-stu-id="ab7da-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="ab7da-108">vorgenommen Ein Zeiger auf den Offset der Spalte in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="ab7da-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="ab7da-109">vorgenommen Ein Zeiger auf die Größe der Spalte in Bytes.</span><span class="sxs-lookup"><span data-stu-id="ab7da-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="ab7da-110">vorgenommen Ein Zeiger auf den Typ der Werte in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="ab7da-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="ab7da-111">vorgenommen Ein Zeiger auf einen Zeiger auf den Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="ab7da-111">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="ab7da-112">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ab7da-112">Remarks</span></span>

<span data-ttu-id="ab7da-113">Der zurückgegebene Spaltentyp liegt innerhalb eines Wertebereichs:</span><span class="sxs-lookup"><span data-stu-id="ab7da-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="ab7da-114">pType</span><span class="sxs-lookup"><span data-stu-id="ab7da-114">pType</span></span>                    | <span data-ttu-id="ab7da-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="ab7da-115">Description</span></span>   | <span data-ttu-id="ab7da-116">Hilfsfunktion</span><span class="sxs-lookup"><span data-stu-id="ab7da-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="ab7da-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="ab7da-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="ab7da-118">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="ab7da-118">(0..63)</span></span>   | <span data-ttu-id="ab7da-119">Gesagt</span><span class="sxs-lookup"><span data-stu-id="ab7da-119">Rid</span></span>           | <span data-ttu-id="ab7da-120">**Isridtype**</span><span class="sxs-lookup"><span data-stu-id="ab7da-120">**IsRidType**</span></span><br><span data-ttu-id="ab7da-121">**Isridortoken**</span><span class="sxs-lookup"><span data-stu-id="ab7da-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="ab7da-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="ab7da-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="ab7da-123">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="ab7da-123">(64..95)</span></span> | <span data-ttu-id="ab7da-124">Codiertes Token</span><span class="sxs-lookup"><span data-stu-id="ab7da-124">Coded token</span></span> | <span data-ttu-id="ab7da-125">**Iscodeddekentype**</span><span class="sxs-lookup"><span data-stu-id="ab7da-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="ab7da-126">**Isridortoken**</span><span class="sxs-lookup"><span data-stu-id="ab7da-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="ab7da-127">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="ab7da-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="ab7da-128">Int16</span><span class="sxs-lookup"><span data-stu-id="ab7da-128">Int16</span></span>         | <span data-ttu-id="ab7da-129">**Isfixedtype**</span><span class="sxs-lookup"><span data-stu-id="ab7da-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="ab7da-130">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="ab7da-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="ab7da-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="ab7da-131">UInt16</span></span>        | <span data-ttu-id="ab7da-132">**Isfixedtype**</span><span class="sxs-lookup"><span data-stu-id="ab7da-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="ab7da-133">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="ab7da-133">`iLONG` (98)</span></span>             | <span data-ttu-id="ab7da-134">Int32</span><span class="sxs-lookup"><span data-stu-id="ab7da-134">Int32</span></span>         | <span data-ttu-id="ab7da-135">**Isfixedtype**</span><span class="sxs-lookup"><span data-stu-id="ab7da-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="ab7da-136">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="ab7da-136">`iULONG` (99)</span></span>            | <span data-ttu-id="ab7da-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="ab7da-137">UInt32</span></span>        | <span data-ttu-id="ab7da-138">**Isfixedtype**</span><span class="sxs-lookup"><span data-stu-id="ab7da-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="ab7da-139">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="ab7da-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="ab7da-140">Byte</span><span class="sxs-lookup"><span data-stu-id="ab7da-140">Byte</span></span>          | <span data-ttu-id="ab7da-141">**Isfixedtype**</span><span class="sxs-lookup"><span data-stu-id="ab7da-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="ab7da-142">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="ab7da-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="ab7da-143">String</span><span class="sxs-lookup"><span data-stu-id="ab7da-143">String</span></span>        | <span data-ttu-id="ab7da-144">**Isheaptype**</span><span class="sxs-lookup"><span data-stu-id="ab7da-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="ab7da-145">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="ab7da-145">`iGUID` (102)</span></span>            | <span data-ttu-id="ab7da-146">Guid</span><span class="sxs-lookup"><span data-stu-id="ab7da-146">Guid</span></span>          | <span data-ttu-id="ab7da-147">**Isheaptype**</span><span class="sxs-lookup"><span data-stu-id="ab7da-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="ab7da-148">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="ab7da-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="ab7da-149">Blob</span><span class="sxs-lookup"><span data-stu-id="ab7da-149">Blob</span></span>          | <span data-ttu-id="ab7da-150">**Isheaptype**</span><span class="sxs-lookup"><span data-stu-id="ab7da-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="ab7da-151">Werte, die im *Heap* gespeichert sind (d. h. `IsHeapType == true` ), können mithilfe von gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="ab7da-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="ab7da-152">`iSTRING`: **IMetadataTables. GetString**</span><span class="sxs-lookup"><span data-stu-id="ab7da-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="ab7da-153">`iGUID`: **IMetadataTables. GetGuid**</span><span class="sxs-lookup"><span data-stu-id="ab7da-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="ab7da-154">`iBLOB`: **IMetadataTables. getBlob**</span><span class="sxs-lookup"><span data-stu-id="ab7da-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ab7da-155">Um die in der obigen Tabelle definierten Konstanten zu verwenden, schließen Sie die-Anweisung ein, `#define _DEFINE_META_DATA_META_CONSTANTS` die von der-Header Datei *Cor. h* bereitgestellt wird</span><span class="sxs-lookup"><span data-stu-id="ab7da-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="ab7da-156">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="ab7da-156">Requirements</span></span>  

 <span data-ttu-id="ab7da-157">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab7da-157">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ab7da-158">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ab7da-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ab7da-159">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="ab7da-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ab7da-160">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab7da-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ab7da-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab7da-161">See also</span></span>

- [<span data-ttu-id="ab7da-162">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab7da-162">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="ab7da-163">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ab7da-163">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
