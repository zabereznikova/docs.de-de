---
title: "Generic parameters used as optional parameter types must be class constrained | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32124"
  - "bc32124"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32124"
ms.assetid: 55aa8b2a-9ce3-4620-a710-2f9b0feb6143
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Generic parameters used as optional parameter types must be class constrained
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Prozedur wurde mit einem optionalen Parameter deklariert, der einen Typparameter verwendet, der nicht als Verweistyp eingeschränkt ist.  
  
 Sie müssen immer für jeden optionalen Parameter einen Standardwert angeben.  Wenn der Parameter kein Verweistyp ist, muss der optionale Wert `Nothing` sein. Dies ist für jeden Verweistyp ein gültiger Wert.  Wenn der Parameter jedoch ein Werttyp ist, muss dieser Typ ein von Visual Basic vordefinierter elementarer Datentyp sein.  Der Grund hierfür ist, dass ein zusammengesetzter Werttyp, z. B. eine benutzerdefinierte Struktur, keinen gültigen Standardwert aufweist.  
  
 Wenn Sie als optionalen Parameter einen Typparameter verwenden, müssen Sie sicherstellen, dass er ein Verweistyp ist, um die Möglichkeit eines Werttyps ohne gültigen Standardwert auszuschließen.  Darum müssen Sie den Typparameter entweder mit dem `Class`\-Schlüsselwort oder mit dem Namen einer bestimmten Klasse einschränken.  
  
 **Fehler\-ID:** BC32124  
  
### So beheben Sie diesen Fehler  
  
-   Schränken Sie den Typparameter darauf ein, nur einen Verweistyp zu akzeptieren, oder verwenden Sie ihn nicht als optionalen Parameter.  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Type List](../../../visual-basic/language-reference/statements/type-list.md)   
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md)   
 [Structures](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Nothing](../../../visual-basic/language-reference/nothing.md)