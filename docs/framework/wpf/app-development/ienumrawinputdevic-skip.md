---
title: IEnumRAWINPUTDEVIC:Skip
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e232d2525f9dfa339516f766d417ea9c3ee976c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="873b0-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="873b0-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="873b0-103">Weist den Enumerator auf das nächste überspringen `celt` Elemente in der Enumeration, damit der nächste Aufruf von [Ienumrawinputdevic](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) diese Elemente werden nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="873b0-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](../../../../docs/framework/wpf/app-development/ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="873b0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="873b0-104">Syntax</span></span>  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="873b0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="873b0-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="873b0-106">[in] Die Anzahl von Elementen übersprungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="873b0-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="873b0-107">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="873b0-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="873b0-108">HRESULT: S_OK, wenn die Anzahl der Elemente `celt` ist. Andernfalls S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="873b0-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
