---
title: "IEnumRAWINPUTDEVIC:Next | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Nächste Methode"
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# IEnumRAWINPUTDEVIC:Next
Listet die nächsten `celt` [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp)\-Strukturen in der Enumeratorliste auf und gibt sie zusammen mit der tatsächlichen Anzahl der aufgelisteten Elemente in `pceltFetched` in `rgelt` zurück.  
  
## Syntax  
  
```  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
#### Parameter  
 `celt`  
  
 \[in\] Anzahl der [RAWINPUTDEVICE](http://msdn.microsoft.com/library/default.asp?url=/library/winui/winui/windowsuserinterface/userinput/rawinput/rawinputreference/rawinputstructures/rawinputdevice.asp)\-Strukturen, die in `rgelt` zurückgegeben werden.  
  
 `rgelt`  
  
 \[out\] Array der Größe "celt" \(oder größer\), um die aufgelisteten RAWINPUTDEVICE\-Strukturen zu empfangen.  
  
 `pceltFetched`  
  
 \[out\] Zeiger auf die Anzahl der Elemente, die tatsächlich in `rgelt` vorhanden sind.  Der Aufrufer kann in `NULL` übergehen, wenn  `rgelt`eins beträgt.  
  
## Eigenschaftswert\/Rückgabewert  
 HRESULT: S\_OK, wenn die Anzahl der Elemente `celt` ist. Andernfalls S\_FALSE.