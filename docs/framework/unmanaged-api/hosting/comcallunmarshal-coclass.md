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
ms.openlocfilehash: 38f3140a181deae1a86569bfc2eb7cf3cd7d1991
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131933"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="45ff9-102">ComCallUnmarshal-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="45ff9-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="45ff9-103">Stellt Schnittstellen zum Verwalten des Marshalling von Schnittstellen Zeigern bereit.</span><span class="sxs-lookup"><span data-stu-id="45ff9-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45ff9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="45ff9-104">Syntax</span></span>  
  
```cpp  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="45ff9-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="45ff9-105">Interfaces</span></span>  
  
|<span data-ttu-id="45ff9-106">Interface</span><span class="sxs-lookup"><span data-stu-id="45ff9-106">Interface</span></span>|<span data-ttu-id="45ff9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="45ff9-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="45ff9-108">Stellt Methoden zum Erstellen, initialisieren und Verwalten eines Proxys in einem Client Prozess bereit.</span><span class="sxs-lookup"><span data-stu-id="45ff9-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="45ff9-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="45ff9-109">Requirements</span></span>  
 <span data-ttu-id="45ff9-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45ff9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45ff9-111">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="45ff9-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="45ff9-112">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="45ff9-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="45ff9-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45ff9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45ff9-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="45ff9-114">See also</span></span>

- [<span data-ttu-id="45ff9-115">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="45ff9-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
