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
ms.openlocfilehash: 489fa217744e41ccb5d27d088790131c15e1ee52
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177397"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="c1642-102">IMetaDataError::OnError-Methode</span><span class="sxs-lookup"><span data-stu-id="c1642-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="c1642-103">Stellt eine Benachrichtigung über Fehler bereit, die während der Metadatenzusammenführung auftreten.</span><span class="sxs-lookup"><span data-stu-id="c1642-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1642-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1642-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1642-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="c1642-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="c1642-106">[in] Der HRESULT-Fehlerwert, der an die aufrufende Methode zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="c1642-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="c1642-107">[in] Das Metadatentoken des Codeobjekts, das beim Auftreten des Fehlers zusammengeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="c1642-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1642-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c1642-108">Requirements</span></span>  
 <span data-ttu-id="c1642-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1642-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1642-110">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c1642-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c1642-111">**Bibliothek:** Wird als Ressource in MsCorEE.dll verwendet</span><span class="sxs-lookup"><span data-stu-id="c1642-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c1642-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1642-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1642-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c1642-113">See also</span></span>

- [<span data-ttu-id="c1642-114">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c1642-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
