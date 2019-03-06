---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: abc8a6e4780c8fe50afcf1b04f7e14aeb6452704
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2019
ms.locfileid: "57485407"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="89efb-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="89efb-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="89efb-103">Erstellt einen weiteren Enumerator für Geräte für die unformatierte Eingabe, der denselben Zustand wie der aktuelle Enumerator aufweist und dieselbe Liste durchlaufen soll.</span><span class="sxs-lookup"><span data-stu-id="89efb-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89efb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="89efb-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89efb-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="89efb-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="89efb-106">[out] Adresse des Output-Variable, die empfängt die [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) Schnittstellenzeiger auf.</span><span class="sxs-lookup"><span data-stu-id="89efb-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="89efb-107">Wenn die Methode fehlschlägt, ist der Wert, der diese Output-Variable nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="89efb-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="89efb-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="89efb-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="89efb-109">HRESULT: Diese Methode unterstützt die Standardrückgabewerte E_INVALIDARG, E_UNEXPECTED und E_OUTOFMEMORY.</span><span class="sxs-lookup"><span data-stu-id="89efb-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89efb-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="89efb-110">Remarks</span></span>  
 <span data-ttu-id="89efb-111">Diese Methode ermöglicht es, einen Punkt in der Enumerationsfolge aufzeichnen, um bis zu diesem Zeitpunkt zu einem späteren Zeitpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="89efb-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="89efb-112">Der Aufrufer muss dieses neuen Enumerator getrennt von der erste Enumerator freigeben.</span><span class="sxs-lookup"><span data-stu-id="89efb-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
