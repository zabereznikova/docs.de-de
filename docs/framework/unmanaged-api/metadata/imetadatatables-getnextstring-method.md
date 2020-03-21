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
ms.openlocfilehash: a1cd932051a9ed90a29ff5eeaa818a67104192bb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175251"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="dda01-102">IMetaDataTables::GetNextString-Methode</span><span class="sxs-lookup"><span data-stu-id="dda01-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="dda01-103">Ruft den Index der nächsten Zeichenfolge in der aktuellen Tabellenspalte ab.</span><span class="sxs-lookup"><span data-stu-id="dda01-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dda01-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="dda01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextString (
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dda01-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="dda01-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="dda01-106">[in] Der Indexwert aus einer Zeichenfolgentabellenspalte.</span><span class="sxs-lookup"><span data-stu-id="dda01-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="dda01-107">[out] Ein Zeiger auf den Index der nächsten Zeichenfolge in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="dda01-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dda01-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="dda01-108">Requirements</span></span>  
 <span data-ttu-id="dda01-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dda01-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dda01-110">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="dda01-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dda01-111">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="dda01-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dda01-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dda01-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dda01-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dda01-113">See also</span></span>

- [<span data-ttu-id="dda01-114">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dda01-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="dda01-115">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="dda01-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
