---
title: IMetaDataImport::ResetEnum-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.ResetEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::ResetEnum
helpviewer_keywords:
- ResetEnum method [.NET Framework metadata]
- IMetaDataImport::ResetEnum method [.NET Framework metadata]
ms.assetid: dda867b5-1050-49ba-b01c-fcc83b7a5617
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 2cdb4c00185d152be856a99e1fec9392fd2a4029
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportresetenum-method"></a><span data-ttu-id="1ab53-102">IMetaDataImport::ResetEnum-Methode</span><span class="sxs-lookup"><span data-stu-id="1ab53-102">IMetaDataImport::ResetEnum Method</span></span>
<span data-ttu-id="1ab53-103">Setzt den angegebenen Enumerator auf die der angegebene Position zurück.</span><span class="sxs-lookup"><span data-stu-id="1ab53-103">Resets the specified enumerator to the specified position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ab53-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ab53-104">Syntax</span></span>  
  
```  
HRESULT ResetEnum (  
   [in] HCORENUM    hEnum,   
   [in] ULONG       ulPos  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1ab53-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ab53-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="1ab53-106">[in] Der Enumerator zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="1ab53-106">[in] The enumerator to reset.</span></span>  
  
 `ulPos`  
 <span data-ttu-id="1ab53-107">[in] Die neue Position, an der den Enumerator platziert werden soll.</span><span class="sxs-lookup"><span data-stu-id="1ab53-107">[in] The new position at which to place the enumerator.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ab53-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1ab53-108">Requirements</span></span>  
 <span data-ttu-id="1ab53-109">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ab53-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ab53-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1ab53-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1ab53-111">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1ab53-111">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1ab53-112">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ab53-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ab53-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ab53-113">See Also</span></span>  
 [<span data-ttu-id="1ab53-114">IMetaDataImport-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ab53-114">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="1ab53-115">IMetaDataImport2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1ab53-115">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
