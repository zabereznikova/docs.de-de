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
ms.openlocfilehash: fe378307ce2bda6e1a267e46433ead70a0e2299e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616518"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="786f5-102">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="786f5-102">CorRuntimeHost Coclass</span></span>
<span data-ttu-id="786f5-103">Stellt Schnittstellen für die Verwaltung von Anwendungen bereit, die von der Common Language Runtime ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="786f5-103">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="786f5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="786f5-104">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="786f5-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="786f5-105">Interfaces</span></span>  
  
|<span data-ttu-id="786f5-106">Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="786f5-106">Interface</span></span>|<span data-ttu-id="786f5-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="786f5-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="786f5-108">ICorConfiguration-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="786f5-108">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)|<span data-ttu-id="786f5-109">Stellt Methoden zum Konfigurieren des Common Language Runtime (CLR) bereit.</span><span class="sxs-lookup"><span data-stu-id="786f5-109">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="786f5-110">ICorRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="786f5-110">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)|<span data-ttu-id="786f5-111">Stellt Methoden bereit, die es dem Host ermöglichen, den Common Language Runtime explizit zu starten und zu unterbinden, Anwendungs Domänen zu erstellen und zu konfigurieren, auf die Standard Domäne zuzugreifen und alle Domänen aufzuzählen, die im Prozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="786f5-111">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="786f5-112">IDebuggerInfo-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="786f5-112">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)|<span data-ttu-id="786f5-113">Stellt Methoden zum Abrufen von Informationen über den Zustand der Debugdienste bereit.</span><span class="sxs-lookup"><span data-stu-id="786f5-113">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="786f5-114">IGCHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="786f5-114">IGCHost Interface</span></span>](igchost-interface.md)|<span data-ttu-id="786f5-115">Bietet Methoden zum Abrufen von Informationen über das Garbage Collection System und zum Steuern einiger Aspekte von Garbage Collection.</span><span class="sxs-lookup"><span data-stu-id="786f5-115">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="786f5-116">IValidator</span><span class="sxs-lookup"><span data-stu-id="786f5-116">"IValidator"</span></span>|<span data-ttu-id="786f5-117">Stellt Methoden für die Validierung von portablen ausführbaren Images und die ausführliche Berichterstellung zu Validierungs Fehlern bereit.</span><span class="sxs-lookup"><span data-stu-id="786f5-117">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="786f5-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="786f5-118">Requirements</span></span>  
 <span data-ttu-id="786f5-119">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="786f5-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="786f5-120">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="786f5-120">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="786f5-121">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="786f5-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="786f5-122">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="786f5-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="786f5-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="786f5-123">See also</span></span>

- [<span data-ttu-id="786f5-124">Hosting-Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="786f5-124">Hosting Coclasses</span></span>](hosting-coclasses.md)
