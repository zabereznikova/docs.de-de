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
ms.openlocfilehash: 65943ac169106a95feaff7d44017444e65764b60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672525"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="6890c-102">IMetaDataTables::GetTableInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="6890c-102">IMetaDataTables::GetTableInfo Method</span></span>

<span data-ttu-id="6890c-103">Ruft den Namen, die Zeilengröße, die Anzahl der Zeilen, die Anzahl der Spalten und den Schlüssel Spalten Index der angegebenen Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="6890c-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6890c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6890c-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6890c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6890c-105">Parameters</span></span>  

 `ixTbl`  
 <span data-ttu-id="6890c-106">in Der Bezeichner der Tabelle, deren Eigenschaften zurückgegeben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6890c-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="6890c-107">vorgenommen Ein Zeiger auf die Größe einer Tabellenzeile in Byte.</span><span class="sxs-lookup"><span data-stu-id="6890c-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="6890c-108">vorgenommen Ein Zeiger auf die Anzahl der Zeilen in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6890c-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="6890c-109">vorgenommen Ein Zeiger auf die Anzahl der Spalten in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6890c-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="6890c-110">vorgenommen Ein Zeiger auf den Index der Schlüssel Spalte oder-1, wenn die Tabelle keine Schlüssel Spalte enthält.</span><span class="sxs-lookup"><span data-stu-id="6890c-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="6890c-111">vorgenommen Ein Zeiger auf einen Zeiger auf den Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="6890c-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6890c-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6890c-112">Requirements</span></span>  

 <span data-ttu-id="6890c-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6890c-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6890c-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6890c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6890c-115">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="6890c-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6890c-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6890c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6890c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6890c-117">See also</span></span>

- [<span data-ttu-id="6890c-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6890c-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="6890c-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6890c-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
