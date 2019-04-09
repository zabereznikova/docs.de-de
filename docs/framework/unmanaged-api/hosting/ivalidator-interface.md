---
title: IValidator-Schnittstelle
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f516bf1f19e4d4a77e2d6af834a1c3d4e34c327
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59121913"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="1011b-102">IValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="1011b-102">IValidator Interface</span></span>
<span data-ttu-id="1011b-103">Stellt Methoden zum Überprüfen der übertragbaren ausführbaren Datei (PE)-Abbildern, und Melden von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="1011b-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1011b-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="1011b-104">Methods</span></span>  
  
|<span data-ttu-id="1011b-105">Methode</span><span class="sxs-lookup"><span data-stu-id="1011b-105">Method</span></span>|<span data-ttu-id="1011b-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1011b-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="1011b-107">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="1011b-107">Validate</span></span>|<span data-ttu-id="1011b-108">Überprüft die angegebene PE oder Microsoft intermediate Language (MSIL)-Datei an.</span><span class="sxs-lookup"><span data-stu-id="1011b-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="1011b-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="1011b-109">FormatEventInfo</span></span>|<span data-ttu-id="1011b-110">Ruft die Fehlermeldung, die für den angegebenen Validierungsfehler ab.</span><span class="sxs-lookup"><span data-stu-id="1011b-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1011b-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="1011b-111">Requirements</span></span>  
 <span data-ttu-id="1011b-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1011b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1011b-113">**Header:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="1011b-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="1011b-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="1011b-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1011b-115">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="1011b-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1011b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1011b-116">See also</span></span>

- [<span data-ttu-id="1011b-117">Hostingschnittstellen</span><span class="sxs-lookup"><span data-stu-id="1011b-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="1011b-118">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="1011b-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
