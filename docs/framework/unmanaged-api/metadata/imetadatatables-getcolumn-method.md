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
ms.openlocfilehash: 90ce56b3959c4768ef9cb6a9c551d53c5300a39e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208357"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="f5a67-102">IMetaDataTables::GetColumn-Methode</span><span class="sxs-lookup"><span data-stu-id="f5a67-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="f5a67-103">Ruft einen Zeiger auf den Wert in der Zelle der angegebenen Spalte und Zeile in der angegebenen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f5a67-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a67-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5a67-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f5a67-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f5a67-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="f5a67-106">[in] Der Index der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f5a67-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="f5a67-107">[in] Der Index der Spalte in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f5a67-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="f5a67-108">[in] Der Index der Zeile in der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f5a67-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="f5a67-109">[out] Ein Zeiger auf den Wert in der Zelle.</span><span class="sxs-lookup"><span data-stu-id="f5a67-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5a67-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f5a67-110">Requirements</span></span>  
 <span data-ttu-id="f5a67-111">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f5a67-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5a67-112">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f5a67-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f5a67-113">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f5a67-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="f5a67-114">.NET Framework-Versionen</span><span class="sxs-lookup"><span data-stu-id="f5a67-114">.NET Framework Versions</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5a67-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5a67-115">See also</span></span>

- [<span data-ttu-id="f5a67-116">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5a67-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="f5a67-117">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f5a67-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
