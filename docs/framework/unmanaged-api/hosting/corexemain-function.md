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
ms.openlocfilehash: 8541e7761e2f8e1839d028fdaea3eb71307ba615
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131198"
---
# <a name="_corexemain-function"></a><span data-ttu-id="3a4bd-102">_CorExeMain-Funktion</span><span class="sxs-lookup"><span data-stu-id="3a4bd-102">_CorExeMain Function</span></span>
<span data-ttu-id="3a4bd-103">Initialisiert den Common Language Runtime (CLR), den verwalteten Einstiegspunkt im CLR-Header der ausführbaren Assembly und beginnt die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a4bd-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3a4bd-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3a4bd-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3a4bd-105">Remarks</span></span>  
 <span data-ttu-id="3a4bd-106">Diese Funktion wird vom Lade Programm in Prozessen aufgerufen, die aus verwalteten ausführbaren Assemblys erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="3a4bd-107">Bei dll-Assemblys Ruft das Lade Modul stattdessen die [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) -Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-107">For DLL assemblies, the loader calls the [_CorDllMain](../../../../docs/framework/unmanaged-api/hosting/cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="3a4bd-108">Das Betriebssystem-Lade Modul ruft diese Methode unabhängig vom Einstiegspunkt auf, der in der Bilddatei angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="3a4bd-109">In Windows 98, Windows Me, Windows NT und Windows 2000 wird die `_CorExeMain`-Funktion indirekt über einen Fixup im Betriebssystem-Lade Modul aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="3a4bd-110">In allen anderen Versionen von Windows wird Sie direkt vom Betriebssystem-Lade Modul aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="3a4bd-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="3a4bd-111">Weitere Informationen finden Sie im Abschnitt "Hinweise" des Themas [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="3a4bd-111">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a4bd-112">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="3a4bd-112">Requirements</span></span>  
 <span data-ttu-id="3a4bd-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a4bd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a4bd-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3a4bd-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3a4bd-115">**Bibliothek:** Als Ressource in Mscoree. dll enthalten</span><span class="sxs-lookup"><span data-stu-id="3a4bd-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3a4bd-116">**.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a4bd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a4bd-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a4bd-117">See also</span></span>

- [<span data-ttu-id="3a4bd-118">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="3a4bd-118">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
