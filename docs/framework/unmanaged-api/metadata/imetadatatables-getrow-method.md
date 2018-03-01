---
title: IMetaDataTables::GetRow-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 760bee2c4a6a6efb16a32579578ab4953492c48e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="f039b-102">IMetaDataTables::GetRow-Methode</span><span class="sxs-lookup"><span data-stu-id="f039b-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="f039b-103">Ruft die Zeile im angegebenen Zeilenindex, in der Tabelle am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="f039b-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f039b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f039b-104">Syntax</span></span>  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f039b-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f039b-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="f039b-106">[in] Der Index der Tabelle, aus der die Zeile abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="f039b-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="f039b-107">[in] Der Index der Zeile abgerufen.</span><span class="sxs-lookup"><span data-stu-id="f039b-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="f039b-108">[out] Ein Zeiger auf einen Zeiger auf die Zeile.</span><span class="sxs-lookup"><span data-stu-id="f039b-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f039b-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f039b-109">Remarks</span></span>  
 <span data-ttu-id="f039b-110">Die Verwendung dieser Methode wird nicht empfohlen, da er keine konsistente Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f039b-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="f039b-111">Informationen über die GUID-Tabelle finden Sie unter der Common Language Infrastructure (CLI)-Dokumentation, insbesondere in "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="f039b-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="f039b-112">Die Dokumentation ist online verfügbar. Sie finden sie unter [ECMA C# and Common Language Infrastructure Standards (Standards von ECMA C# und Common Language Infrastructure)](http://go.microsoft.com/fwlink/?LinkID=99212) auf MSDN und [Standard ECMA-335 - Common Language Infrastructure (CLI) (Standard ECMA-335 – Common Language Infrastructure (CLI))](http://go.microsoft.com/fwlink/?LinkID=65552) auf der Ecma International-Website.</span><span class="sxs-lookup"><span data-stu-id="f039b-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f039b-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f039b-113">Requirements</span></span>  
 <span data-ttu-id="f039b-114">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f039b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f039b-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f039b-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f039b-116">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f039b-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f039b-117">**.NET Framework-Versionen**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f039b-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f039b-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f039b-118">See Also</span></span>  
 [<span data-ttu-id="f039b-119">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f039b-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="f039b-120">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f039b-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
