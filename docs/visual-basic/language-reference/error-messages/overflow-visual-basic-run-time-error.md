---
title: "Überlauf (Visual Basic-Laufzeitfehler)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrERRID_Overflow
ms.assetid: c6a23279-3086-412a-bcff-ff8ed2cb8c6f
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1908ad576a499e79102aff23e3e2f11d7d99d52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="overflow-visual-basic-run-time-error"></a>Überlauf (Visual Basic-Laufzeitfehler)
Ein Überlauf tritt beim Versuch, einer Zuordnung, die die Grenzen eines Ziels für die Zuweisung überschreitet.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass die Ergebnisse der Zuweisungen, Berechnungen und den Datentyp Konvertierungen sind nicht zu groß, um innerhalb des Bereichs von Variablen, die für diesen Typ des Werts zulässig dargestellt werden, und weisen Sie den Wert einer Variablen eines Typs, die eine größere Anzahl von Werten enthalten kann , falls erforderlich.  
  
2.  Stellen Sie sicher, dass Zuweisungen zu Eigenschaften des Bereichs der Eigenschaft entsprechen, zu dem sie bereitgestellt werden.  
  
3.  Stellen Sie sicher, dass die Zahlen in Berechnungen, die in Zahlen umgewandelt werden keine Ergebnisse, die größer als ganze Zahlen.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Int32.MaxValue?displayProperty=nameWithType>  
 <xref:System.Double.MaxValue?displayProperty=nameWithType>  
 [Datentypen](../../../visual-basic/language-reference/data-types/data-type-summary.md)  
 [Fehlertypen](../../../visual-basic/programming-guide/language-features/error-types.md)
