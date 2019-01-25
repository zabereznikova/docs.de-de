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
ms.openlocfilehash: 9f307ad5689602b030c609a51f6834bdbb0ec4f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54717714"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="f9c8c-102">IValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f9c8c-102">IValidator Interface</span></span>
<span data-ttu-id="f9c8c-103">Stellt Methoden zum Überprüfen der übertragbaren ausführbaren Datei (PE)-Abbildern, und Melden von Validierungsfehlern.</span><span class="sxs-lookup"><span data-stu-id="f9c8c-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f9c8c-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="f9c8c-104">Methods</span></span>  
  
|<span data-ttu-id="f9c8c-105">Methode</span><span class="sxs-lookup"><span data-stu-id="f9c8c-105">Method</span></span>|<span data-ttu-id="f9c8c-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f9c8c-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f9c8c-107">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="f9c8c-107">Validate</span></span>|<span data-ttu-id="f9c8c-108">Überprüft die angegebene PE oder Microsoft intermediate Language (MSIL)-Datei an.</span><span class="sxs-lookup"><span data-stu-id="f9c8c-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="f9c8c-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="f9c8c-109">FormatEventInfo</span></span>|<span data-ttu-id="f9c8c-110">Ruft die Fehlermeldung, die für den angegebenen Validierungsfehler ab.</span><span class="sxs-lookup"><span data-stu-id="f9c8c-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f9c8c-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9c8c-111">Requirements</span></span>  
 <span data-ttu-id="f9c8c-112">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9c8c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9c8c-113">**Header:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="f9c8c-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="f9c8c-114">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f9c8c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f9c8c-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9c8c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9c8c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9c8c-116">See also</span></span>
- [<span data-ttu-id="f9c8c-117">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="f9c8c-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="f9c8c-118">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="f9c8c-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
