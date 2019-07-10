---
title: ComCallUnmarshal-Co-Klasse
ms.date: 03/30/2017
api_name:
- ComCallUnmarshal Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ComCallUnmarshal
helpviewer_keywords:
- ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fde42e3ecfac81a168920bc152833be7ba72b995
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779082"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="e76d7-102">ComCallUnmarshal-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="e76d7-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="e76d7-103">Stellt Schnittstellen zum Verwalten von das Marshalling der Schnittstellenzeiger bereit.</span><span class="sxs-lookup"><span data-stu-id="e76d7-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e76d7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e76d7-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="e76d7-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="e76d7-105">Interfaces</span></span>  
  
|<span data-ttu-id="e76d7-106">Interface</span><span class="sxs-lookup"><span data-stu-id="e76d7-106">Interface</span></span>|<span data-ttu-id="e76d7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e76d7-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="e76d7-108">Stellt Methoden zum Erstellen, initialisieren und verwalten einen Proxy in einen Clientprozess.</span><span class="sxs-lookup"><span data-stu-id="e76d7-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e76d7-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="e76d7-109">Requirements</span></span>  
 <span data-ttu-id="e76d7-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e76d7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e76d7-111">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="e76d7-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="e76d7-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="e76d7-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e76d7-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e76d7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e76d7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e76d7-114">See also</span></span>

- [<span data-ttu-id="e76d7-115">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="e76d7-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
