---
title: IMetaDataTables-Schnittstelle
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b2298e2d67e8a50e11d53d864f0e78f3b549e45
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131416"
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="3ed24-102">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ed24-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="3ed24-103">Stellt Methoden zum Speichern und Abrufen von Metadateninformationen in Tabellen bereit.</span><span class="sxs-lookup"><span data-stu-id="3ed24-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3ed24-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="3ed24-104">Methods</span></span>  
  
|<span data-ttu-id="3ed24-105">Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-105">Method</span></span>|<span data-ttu-id="3ed24-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3ed24-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3ed24-107">GetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-107">GetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|<span data-ttu-id="3ed24-108">Ruft einen Zeiger auf das binary large Object (BLOB) am Index angegebene Spalte ab.</span><span class="sxs-lookup"><span data-stu-id="3ed24-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="3ed24-109">GetBlobHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-109">GetBlobHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="3ed24-110">Ruft die Größe des BLOB-Heap in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="3ed24-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="3ed24-111">GetCodedTokenInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-111">GetCodedTokenInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="3ed24-112">Ruft einen Zeiger auf ein Array von Token mit dem angegebenen Zeilenindex verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="3ed24-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="3ed24-113">GetColumn-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-113">GetColumn Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|<span data-ttu-id="3ed24-114">Ruft einen Zeiger auf die Werte in der Spalte auf den angegebenen Spaltenindex in der Tabelle auf den Index der angegebenen Tabelle enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3ed24-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="3ed24-115">GetColumnInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-115">GetColumnInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="3ed24-116">Ruft Daten über die angegebene Spalte in der angegebenen Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="3ed24-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="3ed24-117">GetGuid-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-117">GetGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|<span data-ttu-id="3ed24-118">Ruft eine GUID aus der Zeile am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="3ed24-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="3ed24-119">GetGuidHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-119">GetGuidHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="3ed24-120">Ruft die Größe in Bytes der GUID-Heap an.</span><span class="sxs-lookup"><span data-stu-id="3ed24-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="3ed24-121">GetNextBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-121">GetNextBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|<span data-ttu-id="3ed24-122">Ruft den Index des nächsten BLOBs in der Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="3ed24-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="3ed24-123">GetNextGuid-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-123">GetNextGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|<span data-ttu-id="3ed24-124">Ruft den Index der nächsten GUID-Wert in der aktuellen Spalte ab.</span><span class="sxs-lookup"><span data-stu-id="3ed24-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="3ed24-125">GetNextString-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-125">GetNextString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|<span data-ttu-id="3ed24-126">Ruft den Index der nächsten Zeichenfolge in der aktuellen Spalte ab.</span><span class="sxs-lookup"><span data-stu-id="3ed24-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="3ed24-127">GetNextUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-127">GetNextUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="3ed24-128">Ruft den Index der Zeile, die die nächste hartcodierten Zeichenfolge in der aktuellen Spalte enthält.</span><span class="sxs-lookup"><span data-stu-id="3ed24-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="3ed24-129">GetNumTables-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-129">GetNumTables Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|<span data-ttu-id="3ed24-130">Ruft die Anzahl der Tabellen im Bereich des aktuellen `IMetaDataTables` Instanz.</span><span class="sxs-lookup"><span data-stu-id="3ed24-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="3ed24-131">GetRow-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-131">GetRow Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|<span data-ttu-id="3ed24-132">Ruft die Zeile am angegebenen Zeilenindex, in der Tabelle auf den Index der angegebenen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3ed24-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="3ed24-133">GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-133">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|<span data-ttu-id="3ed24-134">Ruft die Zeichenfolge am angegebenen Index aus der Tabellenspalte in den Gültigkeitsbereich des aktuellen ab.</span><span class="sxs-lookup"><span data-stu-id="3ed24-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="3ed24-135">GetStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-135">GetStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="3ed24-136">Ruft die Größe in Bytes, der dem String-Heap an.</span><span class="sxs-lookup"><span data-stu-id="3ed24-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="3ed24-137">GetTableIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-137">GetTableIndex Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|<span data-ttu-id="3ed24-138">Ruft den Index für die Tabelle, die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="3ed24-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="3ed24-139">GetTableInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-139">GetTableInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|<span data-ttu-id="3ed24-140">Ruft Name, Größe, Anzahl der Zeilen, die Anzahl der Spalten und Schlüssel Spaltenindex der Tabelle vom Index angegebenen Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="3ed24-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="3ed24-141">GetUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-141">GetUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|<span data-ttu-id="3ed24-142">Ruft die hartcodierten Zeichenfolge am angegebenen Index in die Zeichenfolgenspalte im aktuellen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="3ed24-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="3ed24-143">GetUserStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="3ed24-143">GetUserStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="3ed24-144">Ruft die Größe in Bytes, der dem Benutzer String-Heap an.</span><span class="sxs-lookup"><span data-stu-id="3ed24-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3ed24-145">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3ed24-145">Requirements</span></span>  
 <span data-ttu-id="3ed24-146">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ed24-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ed24-147">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3ed24-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3ed24-148">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="3ed24-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3ed24-149">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ed24-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ed24-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ed24-150">See also</span></span>

- [<span data-ttu-id="3ed24-151">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="3ed24-151">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="3ed24-152">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3ed24-152">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
