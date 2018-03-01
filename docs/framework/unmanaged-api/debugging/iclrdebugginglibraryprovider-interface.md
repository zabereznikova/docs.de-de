---
title: ICLRDebuggingLibraryProvider-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a7320bf261f28fed85c44f2550df5ecd06421290
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="6b8cd-102">ICLRDebuggingLibraryProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="6b8cd-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="6b8cd-103">Enthält die [ProvideLibrary-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) -Methode, die eine Bibliotheksanbieter Rückrufschnittstelle abruft, die common Language Runtime versionsspezifische befindet, und Laden bei Bedarf es ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="6b8cd-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6b8cd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="6b8cd-104">Methods</span></span>  
  
|<span data-ttu-id="6b8cd-105">Methode</span><span class="sxs-lookup"><span data-stu-id="6b8cd-105">Method</span></span>|<span data-ttu-id="6b8cd-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b8cd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6b8cd-107">ProvideLibrary-Methode</span><span class="sxs-lookup"><span data-stu-id="6b8cd-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="6b8cd-108">Der Debugger ermöglicht, ein Handle für ein Modul bereitgestellt werden, die zum Laden einer Debugbibliothek verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6b8cd-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6b8cd-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="6b8cd-109">Requirements</span></span>  
 <span data-ttu-id="6b8cd-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b8cd-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b8cd-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b8cd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b8cd-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b8cd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b8cd-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b8cd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b8cd-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6b8cd-114">See Also</span></span>  
 [<span data-ttu-id="6b8cd-115">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="6b8cd-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="6b8cd-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="6b8cd-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
