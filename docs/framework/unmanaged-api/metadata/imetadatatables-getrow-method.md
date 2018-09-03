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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d24dbcbdd8b0ed0736f7b59564cf72dffaa5a8f8
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43463951"
---
# <a name="imetadatatablesgetrow-method"></a><span data-ttu-id="f87b8-102">IMetaDataTables::GetRow-Methode</span><span class="sxs-lookup"><span data-stu-id="f87b8-102">IMetaDataTables::GetRow Method</span></span>
<span data-ttu-id="f87b8-103">Ruft die Zeile am angegebenen Zeilenindex, in der Tabelle auf den Index der angegebenen Tabelle.</span><span class="sxs-lookup"><span data-stu-id="f87b8-103">Gets the row at the specified row index, in the table at the specified table index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f87b8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f87b8-104">Syntax</span></span>  
  
```  
HRESULT GetRow (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   rid,  
    [out] void    **ppRow  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f87b8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f87b8-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="f87b8-106">[in] Der Index des in der Tabelle, aus der die Zeile abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="f87b8-106">[in] The index of the table from which the row will be retrieved.</span></span>  
  
 `rid`  
 <span data-ttu-id="f87b8-107">[in] Der Index der abzurufenden Zeile.</span><span class="sxs-lookup"><span data-stu-id="f87b8-107">[in] The index of the row to get.</span></span>  
  
 `ppRow`  
 <span data-ttu-id="f87b8-108">[out] Ein Zeiger auf einen Zeiger auf die Zeile.</span><span class="sxs-lookup"><span data-stu-id="f87b8-108">[out] A pointer to a pointer to the row.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f87b8-109">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f87b8-109">Remarks</span></span>  
 <span data-ttu-id="f87b8-110">Die Verwendung von dieser Methode wird nicht empfohlen, da es keine konsistente Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f87b8-110">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="f87b8-111">Informationen über den GUID-Tabelle finden Sie unter der Common Language Infrastructure (CLI)-Dokumentation, besonders in "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="f87b8-111">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="f87b8-112">Die Dokumentation ist online verfügbar. Sie finden sie unter [ECMA C# and Common Language Infrastructure Standards (Standards von ECMA C# und Common Language Infrastructure)](https://go.microsoft.com/fwlink/?LinkID=99212) auf MSDN und [Standard ECMA-335 - Common Language Infrastructure (CLI) (Standard ECMA-335 – Common Language Infrastructure (CLI))](https://go.microsoft.com/fwlink/?LinkID=65552) auf der Ecma International-Website.</span><span class="sxs-lookup"><span data-stu-id="f87b8-112">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f87b8-113">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f87b8-113">Requirements</span></span>  
 <span data-ttu-id="f87b8-114">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f87b8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f87b8-115">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f87b8-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f87b8-116">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="f87b8-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f87b8-117">**.NET Framework-Versionen**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f87b8-117">**.NET Framework Versions**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f87b8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f87b8-118">See Also</span></span>  
 [<span data-ttu-id="f87b8-119">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f87b8-119">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="f87b8-120">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f87b8-120">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
