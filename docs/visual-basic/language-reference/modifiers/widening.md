---
title: "Widening (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.widening"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conversions, type"
  - "type conversion"
  - "conversions, data type"
  - "Widening keyword"
  - "data type conversion"
ms.assetid: 646ae263-94d3-40a2-b0cc-64f619292f56
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Widening (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt an, dass ein Konvertierungsoperator \(`CType`\) eine Klasse oder Struktur in einen Typ konvertiert, der alle möglichen Werte der ursprünglichen Klasse oder Struktur aufnehmen kann.  
  
## Konvertieren mit dem Widening\-Schlüsselwort  
 In der Konvertierungsprozedur muss neben `Widening` auch `Public Shared` angegeben werden.  
  
 Erweiternde Konvertierungen sind zur Laufzeit immer erfolgreich. Datenverluste treten hier nie auf.  Beispiele sind die Konvertierung von `Single` in `Double`, `Char` in `String` und von einem abgeleiteten Typ in seinen Basistyp.  Die letzte Konvertierung ist erweiternd, weil der abgeleitete Typ alle Member des Basistyps enthält und folglich eine Instanz des Basistyps ist.  
  
 Im verwendeten Code muss `CType` nicht für Erweiterungskonvertierungen verwendet werden, auch wenn `Option Strict``On` ist.  
  
 Das `Widening`\-Schlüsselwort kann im folgenden Kontext verwendet werden:  
  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 Beispieldefinitionen für Konvertierungsoperatoren zum Erweitern oder Eingrenzen finden Sie unter [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).  
  
## Siehe auch  
 [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)   
 [Narrowing](../../../visual-basic/language-reference/modifiers/narrowing.md)   
 [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)   
 [How to: Define an Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-an-operator.md)   
 [CType\-Funktion](../../../visual-basic/language-reference/functions/ctype-function.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [How to: Define a Conversion Operator](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)