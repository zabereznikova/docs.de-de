---
title: IMetaDataTables::GetGuid-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetGuid
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 52b96fbe582a5c8e1818462a5e28970dbaf50605
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="00be4-102">IMetaDataTables::GetGuid-Methode</span><span class="sxs-lookup"><span data-stu-id="00be4-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="00be4-103">Ruft eine GUID aus der Zeile am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="00be4-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00be4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="00be4-104">Syntax</span></span>  
  
```  
HRESULT GetGuid (   
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="00be4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="00be4-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="00be4-106">[in] Der Index der Zeile, aus der die GUID abgerufen.</span><span class="sxs-lookup"><span data-stu-id="00be4-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="00be4-107">[out] Ein Zeiger auf einen Zeiger auf die GUID.</span><span class="sxs-lookup"><span data-stu-id="00be4-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00be4-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="00be4-108">Remarks</span></span>  
 <span data-ttu-id="00be4-109">Die Verwendung dieser Methode wird nicht empfohlen, da er keine konsistente Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="00be4-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="00be4-110">Informationen über die GUID-Tabelle finden Sie unter der Common Language Infrastructure (CLI)-Dokumentation, insbesondere in "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="00be4-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="00be4-111">Die Dokumentation ist online verfügbar. Sie finden sie unter [ECMA C# and Common Language Infrastructure Standards (Standards von ECMA C# und Common Language Infrastructure)](http://go.microsoft.com/fwlink/?LinkID=99212) auf MSDN und [Standard ECMA-335 - Common Language Infrastructure (CLI) (Standard ECMA-335 – Common Language Infrastructure (CLI))](http://go.microsoft.com/fwlink/?LinkID=65552) auf der Ecma International-Website.</span><span class="sxs-lookup"><span data-stu-id="00be4-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](http://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00be4-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="00be4-112">Requirements</span></span>  
 <span data-ttu-id="00be4-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00be4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00be4-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="00be4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="00be4-115">**Bibliothek:** als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="00be4-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="00be4-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00be4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00be4-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="00be4-117">See Also</span></span>  
 [<span data-ttu-id="00be4-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00be4-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="00be4-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="00be4-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
