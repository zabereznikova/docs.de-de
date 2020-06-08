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
ms.openlocfilehash: d2252f58af1a319d953fb320a99fad1cfec3dca0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492719"
---
# <a name="imetadataerroronerror-method"></a><span data-ttu-id="437d4-102">IMetaDataError::OnError-Methode</span><span class="sxs-lookup"><span data-stu-id="437d4-102">IMetaDataError::OnError Method</span></span>
<span data-ttu-id="437d4-103">Gibt Benachrichtigungen zu Fehlern, die während der Zusammenführung der Metadaten auftreten.</span><span class="sxs-lookup"><span data-stu-id="437d4-103">Provides notification of errors that occur during the metadata merge.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="437d4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="437d4-104">Syntax</span></span>  
  
```cpp  
HRESULT OnError (  
    [in] HRESULT   hrError,
    [in] mdToken   token  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="437d4-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="437d4-105">Parameters</span></span>  
 `hrError`  
 <span data-ttu-id="437d4-106">in Der HRESULT-Fehlerwert, der an die Aufruf Methode zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="437d4-106">[in] The HRESULT error value returned to the calling method.</span></span>  
  
 `token`  
 <span data-ttu-id="437d4-107">in Das Metadatentoken des Code Objekts, das zusammengeführt wurde, als der Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="437d4-107">[in] The metadata token of the code object that was being merged when the error occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="437d4-108">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="437d4-108">Requirements</span></span>  
 <span data-ttu-id="437d4-109">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="437d4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="437d4-110">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="437d4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="437d4-111">**Bibliothek:** Wird als Ressource in Mscoree. dll verwendet.</span><span class="sxs-lookup"><span data-stu-id="437d4-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="437d4-112">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="437d4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="437d4-113">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="437d4-113">See also</span></span>

- [<span data-ttu-id="437d4-114">IMetaDataError-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="437d4-114">IMetaDataError Interface</span></span>](imetadataerror-interface.md)
