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
ms.openlocfilehash: 9b057b0537bbeff7433b776e64456ccc810cee54
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473486"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="11731-102">IMetaDataTables::GetNextString-Methode</span><span class="sxs-lookup"><span data-stu-id="11731-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="11731-103">Ruft den Index der nächsten Zeichenfolge in der aktuellen Spalte ab.</span><span class="sxs-lookup"><span data-stu-id="11731-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11731-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="11731-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11731-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="11731-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="11731-106">[in] Der Indexwert aus einer Zeichenfolge Tabellenspalte.</span><span class="sxs-lookup"><span data-stu-id="11731-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="11731-107">[out] Ein Zeiger auf den Index der nächsten Zeichenfolge in der Spalte.</span><span class="sxs-lookup"><span data-stu-id="11731-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11731-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="11731-108">Requirements</span></span>  
 <span data-ttu-id="11731-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11731-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11731-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="11731-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11731-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="11731-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11731-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11731-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11731-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="11731-113">See also</span></span>
- [<span data-ttu-id="11731-114">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11731-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="11731-115">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="11731-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
