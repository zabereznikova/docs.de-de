---
title: Class Statement
ms.date: 05/12/2018
f1_keywords:
- vb.Class
helpviewer_keywords:
- class modules
- Class statement [Visual Basic]
- classes [Visual Basic], fields
- fields [Visual Basic], of classes
- class types [Visual Basic], class statements
- classes [Visual Basic], creating
- classes [Visual Basic], data members
- data members [Visual Basic], of classes
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
ms.openlocfilehash: 3cb276f134e90ce3b3009234eb980d89477e0d09
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354150"
---
# <a name="class-statement-visual-basic"></a>Class-Anweisung (Visual Basic)
Deklariert den Namen einer Klasse und führt die Definition der Variablen, Eigenschaften, Ereignisse und Prozeduren ein, aus denen die Klasse besteht.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`attributelist`|Optional. Siehe [Attribut Liste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Optional. Einer der folgenden Werte ist möglich:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privat](../../../visual-basic/language-reference/modifiers/private.md)<br />-   [geschützter Freund](../../language-reference/modifiers/protected-friend.md)<br />- [Privat geschützt](../../language-reference/modifiers/private-protected.md)<br/><br/> Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Optional. Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Optional. Siehe [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Optional. Siehe [notvererbt able](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Optional. Gibt eine partielle Definition der-Klasse an. Siehe [partielle](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Erforderlich Der Name dieser Klasse. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Optional. Gibt an, dass es sich um eine generische Klasse handelt.|  
|`typelist`|Erforderlich, wenn Sie das [of](../../../visual-basic/language-reference/statements/of-clause.md) -Schlüsselwort verwenden. Liste der Typparameter für diese Klasse. Siehe [Typliste](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Optional. Gibt an, dass diese Klasse die Member einer anderen Klasse erbt. Siehe [erbt-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Erforderlich, wenn Sie die `Inherits`-Anweisung verwenden. Der Name der Klasse, von der diese Klasse abgeleitet wird.|  
|`Implements`|Optional. Gibt an, dass diese Klasse die Member von einer oder mehreren Schnittstellen implementiert. Siehe [implementierende Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie die `Implements`-Anweisung verwenden. Die Namen der Schnittstellen, die von dieser Klasse implementiert werden.|  
|`statements`|Optional. Anweisungen, die die Member dieser Klasse definieren.|  
|`End Class`|Erforderlich Beendet die `Class`-Definition.|  
  
## <a name="remarks"></a>Hinweise  
 Eine `Class`-Anweisung definiert einen neuen Datentyp. Eine *Klasse* ist ein grundlegender Baustein der objektorientierten Programmierung (OOP). Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 `Class` kann nur auf Namespace- oder Modulebene verwendet werden. Dies bedeutet, dass der *Deklarations Kontext* für eine Klasse eine Quelldatei, ein Namespace, eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein muss und keine Prozedur oder kein Block sein kann. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Jede Instanz einer Klasse hat eine Lebensdauer, die von allen anderen Instanzen unabhängig ist. Diese Lebensdauer beginnt, wenn Sie durch eine [neue Operator](../../../visual-basic/language-reference/operators/new-operator.md) Klausel oder durch eine Funktion wie <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>erstellt wird. Sie endet, wenn alle Variablen, die auf die-Instanz zeigen, auf " [Nothing](../../../visual-basic/language-reference/nothing.md) " oder Instanzen von anderen Klassen festgelegt wurden.  
  
 Klassen sind standardmäßig [Friend](../../../visual-basic/language-reference/modifiers/friend.md) -Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regeln  
  
- **Tigste.** Sie können eine Klasse innerhalb einer anderen Klasse definieren. Die äußere Klasse wird als *enthaltende Klasse*bezeichnet, und die innere Klasse wird als geschachtelte *Klasse*bezeichnet.  
  
- **Vererbung.** Wenn die Klasse die [erbt-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)verwendet, können Sie nur eine Basisklasse oder Schnittstelle angeben. Eine Klasse kann nicht von mehr als einem Element erben.  
  
     Eine Klasse kann nicht von einer anderen Klasse mit einer restriktiveren Zugriffsebene erben. Beispielsweise kann eine `Public` Klasse nicht von einer `Friend` Klasse erben.  
  
     Eine Klasse kann nicht von einer Klasse erben, die darin geschachtelt ist.  
  
- **Ausführungs.** Wenn die Klasse die [implementierte Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md)verwendet, müssen Sie jedes Element implementieren, das von jeder Schnittstelle definiert wird, die Sie in `interfacenames`angeben. Eine Ausnahme hiervon ist die Neuimplementierung eines Basisklassenmembers. Weitere Informationen finden Sie unter "Reimplementierung" in [implementieren](../../../visual-basic/language-reference/statements/implements-clause.md)von.  
  
- **Standard Eigenschaft.** Eine Klasse kann höchstens eine Eigenschaft als *Standard Eigenschaft*angeben. Weitere Informationen finden Sie unter [default (Standard](../../../visual-basic/language-reference/modifiers/default.md)).  
  
## <a name="behavior"></a>Verhalten  
  
- **Zugriffsebene.** Innerhalb einer Klasse können Sie jeden Member mit eigener Zugriffsebene deklarieren. Klassenmember haben standardmäßig den [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) Zugriff, mit Ausnahme von Variablen und Konstanten, die standardmäßig den [privaten](../../../visual-basic/language-reference/modifiers/private.md) Zugriff haben. Wenn eine Klasse einen eingeschränkteren Zugriff als einen ihrer Member hat, hat die Klassen Zugriffsebene Vorrang.  
  
- **Umfang.** Eine-Klasse befindet sich im Gültigkeitsbereich des enthaltenden Namespace, der Klasse, der Struktur oder des Moduls.  
  
     Der Gültigkeitsbereich jedes Klassenmembers ist die gesamte Klasse.  
  
     **Amtszeit.** Visual Basic unterstützt keine statischen Klassen. Das funktionale Äquivalent einer statischen Klasse wird von einem Modul bereitgestellt. Weitere Informationen finden Sie unter [Modul Anweisung](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Klassenmember haben Lebens dauern, abhängig davon, wie und wo Sie deklariert werden. Weitere Informationen finden Sie unter [Lebensdauer in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
- **Abschluss.** Code außerhalb einer Klasse muss den Namen eines Members mit dem Namen dieser Klasse qualifizieren.  
  
     Wenn Code in einer geschachtelten Klasse einen nicht qualifizierten Verweis auf ein Programmier Element erstellt, sucht Visual Basic zuerst nach dem Element in der geschachtelten Klasse, dann in der enthaltenden Klasse usw. bis zum äußersten enthaltenden Element.  
  
## <a name="classes-and-modules"></a>Klassen und Module  
 Diese Elemente weisen viele Ähnlichkeiten auf, aber es gibt auch einige wichtige Unterschiede.  
  
- **Begriffs.** In früheren Versionen von Visual Basic werden zwei Arten von Modulen erkannt: *Klassen Module* (CLS-Dateien) und *Standardmodule* (Bas-Dateien). Mit der aktuellen Version werden diese *Klassen* bzw. *Module*aufgerufen.  
  
- **Freigegebene Member.** Sie können steuern, ob ein Member einer Klasse ein frei Gegebenes oder ein Instanzmember ist.  
  
- **Objekt Ausrichtung.** Klassen sind objektorientiert, aber Module sind nicht. Sie können eine oder mehrere Instanzen einer Klasse erstellen. Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Class`-Anweisung verwendet, um eine-Klasse und mehrere Member zu definieren.  
  
 [!code-vb[VbVbalrStatements#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#62)]  
  
## <a name="see-also"></a>Siehe auch

- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Strukturen und Klassen](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Objektlebensdauer: Erstellen und Zerstören von Objekten](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
