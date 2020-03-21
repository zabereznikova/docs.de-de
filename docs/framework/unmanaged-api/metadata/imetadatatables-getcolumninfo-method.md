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
ms.openlocfilehash: cc8aac32149fed952737d928e16a8f6efc448c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177119"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="6e250-102">IMetaDataTables::GetColumnInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="6e250-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="6e250-103">Ruft Daten über die angegebene Spalte in der angegebenen Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="6e250-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e250-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e250-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6e250-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6e250-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="6e250-106">[in] Der Index der gewünschten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6e250-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="6e250-107">[in] Der Index der gewünschten Spalte.</span><span class="sxs-lookup"><span data-stu-id="6e250-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="6e250-108">[out] Ein Zeiger auf den Versatz der Spalte in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="6e250-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="6e250-109">[out] Ein Zeiger auf die Größe der Spalte in Bytes.</span><span class="sxs-lookup"><span data-stu-id="6e250-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="6e250-110">[out] Ein Zeiger auf den Typ der Werte in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="6e250-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="6e250-111">[out] Ein Zeiger auf einen Zeiger auf den Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="6e250-111">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="6e250-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6e250-112">Remarks</span></span>

<span data-ttu-id="6e250-113">Der zurückgegebene Spaltentyp liegt innerhalb eines Wertebereichs:</span><span class="sxs-lookup"><span data-stu-id="6e250-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="6e250-114">pType</span><span class="sxs-lookup"><span data-stu-id="6e250-114">pType</span></span>                    | <span data-ttu-id="6e250-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6e250-115">Description</span></span>   | <span data-ttu-id="6e250-116">Hilfsfunktion</span><span class="sxs-lookup"><span data-stu-id="6e250-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="6e250-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="6e250-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="6e250-118">(0..63)</span><span class="sxs-lookup"><span data-stu-id="6e250-118">(0..63)</span></span>   | <span data-ttu-id="6e250-119">los</span><span class="sxs-lookup"><span data-stu-id="6e250-119">Rid</span></span>           | <span data-ttu-id="6e250-120">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="6e250-120">**IsRidType**</span></span><br><span data-ttu-id="6e250-121">**IsridorToken**</span><span class="sxs-lookup"><span data-stu-id="6e250-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="6e250-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="6e250-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="6e250-123">(64..95)</span><span class="sxs-lookup"><span data-stu-id="6e250-123">(64..95)</span></span> | <span data-ttu-id="6e250-124">Codiertes Token</span><span class="sxs-lookup"><span data-stu-id="6e250-124">Coded token</span></span> | <span data-ttu-id="6e250-125">**IsCodedTokenType**</span><span class="sxs-lookup"><span data-stu-id="6e250-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="6e250-126">**IsridorToken**</span><span class="sxs-lookup"><span data-stu-id="6e250-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="6e250-127">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="6e250-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="6e250-128">Int16</span><span class="sxs-lookup"><span data-stu-id="6e250-128">Int16</span></span>         | <span data-ttu-id="6e250-129">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="6e250-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="6e250-130">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="6e250-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="6e250-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="6e250-131">UInt16</span></span>        | <span data-ttu-id="6e250-132">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="6e250-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="6e250-133">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="6e250-133">`iLONG` (98)</span></span>             | <span data-ttu-id="6e250-134">Int32</span><span class="sxs-lookup"><span data-stu-id="6e250-134">Int32</span></span>         | <span data-ttu-id="6e250-135">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="6e250-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="6e250-136">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="6e250-136">`iULONG` (99)</span></span>            | <span data-ttu-id="6e250-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="6e250-137">UInt32</span></span>        | <span data-ttu-id="6e250-138">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="6e250-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="6e250-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="6e250-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="6e250-140">Byte</span><span class="sxs-lookup"><span data-stu-id="6e250-140">Byte</span></span>          | <span data-ttu-id="6e250-141">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="6e250-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="6e250-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="6e250-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="6e250-143">String</span><span class="sxs-lookup"><span data-stu-id="6e250-143">String</span></span>        | <span data-ttu-id="6e250-144">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="6e250-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="6e250-145">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="6e250-145">`iGUID` (102)</span></span>            | <span data-ttu-id="6e250-146">Guid</span><span class="sxs-lookup"><span data-stu-id="6e250-146">Guid</span></span>          | <span data-ttu-id="6e250-147">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="6e250-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="6e250-148">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="6e250-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="6e250-149">Blob</span><span class="sxs-lookup"><span data-stu-id="6e250-149">Blob</span></span>          | <span data-ttu-id="6e250-150">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="6e250-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="6e250-151">Werte, die im Heap gespeichert `IsHeapType == true`sind (d. *h.,* ) können mit folgenden Werten gelesen werden:</span><span class="sxs-lookup"><span data-stu-id="6e250-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="6e250-152">`iSTRING`: **IMetadataTables.GetString**</span><span class="sxs-lookup"><span data-stu-id="6e250-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="6e250-153">`iGUID`: **IMetadataTables.GetGUID**</span><span class="sxs-lookup"><span data-stu-id="6e250-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="6e250-154">`iBLOB`: **IMetadataTables.GetBlob**</span><span class="sxs-lookup"><span data-stu-id="6e250-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6e250-155">Um die in der obigen Tabelle definierten `#define _DEFINE_META_DATA_META_CONSTANTS` Konstanten zu verwenden, schließen Sie die Direktive ein, die von der *cor.h-Headerdatei* bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="6e250-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="6e250-156">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6e250-156">Requirements</span></span>  
 <span data-ttu-id="6e250-157">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6e250-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e250-158">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6e250-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e250-159">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="6e250-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e250-160">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e250-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e250-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6e250-161">See also</span></span>

- [<span data-ttu-id="6e250-162">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e250-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="6e250-163">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6e250-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
