---
title: "Class Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Class"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "class modules"
  - "Class statement"
  - "classes [Visual Basic], fields"
  - "fields, of classes"
  - "class types, class statements"
  - "classes [Visual Basic], creating"
  - "classes [Visual Basic], data members"
  - "data members, of classes"
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# Class Statement (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Deklariert den Namen einer Klasse und führt die Definitionen der Variablen, Eigenschaften, Ereignisse und Prozeduren ein, die die Klasse enthält.  
  
## Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`attributelist`|Optional.  Siehe [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Optional.  Einer der folgenden Werte ist möglich:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Optional.  Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Optional.  Weitere Informationen finden Sie unter [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Optional.  Weitere Informationen finden Sie unter [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Optional.  Gibt eine partielle Definition der Klasse an.  Weitere Informationen finden Sie unter [Partial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Erforderlich.  Name dieser Klasse.  Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Optional.  Gibt an, dass dies eine generische Klasse ist.|  
|`typelist`|Erforderlich, wenn Sie das [Of](../../../visual-basic/language-reference/statements/of-clause.md)\-Schlüsselwort verwenden.  Liste mit Typparametern für diese Klasse.  Siehe [Typliste](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Optional.  Gibt an, dass diese Klasse die Member einer anderen Klasse erbt.  Weitere Informationen finden Sie unter [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Erforderlich, wenn Sie die `Inherits`\-Anweisung verwenden.  Der Name der Klasse, von der diese Klasse abgeleitet wird.|  
|`Implements`|Optional.  Gibt an, dass diese Klasse die Member einer oder mehrerer Schnittstellen implementiert.  Weitere Informationen finden Sie unter [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie die `Implements`\-Anweisung verwenden.  Die Namen der von dieser Klasse implementierten Schnittstellen.|  
|`statements`|Optional.  Anweisungen, die die Member dieser Klasse definieren.|  
|`End Class`|Erforderlich.  Beendet die `Class`\-Definition.|  
  
## Hinweise  
 Eine `Class`\-Anweisung definiert einen neuen Datentyp.  Eine *Klasse* ist ein wesentlicher Baustein der objektorientierten Programmierung \(OOP\).  Weitere Informationen finden Sie unter [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 `Class` kann nur auf Namespace\- oder Modulebene verwendet werden.  Dies bedeutet, dass der *Deklarationskontext* für eine Klasse eine Quelldatei, ein Namespace, eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein muss und weder eine Prozedur noch ein Block sein kann.  Weitere Informationen finden Sie unter [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Die Lebensdauer jeder Instanz einer Klasse ist von der Lebensdauer aller anderen Instanzen unabhängig.  Diese Lebensdauer beginnt, wenn die Instanz durch eine [New Operator](../../../visual-basic/language-reference/operators/new-operator.md)\-Klausel oder eine Funktion, z. B. <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>, erstellt wird.  Sie endet, wenn alle Variablen, die auf die Instanz zeigen, auf [Nothing](../../../visual-basic/language-reference/nothing.md) oder auf Instanzen anderer Klassen festgelegt wurden.  
  
 Der Standardzugriff von Klassen ist [Friend](../../../visual-basic/language-reference/modifiers/friend.md).  Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen.  Weitere Informationen finden Sie unter [Access Levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Regeln  
  
-   **Schachtelung.** Sie können eine Klasse in einer anderen Klasse definieren.  Die äußere Klasse wird *als enthaltende Klasse* und die innere Klasse als *geschachtelte Klasse* bezeichnet.  
  
-   **Vererbung.** Wenn die Klasse die [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md) verwendet, können Sie nur eine einzige Basisklasse oder Basisschnittstelle angeben.  Eine Klasse kann nicht von mehreren Elementen erben.  
  
     Eine Klasse kann nicht von einer anderen Klasse mit einer restriktiveren Zugriffsebene erben.  Beispielsweise kann eine `Public`\-Klasse nicht von einer `Friend`\-Klasse erben.  
  
     Eine Klasse kann nicht von einer Klasse erben, die in ihr geschachtelt ist.  
  
-   **Implementierung.** Wenn die Klasse die [Implements Statement](../../../visual-basic/language-reference/statements/implements-statement.md) verwendet, müssen Sie alle Member implementieren, die durch jede in `interfacenames` angegebene Schnittstelle definiert sind.  Eine Ausnahme hiervon ist die erneute Implementierung eines Basisklassenmembers.  Weitere Informationen finden Sie in [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) unter "Erneute Implementierung".  
  
-   **Standardeigenschaft.** Für eine Klasse kann höchstens eine Eigenschaft als *Standardeigenschaft* angegeben werden.  Weitere Informationen finden Sie unter [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## Verhalten  
  
-   **Zugriffsebene.** In einer Klasse können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren.  Der Standardzugriff für Klassen ist [Public](../../../visual-basic/language-reference/modifiers/public.md), mit Ausnahme von Variablen und Konstanten, deren Standardzugriff [Private](../../../visual-basic/language-reference/modifiers/private.md) ist.  Wenn eine Klasse eingeschränkteren Zugriff als einer ihrer Member aufweist, hat die Zugriffsebene der Klasse Vorrang.  
  
-   **Gültigkeitsbereich.** Der Gültigkeitsbereich einer Klasse umfasst den Namespace, die Klasse, Struktur oder das Modul, in dem bzw. der sich die Klasse befindet.  
  
     Der Gültigkeitsbereich jedes Klassenmembers umfasst die gesamte Klasse.  
  
     **Lebensdauer.** Visual Basic unterstützt keine statischen Klassen.  Die funktionale Entsprechung einer statischen Klasse wird von einem Modul bereitgestellt.  Weitere Informationen finden Sie unter [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Die Lebensdauer von Klassenmembern hängt davon ab, wie und wo sie deklariert werden.  Weitere Informationen finden Sie unter [Lifetime in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   **Qualifikation.** In Code außerhalb einer Klasse muss der Name eines Members mit dem Namen dieser Klasse qualifiziert werden.  
  
     Wenn Code in einer geschachtelten Klasse einen nicht qualifizierten Verweis auf ein Programmierelement enthält, sucht Visual Basic das Element zunächst in der geschachtelten Klasse, anschließend in der enthaltenden Klasse und so weiter bis zum äußersten enthaltenden Element.  
  
## Klassen und Module  
 Diese Elemente weisen viele Ähnlichkeiten auf, jedoch bestehen auch einige wichtige Unterschiede.  
  
-   **Begriffe.** In älteren Versionen von Visual Basic werden zwei Typen von Modulen erkannt: *Klassenmodule* \(CLS\-Dateien\) und *Standardmodule* \(BAS\-Dateien\).  In der aktuellen Version werden diese als *Klassen* bzw. *Module* bezeichnet.  
  
-   **Freigegebene Member.** Sie können steuern, ob ein Member einer Klasse ein freigegebener Member oder ein Instanzmember ist.  
  
-   **Objektorientierung.** Klassen sind objektorientiert, Module jedoch nicht.  Sie können eine oder mehrere Instanzen einer Klasse erstellen.  Weitere Informationen finden Sie unter [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## Beispiel  
 Im folgenden Beispiel wird eine `Class`\-Anweisung verwendet, um eine Klasse und mehrere Member zu definieren.  
  
 [!code-vb[VbVbalrStatements#62](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/class-statement_1.vb)]  
  
## Siehe auch  
 [Objects and Classes](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Structures and Classes](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Object Lifetime: How Objects Are Created and Destroyed](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)   
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)