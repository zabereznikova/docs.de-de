---
title: IMetaDataTables::GetNextString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3c2008556ebf1b1961aef7dc0f24fd0a3161d06e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781448"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="8b85b-102">IMetaDataTables::GetNextString-Methode</span><span class="sxs-lookup"><span data-stu-id="8b85b-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="8b85b-103">Ruft den Index der nächsten Zeichenfolge in der aktuellen Spalte ab.</span><span class="sxs-lookup"><span data-stu-id="8b85b-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b85b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b85b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b85b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b85b-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="8b85b-106">[in] Der Indexwert aus einer Zeichenfolge Tabellenspalte.</span><span class="sxs-lookup"><span data-stu-id="8b85b-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="8b85b-107">[out] Ein Zeiger auf den Index der nächsten Zeichenfolge in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="8b85b-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b85b-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b85b-108">Requirements</span></span>  
 <span data-ttu-id="8b85b-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b85b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b85b-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8b85b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b85b-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="8b85b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8b85b-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b85b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b85b-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b85b-113">See also</span></span>

- [<span data-ttu-id="8b85b-114">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b85b-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8b85b-115">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b85b-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
