---
title: ICorPublishProcess::GetProcessID-Methode
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
ms.openlocfilehash: b0defd0a9c4197cf91fde1625794ff0d77c83ea0
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693137"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="60adc-102">ICorPublishProcess::GetProcessID-Methode</span><span class="sxs-lookup"><span data-stu-id="60adc-102">ICorPublishProcess::GetProcessID Method</span></span>

<span data-ttu-id="60adc-103">Ruft den Betriebssystem Bezeichner für diesen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="60adc-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="60adc-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="60adc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="60adc-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="60adc-105">Parameters</span></span>  

 `pid`  
 <span data-ttu-id="60adc-106">vorgenommen Ein Zeiger auf den Bezeichner des Prozesses, der durch dieses [ICorPublishProcess](icorpublishprocess-interface.md) -Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="60adc-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="60adc-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="60adc-107">Requirements</span></span>  

 <span data-ttu-id="60adc-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60adc-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60adc-109">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="60adc-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="60adc-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="60adc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="60adc-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60adc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60adc-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="60adc-112">See also</span></span>

- [<span data-ttu-id="60adc-113">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="60adc-113">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
