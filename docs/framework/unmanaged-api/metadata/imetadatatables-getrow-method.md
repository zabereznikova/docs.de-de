---
title: IMetaDataTables::GetRow-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetRow
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetRow
helpviewer_keywords:
- IMetaDataTables::GetRow method [.NET Framework metadata]
- GetRow method [.NET Framework metadata]
ms.assetid: a7408d51-0bce-45a2-b58f-da4660bbc039
topic_type:
- apiref
ms.openlocfilehash: 71f6c496816fec1a7537f5ccdfdc1b47d17da871
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177106"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="47210-102">IMetaDataTables::GetRow-Methode</span><span class="sxs-lookup"><span data-stu-id="47210-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="47210-103">Ruft die Zeile am angegebenen Zeilenindex in der Tabelle am angegebenen Tabellenindex ab.</span><span class="sxs-lookup"><span data-stu-id="47210-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47210-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="47210-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRow (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47210-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="47210-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="47210-106">[in] Der Index der Tabelle, aus der die Zeile abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="47210-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="47210-107">[in] Der Index der zu erhaltenden Zeile.</span><span class="sxs-lookup"><span data-stu-id="47210-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="47210-108">[out] Ein Zeiger auf einen Zeiger auf die Zeile.</span><span class="sxs-lookup"><span data-stu-id="47210-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47210-109">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="47210-109">Remarks</span></span>  

  <span data-ttu-id="47210-110">Die Verwendung dieser Methode wird nicht empfohlen, da sie keine konsistenten Ergebnisse liefert.</span><span class="sxs-lookup"><span data-stu-id="47210-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="47210-111">Informationen zur GUID-Tabelle finden Sie in der CLI-Dokumentation (Common Language Infrastructure), insbesondere "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="47210-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="47210-112">Die Dokumentation ist online verfügbar; siehe [ECMA-C- und Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) und Standard [ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="47210-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47210-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="47210-113">Requirements</span></span>  
 <span data-ttu-id="47210-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47210-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47210-115">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="47210-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47210-116">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="47210-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47210-117">**.NET Framework-Versionen**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47210-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47210-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="47210-118">See also</span></span>

- [<span data-ttu-id="47210-119">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47210-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="47210-120">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="47210-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
