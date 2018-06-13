---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 3cf3231bd48290c5b6b0ce8eeb6534de564c0c85
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546405"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="390c6-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="390c6-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="390c6-103">Listet die nächsten `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) Strukturen in der Liste des Enumerators, Rückgabe in `rgelt` zusammen mit der tatsächlichen Anzahl der aufgelisteten Elemente in `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="390c6-103">Enumerates the next `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="390c6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="390c6-104">Syntax</span></span>  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="390c6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="390c6-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="390c6-106">[in] Anzahl der [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) Strukturen im zurückgegebenen `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="390c6-106">[in] Number of [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="390c6-107">[out] Array der Größe "celt" (oder größer), um die aufgelisteten RAWINPUTDEVICE-Strukturen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="390c6-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="390c6-108">[out] Zeiger auf die Anzahl der Elemente, die tatsächlich in `rgelt` vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="390c6-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="390c6-109">Der Aufrufer kann in `NULL` übergehen, wenn  `rgelt`eins beträgt. </span><span class="sxs-lookup"><span data-stu-id="390c6-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="390c6-110">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="390c6-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="390c6-111">HRESULT: S_OK, wenn die Anzahl der Elemente `celt` ist. Andernfalls S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="390c6-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
