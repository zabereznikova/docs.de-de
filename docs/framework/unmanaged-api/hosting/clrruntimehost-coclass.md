---
title: CLRRuntimeHost-Co-Klasse
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8bae2d134c412023d0f126453b5285662d994c78
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59207759"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="83e5e-102">CLRRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="83e5e-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="83e5e-103">Stellt Schnittstellen für die Verwaltung der Ausführung von Code von der Laufzeit bereit.</span><span class="sxs-lookup"><span data-stu-id="83e5e-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83e5e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="83e5e-104">Syntax</span></span>  
  
```  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="83e5e-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="83e5e-105">Interfaces</span></span>  
  
|<span data-ttu-id="83e5e-106">Interface</span><span class="sxs-lookup"><span data-stu-id="83e5e-106">Interface</span></span>|<span data-ttu-id="83e5e-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="83e5e-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="83e5e-108">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83e5e-108">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)|<span data-ttu-id="83e5e-109">Stellt Methoden zum Steuern der Ausführung von Anwendungen von der Laufzeit bereit.</span><span class="sxs-lookup"><span data-stu-id="83e5e-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="83e5e-110">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="83e5e-110">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)|<span data-ttu-id="83e5e-111">Stellt Methoden für die Überprüfung von portierbare ausführbare Images und detaillierte Melden von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="83e5e-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83e5e-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="83e5e-112">Requirements</span></span>  
 <span data-ttu-id="83e5e-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83e5e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83e5e-114">**Header:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="83e5e-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="83e5e-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="83e5e-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83e5e-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83e5e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83e5e-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="83e5e-117">See also</span></span>

- [<span data-ttu-id="83e5e-118">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="83e5e-118">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
