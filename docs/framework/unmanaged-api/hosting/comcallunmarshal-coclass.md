---
title: ComCallUnmarshal-Co-Klasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ComCallUnmarshal Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: ComCallUnmarshal
helpviewer_keywords: ComCallUnmarshal coclass [.NET Framework hosting]
ms.assetid: 2adb5827-2268-4914-a1c6-f62b61880a45
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2cbaefd2b2c3b79a97107f4aaa394a3db2c68b33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="comcallunmarshal-coclass"></a><span data-ttu-id="c0ff2-102">ComCallUnmarshal-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="c0ff2-102">ComCallUnmarshal Coclass</span></span>
<span data-ttu-id="c0ff2-103">Stellt Schnittstellen für die Verwaltung, das das Marshalling von Schnittstellenzeigern bereit.</span><span class="sxs-lookup"><span data-stu-id="c0ff2-103">Provides interfaces for managing the marshaling of interface pointers.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0ff2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="c0ff2-104">Syntax</span></span>  
  
```  
coclass ComCallUnmarshal {  
    [default] interface IMarshal;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="c0ff2-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="c0ff2-105">Interfaces</span></span>  
  
|<span data-ttu-id="c0ff2-106">Interface</span><span class="sxs-lookup"><span data-stu-id="c0ff2-106">Interface</span></span>|<span data-ttu-id="c0ff2-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c0ff2-107">Description</span></span>|  
|---------------|-----------------|  
|`IMarshal`|<span data-ttu-id="c0ff2-108">Stellt Methoden zum Erstellen, initialisieren und Verwalten eines Proxys in einem Clientprozess bereit.</span><span class="sxs-lookup"><span data-stu-id="c0ff2-108">Provides methods for creating, initializing, and managing a proxy in a client process.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0ff2-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c0ff2-109">Requirements</span></span>  
 <span data-ttu-id="c0ff2-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0ff2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0ff2-111">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="c0ff2-111">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="c0ff2-112">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c0ff2-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0ff2-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0ff2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ff2-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c0ff2-114">See Also</span></span>  
 [<span data-ttu-id="c0ff2-115">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="c0ff2-115">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
