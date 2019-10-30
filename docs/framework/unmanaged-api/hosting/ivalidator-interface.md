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
ms.openlocfilehash: 1a732e59d539c330f91e8665e81dc4771b40e2d0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123285"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="ee478-102">IValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="ee478-102">IValidator Interface</span></span>
<span data-ttu-id="ee478-103">Stellt Methoden zum Überprüfen von PE-Images (portable ausführbare Dateien) und zum Melden von Validierungs Fehlern bereit.</span><span class="sxs-lookup"><span data-stu-id="ee478-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ee478-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="ee478-104">Methods</span></span>  
  
|<span data-ttu-id="ee478-105">Methode</span><span class="sxs-lookup"><span data-stu-id="ee478-105">Method</span></span>|<span data-ttu-id="ee478-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee478-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="ee478-107">Überprüfen</span><span class="sxs-lookup"><span data-stu-id="ee478-107">Validate</span></span>|<span data-ttu-id="ee478-108">Überprüft die angegebene PE-oder MSIL-Datei (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="ee478-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="ee478-109">Format Event Info</span><span class="sxs-lookup"><span data-stu-id="ee478-109">FormatEventInfo</span></span>|<span data-ttu-id="ee478-110">Ruft die Fehlermeldung ab, die dem angegebenen Validierungs Fehler entspricht.</span><span class="sxs-lookup"><span data-stu-id="ee478-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ee478-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="ee478-111">Requirements</span></span>  
 <span data-ttu-id="ee478-112">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ee478-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ee478-113">**Header:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="ee478-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="ee478-114">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="ee478-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ee478-115">**.NET Framework-Versionen:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ee478-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee478-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ee478-116">See also</span></span>

- [<span data-ttu-id="ee478-117">Hosten von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="ee478-117">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="ee478-118">CorRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="ee478-118">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
