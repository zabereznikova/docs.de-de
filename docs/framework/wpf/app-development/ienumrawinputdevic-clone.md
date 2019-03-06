---
title: IEnumRAWINPUTDEVIC:Clone
ms.date: 03/30/2017
helpviewer_keywords:
- Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
ms.openlocfilehash: a4c5e7db813089d1dd138416ac54dd4be467b87b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57355018"
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="5735c-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="5735c-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="5735c-103">Erstellt einen weiteren Enumerator für Geräte für die unformatierte Eingabe, der denselben Zustand wie der aktuelle Enumerator aufweist und dieselbe Liste durchlaufen soll.</span><span class="sxs-lookup"><span data-stu-id="5735c-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5735c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5735c-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5735c-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="5735c-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="5735c-106">[out] Adresse des Output-Variable, die empfängt die [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) Schnittstellenzeiger auf.</span><span class="sxs-lookup"><span data-stu-id="5735c-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="5735c-107">Wenn die Methode fehlschlägt, ist der Wert, der diese Output-Variable nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="5735c-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="5735c-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5735c-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="5735c-109">HRESULT: Diese Methode unterstützt die Standardrückgabewerte E_INVALIDARG, E_UNEXPECTED und E_OUTOFMEMORY.</span><span class="sxs-lookup"><span data-stu-id="5735c-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5735c-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5735c-110">Remarks</span></span>  
 <span data-ttu-id="5735c-111">Diese Methode ermöglicht es, einen Punkt in der Enumerationsfolge aufzeichnen, um bis zu diesem Zeitpunkt zu einem späteren Zeitpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="5735c-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="5735c-112">Der Aufrufer muss dieses neuen Enumerator getrennt von der erste Enumerator freigeben.</span><span class="sxs-lookup"><span data-stu-id="5735c-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
