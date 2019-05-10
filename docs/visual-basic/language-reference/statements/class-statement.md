---
title: Class-Anweisung (Visual Basic)
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
ms.openlocfilehash: 7fbf2b15105a9fdcda5c7f6653753a4da54b394b
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64622344"
---
# <a name="class-statement-visual-basic"></a>Class-Anweisung (Visual Basic)
Deklariert den Namen einer Klasse, und führt die Definitionen der Variablen, Eigenschaften, Ereignisse und Prozeduren, die die Klasse umfasst.  
  
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
|`attributelist`|Dies ist optional. Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Dies ist optional. Einer der folgenden Werte ist möglich:<br /><br /> -   [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [Privat geschützt](../../language-reference/modifiers/private-protected.md)<br/><br/> Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Dies ist optional. Finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Dies ist optional. Finden Sie unter [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Dies ist optional. Finden Sie unter [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Dies ist optional. Gibt eine partielle Definition der Klasse an. Finden Sie unter [teilweise](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Erforderlich. Der Name dieser Klasse. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Dies ist optional. Gibt an, dass es sich um eine generische Klasse handelt.|  
|`typelist`|Erforderlich, wenn Sie die [von](../../../visual-basic/language-reference/statements/of-clause.md) Schlüsselwort. Die Liste der Typparameter für diese Klasse. Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Dies ist optional. Gibt an, dass diese Klasse die Member einer anderen Klasse erbt. Finden Sie unter [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Erforderlich, wenn Sie die `Inherits`-Anweisung verwenden. Der Name der Klasse, aus der dieser Klasse abgeleitet wird.|  
|`Implements`|Dies ist optional. Gibt an, dass diese Klasse die Member eine oder mehrere Schnittstellen implementiert. Finden Sie unter [Anweisung implementiert](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie die `Implements`-Anweisung verwenden. Die Namen der Schnittstellen, die von die dieser Klasse implementiert.|  
|`statements`|Dies ist optional. Anweisungen, die die Member dieser Klasse zu definieren.|  
|`End Class`|Erforderlich. Beendet die `Class`-Definition.|  
  
## <a name="remarks"></a>Hinweise  
 Ein `Class` -Anweisung definiert einen neuen Datentyp. Ein *Klasse* ist ein wesentlicher Baustein der objektorientierten Programmierung (OOP). Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 `Class` kann nur auf Namespace- oder Modulebene verwendet werden. Dies bedeutet, dass die *Deklarationskontext* für eine Klasse, eine Quelldatei, Namespace, Klasse, Struktur, Modul oder Schnittstelle sein muss, und eine Prozedur oder der Block nicht möglich. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Jede Instanz einer Klasse verfügt über eine Lebensdauer, die unabhängig von allen anderen Instanzen. Diese Lebensdauer beginnt bei der Erstellung von einem [neuer Operator](../../../visual-basic/language-reference/operators/new-operator.md) Klausel oder eine Funktion, wie z. B. <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>. Sie endet, wenn alle Variablen, zeigen auf die Instanz, dass festgelegt wurden [nichts](../../../visual-basic/language-reference/nothing.md) oder Instanzen anderer Klassen.  
  
 Klassen ist [Friend](../../../visual-basic/language-reference/modifiers/friend.md) Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regeln  
  
- **Schachteln.** Sie können eine Klasse in einer anderen definieren. Die äußere Klasse heißt die *, die Klasse enthält*, und die interne Klasse heißt eine *der geschachtelten Klasse*.  
  
- **Vererbung.** Wenn die Klasse verwendet die [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md), Sie können angeben, nur eine Basisklasse oder Schnittstelle. Eine Klasse kann nicht von mehr als ein Element erben.  
  
     Eine Klasse kann nicht von einer anderen Klasse mit einer stärker einschränkende Zugriffsebene erben. Z. B. eine `Public` Klasse erben kann keinem `Friend` Klasse.  
  
     Eine Klasse kann nicht von einer Klasse, die in ihr geschachtelt ist, erben.  
  
- **-Implementierung.** Wenn die Klasse verwendet die [Implements-Anweisung](../../../visual-basic/language-reference/statements/implements-statement.md), Sie müssen alle Member, die durch jede Schnittstelle, die Sie, in angeben definierten implementieren `interfacenames`. Eine Ausnahme ist die erneute Implementierung eines Members der Basisklasse. Weitere Informationen finden Sie unter "Neuimplementierung" in [implementiert](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
- **Standardeigenschaft.** Eine Klasse kann höchstens eine Eigenschaft als Festlegen der *Standardeigenschaft*. Weitere Informationen finden Sie unter [Standard](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Verhalten  
  
- **Zugriffsebene.** Innerhalb einer Klasse können Sie jeden Member mit einer eigenen Zugriffsebene deklarieren. Standardzugriff für Klassen [öffentliche](../../../visual-basic/language-reference/modifiers/public.md) zuzugreifen, mit Ausnahme von Variablen und Konstanten, die standardmäßig [Private](../../../visual-basic/language-reference/modifiers/private.md) Zugriff. Wenn eine Klasse mehr als einen seiner Member Zugriff eingeschränktem, hat Zugriff auf Klassenebene Vorrang vor.  
  
- **Bereich.** Eine Klasse ist der Gültigkeitsbereich der enthaltenden Namespace, Klasse, Struktur oder Modul.  
  
     Der Gültigkeitsbereich Jeder Klassenmember ist die gesamte Klasse.  
  
     **Lifetime.** Visual Basic unterstützt keine statische Klassen. Die funktionale Entsprechung einer statischen Klasse wird von einem Modul bereitgestellt. Weitere Informationen finden Sie unter [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Klassenmember verfügen über eine Lebensdauer, je nachdem, wie und wo sie deklariert werden. Weitere Informationen finden Sie unter [Lebensdauer in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
- **Qualifizierung.** Code außerhalb einer Klasse muss den Namen eines Mitglieds mit dem Namen dieser Klasse qualifizieren.  
  
     Wenn Code in einer geschachtelten Klasse einen nicht qualifizierten Verweis auf ein Programmierelement enthält, sucht Visual Basic für das Element zuerst in der geschachtelten Klasse, klicken Sie dann in der enthaltenden Klasse, und so weiter bis zum äußersten enthaltenden Element.  
  
## <a name="classes-and-modules"></a>Klassen und Modulen  
 Diese Elemente verfügen über viele ähnlichkeiten, aber es gibt auch einige wichtige Unterschiede.  
  
- **-Terminologie verwenden.** Zwei Arten von Modulen zur Erkennung von früheren Versionen von Visual Basic: *Klassenmodule* (CLS-Dateien) und *Standardmodulen* (BAS-Dateien). Der aktuellen Version werden diese *Klassen* und *Module*bzw.  
  
- **Freigegebene Member.** Sie können steuern, ob ein Member einer Klasse eines freigegebenen oder Instanzmember.  
  
- **Objektorientierung.** Klassen sind objektorientiert, Module jedoch nicht. Sie können eine oder mehrere Instanzen einer Klasse erstellen. Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine `Class` Anweisung, um eine Klasse und mehrere Member definieren.  
  
 [!code-vb[VbVbalrStatements#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#62)]  
  
## <a name="see-also"></a>Siehe auch

- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Strukturen und Klassen](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Interface-Anweisung](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Objektlebensdauer: Wie die Objekte erstellt und zerstört werden](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Vorgehensweise: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
