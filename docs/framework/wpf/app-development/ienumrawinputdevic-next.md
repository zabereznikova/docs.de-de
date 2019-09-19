---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: c7450a9ababa9cf3cb02d572f5ed84f0791d74e4
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71053400"
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
Listet `celt` die nächsten [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) -Strukturen in der Enumeratorliste auf `rgelt` und gibt Sie zusammen mit der tatsächlichen Anzahl der aufgelisteten Elemente in `pceltFetched`zurück.  
  
## <a name="syntax"></a>Syntax  
  
```cpp  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a>Parameter  
 `celt`  
  
 in Anzahl der [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) -Strukturen, `rgelt`die in zurückgegeben werden.  
  
 `rgelt`  
  
 [out] Array der Größe "celt" (oder größer), um die aufgelisteten RAWINPUTDEVICE-Strukturen zu empfangen.  
  
 `pceltFetched`  
  
 [out] Zeiger auf die Anzahl der Elemente, die tatsächlich in `rgelt` vorhanden sind. Der Aufrufer kann in `NULL` übergehen, wenn  `rgelt`eins beträgt.  
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT: S_OK, wenn die Anzahl der bereitgestellten `celt`Elemente ist. S_FALSE andernfalls.
