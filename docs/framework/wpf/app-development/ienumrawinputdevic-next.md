---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: 329a2cd96346e199ee834856dd6dbfac6175b722
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43481177"
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
Listet die nächsten `celt` [RAWINPUTDEVICE](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) Strukturen in der Liste des Enumerators, Rückgabe in `rgelt` zusammen mit der tatsächlichen Anzahl der aufgelisteten Elemente in `pceltFetched`.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a>Parameter  
 `celt`  
  
 [in] Anzahl der [RAWINPUTDEVICE](https://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) -Strukturen zurückgegeben `rgelt`.  
  
 `rgelt`  
  
 [out] Array der Größe "celt" (oder größer), um die aufgelisteten RAWINPUTDEVICE-Strukturen zu empfangen.  
  
 `pceltFetched`  
  
 [out] Zeiger auf die Anzahl der Elemente, die tatsächlich in `rgelt` vorhanden sind. Der Aufrufer kann in `NULL` übergehen, wenn  `rgelt`eins beträgt.   
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT: S_OK, wenn die Anzahl der Elemente `celt` ist. Andernfalls S_FALSE.
