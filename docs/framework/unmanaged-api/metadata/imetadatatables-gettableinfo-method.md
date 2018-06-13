---
title: IMetaDataTables::GetTableInfo-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ea617668a72413f3387a35fe009b37fa15d03354
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449607"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="d0d3d-102">IMetaDataTables::GetTableInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="d0d3d-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="d0d3d-103">Ruft ab, der Name, Zeilengröße, Anzahl der Zeilen, die Anzahl der Spalten und Schlüssel Spaltenindex der angegebenen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d0d3d-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0d3d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d0d3d-104">Syntax</span></span>  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d0d3d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d0d3d-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="d0d3d-106">[in] Der Bezeichner der Tabelle, deren Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d0d3d-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="d0d3d-107">[out] Ein Zeiger auf die Größe in Bytes, der eine Zeile einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d0d3d-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="d0d3d-108">[out] Ein Zeiger auf die Anzahl der Zeilen in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d0d3d-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="d0d3d-109">[out] Ein Zeiger auf die Anzahl der Spalten in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="d0d3d-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="d0d3d-110">[out] Ein Zeiger auf den Index der Spalte für den Schlüssel oder-1 zurück, wenn die Tabelle keine Schlüsselspalte enthält.</span><span class="sxs-lookup"><span data-stu-id="d0d3d-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="d0d3d-111">[out] Ein Zeiger auf einen Zeiger auf den Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="d0d3d-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0d3d-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d0d3d-112">Requirements</span></span>  
 <span data-ttu-id="d0d3d-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0d3d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0d3d-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d0d3d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d0d3d-115">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d0d3d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d0d3d-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0d3d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d3d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0d3d-117">See Also</span></span>  
 [<span data-ttu-id="d0d3d-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0d3d-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="d0d3d-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d0d3d-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
