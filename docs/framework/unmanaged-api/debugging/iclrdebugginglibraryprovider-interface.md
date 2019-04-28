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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697861"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="610c3-102">ICLRDebuggingLibraryProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="610c3-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="610c3-103">Enthält die [ProvideLibrary-Methode](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) Methode, die eine Bibliotheksanbieter-Rückrufschnittstelle, die common Language Runtime versionsspezifische Debugbibliotheken abruft zu suchen und zu laden, auf Anforderung ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="610c3-103">Includes the [ProvideLibrary Method](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="610c3-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="610c3-104">Methods</span></span>  
  
|<span data-ttu-id="610c3-105">Methode</span><span class="sxs-lookup"><span data-stu-id="610c3-105">Method</span></span>|<span data-ttu-id="610c3-106">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="610c3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="610c3-107">ProvideLibrary-Methode</span><span class="sxs-lookup"><span data-stu-id="610c3-107">ProvideLibrary Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="610c3-108">Ermöglicht dem Debugger ein Handle für ein Modul bereitstellen, das zum Laden einer Debugbibliothek verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="610c3-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="610c3-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="610c3-109">Requirements</span></span>  
 <span data-ttu-id="610c3-110">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="610c3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="610c3-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="610c3-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="610c3-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="610c3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="610c3-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="610c3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="610c3-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="610c3-114">See also</span></span>

- [<span data-ttu-id="610c3-115">Debuggen von Schnittstellen</span><span class="sxs-lookup"><span data-stu-id="610c3-115">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="610c3-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="610c3-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
