---
title: IMetaDataTables::GetGuid-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetGuid
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetGuid
helpviewer_keywords:
- GetGuid method [.NET Framework metadata]
- IMetaDataTables::GetGuid method [.NET Framework metadata]
ms.assetid: a3546316-e24d-417f-9909-e45d42c9d471
topic_type:
- apiref
ms.openlocfilehash: 6f273cb03ad00957afb2bd78fe538a940fae236a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501234"
---
# <a name="imetadatatablesgetguid-method"></a><span data-ttu-id="6de90-102">IMetaDataTables::GetGuid-Methode</span><span class="sxs-lookup"><span data-stu-id="6de90-102">IMetaDataTables::GetGuid Method</span></span>
<span data-ttu-id="6de90-103">Ruft eine GUID aus der Zeile am angegebenen Index ab.</span><span class="sxs-lookup"><span data-stu-id="6de90-103">Gets a GUID from the row at the specified index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6de90-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6de90-104">Syntax</span></span>  
  
```cpp  
HRESULT GetGuid (
    [in]  ULONG       ixGuid,  
    [out] const GUID  **ppGUID  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6de90-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="6de90-105">Parameters</span></span>  
 `ixGuid`  
 <span data-ttu-id="6de90-106">in Der Index der Zeile, aus der die GUID abgeleitet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6de90-106">[in] The index of the row from which to get the GUID.</span></span>  
  
 `ppGuid`  
 <span data-ttu-id="6de90-107">vorgenommen Ein Zeiger auf einen Zeiger auf die GUID.</span><span class="sxs-lookup"><span data-stu-id="6de90-107">[out] A pointer to a pointer to the GUID.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6de90-108">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6de90-108">Remarks</span></span>  

  <span data-ttu-id="6de90-109">Die Verwendung dieser Methode wird nicht empfohlen, da Sie keine konsistenten Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6de90-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="6de90-110">Weitere Informationen zur GUID-Tabelle finden Sie in der Common Language Infrastructure (CLI)-Dokumentation, insbesondere "Partition II: Metadatendefinition und Semantik".</span><span class="sxs-lookup"><span data-stu-id="6de90-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="6de90-111">Die Dokumentation ist online verfügbar. Weitere Informationen finden Sie unter [ECMA c# und Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) und [Standard-ECMA-335-Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="6de90-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](../../../standard/components.md#applicable-standards) and [Standard ECMA-335 - Common Language Infrastructure (CLI)](http://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6de90-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="6de90-112">Requirements</span></span>  
 <span data-ttu-id="6de90-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6de90-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6de90-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6de90-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6de90-115">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="6de90-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6de90-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6de90-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6de90-117">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="6de90-117">See also</span></span>

- [<span data-ttu-id="6de90-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6de90-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="6de90-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6de90-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
