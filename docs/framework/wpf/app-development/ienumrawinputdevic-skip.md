---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: f7d7df77c54d4551025aa5a344c96083c263f455
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949759"
---
# <a name="ienumrawinputdevicskip"></a>IEnumRAWINPUTDEVIC:Skip
Weist den Enumerator zum nächsten überspringen `celt` Elemente in der Enumeration, damit der nächste Aufruf von [Ienumrawinputdevic](ienumrawinputdevic-next.md) diese Elemente nicht zurückgibt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Skip( [in] ULONG celt);  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
  
 [in] Anzahl von Elementen übersprungen werden soll.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT: S_OK, wenn die Anzahl der Elemente ist `celt`; Andernfalls S_FALSE.
