---
title: Class-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: df86ef0eec67d96f2f997dc5dac7ee2357c6362b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="class-statement-visual-basic"></a>Class-Anweisung (Visual Basic)
Der Name einer Klasse deklariert, und führt die Definitionen der Variablen, Eigenschaften, Ereignisse und Prozeduren, die die Klasse umfasst.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`attributelist`|Dies ist optional. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Dies ist optional. Einer der folgenden Werte ist möglich:<br /><br /> -   [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Dies ist optional. Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Dies ist optional. Finden Sie unter [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Dies ist optional. Finden Sie unter [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Dies ist optional. Gibt eine partielle Definition der Klasse an. Finden Sie unter [partielle](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Erforderlich. Der Name dieser Klasse. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Dies ist optional. Gibt an, dass dies eine generische Klasse.|  
|`typelist`|Erforderlich, wenn Sie mithilfe der [von](../../../visual-basic/language-reference/statements/of-clause.md) Schlüsselwort. Liste mit Typparametern für diese Klasse. Finden Sie unter [geben Liste](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Dies ist optional. Gibt an, dass diese Klasse die Member einer anderen Klasse erbt. Finden Sie unter [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Erforderlich, wenn Sie die `Inherits`-Anweisung verwenden. Der Name der Klasse, von der diese Klasse abgeleitet wird.|  
|`Implements`|Dies ist optional. Gibt an, dass diese Klasse die Member eine oder mehrere Schnittstellen implementiert. Finden Sie unter [Anweisung implementiert](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie die `Implements`-Anweisung verwenden. Die Namen der von dieser Klasse implementierten Schnittstellen.|  
|`statements`|Dies ist optional. Anweisungen, die die Member dieser Klasse zu definieren.|  
|`End Class`|Erforderlich. Beendet die `Class`-Definition.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `Class` -Anweisung definiert einen neuen Datentyp. Ein *Klasse* ist ein wichtiger Baustein der objektorientierten Programmierung (OOP). Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 `Class` kann nur auf Namespace- oder Modulebene verwendet werden. Dies bedeutet, dass die *Deklarationskontext* für eine Klasse muss eine Quelldatei, Namespace, Klasse, Struktur, Modul oder Schnittstelle, und nicht mit einer Prozedur oder eines Blocks. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Jede Instanz einer Klasse hat eine Lebensdauer von allen anderen Instanzen unabhängig. Diese Lebensdauer beginnt, während der Erstellung von einem [New-Operator](../../../visual-basic/language-reference/operators/new-operator.md) -Klausel oder eine Funktion, wie z. B. <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>. Sie endet, wenn alle Variablen, zeigen auf die Instanz festgelegte [nichts](../../../visual-basic/language-reference/nothing.md) oder Instanzen von anderen Klassen.  
  
 Klassen ist ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md) Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Schachteln.** Sie können eine Klasse in einer anderen definieren. Die äußere Klasse heißt die *, die Klasse enthält*, und die innere Klasse heißt ein *der geschachtelten Klasse*.  
  
-   **Vererbung.** Wenn die Klasse verwendet die [Anweisung erbt](../../../visual-basic/language-reference/statements/inherits-statement.md), können Sie nur eine Basisklasse oder Schnittstelle angeben. Eine Klasse kann nicht von mehr als ein Element erben.  
  
     Eine Klasse kann nicht von einer anderen Klasse mit einer stärker einschränkende Zugriffsebene erben. Z. B. eine `Public` Klasse kann nicht Vererben eine `Friend` Klasse.  
  
     Eine Klasse kann nicht von einer Klasse, die in ihr geschachtelt erben.  
  
-   **-Implementierung.** Wenn die Klasse verwendet die [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md), müssen Sie jedes Element durch jede Schnittstelle, die Sie, in angeben definierten implementieren `interfacenames`. Eine Ausnahme ist die erneute Implementierung eines Members der Basisklasse. Weitere Informationen finden Sie unter "Neuimplementierung" in [implementiert](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
-   **Standardeigenschaft.** Eine Klasse kann höchstens eine Eigenschaft als angeben seiner *Standardeigenschaft*. Weitere Informationen finden Sie unter [Standard](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zugriffsebene.** Innerhalb einer Klasse können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren. Klassenmember standardmäßig [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) zuzugreifen, mit Ausnahme von Variablen und Konstanten, die standardmäßig die [Private](../../../visual-basic/language-reference/modifiers/private.md) Zugriff. Wenn eine Klasse Zugriff als eines seiner Elemente stärker eingeschränkt ist, hat Zugriff auf Klassenebene Vorrang vor.  
  
-   **Bereich.** Eine Klasse ist der Gültigkeitsbereich der enthaltenden Namespace, Klasse, Struktur oder Modul.  
  
     Der Gültigkeitsbereich Jeder Klassenmember ist die gesamte Klasse.  
  
     **Lebensdauer.** Visual Basic unterstützt keine statische Klassen. Die funktionale Entsprechung einer statischen Klasse wird von einem Modul bereitgestellt. Weitere Informationen finden Sie unter [Modulanweisung](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Klassenmember verfügen über eine Lebensdauer, je nachdem, wie und wo sie deklariert werden. Weitere Informationen finden Sie unter [Lebensdauer in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   **Qualifizierung.** Code außerhalb einer Klasse muss den Namen eines Mitglieds mit dem Namen dieser Klasse qualifizieren.  
  
     Wenn Code in einer geschachtelten Klasse einen nicht qualifizierten Verweis auf ein Programmierelement enthält, sucht Visual Basic für das Element zunächst in der geschachtelten Klasse, klicken Sie dann in der enthaltenden Klasse und so weiter bis zum äußersten enthaltenden Element.  
  
## <a name="classes-and-modules"></a>Klassen und Module  
 Diese Elemente haben viele ähnlichkeiten, aber es gibt auch einige wichtige Unterschiede.  
  
-   **Terminologie.** Frühere Versionen von Visual Basic werden zwei Typen von Modulen erkannt: *Klassenmodule* (CLS-Dateien) und *Standardmodulen* (BAS-Dateien). Die aktuelle Version ruft diese *Klassen* und *Module*zugeordnet.  
  
-   **Freigegebene Member.** Sie können steuern, ob ein Member einer Klasse eine freigegebene oder Instanzmember.  
  
-   **Objektorientierung.** Klassen können mit dem objektorientierten Module sind allerdings nicht. Sie können eine oder mehrere Instanzen einer Klasse erstellen. Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Class` Anweisung, um eine Klasse und mehrere Member definieren.  
  
 [!code-vb[VbVbalrStatements#62](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/class-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Strukturen und Klassen](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Objektlebensdauer: Erstellen und Zerstören von Objekten](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
