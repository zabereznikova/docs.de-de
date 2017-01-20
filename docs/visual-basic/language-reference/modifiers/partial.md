---
title: "Partial (Visual Basic) | Microsoft Docs"
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
  - "vb.Partial"
  - "partial"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "structures, partial"
  - "classes [Visual Basic]"
  - "partial, types [Visual Basic]"
  - "partial, structures"
  - "partial, classes [Visual Basic]"
  - "classes [Visual Basic], partial"
  - "Partial keyword [Visual Basic]"
  - "type promotion"
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
caps.latest.revision: 36
caps.handback.revision: 36
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Partial (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Gibt an, dass eine Typdeklaration eine partielle Definition des Typs ist.  
  
 Mit dem `Partial`\-Schlüsselwort können Sie die Typdefinition auf mehrere Deklarationen aufteilen.  Sie können beliebig viele partielle Deklarationen in beliebig vielen verschiedenen Quelldateien verwenden.  Alle Deklarationen müssen jedoch in der gleichen Assembly und dem gleichen Namespace enthalten sein.  
  
> [!NOTE]
>  Visual Basic unterstützt *partielle Methoden*, die in der Regel in partiellen Klassen implementiert werden.  Weitere Informationen finden Sie unter [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md) und [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md).  
  
## Syntax  
  
```  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`attrlist`|Dies ist optional.  Liste der Attribute, die für diesen Typ gelten.  Sie müssen die [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in spitze Klammern \(`< >`\) einschließen.|  
|`accessmodifier`|Dies ist optional.  Gibt an, welcher Code auf diesen Typ zugreifen kann.  Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Dies ist optional.  Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Dies ist optional.  Weitere Informationen finden Sie unter [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Dies ist optional.  Weitere Informationen finden Sie unter [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`name`|Erforderlich.  Der Name dieses Typs.  Muss mit dem Namen übereinstimmen, der in allen anderen partiellen Deklarationen desselben Typs definiert ist.|  
|`Of`|Dies ist optional.  Gibt an, dass dies ein generischer Typ ist.  Weitere Informationen finden Sie unter [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md).|  
|`typelist`|Erforderlich, wenn Sie [Of](../../../visual-basic/language-reference/statements/of-clause.md) verwenden.  Siehe [Type List](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Dies ist optional.  Weitere Informationen finden Sie unter [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Erforderlich, wenn Sie `Inherits` verwenden.  Der Name der Klasse oder Schnittstelle, von der diese Klasse abgeleitet wird.|  
|`Implements`|Dies ist optional.  Weitere Informationen finden Sie unter [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie `Implements` verwenden.  Die Namen der von diesem Typ implementierten Schnittstellen.|  
|`variabledeclarations`|Dies ist optional.  Anweisungen, die zusätzliche Variablen und Ereignisse für den Typ definieren.|  
|`proceduredeclarations`|Dies ist optional.  Anweisungen, die zusätzliche Prozeduren für den Typ deklarieren und definieren.|  
|`End Class` oder `End Structure`|Beendet diese partielle `Class`\- oder `Structure`\-Definition.|  
  
## Hinweise  
 Visual Basic verwendet partielle Klassendefinitionen, um in jeweils eigenen Quelldateien generierten Code von Code zu trennen, der vom Benutzer erstellt wurde.  Zum Beispiel definiert der **Windows Form\-Designer** partielle Klassen für Steuerelemente, z. B. <xref:System.Windows.Forms.Form>.  Sie sollten den generierten Code in diesen Steuerelementen nicht ändern.  
  
 Beim Erstellen eines partiellen Typs gelten alle Regeln für die Erstellung von Klassen, Strukturen, Schnittstellen und Modulen, beispielsweise diejenigen für die Verwendung und Vererbung von Modifizierern.  
  
## Bewährte Methoden  
  
-   Normalerweise wird die Entwicklung eines einzelnen Typs nicht auf zwei oder mehr Deklarationen aufgeteilt.  In der Regel benötigen Sie das `Partial`\-Schlüsselwort daher nicht.  
  
-   Zur besseren Lesbarkeit sollte jede partielle Deklaration eines Typs das `Partial`\-Schlüsselwort enthalten.  Der Compiler gestattet den Wegfall des Schlüsselworts nur bei höchstens einer partiellen Deklaration. Fällt es bei mehr als einer Deklaration weg, tritt ein Fehler auf.  
  
## Verhalten  
  
-   **Union von Deklarationen** Der Compiler behandelt den Typ als die Union all seiner partiellen Deklarationen.  Jeder Modifizierer aus jeder partiellen Definition wird auf den gesamten Typ angewendet, und jeder Member aus jeder partiellen Definition steht dem gesamten Typ zur Verfügung.  
  
-   **Typerweiterung nicht zulässig für partielle Typen in Modulen.** Wenn eine partielle Definition in einem Modul enthalten ist, ist automatisch keine Typerweiterung für diesen Typ möglich.  In einem solchen Fall kann eine Reihe partieller Definitionen zu unerwarteten Ergebnissen und sogar zu Compilerfehlern führen.  Weitere Informationen finden Sie unter [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md).  
  
     Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.  
  
 Das `Partial`\-Schlüsselwort kann in den folgenden Kontexten verwendet werden:  
  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)  
  
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
## Beispiel  
 Im folgenden Beispiel wird die Definition der `sampleClass`\-Klasse auf zwei Deklarationen aufgeteilt, die jeweils eine andere `Sub`\-Prozedur definieren.  
  
 [!code-vb[VbVbalrKeywords#3](../../../visual-basic/language-reference/codesnippet/VisualBasic/partial_1.vb)]  
  
 Die beiden partiellen Definitionen aus dem vorhergehenden Beispiel können in derselben Quelldatei oder in zwei unterschiedlichen Quelldateien enthalten sein.  
  
## Siehe auch  
 [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Type Promotion](../../../visual-basic/programming-guide/language-features/declared-elements/type-promotion.md)   
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Partial Methods](../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)