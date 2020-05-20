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
ms.openlocfilehash: 40766ce5837053493f2e3f1f25fe7d1d63ec695f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616800"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="4dc20-102">CLRRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="4dc20-102">CLRRuntimeHost Coclass</span></span>
<span data-ttu-id="4dc20-103">Stellt Schnittstellen zum Verwalten der Codeausführung durch die Laufzeit bereit.</span><span class="sxs-lookup"><span data-stu-id="4dc20-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4dc20-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="4dc20-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="4dc20-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="4dc20-105">Interfaces</span></span>  
  
|<span data-ttu-id="4dc20-106">Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dc20-106">Interface</span></span>|<span data-ttu-id="4dc20-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4dc20-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="4dc20-108">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dc20-108">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)|<span data-ttu-id="4dc20-109">Stellt Methoden zum Steuern der Ausführung von Anwendungen durch die Laufzeit bereit.</span><span class="sxs-lookup"><span data-stu-id="4dc20-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="4dc20-110">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4dc20-110">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)|<span data-ttu-id="4dc20-111">Stellt Methoden für die Validierung von portablen ausführbaren Images sowie für die ausführliche Berichterstellung von Validierungs Fehlern bereit.</span><span class="sxs-lookup"><span data-stu-id="4dc20-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4dc20-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4dc20-112">Requirements</span></span>  
 <span data-ttu-id="4dc20-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4dc20-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4dc20-114">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="4dc20-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="4dc20-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="4dc20-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4dc20-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4dc20-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dc20-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4dc20-117">See also</span></span>

- [<span data-ttu-id="4dc20-118">Hosting-Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="4dc20-118">Hosting Coclasses</span></span>](hosting-coclasses.md)
