---
title: _CorImageUnloading-Funktion
ms.date: 03/30/2017
api_name:
- _CorImageUnloading
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorImageUnloading
helpviewer_keywords:
- _CorImageUnloading function [.NET Framework hosting]
ms.assetid: b4367214-6dac-4280-aa11-fd487ff30bc4
topic_type:
- apiref
ms.openlocfilehash: 4932e1fd6294f4a01264e982835dd0707324082a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178232"
---
# <a name="_corimageunloading-function"></a><span data-ttu-id="c3c04-102">_CorImageUnloading-Funktion</span><span class="sxs-lookup"><span data-stu-id="c3c04-102">_CorImageUnloading Function</span></span>
<span data-ttu-id="c3c04-103">Benachrichtigt das Ladeprogramm, wenn die Images des verwalteten Moduls entladen werden.</span><span class="sxs-lookup"><span data-stu-id="c3c04-103">Notifies the loader when the managed module images are unloaded.</span></span>  
  
 <span data-ttu-id="c3c04-104">Diese Funktion ist nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="c3c04-104">This function is not implemented.</span></span> <span data-ttu-id="c3c04-105">Wenn aufgerufen, wird E_NOTIMPL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c3c04-105">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3c04-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c3c04-106">Syntax</span></span>  
  
```cpp  
STDAPI (VOID) _CorImageUnloading(
   [in] PVOID* ImageBase  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3c04-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="c3c04-107">Parameters</span></span>  
 `ImageBase`  
 <span data-ttu-id="c3c04-108">[in] Ein Zeiger auf die Startposition des zu entladenden Bildes.</span><span class="sxs-lookup"><span data-stu-id="c3c04-108">[in] A pointer to the starting location of the image to unload.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3c04-109">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="c3c04-109">Requirements</span></span>  
 <span data-ttu-id="c3c04-110">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3c04-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3c04-111">**Kopfzeile:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c3c04-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c3c04-112">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="c3c04-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c3c04-113">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3c04-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3c04-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3c04-114">See also</span></span>

- [<span data-ttu-id="c3c04-115">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="c3c04-115">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
