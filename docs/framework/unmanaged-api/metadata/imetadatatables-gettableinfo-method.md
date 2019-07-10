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
ms.openlocfilehash: 4844834232e34ab5dacfa34e7aa5d204ee344612
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781357"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="2bc40-102">IMetaDataTables::GetTableInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="2bc40-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="2bc40-103">Ruft ab, Name, Größe, Anzahl der Zeilen, die Anzahl der Spalten und Schlüsselspaltenindex der angegebenen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2bc40-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bc40-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bc40-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bc40-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="2bc40-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="2bc40-106">[in] Der Bezeichner der Tabelle, deren Eigenschaften zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2bc40-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="2bc40-107">[out] Ein Zeiger auf die Größe in Bytes, der eine Zeile einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2bc40-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="2bc40-108">[out] Ein Zeiger auf die Anzahl der Zeilen in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2bc40-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="2bc40-109">[out] Ein Zeiger auf die Anzahl der Spalten in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2bc40-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="2bc40-110">[out] Ein Zeiger auf den Index der Spalte für den Schlüssel oder -1, wenn die Tabelle keine Schlüsselspalte.</span><span class="sxs-lookup"><span data-stu-id="2bc40-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="2bc40-111">[out] Ein Zeiger auf einen Zeiger auf den Namen der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2bc40-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bc40-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2bc40-112">Requirements</span></span>  
 <span data-ttu-id="2bc40-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bc40-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bc40-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2bc40-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2bc40-115">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="2bc40-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2bc40-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bc40-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc40-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2bc40-117">See also</span></span>

- [<span data-ttu-id="2bc40-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2bc40-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="2bc40-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2bc40-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
