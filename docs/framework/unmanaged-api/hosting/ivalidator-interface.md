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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59121913"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="65c1c-102">IValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="65c1c-102">IValidator Interface</span></span>
<span data-ttu-id="65c1c-103">Stellt Methoden zum Überprüfen der übertragbaren ausführbaren Datei (PE)-Abbildern, und Melden von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="65c1c-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="65c1c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="65c1c-104">Methods</span></span>  
  
|<span data-ttu-id="65c1c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="65c1c-105">Method</span></span>|<span data-ttu-id="65c1c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="65c1c-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="65c1c-107">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="65c1c-107">Validate</span></span>|<span data-ttu-id="65c1c-108">Überprüft die angegebene PE oder Microsoft intermediate Language (MSIL)-Datei an.</span><span class="sxs-lookup"><span data-stu-id="65c1c-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="65c1c-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="65c1c-109">FormatEventInfo</span></span>|<span data-ttu-id="65c1c-110">Ruft die Fehlermeldung, die für den angegebenen Validierungsfehler ab.</span><span class="sxs-lookup"><span data-stu-id="65c1c-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65c1c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="65c1c-111">Requirements</span></span>  
 <span data-ttu-id="65c1c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65c1c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65c1c-113">**Header:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="65c1c-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="65c1c-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="65c1c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="65c1c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65c1c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c1c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65c1c-116">See also</span></span>

- [<span data-ttu-id="65c1c-117">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="65c1c-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="65c1c-118">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="65c1c-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
