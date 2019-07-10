---
title: IMetaDataTables::GetStringHeapSize-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetStringHeapSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetStringHeapSize
helpviewer_keywords:
- IMetaDataTables::GetStringHeapSize method [.NET Framework metadata]
- GetStringHeapSize method [.NET Framework metadata]
ms.assetid: ed8f6335-81f5-4c09-81a9-2a909fc530c9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b842fb4d0853f473ae8e237a42e800cf0af8dc11
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781390"
---
# <a name="imetadatatablesgetstringheapsize-method"></a><span data-ttu-id="71aa6-102">IMetaDataTables::GetStringHeapSize-Methode</span><span class="sxs-lookup"><span data-stu-id="71aa6-102">IMetaDataTables::GetStringHeapSize Method</span></span>
<span data-ttu-id="71aa6-103">Ruft die Größe in Bytes, der dem String-Heap an.</span><span class="sxs-lookup"><span data-stu-id="71aa6-103">Gets the size, in bytes, of the string heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71aa6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="71aa6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStringHeapSize (  
    [out] ULONG   *pcbStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="71aa6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="71aa6-105">Parameters</span></span>  
 `pcbStrings`  
 <span data-ttu-id="71aa6-106">[out] Ein Zeiger auf die Größe in Bytes, der dem String-Heap.</span><span class="sxs-lookup"><span data-stu-id="71aa6-106">[out] A pointer to the size, in bytes, of the string heap.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71aa6-107">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="71aa6-107">Requirements</span></span>  
 <span data-ttu-id="71aa6-108">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71aa6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71aa6-109">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="71aa6-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71aa6-110">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="71aa6-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71aa6-111">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71aa6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71aa6-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71aa6-112">See also</span></span>

- [<span data-ttu-id="71aa6-113">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71aa6-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="71aa6-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="71aa6-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
