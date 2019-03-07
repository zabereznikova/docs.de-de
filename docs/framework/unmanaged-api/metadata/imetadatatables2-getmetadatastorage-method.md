---
title: IMetaDataTables2::GetMetaDataStorage-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataTables2.GetMetaDataStorage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables2::GetMetaDataStorage
helpviewer_keywords:
- GetMetaDataStorage method [.NET Framework metadata]
- IMetaDataTables2::GetMetaDataStorage method [.NET Framework metadata]
ms.assetid: 667a6d1e-753d-4ea2-8fd8-a8337d1bb9cd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1c177a315a76009b7ac82055cba2d0b23821333b
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494878"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="34aaa-102">IMetaDataTables2::GetMetaDataStorage-Methode</span><span class="sxs-lookup"><span data-stu-id="34aaa-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="34aaa-103">Ruft ab, die Größe und den Inhalt der Metadaten im angegebenen Abschnitt gespeichert.</span><span class="sxs-lookup"><span data-stu-id="34aaa-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34aaa-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="34aaa-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="34aaa-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="34aaa-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="34aaa-106">[in, out] Ein Zeiger auf ein Metadatenabschnitt.</span><span class="sxs-lookup"><span data-stu-id="34aaa-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="34aaa-107">[out] Die Größe des Metadatenstreams, der.</span><span class="sxs-lookup"><span data-stu-id="34aaa-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34aaa-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="34aaa-108">Requirements</span></span>  
 <span data-ttu-id="34aaa-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34aaa-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34aaa-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="34aaa-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34aaa-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="34aaa-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34aaa-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34aaa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34aaa-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34aaa-113">See also</span></span>
- [<span data-ttu-id="34aaa-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34aaa-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="34aaa-115">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="34aaa-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
