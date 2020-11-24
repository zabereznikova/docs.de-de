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
ms.openlocfilehash: af1d0e2039024a51341e30bec497c581a0bcacb3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95673669"
---
# <a name="_corexemain-function"></a><span data-ttu-id="8ed7f-102">_CorExeMain-Funktion</span><span class="sxs-lookup"><span data-stu-id="8ed7f-102">_CorExeMain Function</span></span>

<span data-ttu-id="8ed7f-103">Initialisiert den Common Language Runtime (CLR), den verwalteten Einstiegspunkt im CLR-Header der ausführbaren Assembly und beginnt die Ausführung.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-103">Initializes the common language runtime (CLR), locates the managed entry point in the executable assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ed7f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8ed7f-104">Syntax</span></span>  
  
```cpp  
__int32 STDMETHODCALLTYPE _CorExeMain ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8ed7f-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ed7f-105">Remarks</span></span>  

 <span data-ttu-id="8ed7f-106">Diese Funktion wird vom Lade Programm in Prozessen aufgerufen, die aus verwalteten ausführbaren Assemblys erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-106">This function is called by the loader in processes created from managed executable assemblies.</span></span> <span data-ttu-id="8ed7f-107">Bei dll-Assemblys Ruft das Lade Modul stattdessen die [_CorDllMain](cordllmain-function.md) -Funktion auf.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-107">For DLL assemblies, the loader calls the [_CorDllMain](cordllmain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="8ed7f-108">Das Betriebssystem-Lade Modul ruft diese Methode unabhängig vom Einstiegspunkt auf, der in der Bilddatei angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-108">The operating system loader calls this method regardless of the entry point specified in the image file.</span></span>  
  
 <span data-ttu-id="8ed7f-109">In Windows 98, Windows Me, Windows NT und Windows 2000 `_CorExeMain` wird die Funktion indirekt über einen Fixup im Betriebssystem-Lade Modul aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-109">In Windows 98, Windows ME, Windows NT, and Windows 2000, the `_CorExeMain` function is called indirectly through a fixup in the operating system loader.</span></span> <span data-ttu-id="8ed7f-110">In allen anderen Versionen von Windows wird Sie direkt vom Betriebssystem-Lade Modul aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-110">In all other versions of Windows, it is called directly by the operating system loader.</span></span>  
  
 <span data-ttu-id="8ed7f-111">Weitere Informationen finden Sie im Abschnitt "Hinweise" im [_CorValidateImage](corvalidateimage-function.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="8ed7f-111">For additional information, see the Remarks section in the [_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ed7f-112">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="8ed7f-112">Requirements</span></span>  

 <span data-ttu-id="8ed7f-113">**Plattformen:** Informationen finden Sie unter [Systemanforderungen](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ed7f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ed7f-114">**Header:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="8ed7f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ed7f-115">**Bibliothek:** Als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="8ed7f-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8ed7f-116">**.NET Framework Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ed7f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ed7f-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ed7f-117">See also</span></span>

- [<span data-ttu-id="8ed7f-118">Globale statische Metadatenfunktionen</span><span class="sxs-lookup"><span data-stu-id="8ed7f-118">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
