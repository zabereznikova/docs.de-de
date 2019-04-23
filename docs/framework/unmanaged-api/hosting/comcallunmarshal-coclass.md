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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59166880"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="73eb7-102">ComCallUnmarshal-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="73eb7-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="73eb7-103">Stellt Schnittstellen zum Verwalten von das Marshalling der Schnittstellenzeiger bereit.</span><span class="sxs-lookup"><span data-stu-id="73eb7-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="73eb7-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="73eb7-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="73eb7-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="73eb7-105">Interfaces</span></span>  
  
|<span data-ttu-id="73eb7-106">Interface</span><span class="sxs-lookup"><span data-stu-id="73eb7-106">Interface</span></span>|<span data-ttu-id="73eb7-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="73eb7-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="73eb7-108">Stellt Methoden zum Erstellen, initialisieren und verwalten einen Proxy in einen Clientprozess.</span><span class="sxs-lookup"><span data-stu-id="73eb7-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="73eb7-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="73eb7-109">Requirements</span></span>  
 <span data-ttu-id="73eb7-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73eb7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73eb7-111">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="73eb7-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="73eb7-112">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="73eb7-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73eb7-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73eb7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73eb7-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73eb7-114">See also</span></span>

- [<span data-ttu-id="73eb7-115">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="73eb7-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
