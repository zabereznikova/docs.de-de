---
title: IMetaDataTables::GetColumn-Methode
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a88acf59043613bb216ffe84dfb1593bd6ebea00
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54651889"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="5c540-102">IMetaDataTables::GetColumn-Methode</span><span class="sxs-lookup"><span data-stu-id="5c540-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="5c540-103">Ruft einen Zeiger auf den Wert in der Zelle der angegebenen Spalte und Zeile in der angegebenen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5c540-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c540-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5c540-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5c540-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5c540-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="5c540-106">[in] Der Index der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5c540-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="5c540-107">[in] Der Index der Spalte in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5c540-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="5c540-108">[in] Der Index der Zeile in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="5c540-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="5c540-109">[out] Ein Zeiger auf den Wert in der Zelle.</span><span class="sxs-lookup"><span data-stu-id="5c540-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c540-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5c540-110">Requirements</span></span>  
 <span data-ttu-id="5c540-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c540-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c540-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5c540-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5c540-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="5c540-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5c540-114">**.NET Framework-Versionen** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c540-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c540-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5c540-115">See also</span></span>
- [<span data-ttu-id="5c540-116">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5c540-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="5c540-117">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="5c540-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
