---
title: "Declared Element Characteristics (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declared elements, lifetime"
  - "access levels, declared elements"
  - "declared elements, scope"
  - "visibility, declared elements"
  - "elements, programming"
  - "scope, declared elements"
  - "lifetime, declared elements"
  - "declared elements, access level"
  - "data types [Visual Basic], declared elements"
  - "declared elements, visibility"
ms.assetid: 1bc40fb8-b67c-4428-90a4-76b630ae2583
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Declared Element Characteristics (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Ein *Merkmal* eines deklarierten Elements ist ein Aspekt dieses Elements, der beeinflusst, wie der Code mit ihm interagieren kann.  Jedem deklarierten Element ist mindestens eines der folgenden Merkmale zugeordnet:  
  
-   *Datentyp* – die Werte, die das Element enthalten kann, und die Art, wie diese Werte gespeichert werden.  Weitere Informationen finden Sie unter [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md).  
  
-   *Lebensdauer* – der Zeitraum innerhalb der Ausführungszeit, während dessen das Element verfügbar ist.  Weitere Informationen finden Sie unter [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   *Gültigkeitsbereich* – der Codesatz, der auf das Element verweisen kann, ohne dessen Namen zu qualifizieren.  Weitere Informationen finden Sie unter [How to: Control the Scope of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md).  
  
-   *Zugriffsebene* – die Berechtigung für den Code, das Element zu verwenden.  Weitere Informationen finden Sie unter [How to: Control the Availability of a Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-availability-of-a-variable.md).  
  
## Merkmale der Elemente  
 In der folgenden Tabelle werden die deklarierten Elemente und die jeweils gültigen Merkmale aufgelistet.  
  
|Element|Datentyp|Lebensdauer|Gültigkeitsbereich <sup>1</sup>|Zugriffsebene|  
|-------------|--------------|-----------------|-------------------------------------|-------------------|  
|Variable|Ja|Ja|Ja|Ja|  
|Konstante|Ja|Nein|Ja|Ja|  
|Enumeration|Ja|Nein|Ja|Ja|  
|Struktur|Nein|Nein|Ja|Ja|  
|Property|Ja|Ja|Ja|Ja|  
|Methode|Nein|Ja|Ja|Ja|  
|Prozedur \(`Sub` oder `Function`\)|Nein|Ja|Ja|Ja|  
|Prozedurparameter|Ja|Ja|Ja|Nein|  
|Funktionsrückgabe|Ja|Ja|Ja|Nein|  
|Operator|Ja|Nein|Ja|Ja|  
|Schnittstelle|Nein|Nein|Ja|Ja|  
|Klasse|Nein|Nein|Ja|Ja|  
|Ereignis|Nein|Nein|Ja|Ja|  
|Delegat|Nein|Nein|Ja|Ja|  
  
 <sup>1</sup> Gültigkeitsbereich wird gelegentlich als *Sichtbarkeit* bezeichnet.  
  
## Siehe auch  
 [Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/index.md)   
 [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)