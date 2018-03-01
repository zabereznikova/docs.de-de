---
title: IEnumRAWINPUTDEVIC:Next
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: af6cb5bfe07923e13f1b76c785d830a9af15eaf9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ienumrawinputdevicnext"></a>IEnumRAWINPUTDEVIC:Next
Listet die nächsten `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) Strukturen in der Liste des Enumerators, Rückgabe in `rgelt` zusammen mit der tatsächlichen Anzahl der aufgelisteten Elemente in `pceltFetched`.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### <a name="parameters"></a>Parameter  
 `celt`  
  
 [in] Anzahl der [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp) Strukturen im zurückgegebenen `rgelt`.  
  
 `rgelt`  
  
 [out] Array der Größe "celt" (oder größer), um die aufgelisteten RAWINPUTDEVICE-Strukturen zu empfangen.  
  
 `pceltFetched`  
  
 [out] Zeiger auf die Anzahl der Elemente, die tatsächlich in `rgelt` vorhanden sind. Der Aufrufer kann in `NULL` übergehen, wenn  `rgelt`eins beträgt.   
  
## <a name="property-valuereturn-value"></a>Eigenschaftswert/Rückgabewert  
 HRESULT: S_OK, wenn die Anzahl der Elemente `celt` ist. Andernfalls S_FALSE.
