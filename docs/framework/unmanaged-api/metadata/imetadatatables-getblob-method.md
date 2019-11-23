---
title: IMetaDataTables::GetBlob-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
ms.openlocfilehash: f5a736d80f36afb8d0a643d4a4e36c9abff01995
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445427"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="8b124-102">IMetaDataTables::GetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="8b124-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="8b124-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span><span class="sxs-lookup"><span data-stu-id="8b124-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b124-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8b124-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b124-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="8b124-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="8b124-106">[in] The memory address from which to get `ppData`.</span><span class="sxs-lookup"><span data-stu-id="8b124-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="8b124-107">[out] A pointer to the size, in bytes, of `ppData`.</span><span class="sxs-lookup"><span data-stu-id="8b124-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="8b124-108">[out] A pointer to a pointer to the binary data retrieved.</span><span class="sxs-lookup"><span data-stu-id="8b124-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b124-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="8b124-109">Requirements</span></span>  
 <span data-ttu-id="8b124-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b124-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b124-111">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8b124-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b124-112">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b124-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8b124-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b124-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b124-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b124-114">See also</span></span>

- [<span data-ttu-id="8b124-115">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b124-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8b124-116">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="8b124-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
