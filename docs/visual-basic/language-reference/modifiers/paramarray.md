---
title: "ParamArray (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ParamArray"
  - "ParamArray"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ParamArray keyword"
  - "ParamArray keyword, syntax"
ms.assetid: a5f18789-92bd-488f-9c7e-cf3719963635
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# ParamArray (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt an, dass ein Prozedurparameter ein optionales Array aus Elementen mit dem angegebenen Typ verwendet.  `ParamArray` kann nur auf dem letzten Parameter einer Parameterliste verwendet werden.  
  
## Hinweise  
 `ParamArray` bietet die Möglichkeit, eine beliebige Anzahl von Argumenten an die Prozedur zu übergeben.  Ein `ParamArray`\-Parameter wird stets mit [ByVal](../../../visual-basic/language-reference/modifiers/byval.md) deklariert.  
  
 Sie können ein oder mehrere Argumente für einen `ParamArray`\-Parameter angeben, indem Sie ein Array des entsprechenden Datentyps, eine durch Trennzeichen getrennte Liste von Werten oder gar keinen Wert übergeben.  Weitere Informationen finden Sie im Abschnitt "Calling a ParamArray" unter [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
> [!IMPORTANT]
>  Wenn Sie mit einem Array arbeiten, das unendlich groß sein kann, besteht die Gefahr, dass eine interne Kapazität der Anwendung überschritten wird.  Wenn Sie ein Parameterarray vom Aufrufcode akzeptieren, müssen Sie seine Länge testen und entsprechende Maßnahmen ergreifen, wenn es für Ihre Anwendung zu groß ist.  
  
 Der `ParamArray`\-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Siehe auch  
 [Stichwörter](../../../visual-basic/language-reference/keywords/index.md)   
 [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md)