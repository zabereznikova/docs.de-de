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
ms.openlocfilehash: 7c77cb2e89cb8fd87bf219780b9460649de19c9d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731760"
---
# <a name="clrruntimehost-coclass"></a><span data-ttu-id="53670-102">CLRRuntimeHost-Co-Klasse</span><span class="sxs-lookup"><span data-stu-id="53670-102">CLRRuntimeHost Coclass</span></span>

<span data-ttu-id="53670-103">Stellt Schnittstellen zum Verwalten der Codeausführung durch die Laufzeit bereit.</span><span class="sxs-lookup"><span data-stu-id="53670-103">Provides interfaces for managing code execution by the runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53670-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53670-104">Syntax</span></span>  
  
```cpp  
coclass CLRRuntimeHost {  
    [default] interface  ICLRRuntimeHost;  
    interface            ICLRValidator;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="53670-105">Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="53670-105">Interfaces</span></span>  
  
|<span data-ttu-id="53670-106">Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53670-106">Interface</span></span>|<span data-ttu-id="53670-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="53670-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="53670-108">ICLRRuntimeHost-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53670-108">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)|<span data-ttu-id="53670-109">Stellt Methoden zum Steuern der Ausführung von Anwendungen durch die Laufzeit bereit.</span><span class="sxs-lookup"><span data-stu-id="53670-109">Provides methods for controlling the execution of applications by the runtime.</span></span>|  
|[<span data-ttu-id="53670-110">ICLRValidator-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="53670-110">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)|<span data-ttu-id="53670-111">Stellt Methoden für die Validierung von portablen ausführbaren Images sowie für die ausführliche Berichterstellung von Validierungs Fehlern bereit.</span><span class="sxs-lookup"><span data-stu-id="53670-111">Provides methods for validation of portable executable images and for detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="53670-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="53670-112">Requirements</span></span>  

 <span data-ttu-id="53670-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="53670-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53670-114">**Header:** Mscoree. idl</span><span class="sxs-lookup"><span data-stu-id="53670-114">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="53670-115">**Bibliothek:** Als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="53670-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53670-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53670-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53670-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53670-117">See also</span></span>

- [<span data-ttu-id="53670-118">Hosten von Co-Klassen</span><span class="sxs-lookup"><span data-stu-id="53670-118">Hosting Coclasses</span></span>](hosting-coclasses.md)
