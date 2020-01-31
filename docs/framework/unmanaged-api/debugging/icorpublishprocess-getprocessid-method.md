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
ms.openlocfilehash: 4cc6bbde2c7367c1109ca73e66f2670a56b2cdbe
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790554"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="9c9f7-102">ICorPublishProcess::GetProcessID-Methode</span><span class="sxs-lookup"><span data-stu-id="9c9f7-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="9c9f7-103">Ruft den Betriebssystem Bezeichner für diesen Prozess ab.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c9f7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9c9f7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c9f7-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9c9f7-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="9c9f7-106">vorgenommen Ein Zeiger auf den Bezeichner des Prozesses, der durch dieses [ICorPublishProcess](icorpublishprocess-interface.md) -Objekt dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="9c9f7-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c9f7-107">-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="9c9f7-107">Requirements</span></span>  
 <span data-ttu-id="9c9f7-108">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c9f7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c9f7-109">**Header:** Corpub. idl, Corpub. h</span><span class="sxs-lookup"><span data-stu-id="9c9f7-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="9c9f7-110">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c9f7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c9f7-111">**.NET Framework Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c9f7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c9f7-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9c9f7-112">See also</span></span>

- [<span data-ttu-id="9c9f7-113">ICorPublishProcess-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="9c9f7-113">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)
