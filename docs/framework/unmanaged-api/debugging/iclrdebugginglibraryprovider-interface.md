---
title: ICLRDebuggingLibraryProvider-Schnittstelle
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider
helpviewer_keywords:
- ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c62079a87c09bcbe09167a137fd39530652ae3e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59106339"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="fe582-102">ICLRDebuggingLibraryProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="fe582-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="fe582-103">Enthält die [ProvideLibrary-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) Methode, die eine Bibliotheksanbieter-Rückrufschnittstelle, die common Language Runtime versionsspezifische Debugbibliotheken abruft zu suchen und zu laden, auf Anforderung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="fe582-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fe582-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="fe582-104">Methods</span></span>  
  
|<span data-ttu-id="fe582-105">Methode</span><span class="sxs-lookup"><span data-stu-id="fe582-105">Method</span></span>|<span data-ttu-id="fe582-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fe582-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fe582-107">ProvideLibrary-Methode</span><span class="sxs-lookup"><span data-stu-id="fe582-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="fe582-108">Ermöglicht dem Debugger ein Handle für ein Modul bereitstellen, das zum Laden einer Debugbibliothek verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fe582-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fe582-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fe582-109">Requirements</span></span>  
 <span data-ttu-id="fe582-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe582-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe582-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fe582-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fe582-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fe582-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="fe582-113">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="fe582-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fe582-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe582-114">See also</span></span>

- [<span data-ttu-id="fe582-115">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="fe582-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="fe582-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="fe582-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
