---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 05867af48b64cd1898b13fa055859c8cc0367c8c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949577"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="bf9f9-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="bf9f9-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="bf9f9-103">Listet die nächsten `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) Strukturen in der Liste des Enumerators, Rückgabe in `rgelt` zusammen mit der tatsächlichen Anzahl der aufgelisteten Elemente in `pceltFetched`.</span><span class="sxs-lookup"><span data-stu-id="bf9f9-103">Enumerates the next `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf9f9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bf9f9-104">Syntax</span></span>  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf9f9-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bf9f9-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="bf9f9-106">[in] Anzahl der [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) -Strukturen zurückgegeben `rgelt`.</span><span class="sxs-lookup"><span data-stu-id="bf9f9-106">[in] Number of [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="bf9f9-107">[out] Array der Größe "celt" (oder größer), um die aufgelisteten RAWINPUTDEVICE-Strukturen zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="bf9f9-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="bf9f9-108">[out] Zeiger auf die Anzahl der Elemente, die tatsächlich in `rgelt` vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="bf9f9-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="bf9f9-109">Der Aufrufer kann in `NULL` übergehen, wenn  `rgelt`eins beträgt. </span><span class="sxs-lookup"><span data-stu-id="bf9f9-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bf9f9-110">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bf9f9-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="bf9f9-111">HRESULT: S_OK, wenn die Anzahl der Elemente ist `celt`; Andernfalls S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="bf9f9-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
