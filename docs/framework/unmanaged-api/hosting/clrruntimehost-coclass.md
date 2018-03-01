---
title: CLRRuntimeHost-Co-Klasse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CLRRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CLRRuntimeHost
helpviewer_keywords:
- CLRRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 2ac9cbf5-8a2d-4e4f-8831-0dad8ef0a897
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 18e4518a2e321609a8add06c399ed9588748d1ae
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="24a13-102">CLRRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="24a13-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="24a13-103">Stellt Schnittstellen für die Verwaltung der Ausführung von Code von der Laufzeit bereit.</span><span class="sxs-lookup"><span data-stu-id="24a13-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24a13-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="24a13-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="24a13-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="24a13-105">Interfaces</span></span>  
  
|<span data-ttu-id="24a13-106">Interface</span><span class="sxs-lookup"><span data-stu-id="24a13-106">Interface</span></span>|<span data-ttu-id="24a13-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="24a13-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="24a13-108">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24a13-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="24a13-109">Stellt Methoden zum Steuern der Ausführung von Anwendungen von der Laufzeit bereit.</span><span class="sxs-lookup"><span data-stu-id="24a13-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="24a13-110">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="24a13-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="24a13-111">Stellt Methoden für die Überprüfung von portable ausführbare Images und ausführliche Melden von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="24a13-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24a13-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="24a13-112">Requirements</span></span>  
 <span data-ttu-id="24a13-113">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24a13-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24a13-114">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="24a13-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="24a13-115">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="24a13-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24a13-116">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24a13-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24a13-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="24a13-117">See Also</span></span>  
 [<span data-ttu-id="24a13-118">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="24a13-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
