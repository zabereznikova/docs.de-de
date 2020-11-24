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
ms.openlocfilehash: ba694f485d5a51870a1283b6ccbcb7b042a14501
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95685642"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="0b88b-102">IMetaDataTables::GetNextBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="0b88b-102">IMetaDataTables::GetNextBlob Method</span></span>

<span data-ttu-id="0b88b-103">Ruft den Index des nächsten Binary Large Object (BLOB) in der Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="0b88b-103">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b88b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0b88b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0b88b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="0b88b-105">Parameters</span></span>  

 `ixBlob`  
 <span data-ttu-id="0b88b-106">in Der Index, wie von einer blobspalte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0b88b-106">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="0b88b-107">vorgenommen Ein Zeiger auf den Index des nächsten BLOBs.</span><span class="sxs-lookup"><span data-stu-id="0b88b-107">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0b88b-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="0b88b-108">Requirements</span></span>  

 <span data-ttu-id="0b88b-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0b88b-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b88b-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0b88b-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0b88b-111">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="0b88b-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0b88b-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b88b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b88b-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0b88b-113">See also</span></span>

- [<span data-ttu-id="0b88b-114">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b88b-114">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="0b88b-115">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="0b88b-115">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
