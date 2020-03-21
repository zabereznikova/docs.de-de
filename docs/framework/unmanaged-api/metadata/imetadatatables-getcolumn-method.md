---
title: IMetaDataTables::GetColumn-Methode
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: f43d4d1547cbe92f325950e1697dada83b42c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177139"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="4cbf4-102">IMetaDataTables::GetColumn-Methode</span><span class="sxs-lookup"><span data-stu-id="4cbf4-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="4cbf4-103">Ruft einen Zeiger auf den Wert ab, der in der Zelle der angegebenen Spalte und Zeile in der angegebenen Tabelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4cbf4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4cbf4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4cbf4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="4cbf4-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="4cbf4-106">[in] Der Index der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="4cbf4-107">[in] Der Index der Spalte in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="4cbf4-108">[in] Der Index der Zeile in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="4cbf4-109">[out] Ein Zeiger auf den Wert in der Zelle.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-109">[out] A pointer to the value in the cell.</span></span>  

## <a name="remarks"></a><span data-ttu-id="4cbf4-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="4cbf4-110">Remarks</span></span>

<span data-ttu-id="4cbf4-111">Die Interpretation des zurückgegebenen `pVal` Werts hängt vom Spaltentyp ab.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="4cbf4-112">Der Spaltentyp kann durch Aufrufen von [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md)bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="4cbf4-113">Die **GetColumn-Methode** konvertiert automatisch Spalten vom Typ **Rid** oder `mdToken` **CodedToken** in vollständige 32-Bit-Werte.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="4cbf4-114">Außerdem werden 8-Bit- oder 16-Bit-Werte automatisch in vollständige 32-Bit-Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span>
- <span data-ttu-id="4cbf4-115">Bei *Heaptypspalten* ist das zurückgegebene *pVal* ein Index in den entsprechenden Heap.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="4cbf4-116">Spaltentyp</span><span class="sxs-lookup"><span data-stu-id="4cbf4-116">Column type</span></span>              | <span data-ttu-id="4cbf4-117">pVal enthält</span><span class="sxs-lookup"><span data-stu-id="4cbf4-117">pVal contains</span></span> | <span data-ttu-id="4cbf4-118">Comment</span><span class="sxs-lookup"><span data-stu-id="4cbf4-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="4cbf4-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="4cbf4-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="4cbf4-120">(0..63)</span><span class="sxs-lookup"><span data-stu-id="4cbf4-120">(0..63)</span></span>  | <span data-ttu-id="4cbf4-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="4cbf4-121">mdToken</span></span>     | <span data-ttu-id="4cbf4-122">*pVal* enthält ein vollständiges Token.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="4cbf4-123">Die Funktion konvertiert den Rid automatisch in ein vollständiges Token.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="4cbf4-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="4cbf4-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="4cbf4-125">(64..95)</span><span class="sxs-lookup"><span data-stu-id="4cbf4-125">(64..95)</span></span> | <span data-ttu-id="4cbf4-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="4cbf4-126">mdToken</span></span> | <span data-ttu-id="4cbf4-127">Nach der Rückkehr enthält *pVal* einen vollständigen Token.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="4cbf4-128">Die Funktion dekomprimiert den CodedToken automatisch in ein vollständiges Token.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="4cbf4-129">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="4cbf4-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="4cbf4-130">Int16</span><span class="sxs-lookup"><span data-stu-id="4cbf4-130">Int16</span></span>         | <span data-ttu-id="4cbf4-131">Automatisch sign-extended auf 32-Bit.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="4cbf4-132">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="4cbf4-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="4cbf4-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="4cbf4-133">UInt16</span></span>        | <span data-ttu-id="4cbf4-134">Automatisch sign-extended auf 32-Bit.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="4cbf4-135">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="4cbf4-135">`iLONG` (98)</span></span>             | <span data-ttu-id="4cbf4-136">Int32</span><span class="sxs-lookup"><span data-stu-id="4cbf4-136">Int32</span></span>         |                                        |
| <span data-ttu-id="4cbf4-137">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="4cbf4-137">`iULONG` (99)</span></span>            | <span data-ttu-id="4cbf4-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="4cbf4-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="4cbf4-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="4cbf4-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="4cbf4-140">Byte</span><span class="sxs-lookup"><span data-stu-id="4cbf4-140">Byte</span></span>          | <span data-ttu-id="4cbf4-141">Automatisch sign-extended auf 32-Bit.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="4cbf4-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="4cbf4-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="4cbf4-143">String-Heap-Index</span><span class="sxs-lookup"><span data-stu-id="4cbf4-143">String heap index</span></span> | <span data-ttu-id="4cbf4-144">*pVal* ist ein Index im String-Heap.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="4cbf4-145">Verwenden Sie [IMetadataTables::GetString,](imetadatatables-getstring-method.md) um den tatsächlichen Spaltenzeichenfolgenwert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="4cbf4-146">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="4cbf4-146">`iGUID` (102)</span></span>            | <span data-ttu-id="4cbf4-147">Guid-Heapindex</span><span class="sxs-lookup"><span data-stu-id="4cbf4-147">Guid heap index</span></span> | <span data-ttu-id="4cbf4-148">*pVal* ist ein Index im Guid-Heap.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="4cbf4-149">Verwenden Sie [IMetadataTables::GetGuid,](imetadatatables-getguid-method.md) um den tatsächlichen Spalten-Guid-Wert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="4cbf4-150">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="4cbf4-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="4cbf4-151">Blob-Heap-Index</span><span class="sxs-lookup"><span data-stu-id="4cbf4-151">Blob heap index</span></span> | <span data-ttu-id="4cbf4-152">*pVal* ist ein Index im Blob-Heap.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="4cbf4-153">Verwenden Sie [IMetadataTables::GetBlob,](imetadatatables-getblob-method.md) um den tatsächlichen Spalten-Blobwert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="4cbf4-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="4cbf4-154">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="4cbf4-154">Requirements</span></span>  
 <span data-ttu-id="4cbf4-155">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4cbf4-155">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4cbf4-156">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4cbf4-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4cbf4-157">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="4cbf4-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4cbf4-158">**.NET Framework-Versionen**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4cbf4-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cbf4-159">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4cbf4-159">See also</span></span>

- [<span data-ttu-id="4cbf4-160">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4cbf4-160">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="4cbf4-161">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4cbf4-161">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
