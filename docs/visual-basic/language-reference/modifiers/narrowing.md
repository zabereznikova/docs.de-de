---
title: "Narrowing (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.narrowing"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conversions, type"
  - "type conversion"
  - "conversions, data type"
  - "Narrowing keyword"
  - "data type conversion"
ms.assetid: a207ee91-aca4-4771-b4e2-713f029bf2bb
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Narrowing (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt an, dass ein Konvertierungsoperator \(`CType`\) eine Klasse oder Struktur in einen Typ konvertiert, der unter Umständen einige der möglichen Werte der ursprünglichen Klasse oder Struktur nicht enthalten kann.  
  
## Konvertieren mit dem Narrowing\-Schlüsselwort  
 In der Konvertierungsprozedur muss neben `Narrowing` auch `Public Shared` angegeben werden.  
  
 Eingrenzende Konvertierungen sind zur Laufzeit nicht immer erfolgreich. Sie können fehlschlagen, oder es können Datenverluste auftreten.  Beispiele hierfür sind die Konvertierungen von `Long` in `Integer`, von `String` in `Date` und von einem Basistyp in einen abgeleiteten Typ.  Bei der letzten Konvertierung handelt es sich um eine eingrenzende Konvertierung, da der Basistyp nicht unbedingt alle Member des abgeleiteten Typs enthält und somit keine Instanz des abgeleiteten Typs ist.  
  
 Wenn `Option Strict` den Wert `On` hat, muss im verwendeten Code `CType` für alle eingrenzenden Konvertierungen verwendet werden.  
  
 Das `Narrowing`\-Schlüsselwort kann im folgenden Kontext verwendet werden:  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
## Siehe auch  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Widening](../../../visual-basic/language-reference/modifiers/widening.md)   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [CType\-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)