---
title: IMetaDataTables::GetNextBlob-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b1e7181f50d94fa417bf9d00c3531747cefca82c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781474"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="9dfba-102">IMetaDataTables::GetNextBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="9dfba-102">IMetaDataTables::GetNextBlob Method</span></span>
<span data-ttu-id="9dfba-103">Ruft den Index des nächsten binary large Object (BLOB) in der Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="9dfba-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dfba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9dfba-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dfba-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="9dfba-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="9dfba-106">[in] Der Index, wie aus einem BLOB-Spalte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="9dfba-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="9dfba-107">[out] Ein Zeiger auf den Index des nächsten BLOB.</span><span class="sxs-lookup"><span data-stu-id="9dfba-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dfba-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9dfba-108">Requirements</span></span>  
 <span data-ttu-id="9dfba-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dfba-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dfba-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9dfba-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9dfba-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="9dfba-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9dfba-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dfba-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dfba-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9dfba-113">See also</span></span>

- [<span data-ttu-id="9dfba-114">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9dfba-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="9dfba-115">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9dfba-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
