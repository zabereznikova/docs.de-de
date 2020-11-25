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
ms.openlocfilehash: 32f32625ee40d50249ce3e009add543c4137b196
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726469"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="3aaf3-102">IMetaDataTables::GetBlob-Methode</span><span class="sxs-lookup"><span data-stu-id="3aaf3-102">IMetaDataTables::GetBlob Method</span></span>

<span data-ttu-id="3aaf3-103">Ruft einen Zeiger auf den Binary Large Object (BLOB) am angegebenen Spalten Index ab.</span><span class="sxs-lookup"><span data-stu-id="3aaf3-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aaf3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3aaf3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3aaf3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3aaf3-105">Parameters</span></span>  

 `ixBlob`  
 <span data-ttu-id="3aaf3-106">in Die Speicheradresse, von der aus Sie abgeleitet werden soll `ppData` .</span><span class="sxs-lookup"><span data-stu-id="3aaf3-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="3aaf3-107">vorgenommen Ein Zeiger auf die Größe von in Bytes `ppData` .</span><span class="sxs-lookup"><span data-stu-id="3aaf3-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="3aaf3-108">vorgenommen Ein Zeiger auf einen Zeiger auf die abgerufenen Binärdaten.</span><span class="sxs-lookup"><span data-stu-id="3aaf3-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aaf3-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="3aaf3-109">Requirements</span></span>  

 <span data-ttu-id="3aaf3-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3aaf3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aaf3-111">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3aaf3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3aaf3-112">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="3aaf3-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3aaf3-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3aaf3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aaf3-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3aaf3-114">See also</span></span>

- [<span data-ttu-id="3aaf3-115">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3aaf3-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="3aaf3-116">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="3aaf3-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
