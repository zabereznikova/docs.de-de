---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: da089e5342e641ffebe22ca6a4a593f97faeb89c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545341"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="bbc3a-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="bbc3a-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="bbc3a-103">Erstellt einen weiteren Enumerator für Geräte für die unformatierte Eingabe, der denselben Zustand wie der aktuelle Enumerator aufweist und dieselbe Liste durchlaufen soll.</span><span class="sxs-lookup"><span data-stu-id="bbc3a-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbc3a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bbc3a-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bbc3a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="bbc3a-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="bbc3a-106">[out] Adresse des Output-Variable, die empfängt die [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) Schnittstellenzeiger auf.</span><span class="sxs-lookup"><span data-stu-id="bbc3a-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="bbc3a-107">Wenn die Methode fehlschlägt, ist der Wert dieser Variablen Ausgabe nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="bbc3a-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bbc3a-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bbc3a-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="bbc3a-109">HRESULT: Diese Methode unterstützt die Standardrückgabewerte E_INVALIDARG und E_OUTOFMEMORY E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="bbc3a-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbc3a-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bbc3a-110">Remarks</span></span>  
 <span data-ttu-id="bbc3a-111">Dieser Methode ist es möglich, einen Punkt in der Enumerationsfolge zu erfassen, um bis zu diesem Zeitpunkt zu einem späteren Zeitpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="bbc3a-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="bbc3a-112">Der Aufrufer muss diesen neuen Enumerator separat aus dem ersten Enumerator freigeben.</span><span class="sxs-lookup"><span data-stu-id="bbc3a-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
