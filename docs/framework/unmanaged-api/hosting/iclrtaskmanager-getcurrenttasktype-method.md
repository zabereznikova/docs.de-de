---
title: ICLRTaskManager::GetCurrentTaskType-Methode
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTaskType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTaskType
helpviewer_keywords:
- GetCurrentTaskType method [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTaskType method [.NET Framework hosting]
ms.assetid: 6b0d9259-dbe2-45bb-b34d-990f60c73424
topic_type:
- apiref
ms.openlocfilehash: 684b94471c53701c5ebe1dc7e7593eae16ad50fd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728783"
---
# <a name="iclrtaskmanagergetcurrenttasktype-method"></a><span data-ttu-id="f0ba7-102">ICLRTaskManager::GetCurrentTaskType-Methode</span><span class="sxs-lookup"><span data-stu-id="f0ba7-102">ICLRTaskManager::GetCurrentTaskType Method</span></span>

<span data-ttu-id="f0ba7-103">Ruft den Typ der Aufgabe ab, die gerade ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f0ba7-103">Gets the type of the task that is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0ba7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0ba7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCurrentTaskType(  
    [out] ETaskType *pTaskType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0ba7-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f0ba7-105">Parameters</span></span>  

 `pTaskType`  
 <span data-ttu-id="f0ba7-106">vorgenommen Ein Zeiger auf einen Wert der [ETaskType](etasktype-enumeration.md) -Enumeration, der den Typ des aktuell ausgeführten Tasks angibt.</span><span class="sxs-lookup"><span data-stu-id="f0ba7-106">[out] A pointer to a value of the [ETaskType](etasktype-enumeration.md) enumeration that indicates the type of task that is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0ba7-107">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f0ba7-107">Requirements</span></span>  

 <span data-ttu-id="f0ba7-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0ba7-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0ba7-109">**Header:** Mscoree. h</span><span class="sxs-lookup"><span data-stu-id="f0ba7-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f0ba7-110">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f0ba7-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f0ba7-111">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0ba7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0ba7-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0ba7-112">See also</span></span>

- [<span data-ttu-id="f0ba7-113">ICLRTaskManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f0ba7-113">ICLRTaskManager Interface</span></span>](iclrtaskmanager-interface.md)
