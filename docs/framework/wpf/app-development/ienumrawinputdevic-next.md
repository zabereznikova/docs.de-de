---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: a1f76bf42da9a311633de39e42dee2055fac4a27
ms.sourcegitcommit: 8f95d3a37e591963ebbb9af6e90686fd5f3b8707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2019
ms.locfileid: "56745184"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="d6447-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="d6447-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="d6447-103">Listet die nächsten `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) Strukturen in der Liste des Enumerators, Rückgabe in `rgelt` zusammen mit der tatsächlichen Anzahl der aufgelisteten Elemente in `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="d6447-103">Enumerates the next `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6447-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d6447-104">Syntax</span></span>  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d6447-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="d6447-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="d6447-106">[in] Anzahl der [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) -Strukturen zurückgegeben `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="d6447-106">[in] Number of [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="d6447-107">[out] Array der Größe "celt" (oder größer), um die aufgelisteten RAWINPUTDEVICE-Strukturen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="d6447-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="d6447-108">[out] Zeiger auf die Anzahl der Elemente, die tatsächlich in `rgelt` vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d6447-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="d6447-109">Der Aufrufer kann in `NULL` übergehen, wenn  `rgelt`eins beträgt. </span><span class="sxs-lookup"><span data-stu-id="d6447-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d6447-110">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d6447-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="d6447-111">HRESULT: S_OK, wenn die Anzahl der Elemente ist `celt`; Andernfalls S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="d6447-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
