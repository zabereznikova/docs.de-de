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
ms.openlocfilehash: 073e73f082416308b893974471e39cbf5243d01c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708854"
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="71bef-102">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71bef-102">IMetaDataTables Interface</span></span>

<span data-ttu-id="71bef-103">Stellt Methoden zum Speichern und Abrufen von Metadateninformationen in Tabellen bereit.</span><span class="sxs-lookup"><span data-stu-id="71bef-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="71bef-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="71bef-104">Methods</span></span>  
  
|<span data-ttu-id="71bef-105">Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-105">Method</span></span>|<span data-ttu-id="71bef-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="71bef-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="71bef-107">GetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-107">GetBlob Method</span></span>](imetadatatables-getblob-method.md)|<span data-ttu-id="71bef-108">Ruft einen Zeiger auf den Binary Large Object (BLOB) am angegebenen Spalten Index ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="71bef-109">GetBlobHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-109">GetBlobHeapSize Method</span></span>](imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="71bef-110">Ruft die Größe des BLOB-Heaps in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="71bef-111">GetCodedTokenInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-111">GetCodedTokenInfo Method</span></span>](imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="71bef-112">Ruft einen Zeiger auf ein Array von Token ab, die dem angegebenen Zeilen Index zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="71bef-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="71bef-113">GetColumn-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-113">GetColumn Method</span></span>](imetadatatables-getcolumn-method.md)|<span data-ttu-id="71bef-114">Ruft einen Zeiger auf die Werte ab, die in der Spalte am angegebenen Spalten Index in der Tabelle am angegebenen Tabellenindex enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="71bef-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="71bef-115">GetColumnInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-115">GetColumnInfo Method</span></span>](imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="71bef-116">Ruft Daten über die angegebene Spalte in der angegebenen Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="71bef-117">GetGuid-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-117">GetGuid Method</span></span>](imetadatatables-getguid-method.md)|<span data-ttu-id="71bef-118">Ruft eine GUID aus der Zeile am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="71bef-119">GetGuidHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-119">GetGuidHeapSize Method</span></span>](imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="71bef-120">Ruft die Größe des GUID-Heaps in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="71bef-121">GetNextBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-121">GetNextBlob Method</span></span>](imetadatatables-getnextblob-method.md)|<span data-ttu-id="71bef-122">Ruft den Index des nächsten BLOBs in der Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="71bef-123">GetNextGuid-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-123">GetNextGuid Method</span></span>](imetadatatables-getnextguid-method.md)|<span data-ttu-id="71bef-124">Ruft den Index des nächsten GUID-Werts in der aktuellen Tabellenspalte ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="71bef-125">GetNextString-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-125">GetNextString Method</span></span>](imetadatatables-getnextstring-method.md)|<span data-ttu-id="71bef-126">Ruft den Index der nächsten Zeichenfolge in der aktuellen Tabellenspalte ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="71bef-127">GetNextUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-127">GetNextUserString Method</span></span>](imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="71bef-128">Ruft den Index der Zeile ab, die die nächste hart codierte Zeichenfolge in der aktuellen Tabellenspalte enthält.</span><span class="sxs-lookup"><span data-stu-id="71bef-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="71bef-129">GetNumTables-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-129">GetNumTables Method</span></span>](imetadatatables-getnumtables-method.md)|<span data-ttu-id="71bef-130">Ruft die Anzahl der Tabellen im Gültigkeitsbereich der aktuellen `IMetaDataTables` Instanz ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="71bef-131">GetRow-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-131">GetRow Method</span></span>](imetadatatables-getrow-method.md)|<span data-ttu-id="71bef-132">Ruft die Zeile am angegebenen Zeilen Index in der Tabelle am angegebenen Tabellenindex ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="71bef-133">GetString-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-133">GetString Method</span></span>](imetadatatables-getstring-method.md)|<span data-ttu-id="71bef-134">Ruft die Zeichenfolge am angegebenen Index aus der Tabellenspalte im aktuellen Verweis Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="71bef-135">GetStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-135">GetStringHeapSize Method</span></span>](imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="71bef-136">Ruft die Größe des Zeichen folgen Heaps in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="71bef-137">GetTableIndex-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-137">GetTableIndex Method</span></span>](imetadatatables-gettableindex-method.md)|<span data-ttu-id="71bef-138">Ruft den Index für die Tabelle ab, auf die durch das angegebene Token verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="71bef-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="71bef-139">GetTableInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-139">GetTableInfo Method</span></span>](imetadatatables-gettableinfo-method.md)|<span data-ttu-id="71bef-140">Ruft den Namen, die Zeilengröße, die Anzahl der Zeilen, die Anzahl der Spalten und den Schlüssel Spalten Index der Tabelle am angegebenen Tabellenindex ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="71bef-141">GetUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-141">GetUserString Method</span></span>](imetadatatables-getuserstring-method.md)|<span data-ttu-id="71bef-142">Ruft die hart codierte Zeichenfolge am angegebenen Index in der Zeichen folgen Spalte im aktuellen Bereich ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="71bef-143">GetUserStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="71bef-143">GetUserStringHeapSize Method</span></span>](imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="71bef-144">Ruft die Größe des Benutzer Zeichen folgen Heaps in Bytes ab.</span><span class="sxs-lookup"><span data-stu-id="71bef-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="71bef-145">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="71bef-145">Requirements</span></span>  

 <span data-ttu-id="71bef-146">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71bef-146">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71bef-147">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="71bef-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71bef-148">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="71bef-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71bef-149">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71bef-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71bef-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71bef-150">See also</span></span>

- [<span data-ttu-id="71bef-151">Metadatenschnittstellen</span><span class="sxs-lookup"><span data-stu-id="71bef-151">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="71bef-152">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71bef-152">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
