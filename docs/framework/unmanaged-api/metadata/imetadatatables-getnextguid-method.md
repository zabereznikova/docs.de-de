---
title: IMetaDataTables::GetNextGuid-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextGuid
helpviewer_keywords:
- GetNextGuid method [.NET Framework metadata]
- IMetaDataTables::GetNextGuid method [.NET Framework metadata]
ms.assetid: 68f6ea4d-9112-4d6b-93d9-e34f1e2f2496
topic_type:
- apiref
ms.openlocfilehash: 645a9913d0de6f93e59df3dd8ba7267ddb13b41b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490236"
---
# <a name="imetadatatablesgetnextguid-method"></a><span data-ttu-id="46b0d-102">IMetaDataTables::GetNextGuid-Methode</span><span class="sxs-lookup"><span data-stu-id="46b0d-102">IMetaDataTables::GetNextGuid Method</span></span>
<span data-ttu-id="46b0d-103">Ruft den Index des nächsten GUID-Werts in der aktuellen Tabellenspalte ab.</span><span class="sxs-lookup"><span data-stu-id="46b0d-103">Gets the index of the next GUID value in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46b0d-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46b0d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextGuid (  
    [in]  ULONG   ixGuid,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="46b0d-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="46b0d-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="46b0d-106">in Der Indexwert aus einer GUID-Tabellenspalte.</span><span class="sxs-lookup"><span data-stu-id="46b0d-106">[in] The index value from a GUID table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="46b0d-107">vorgenommen Ein Zeiger auf den Index des nächsten GUID-Werts.</span><span class="sxs-lookup"><span data-stu-id="46b0d-107">[out] A pointer to the index of the next GUID value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46b0d-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="46b0d-108">Remarks</span></span>  

  <span data-ttu-id="46b0d-109">Die Verwendung dieser Methode wird nicht empfohlen, da Sie keine konsistenten Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="46b0d-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="46b0d-110">Weitere Informationen zur GUID-Tabelle finden Sie in der Common Language Infrastructure (CLI)-Dokumentation, insbesondere "Partition II: Metadatendefinition und Semantik".</span><span class="sxs-lookup"><span data-stu-id="46b0d-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="46b0d-111">Die Dokumentation ist online verfügbar. Weitere Informationen finden Sie unter [ECMA c# und Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) und [Standard-ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="46b0d-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46b0d-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="46b0d-112">Requirements</span></span>  
 <span data-ttu-id="46b0d-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46b0d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46b0d-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="46b0d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="46b0d-115">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="46b0d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="46b0d-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46b0d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46b0d-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="46b0d-117">See also</span></span>

- [<span data-ttu-id="46b0d-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46b0d-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="46b0d-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46b0d-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
