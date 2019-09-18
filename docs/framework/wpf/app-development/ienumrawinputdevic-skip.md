---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: a74f71345a22f6d766c2d5966ca5d2cb33ab756e
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053378"
---
# <a name="ienumrawinputdevicskip"></a>IEnumRAWINPUTDEVIC:Skip
Weist den Enumerator an, die nächsten `celt` Elemente in der-Enumeration zu überspringen, sodass der nächste [IEnumRAWINPUTDEVIC: Next](ienumrawinputdevic-next.md) -Aufrufe diese Elemente nicht zurückgibt.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Skip( [in] ULONG celt);  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
  
 in Anzahl der Elemente, die übersprungen werden sollen.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT: S_OK, wenn die Anzahl der bereitgestellten `celt`Elemente ist. S_FALSE andernfalls.
