---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: fadf7b5526598f446eb7e49640bf4d43ec7395bf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354517"
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="53eb1-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="53eb1-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="53eb1-103">Weist den Enumerator zum nächsten überspringen `celt` Elemente in der Enumeration, damit der nächste Aufruf von [Ienumrawinputdevic](ienumrawinputdevic-next.md) diese Elemente nicht zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="53eb1-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53eb1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53eb1-104">Syntax</span></span>  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="53eb1-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="53eb1-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="53eb1-106">[in] Anzahl von Elementen übersprungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="53eb1-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="53eb1-107">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="53eb1-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="53eb1-108">HRESULT: S_OK, wenn die Anzahl der Elemente ist `celt`; Andernfalls S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="53eb1-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
