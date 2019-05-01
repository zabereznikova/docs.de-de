---
title: IMetaDataError::OnError-Methode
ms.date: 03/30/2017
api_name:
- IMetaDataError.OnError
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataError::OnError
helpviewer_keywords:
- IMetaDataError::OnError method [.NET Framework metadata]
- OnError method, IMetaDataError interface [.NET Framework metadata]
ms.assetid: c1e744b8-a6fb-4d9c-a971-8babc875d8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 68fe41afa1999295a32b930b779991e2bbddb19a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62042767"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="eb39f-102">IMetaDataError::OnError-Methode</span><span class="sxs-lookup"><span data-stu-id="eb39f-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="eb39f-103">Stellt eine Benachrichtigung von Fehlern, während das Zusammenführen von Metadaten bereit.</span><span class="sxs-lookup"><span data-stu-id="eb39f-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb39f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb39f-104">Syntax</span></span>  
  
```  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eb39f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb39f-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="eb39f-106">[in] Der Wert des HRESULT-Fehlercodes, an die aufrufende Methode zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="eb39f-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="eb39f-107">[in] Das Metadatentoken des Codeobjekts, die beim Auftreten des Fehlers zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="eb39f-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb39f-108">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eb39f-108">Requirements</span></span>  
 <span data-ttu-id="eb39f-109">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb39f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb39f-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eb39f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eb39f-111">**Bibliothek:** Als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="eb39f-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb39f-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb39f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb39f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb39f-113">See also</span></span>

- [<span data-ttu-id="eb39f-114">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb39f-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
