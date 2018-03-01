---
title: IMetaDataTables-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ff70e99a963c929792a73cefd6e8feaefa8b252e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="ef7a2-102">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef7a2-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="ef7a2-103">Stellt Methoden zum Speichern und Abrufen von Metadateninformationen in Tabellen bereit.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ef7a2-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ef7a2-104">Methods</span></span>  
  
|<span data-ttu-id="ef7a2-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-105">Method</span></span>|<span data-ttu-id="ef7a2-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef7a2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ef7a2-107">GetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-107">GetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|<span data-ttu-id="ef7a2-108">Ruft einen Zeiger auf das binary large Object (BLOB) am angegebenen Spaltenindex.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="ef7a2-109">GetBlobHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-109">GetBlobHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="ef7a2-110">Ruft die Größe des BLOB-Heap in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="ef7a2-111">GetCodedTokenInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-111">GetCodedTokenInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="ef7a2-112">Ruft einen Zeiger auf ein Array von Token, die der Index der angegebenen Zeile zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="ef7a2-113">GetColumn-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-113">GetColumn Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|<span data-ttu-id="ef7a2-114">Ruft einen Zeiger auf die Werte in der Spalte an der angegebenen Spaltenindex in der Tabelle am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="ef7a2-115">GetColumnInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-115">GetColumnInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="ef7a2-116">Ruft Daten über die angegebene Spalte in der angegebenen Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="ef7a2-117">GetGuid-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-117">GetGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|<span data-ttu-id="ef7a2-118">Ruft eine GUID aus der Zeile am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="ef7a2-119">GetGuidHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-119">GetGuidHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="ef7a2-120">Ruft die Größe in Bytes der GUID-Heap.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="ef7a2-121">GetNextBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-121">GetNextBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|<span data-ttu-id="ef7a2-122">Ruft den Index des nächsten BLOBs in der Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="ef7a2-123">GetNextGuid-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-123">GetNextGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|<span data-ttu-id="ef7a2-124">Ruft den Index des nächsten GUID-Wert in der aktuellen Spalte ab.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="ef7a2-125">GetNextString-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-125">GetNextString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|<span data-ttu-id="ef7a2-126">Ruft den Index der nächsten Zeichenfolge in der aktuellen Spalte ab.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="ef7a2-127">GetNextUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-127">GetNextUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="ef7a2-128">Ruft den Index der Zeile, die die nächste hartcodierte Zeichenfolge in der aktuellen Spalte enthält.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="ef7a2-129">GetNumTables-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-129">GetNumTables Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|<span data-ttu-id="ef7a2-130">Ruft die Anzahl der Tabellen im Bereich des aktuellen `IMetaDataTables` Instanz.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="ef7a2-131">GetRow-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-131">GetRow Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|<span data-ttu-id="ef7a2-132">Ruft die Zeile im angegebenen Zeilenindex, in der Tabelle am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="ef7a2-133">GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-133">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|<span data-ttu-id="ef7a2-134">Ruft die Zeichenfolge am angegebenen Index aus der Tabellenspalte im aktuellen Verweisbereich.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="ef7a2-135">GetStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-135">GetStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="ef7a2-136">Ruft die Größe des dem String-Heap in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="ef7a2-137">GetTableIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-137">GetTableIndex Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|<span data-ttu-id="ef7a2-138">Ruft den Index für die Tabelle, die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="ef7a2-139">GetTableInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-139">GetTableInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|<span data-ttu-id="ef7a2-140">Ruft den Namen, Zeilengröße, Anzahl der Zeilen, die Anzahl der Spalten und Schlüssel Spaltenindex der Tabelle am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="ef7a2-141">GetUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-141">GetUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|<span data-ttu-id="ef7a2-142">Ruft die hartcodierte Zeichenfolge am angegebenen Index in der Zeichenfolgenspalte im aktuellen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="ef7a2-143">GetUserStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="ef7a2-143">GetUserStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="ef7a2-144">Ruft die Größe des dem Benutzer String-Heap in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="ef7a2-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ef7a2-145">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ef7a2-145">Requirements</span></span>  
 <span data-ttu-id="ef7a2-146">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef7a2-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef7a2-147">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ef7a2-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ef7a2-148">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="ef7a2-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ef7a2-149">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef7a2-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef7a2-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ef7a2-150">See Also</span></span>  
 [<span data-ttu-id="ef7a2-151">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="ef7a2-151">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [<span data-ttu-id="ef7a2-152">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ef7a2-152">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
