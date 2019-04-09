---
title: _CorExeMain-Funktion
ms.date: 03/30/2017
api_name:
- _CorExeMain
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- _CorExeMain
helpviewer_keywords:
- _CorExeMain function [.NET Framework hosting]
ms.assetid: 898f76e2-16f4-4a63-b7d9-dad2d3824d8a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7407db297a827004c851b904b2da8652778cb08
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177488"
---
# <a name="corexemain-function"></a><span data-ttu-id="20db5-102">_CorExeMain-Funktion</span><span class="sxs-lookup"><span data-stu-id="20db5-102">_CorExeMain Function</span></span>
<span data-ttu-id="20db5-103">Initialisiert die common Language Runtime (CLR), sucht den verwalteten Einstiegspunkt im CLR-Header der ausführbaren Assembly und startet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="20db5-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20db5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="20db5-104">Syntax</span></span>  
  
```  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="20db5-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="20db5-105">Remarks</span></span>  
 <span data-ttu-id="20db5-106">Diese Funktion wird vom Ladeprogramm in Prozesse, die von verwalteten ausführbare Assemblys erstellt aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="20db5-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="20db5-107">Für DLL-Assemblys, die das Ladeprogramm ruft die [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) stattdessen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="20db5-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="20db5-108">Vom Ladeprogramm des Betriebssystems ruft diese Methode unabhängig von der Einstiegspunkt in die Image-Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="20db5-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="20db5-109">In Windows 98, Windows ME, Windows NT und Windows 2000 die `_CorExeMain` Funktion wird durch einen Fixup im Betriebssystem-Lader indirekt aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="20db5-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="20db5-110">In allen anderen Versionen von Windows spricht man direkt vom Ladeprogramm Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="20db5-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="20db5-111">Weitere Informationen finden Sie im Abschnitt "Hinweise" in der [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="20db5-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20db5-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="20db5-112">Requirements</span></span>  
 <span data-ttu-id="20db5-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20db5-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20db5-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="20db5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="20db5-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="20db5-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="20db5-116">.NET Framework-Versionen:</span><span class="sxs-lookup"><span data-stu-id="20db5-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="20db5-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="20db5-117">See also</span></span>

- [<span data-ttu-id="20db5-118">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="20db5-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
