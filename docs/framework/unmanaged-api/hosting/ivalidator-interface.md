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
ms.openlocfilehash: 9e79a69bf71aee035fb1f9a0178879d7c19e62b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448920"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="d923e-102">IValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="d923e-102">IValidator Interface</span></span>
<span data-ttu-id="d923e-103">Stellt Methoden zum Überprüfen von portablen ausführbaren Datei (PE) Bilder aus, und Melden von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="d923e-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d923e-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="d923e-104">Methods</span></span>  
  
|<span data-ttu-id="d923e-105">Methode</span><span class="sxs-lookup"><span data-stu-id="d923e-105">Method</span></span>|<span data-ttu-id="d923e-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d923e-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d923e-107">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="d923e-107">Validate</span></span>|<span data-ttu-id="d923e-108">Überprüft die angegebene PE oder Microsoft intermediate Language (MSIL)-Datei.</span><span class="sxs-lookup"><span data-stu-id="d923e-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="d923e-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="d923e-109">FormatEventInfo</span></span>|<span data-ttu-id="d923e-110">Ruft die Fehlermeldung, die entsprechend des angegebenen Validierungsfehlers ab.</span><span class="sxs-lookup"><span data-stu-id="d923e-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d923e-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="d923e-111">Requirements</span></span>  
 <span data-ttu-id="d923e-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d923e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d923e-113">**Header:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="d923e-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="d923e-114">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="d923e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d923e-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d923e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d923e-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d923e-116">See Also</span></span>  
 [<span data-ttu-id="d923e-117">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="d923e-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="d923e-118">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="d923e-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
