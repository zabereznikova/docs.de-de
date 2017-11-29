---
title: "Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords: BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e7a5450d812260d3916296dff56abee27b3d586c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>Der Rückschluss von Typen, die NULL-Werte zulassen, wird in diesem Kontext nicht unterstützt
Werttypen und Strukturen können NULL-Werte zulassen deklariert werden.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Sie können nicht jedoch auf NULL festlegbare Deklaration in Kombination mit den Typrückschluss verwenden. In den folgenden Beispielen wird dieser Fehler verursacht.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **Fehler-ID:** BC36629  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Verwenden einer `As` -Klausel, um die Variable als auf NULL festlegbar deklariert.  
  
## <a name="see-also"></a>Siehe auch  
 [Auf NULL festlegbare Werttypen](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [Lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
