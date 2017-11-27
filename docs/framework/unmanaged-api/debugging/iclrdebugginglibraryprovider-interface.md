---
title: ICLRDebuggingLibraryProvider-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebuggingLibraryProvider
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDebuggingLibraryProvider
helpviewer_keywords: ICLRDebuggingLibraryProvider interface [.NET Framework debugging]
ms.assetid: 67739617-6add-41a9-9de5-a3200c3109ce
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 82ed352e3f5fb83a2f464f2d82ff9a9885227fe7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="a1fcc-102">ICLRDebuggingLibraryProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="a1fcc-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="a1fcc-103">Enthält die [ProvideLibrary-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) -Methode, die eine Bibliotheksanbieter Rückrufschnittstelle abruft, die common Language Runtime versionsspezifische befindet, und Laden bei Bedarf es ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="a1fcc-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a1fcc-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="a1fcc-104">Methods</span></span>  
  
|<span data-ttu-id="a1fcc-105">Methode</span><span class="sxs-lookup"><span data-stu-id="a1fcc-105">Method</span></span>|<span data-ttu-id="a1fcc-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a1fcc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a1fcc-107">ProvideLibrary-Methode</span><span class="sxs-lookup"><span data-stu-id="a1fcc-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="a1fcc-108">Der Debugger ermöglicht, ein Handle für ein Modul bereitgestellt werden, die zum Laden einer Debugbibliothek verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a1fcc-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a1fcc-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="a1fcc-109">Requirements</span></span>  
 <span data-ttu-id="a1fcc-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a1fcc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1fcc-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a1fcc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a1fcc-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1fcc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1fcc-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1fcc-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1fcc-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1fcc-114">See Also</span></span>  
 [<span data-ttu-id="a1fcc-115">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="a1fcc-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="a1fcc-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="a1fcc-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
