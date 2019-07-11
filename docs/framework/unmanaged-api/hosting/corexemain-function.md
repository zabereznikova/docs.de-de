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
ms.openlocfilehash: f97e90e3953a01f07d77e604628fbdb79eb9efa0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779178"
---
# <a name="corexemain-function"></a><span data-ttu-id="32ab9-102">_CorExeMain-Funktion</span><span class="sxs-lookup"><span data-stu-id="32ab9-102">_CorExeMain Function</span></span>
<span data-ttu-id="32ab9-103">Initialisiert die common Language Runtime (CLR), sucht den verwalteten Einstiegspunkt im CLR-Header der ausführbaren Assembly und startet die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="32ab9-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32ab9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="32ab9-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="32ab9-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="32ab9-105">Remarks</span></span>  
 <span data-ttu-id="32ab9-106">Diese Funktion wird vom Ladeprogramm in Prozesse, die von verwalteten ausführbare Assemblys erstellt aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="32ab9-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="32ab9-107">Für DLL-Assemblys, die das Ladeprogramm ruft die [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) stattdessen funktionieren.</span><span class="sxs-lookup"><span data-stu-id="32ab9-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="32ab9-108">Vom Ladeprogramm des Betriebssystems ruft diese Methode unabhängig von der Einstiegspunkt in die Image-Datei angegeben.</span><span class="sxs-lookup"><span data-stu-id="32ab9-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="32ab9-109">In Windows 98, Windows ME, Windows NT und Windows 2000 die `_CorExeMain` Funktion wird durch einen Fixup im Betriebssystem-Lader indirekt aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="32ab9-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="32ab9-110">In allen anderen Versionen von Windows spricht man direkt vom Ladeprogramm Betriebssystems.</span><span class="sxs-lookup"><span data-stu-id="32ab9-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="32ab9-111">Weitere Informationen finden Sie im Abschnitt "Hinweise" in der [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="32ab9-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32ab9-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="32ab9-112">Requirements</span></span>  
 <span data-ttu-id="32ab9-113">**Plattformen:** Weitere Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32ab9-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32ab9-114">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="32ab9-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="32ab9-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="32ab9-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="32ab9-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32ab9-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32ab9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32ab9-117">See also</span></span>

- [<span data-ttu-id="32ab9-118">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="32ab9-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
