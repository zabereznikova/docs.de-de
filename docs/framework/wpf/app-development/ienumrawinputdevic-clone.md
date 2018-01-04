---
title: IEnumRAWINPUTDEVIC:Clone
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Clone method [WPF]
ms.assetid: 2a6a1900-aa55-45fa-9382-241d569a2dc4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: db218ec824dfe163946b0c1bd412efd0f78f4ad8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ienumrawinputdevicclone"></a><span data-ttu-id="3668f-102">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="3668f-102">IEnumRAWINPUTDEVIC:Clone</span></span>
<span data-ttu-id="3668f-103">Erstellt einen weiteren Enumerator für Geräte für die unformatierte Eingabe, der denselben Zustand wie der aktuelle Enumerator aufweist und dieselbe Liste durchlaufen soll.</span><span class="sxs-lookup"><span data-stu-id="3668f-103">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3668f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3668f-104">Syntax</span></span>  
  
```  
HRESULT Clone( [out] IEnumRAWINPUTDEVICE **ppenum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3668f-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="3668f-105">Parameters</span></span>  
 `ppenum`  
  
 <span data-ttu-id="3668f-106">[out] Adresse des Output-Variable, die empfängt die [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) Schnittstellenzeiger auf.</span><span class="sxs-lookup"><span data-stu-id="3668f-106">[out] Address of output variable that receives the [IEnumRAWINPUTDEVICE](../../../../docs/framework/wpf/app-development/ienumrawinputdevice.md) interface pointer.</span></span> <span data-ttu-id="3668f-107">Wenn die Methode fehlschlägt, ist der Wert dieser Variablen Ausgabe nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="3668f-107">If the method is unsuccessful, the value of this output variable is undefined.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="3668f-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="3668f-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="3668f-109">HRESULT: Diese Methode unterstützt die Standardrückgabewerte E_INVALIDARG und E_OUTOFMEMORY E_UNEXPECTED.</span><span class="sxs-lookup"><span data-stu-id="3668f-109">HRESULT: This method supports the standard return values E_INVALIDARG, E_OUTOFMEMORY, and E_UNEXPECTED.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3668f-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3668f-110">Remarks</span></span>  
 <span data-ttu-id="3668f-111">Dieser Methode ist es möglich, einen Punkt in der Enumerationsfolge zu erfassen, um bis zu diesem Zeitpunkt zu einem späteren Zeitpunkt zurück.</span><span class="sxs-lookup"><span data-stu-id="3668f-111">This method makes it possible to record a point in the enumeration sequence in order to return to that point at a later time.</span></span> <span data-ttu-id="3668f-112">Der Aufrufer muss diesen neuen Enumerator separat aus dem ersten Enumerator freigeben.</span><span class="sxs-lookup"><span data-stu-id="3668f-112">The caller must release this new enumerator separately from the first enumerator.</span></span>
