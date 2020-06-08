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
ms.openlocfilehash: 76d23fe9221ae5a07d79b8c5c1a7ad297922b003
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501247"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="a106b-102">IMetaDataTables::GetColumn-Methode</span><span class="sxs-lookup"><span data-stu-id="a106b-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="a106b-103">Ruft einen Zeiger auf den Wert ab, der in der Zelle der angegebenen Spalte und Zeile in der angegebenen Tabelle enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="a106b-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a106b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a106b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a106b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a106b-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="a106b-106">in Der Index der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a106b-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="a106b-107">in Der Index der Spalte in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a106b-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="a106b-108">in Der Index der Zeile in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="a106b-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="a106b-109">vorgenommen Ein Zeiger auf den Wert in der Zelle.</span><span class="sxs-lookup"><span data-stu-id="a106b-109">[out] A pointer to the value in the cell.</span></span>  

## <a name="remarks"></a><span data-ttu-id="a106b-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a106b-110">Remarks</span></span>

<span data-ttu-id="a106b-111">Die Interpretation des Werts, der durch zurückgegeben wird, `pVal` hängt vom Typ der Spalte ab.</span><span class="sxs-lookup"><span data-stu-id="a106b-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="a106b-112">Der Spaltentyp kann durch Aufrufen von [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md)bestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="a106b-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="a106b-113">Die **GetColumn** -Methode konvertiert Spalten vom Typ **RID** oder **codedtoken** automatisch in vollständige 32-Bit- `mdToken` Werte.</span><span class="sxs-lookup"><span data-stu-id="a106b-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="a106b-114">Außerdem werden 8-Bit-oder 16-Bit-Werte automatisch in vollständige 32-Bit-Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="a106b-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span>
- <span data-ttu-id="a106b-115">Bei *Heap* -Typspalten ist das zurückgegebene *PVal* ein Index in den entsprechenden Heap.</span><span class="sxs-lookup"><span data-stu-id="a106b-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="a106b-116">Spaltentyp</span><span class="sxs-lookup"><span data-stu-id="a106b-116">Column type</span></span>              | <span data-ttu-id="a106b-117">PVAL enthält</span><span class="sxs-lookup"><span data-stu-id="a106b-117">pVal contains</span></span> | <span data-ttu-id="a106b-118">Comment</span><span class="sxs-lookup"><span data-stu-id="a106b-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="a106b-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="a106b-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="a106b-120">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="a106b-120">(0..63)</span></span>  | <span data-ttu-id="a106b-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="a106b-121">mdToken</span></span>     | <span data-ttu-id="a106b-122">*PVal* enthält ein vollständiges Token.</span><span class="sxs-lookup"><span data-stu-id="a106b-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="a106b-123">Die-Funktion konvertiert die RID automatisch in ein vollständiges Token.</span><span class="sxs-lookup"><span data-stu-id="a106b-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="a106b-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="a106b-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="a106b-125">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="a106b-125">(64..95)</span></span> | <span data-ttu-id="a106b-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="a106b-126">mdToken</span></span> | <span data-ttu-id="a106b-127">Bei der Rückgabe enthält *PVal* ein vollständiges Token.</span><span class="sxs-lookup"><span data-stu-id="a106b-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="a106b-128">Die Funktion dekomprimiert das codedtoken automatisch in ein vollständiges Token.</span><span class="sxs-lookup"><span data-stu-id="a106b-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="a106b-129">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="a106b-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="a106b-130">Int16</span><span class="sxs-lookup"><span data-stu-id="a106b-130">Int16</span></span>         | <span data-ttu-id="a106b-131">Automatisches Signieren auf 32-Bit.</span><span class="sxs-lookup"><span data-stu-id="a106b-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="a106b-132">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="a106b-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="a106b-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="a106b-133">UInt16</span></span>        | <span data-ttu-id="a106b-134">Automatisches Signieren auf 32-Bit.</span><span class="sxs-lookup"><span data-stu-id="a106b-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="a106b-135">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="a106b-135">`iLONG` (98)</span></span>             | <span data-ttu-id="a106b-136">Int32</span><span class="sxs-lookup"><span data-stu-id="a106b-136">Int32</span></span>         |                                        |
| <span data-ttu-id="a106b-137">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="a106b-137">`iULONG` (99)</span></span>            | <span data-ttu-id="a106b-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="a106b-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="a106b-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="a106b-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="a106b-140">Byte</span><span class="sxs-lookup"><span data-stu-id="a106b-140">Byte</span></span>          | <span data-ttu-id="a106b-141">Automatisches Signieren auf 32-Bit.</span><span class="sxs-lookup"><span data-stu-id="a106b-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="a106b-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="a106b-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="a106b-143">String-Heap Index</span><span class="sxs-lookup"><span data-stu-id="a106b-143">String heap index</span></span> | <span data-ttu-id="a106b-144">*PVal* ist ein Index in den Zeichen folgen Heap.</span><span class="sxs-lookup"><span data-stu-id="a106b-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="a106b-145">Verwenden Sie [IMetadataTables:: GetString](imetadatatables-getstring-method.md) , um den tatsächlichen Spalten Zeichen folgen Wert zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a106b-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="a106b-146">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="a106b-146">`iGUID` (102)</span></span>            | <span data-ttu-id="a106b-147">GUID-Heap Index</span><span class="sxs-lookup"><span data-stu-id="a106b-147">Guid heap index</span></span> | <span data-ttu-id="a106b-148">*PVal* ist ein Index für den GUID-Heap.</span><span class="sxs-lookup"><span data-stu-id="a106b-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="a106b-149">Verwenden Sie [IMetadataTables:: GetGuid](imetadatatables-getguid-method.md) , um den tatsächlichen Spalten-GUID-Wert zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a106b-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="a106b-150">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="a106b-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="a106b-151">BLOB-Heap Index</span><span class="sxs-lookup"><span data-stu-id="a106b-151">Blob heap index</span></span> | <span data-ttu-id="a106b-152">*PVal* ist ein Index im BLOB-Heap.</span><span class="sxs-lookup"><span data-stu-id="a106b-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="a106b-153">Verwenden Sie [IMetadataTables:: GetBlob](imetadatatables-getblob-method.md) , um den tatsächlichen spaltenblob-Wert zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a106b-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="a106b-154">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a106b-154">Requirements</span></span>  
 <span data-ttu-id="a106b-155">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a106b-155">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a106b-156">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="a106b-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a106b-157">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="a106b-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a106b-158">**.NET Framework Versionen**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a106b-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a106b-159">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a106b-159">See also</span></span>

- [<span data-ttu-id="a106b-160">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a106b-160">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="a106b-161">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a106b-161">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
