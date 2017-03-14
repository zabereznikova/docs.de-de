---
title: "Type &lt;typename&gt; is not CLS-compliant | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc40041"
  - "vbc40041"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40041"
ms.assetid: 634132c2-5646-44aa-98c6-f773e2e63882
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# Type &lt;typename&gt; is not CLS-compliant
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Variable, Eigenschaft, oder Funktionsrückgabe ist mit einem Datentyp deklariert, der nicht CLS\-kompatibel ist.  
  
 Damit eine Anwendung mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) kompatibel ist, darf sie nur CLS\-kompatible Typen verwenden.  
  
 Die folgenden [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]\-Datentypen sind nicht CLS\-kompatibel:  
  
-   [SByte Data Type](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong Data Type](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort Data Type](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 **Fehler\-ID:** BC40041  
  
### So beheben Sie diesen Fehler  
  
-   Wenn die Anwendung CLS\-kompatibel sein muss, ändern Sie den Datentyp dieses Elements in den ähnlichsten CLS\-kompatiblen Typ.  Möglicherweise können Sie z. B. `Integer` anstelle von `UInteger` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.  Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long` ersetzen.  
  
-   Wenn die Anwendung nicht CLS\-kompatibel sein muss, müssen Sie nichts ändern.  Sie sollten sich jedoch der Tatsache bewusst sein, dass die Anwendung nicht CLS\-kompatibel ist.  
  
## Siehe auch  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/de-de/4c705105-69a2-4e5e-b24e-0633bc32c7f3)