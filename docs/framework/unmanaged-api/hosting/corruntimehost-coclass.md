---
title: CorRuntimeHost-Co-Klasse
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 942c9544a6ce868c3b6296569d4a16a44281cdba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67758323"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="f30c9-102">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="f30c9-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="f30c9-103">Stellt Schnittstellen zum Verwalten von Anwendungen, die von der common Language Runtime ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f30c9-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f30c9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f30c9-104">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="f30c9-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f30c9-105">Interfaces</span></span>  
  
|<span data-ttu-id="f30c9-106">Interface</span><span class="sxs-lookup"><span data-stu-id="f30c9-106">Interface</span></span>|<span data-ttu-id="f30c9-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f30c9-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="f30c9-108">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f30c9-108">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)|<span data-ttu-id="f30c9-109">Stellt Methoden für die common Language Runtime (CLR) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f30c9-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="f30c9-110">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f30c9-110">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)|<span data-ttu-id="f30c9-111">Bietet Methoden, mit denen der Host zum Starten und beenden die common Language Runtime explizit zum Erstellen und Konfigurieren von Anwendungsdomänen, die Zugriff auf die Standarddomäne und zum Aufzählen von allen Domänen, die im Prozess ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f30c9-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="f30c9-112">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f30c9-112">IDebuggerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerinfo-interface.md)|<span data-ttu-id="f30c9-113">Stellt Methoden zum Abrufen von Informationen über den Status der Debugdienste bereit.</span><span class="sxs-lookup"><span data-stu-id="f30c9-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="f30c9-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f30c9-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)|<span data-ttu-id="f30c9-115">Stellt Methoden zum Abrufen von Informationen über die Garbage Collection-System und zum Steuern einige Aspekte der Garbagecollection.</span><span class="sxs-lookup"><span data-stu-id="f30c9-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="f30c9-116">"IValidator"</span><span class="sxs-lookup"><span data-stu-id="f30c9-116">"IValidator"</span></span>|<span data-ttu-id="f30c9-117">Stellt Methoden für die Überprüfung der portierbare ausführbare Images und ausführliche berichterstellung von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="f30c9-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f30c9-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f30c9-118">Requirements</span></span>  
 <span data-ttu-id="f30c9-119">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f30c9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f30c9-120">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="f30c9-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="f30c9-121">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f30c9-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f30c9-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f30c9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f30c9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f30c9-123">See also</span></span>

- [<span data-ttu-id="f30c9-124">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="f30c9-124">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
