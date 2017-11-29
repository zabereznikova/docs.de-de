---
title: IValidator-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IValidator
api_location: mscoree.dll
api_type: COM
f1_keywords: IValidator
helpviewer_keywords: IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7d88bfa0a3e71f34a7439e97f4347a06aa2c4058
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ivalidator-interface"></a><span data-ttu-id="19e08-102">IValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="19e08-102">IValidator Interface</span></span>
<span data-ttu-id="19e08-103">Stellt Methoden zum Überprüfen von portablen ausführbaren Datei (PE) Bilder aus, und Melden von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="19e08-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19e08-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="19e08-104">Methods</span></span>  
  
|<span data-ttu-id="19e08-105">Methode</span><span class="sxs-lookup"><span data-stu-id="19e08-105">Method</span></span>|<span data-ttu-id="19e08-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="19e08-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="19e08-107">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="19e08-107">Validate</span></span>|<span data-ttu-id="19e08-108">Überprüft die angegebene PE oder Microsoft intermediate Language (MSIL)-Datei.</span><span class="sxs-lookup"><span data-stu-id="19e08-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="19e08-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="19e08-109">FormatEventInfo</span></span>|<span data-ttu-id="19e08-110">Ruft die Fehlermeldung, die entsprechend des angegebenen Validierungsfehlers ab.</span><span class="sxs-lookup"><span data-stu-id="19e08-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="19e08-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="19e08-111">Requirements</span></span>  
 <span data-ttu-id="19e08-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19e08-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19e08-113">**Header:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="19e08-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="19e08-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="19e08-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="19e08-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19e08-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19e08-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="19e08-116">See Also</span></span>  
 [<span data-ttu-id="19e08-117">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="19e08-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="19e08-118">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="19e08-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
