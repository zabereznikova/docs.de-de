---
title: IMetaDataTables::GetColumnInfo-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetColumnInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 939085294666a233341f65a8f5736d9dce201470
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="bd3c4-102">IMetaDataTables::GetColumnInfo-Methode</span><span class="sxs-lookup"><span data-stu-id="bd3c4-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="bd3c4-103">Ruft Daten über die angegebene Spalte in der angegebenen Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="bd3c4-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd3c4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bd3c4-104">Syntax</span></span>  
  
```  
HRESULT GetColumnInfo (   
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd3c4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bd3c4-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="bd3c4-106">[in] Der Index der gewünschten Tabelle.</span><span class="sxs-lookup"><span data-stu-id="bd3c4-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="bd3c4-107">[in] Der Index der gewünschten Spalte.</span><span class="sxs-lookup"><span data-stu-id="bd3c4-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="bd3c4-108">[out] Ein Zeiger auf den Offset der Spalte in der Zeile.</span><span class="sxs-lookup"><span data-stu-id="bd3c4-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="bd3c4-109">[out] Ein Zeiger auf die Größe in Bytes, der Spalte.</span><span class="sxs-lookup"><span data-stu-id="bd3c4-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="bd3c4-110">[out] Ein Zeiger auf den Typ der Werte in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="bd3c4-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="bd3c4-111">[out] Ein Zeiger auf einen Zeiger auf den Namen der Spalte.</span><span class="sxs-lookup"><span data-stu-id="bd3c4-111">[out] A pointer to a pointer to the column name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd3c4-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="bd3c4-112">Requirements</span></span>  
 <span data-ttu-id="bd3c4-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd3c4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd3c4-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bd3c4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bd3c4-115">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="bd3c4-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="bd3c4-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd3c4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd3c4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd3c4-117">See Also</span></span>  
 [<span data-ttu-id="bd3c4-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd3c4-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="bd3c4-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="bd3c4-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
