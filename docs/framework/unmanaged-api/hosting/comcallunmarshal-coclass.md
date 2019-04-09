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
ms.openlocfilehash: 2f17a88a90905006432ae8c5dc040277124c947b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59166880"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="d02d9-102">ComCallUnmarshal-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="d02d9-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="d02d9-103">Stellt Schnittstellen zum Verwalten von das Marshalling der Schnittstellenzeiger bereit.</span><span class="sxs-lookup"><span data-stu-id="d02d9-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d02d9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d02d9-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="d02d9-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d02d9-105">Interfaces</span></span>  
  
|<span data-ttu-id="d02d9-106">Interface</span><span class="sxs-lookup"><span data-stu-id="d02d9-106">Interface</span></span>|<span data-ttu-id="d02d9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d02d9-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="d02d9-108">Stellt Methoden zum Erstellen, initialisieren und verwalten einen Proxy in einen Clientprozess.</span><span class="sxs-lookup"><span data-stu-id="d02d9-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d02d9-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d02d9-109">Requirements</span></span>  
 <span data-ttu-id="d02d9-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d02d9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d02d9-111">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="d02d9-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="d02d9-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d02d9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d02d9-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="d02d9-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d02d9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d02d9-114">See also</span></span>

- [<span data-ttu-id="d02d9-115">Hosting-Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="d02d9-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
