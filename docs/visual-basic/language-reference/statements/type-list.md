---
title: "Type List (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "StructureConstraint"
  - "vb.StructureConstraint"
  - "ClassConstraint"
  - "vb.ClassConstraint"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "class constraint"
  - "constraints, Visual Basic generic types"
  - "generic parameters"
  - "generics [Visual Basic], constraints"
  - "generics [Visual Basic], type list"
  - "structure constraint"
  - "constraints, in type parameters"
  - "generics [Visual Basic], generic types"
  - "parameters, type"
  - "constraints, Structure keyword"
  - "type parameters, constraints"
  - "types [Visual Basic], generic"
  - "parameters, generic"
  - "generics [Visual Basic], type parameters"
  - "type parameters"
  - "constraints, Class keyword"
ms.assetid: 56db947a-2ae8-40f2-a70a-960764e9d0db
caps.latest.revision: 33
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 33
---
# Type List (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Gibt die *Typparameter* für ein *generisches* Programmierelement an.  Mehrere Parameter werden durch Komma voneinander getrennt.  Im Folgenden wird die Syntax für einen Typparameter gezeigt.  
  
## Syntax  
  
```  
  
[genericmodifier] typename [ As constraintlist ]  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`genericmodifier`|Optional.  Kann nur in generischen Schnittstellen und Delegaten verwendet werden.  Sie können einen Typ\-Covariant mit dem [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)\-Schlüsselwort oder einen Contravariant mit dem [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)\-Schlüsselwort deklarieren.  Weitere Informationen finden Sie unter [Kovarianz und Kontravarianz](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md).|  
|`typename`|Erforderlich.  Name des Typparameters.  Dies ist ein Platzhalter. Dieser Platzhalter wird durch einen definierten Typ ersetzt, der vom entsprechenden Typargument angegeben wird.|  
|`constraintlist`|Optional.  Liste mit Anforderungen, die den Datentyp einschränken, der für `typename` angegeben werden kann.  Wenn Sie mehrere Einschränkungen haben, schließen Sie diese in geschweifte Klammern \(`{ }`\) ein, und trennen Sie sie durch Kommas.  ‎Leiten Sie die Einschränkungsliste mit dem [As](../../../visual-basic/language-reference/statements/as-clause.md)\-Schlüsselwort ein.  `As` wird nur einmal, und zwar am Anfang der Liste, verwendet.|  
  
## Hinweise  
 Jedes generische Programmierelement muss mindestens einen Typparameter annehmen.  Ein Typparameter ist ein Platzhalter für einen bestimmten Typ \(ein *konstruiertes Element*\), der beim Erstellen einer Instanz des generischen Typs vom Clientcode angegeben wird.  Sie können einen generischen Delegaten oder eine generische Klasse, Struktur, Schnittstelle oder Prozedur definieren.  
  
 Weitere Informationen darüber, wann ein generischer Typ definiert wird, finden Sie unter [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).  Weitere Informationen zu Typparameternamen finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## Regeln  
  
-   **Runde Klammern.** Bei Angabe einer Liste mit Typparametern müssen Sie die Liste in runde Klammern einfügen. Außerdem müssen Sie die Liste mit dem [Of](../../../visual-basic/language-reference/statements/of-clause.md)\-Schlüsselwort einleiten.  `Of` wird nur einmal, und zwar am Anfang der Liste, verwendet.  
  
-   **Einschränkungen.** Eine Liste mit *Einschränkungen* für einen Typparameter kann die folgenden Elemente in beliebiger Kombination enthalten:  
  
    -   Beliebige Anzahl von Schnittstellen.  Der angegebene Typ muss jede Schnittstelle in dieser Liste implementieren.  
  
    -   Maximal eine Klasse.  Der angegebene Typ muss von dieser Klasse erben.  
  
    -   Das `New`\-Schlüsselwort.  Der angegebene Typ muss einen parameterlosen Konstruktor verfügbar machen, auf den der generische Typ zugreifen kann.  Dies ist hilfreich, wenn Sie einen Typparameter um eine oder mehrere Schnittstellen einschränken.  Ein Typ, der Schnittstellen implementiert, macht nicht unbedingt einen Konstruktor verfügbar. Außerdem kann der Code innerhalb des generischen Typs je nach der Zugriffsebene eines Konstruktors unter Umständen nicht auf den Konstruktor zugreifen.  
  
    -   Entweder das `Class`\-Schlüsselwort oder das `Structure`\-Schlüsselwort.  Das `Class`\-Schlüsselwort schränkt einen generischen Typparameter so ein, dass jedes an ihn übergebene Typargument ein Verweistyp sein muss, beispielsweise eine Zeichenfolge, ein Array oder ein Delegat bzw. ein aus einer Klasse erstelltes Objekt.  Das `Structure`\-Schlüsselwort schränkt einen generischen Typparameter so ein, dass jedes an ihn übergebene Typargument ein Werttyp sein muss, beispielsweise eine Struktur, eine Enumeration oder ein elementarer Datentyp.  `Class` und `Structure` dürfen nicht zusammen in einer `constraintlist` angegeben werden.  
  
     Der angegebene Typ muss jeder Anforderung genügen, die Sie in `constraintlist` einfügen.  
  
     Einschränkungen für die einzelnen Typparameter sind unabhängig von Einschränkungen für andere Typparameter.  
  
## Verhalten  
  
-   **Typersetzung zur Kompilierungszeit.** Wenn Sie einen konstruierten Typ eines generischen Programmierelements erstellen, geben Sie für jeden Typparameter einen definierten Typ an.  Der Visual Basic\-Compiler ersetzt alle Vorkommen von `typename` im generischen Element durch diesen angegebenen Typ.  
  
-   **Keine Einschränkungen.** Wenn Sie für einen Typparameter keine Einschränkungen angeben, ist der Code auf die Operationen und Member beschränkt, die vom [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) für diesen Typparameter unterstützt werden.  
  
## Beispiel  
 Das folgende Beispiel zeigt die Skelettdefinition einer generischen Wörterbuchklasse, einschließlich einer Skelettfunktion zum Hinzufügen eines neuen Eintrags zum Wörterbuch.  
  
 [!code-vb[VbVbalrStatements#3](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_1.vb)]  
  
## Beispiel  
 Weil das `dictionary` generisch ist, kann der Code, der es verwendet, eine Vielzahl von Objekten daraus erstellen. Dabei haben alle diese Objekte die gleiche Funktionalität, werden aber auf verschiedene Datentypen angewendet.  Das folgende Beispiel zeigt eine Codezeile, die ein `dictionary`\-Objekt mit `String`\-Einträgen und `Integer`\-Schlüsseln erstellt.  
  
 [!code-vb[VbVbalrStatements#4](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_2.vb)]  
  
## Beispiel  
 Das folgende Beispiel zeigt die entsprechende, vom vorangehenden Beispiel generierte Skelettdefinition.  
  
 [!code-vb[VbVbalrStatements#5](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/type-list_3.vb)]  
  
## Siehe auch  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)   
 [New Operator](../../../visual-basic/language-reference/operators/new-operator.md)   
 [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Kovarianz und Kontravarianz](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)