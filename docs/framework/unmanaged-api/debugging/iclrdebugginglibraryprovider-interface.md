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
ms.openlocfilehash: 77c2011ce677d1bd2823d47740782f48151b408a
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860281"
---
# <a name="iclrdebugginglibraryprovider-interface"></a><span data-ttu-id="512fd-102">ICLRDebuggingLibraryProvider-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="512fd-102">ICLRDebuggingLibraryProvider Interface</span></span>
<span data-ttu-id="512fd-103">Schließt die [Methode der ProvideLibrary-Methode](iclrdebugginglibraryprovider-providelibrary-method.md) ein, die eine Bibliotheks Anbieter-Rückruf Schnittstelle abruft, die es ermöglicht, Common Language Runtime versionsspezifische Debugbibliotheken bei Bedarf zu finden und zu laden.</span><span class="sxs-lookup"><span data-stu-id="512fd-103">Includes the [ProvideLibrary Method](iclrdebugginglibraryprovider-providelibrary-method.md) method, which gets a library provider callback interface that allows common language runtime version-specific debugging libraries to be located and loaded on demand.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="512fd-104">Methoden</span><span class="sxs-lookup"><span data-stu-id="512fd-104">Methods</span></span>  
  
|<span data-ttu-id="512fd-105">Methode</span><span class="sxs-lookup"><span data-stu-id="512fd-105">Method</span></span>|<span data-ttu-id="512fd-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="512fd-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="512fd-107">ProvideLibrary-Methode</span><span class="sxs-lookup"><span data-stu-id="512fd-107">ProvideLibrary Method</span></span>](iclrdebugginglibraryprovider-providelibrary-method.md)|<span data-ttu-id="512fd-108">Ermöglicht dem Debugger, ein Handle für ein Modul bereitzustellen, das zum Laden einer Debugbibliothek verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="512fd-108">Allows the debugger to provide a handle to a module which can be used to load a debug library.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="512fd-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="512fd-109">Requirements</span></span>  
 <span data-ttu-id="512fd-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="512fd-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="512fd-111">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="512fd-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="512fd-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="512fd-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="512fd-113">**.NET Framework Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="512fd-113">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="512fd-114">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="512fd-114">See also</span></span>

- [<span data-ttu-id="512fd-115">Debugschnittstellen</span><span class="sxs-lookup"><span data-stu-id="512fd-115">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="512fd-116">Debuggen</span><span class="sxs-lookup"><span data-stu-id="512fd-116">Debugging</span></span>](index.md)
