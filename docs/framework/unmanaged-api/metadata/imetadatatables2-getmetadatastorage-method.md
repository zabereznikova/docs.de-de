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
ms.openlocfilehash: e832bbb58a08c50d8c2bb37fa0c310ef3133d02c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54583636"
---
# <a name="imetadatatables2getmetadatastorage-method"></a><span data-ttu-id="d36a8-102">IMetaDataTables2::GetMetaDataStorage-Methode</span><span class="sxs-lookup"><span data-stu-id="d36a8-102">IMetaDataTables2::GetMetaDataStorage Method</span></span>
<span data-ttu-id="d36a8-103">Ruft ab, die Größe und den Inhalt der Metadaten im angegebenen Abschnitt gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d36a8-103">Gets the size and contents of the metadata stored in the specified section.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d36a8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d36a8-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataStorage (  
   [in, out] const void   **ppvMd,  
   [out] ULONG   *pcbMd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d36a8-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d36a8-105">Parameters</span></span>  
 `ppvMd`  
 <span data-ttu-id="d36a8-106">[in, out] Ein Zeiger auf ein Metadatenabschnitt.</span><span class="sxs-lookup"><span data-stu-id="d36a8-106">[in, out] A pointer to a metadata section.</span></span>  
  
 `pcbMd`  
 <span data-ttu-id="d36a8-107">[out] Die Größe des Metadatenstreams, der.</span><span class="sxs-lookup"><span data-stu-id="d36a8-107">[out] The size of the metadata stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d36a8-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d36a8-108">Requirements</span></span>  
 <span data-ttu-id="d36a8-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d36a8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d36a8-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d36a8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d36a8-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="d36a8-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d36a8-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d36a8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d36a8-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d36a8-113">See also</span></span>
- [<span data-ttu-id="d36a8-114">IMetaDataTables2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d36a8-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
- [<span data-ttu-id="d36a8-115">IMetaDataTables-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d36a8-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
