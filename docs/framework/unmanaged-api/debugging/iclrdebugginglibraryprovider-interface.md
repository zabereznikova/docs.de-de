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
ms.openlocfilehash: 81b9ffe5979ad553a5bdfbc27111469b2ff4db6f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111375"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="2cb43-102">ICLRDebuggingLibraryProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="2cb43-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="2cb43-103">Schließt die [Methode der ProvideLibrary-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) ein, die eine Bibliotheks Anbieter-Rückruf Schnittstelle abruft, die es ermöglicht, Common Language Runtime versionsspezifische Debugbibliotheken bei Bedarf zu finden und zu laden.</span><span class="sxs-lookup"><span data-stu-id="2cb43-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2cb43-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="2cb43-104">Methods</span></span>  
  
|<span data-ttu-id="2cb43-105">Methode</span><span class="sxs-lookup"><span data-stu-id="2cb43-105">Method</span></span>|<span data-ttu-id="2cb43-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2cb43-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2cb43-107">ProvideLibrary-Methode</span><span class="sxs-lookup"><span data-stu-id="2cb43-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="2cb43-108">Ermöglicht dem Debugger, ein Handle für ein Modul bereitzustellen, das zum Laden einer Debugbibliothek verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2cb43-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2cb43-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="2cb43-109">Requirements</span></span>  
 <span data-ttu-id="2cb43-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cb43-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cb43-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2cb43-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2cb43-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cb43-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cb43-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cb43-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cb43-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2cb43-114">See also</span></span>

- [<span data-ttu-id="2cb43-115">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="2cb43-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="2cb43-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="2cb43-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
