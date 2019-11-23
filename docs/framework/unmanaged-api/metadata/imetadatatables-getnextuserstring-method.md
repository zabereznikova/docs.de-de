---
title: IMetaDataTables::GetNextUserString-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextUserString
helpviewer_keywords:
- GetNextUserString method [.NET Framework metadata]
- IMetaDataTables::GetNextUserString method [.NET Framework metadata]
ms.assetid: b7cb40ee-67b7-4f4e-8dcc-ee7ac8bc986b
topic_type:
- apiref
ms.openlocfilehash: 44ae2d16563220f8f5b81b6f609dee7df715fd0e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447394"
---
# <a name="imetadatatablesgetnextuserstring-method"></a><span data-ttu-id="baa97-102">IMetaDataTables::GetNextUserString-Methode</span><span class="sxs-lookup"><span data-stu-id="baa97-102">IMetaDataTables::GetNextUserString Method</span></span>
<span data-ttu-id="baa97-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span><span class="sxs-lookup"><span data-stu-id="baa97-103">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baa97-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="baa97-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNextUserString (  
    [in]  ULONG   ixUserString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baa97-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="baa97-105">Parameters</span></span>  
 `ixUserString`  
 <span data-ttu-id="baa97-106">[in] An index value from the current string column.</span><span class="sxs-lookup"><span data-stu-id="baa97-106">[in] An index value from the current string column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="baa97-107">[out] A pointer to the row index of the next string in the column.</span><span class="sxs-lookup"><span data-stu-id="baa97-107">[out] A pointer to the row index of the next string in the column.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="baa97-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="baa97-108">Remarks</span></span>  
 <span data-ttu-id="baa97-109">We do not recommend the use of this method, because it does not return consistent results.</span><span class="sxs-lookup"><span data-stu-id="baa97-109">We do not recommend the use of this method, because it does not return consistent results.</span></span> <span data-ttu-id="baa97-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span><span class="sxs-lookup"><span data-stu-id="baa97-110">For information about the GUID table, see the Common Language Infrastructure (CLI) documentation, especially "Partition II: Metadata Definition and Semantics".</span></span> <span data-ttu-id="baa97-111">Die Dokumentation ist online verfügbar. Sie finden sie unter [ECMA C# and Common Language Infrastructure Standards (Standards von ECMA C# und Common Language Infrastructure)](https://go.microsoft.com/fwlink/?LinkID=99212) auf MSDN und [Standard ECMA-335 - Common Language Infrastructure (CLI) (Standard ECMA-335 – Common Language Infrastructure (CLI))](https://go.microsoft.com/fwlink/?LinkID=65552) auf der Ecma International-Website.</span><span class="sxs-lookup"><span data-stu-id="baa97-111">The documentation is available online; see [ECMA C# and Common Language Infrastructure Standards](https://go.microsoft.com/fwlink/?LinkID=99212) on MSDN and [Standard ECMA-335 - Common Language Infrastructure (CLI)](https://go.microsoft.com/fwlink/?LinkID=65552) on the Ecma International Web site.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baa97-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="baa97-112">Requirements</span></span>  
 <span data-ttu-id="baa97-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baa97-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baa97-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="baa97-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="baa97-115">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="baa97-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="baa97-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baa97-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baa97-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="baa97-117">See also</span></span>

- [<span data-ttu-id="baa97-118">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="baa97-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="baa97-119">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="baa97-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
