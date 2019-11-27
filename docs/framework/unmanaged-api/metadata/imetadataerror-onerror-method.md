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
ms.openlocfilehash: f10c55abcc044b5bbdbb940001a25f530a4688e4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431222"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="7f860-102">IMetaDataError::OnError-Methode</span><span class="sxs-lookup"><span data-stu-id="7f860-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="7f860-103">Gibt Benachrichtigungen zu Fehlern, die während der Zusammenführung der Metadaten auftreten.</span><span class="sxs-lookup"><span data-stu-id="7f860-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f860-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7f860-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,   
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7f860-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="7f860-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="7f860-106">in Der HRESULT-Fehlerwert, der an die Aufruf Methode zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="7f860-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="7f860-107">in Das Metadatentoken des Code Objekts, das zusammengeführt wurde, als der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="7f860-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7f860-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="7f860-108">Requirements</span></span>  
 <span data-ttu-id="7f860-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f860-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f860-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7f860-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7f860-111">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="7f860-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7f860-112">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f860-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f860-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f860-113">See also</span></span>

- [<span data-ttu-id="7f860-114">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7f860-114">IMetaDataError Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md)
