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
ms.openlocfilehash: 7884d53630ca13a30d7b4efd55d46684a9dd7d30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427641"
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="99d42-102">ComCallUnmarshal-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="99d42-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="99d42-103">Stellt Schnittstellen für die Verwaltung, das das Marshalling von Schnittstellenzeigern bereit.</span><span class="sxs-lookup"><span data-stu-id="99d42-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99d42-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="99d42-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="99d42-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="99d42-105">Interfaces</span></span>  
  
|<span data-ttu-id="99d42-106">Interface</span><span class="sxs-lookup"><span data-stu-id="99d42-106">Interface</span></span>|<span data-ttu-id="99d42-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="99d42-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="99d42-108">Stellt Methoden zum Erstellen, initialisieren und Verwalten eines Proxys in einem Clientprozess bereit.</span><span class="sxs-lookup"><span data-stu-id="99d42-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="99d42-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="99d42-109">Requirements</span></span>  
 <span data-ttu-id="99d42-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99d42-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99d42-111">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="99d42-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="99d42-112">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="99d42-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="99d42-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99d42-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99d42-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="99d42-114">See Also</span></span>  
 [<span data-ttu-id="99d42-115">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="99d42-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
