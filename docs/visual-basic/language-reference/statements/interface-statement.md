---
title: Interface-Anweisung (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: 31ff9211034438e225494b916045acd07c37810f
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
ms.locfileid: "34233911"
---
# <a name="interface-statement-visual-basic"></a>Interface-Anweisung (Visual Basic)
Deklariert den Namen einer Schnittstelle, und führt die Definitionen der Elemente, die die Schnittstelle umfasst.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] _  
Interface name [ ( Of typelist ) ]  
    [ Inherits interfacenames ]  
    [ [ modifiers ] Property membername ]  
    [ [ modifiers ] Function membername ]  
    [ [ modifiers ] Sub membername ]  
    [ [ modifiers ] Event membername ]  
    [ [ modifiers ] Interface membername ]  
    [ [ modifiers ] Class membername ]  
    [ [ modifiers ] Structure membername ]  
End Interface  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`attributelist`|Dies ist optional. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Dies ist optional. Einer der folgenden Werte ist möglich:<br /><br /> -   [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-  [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [Geschützt privat](../../language-reference/modifiers/private-protected.md)<br /><br /> Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Dies ist optional. Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Erforderlich. Der Name dieser Schnittstelle. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Dies ist optional. Gibt an, dass dies eine generische Schnittstelle ist.|  
|`typelist`|Erforderlich, wenn Sie mithilfe der [von](../../../visual-basic/language-reference/statements/of-clause.md) Schlüsselwort. Liste mit Typparametern für diese Schnittstelle. Optional, jeden von Typparameter kann deklariert werden Variante mit `In` und `Out` generischer Modifizierer. Finden Sie unter [geben Liste](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Dies ist optional. Gibt an, dass diese Schnittstelle die Attribute und die Member einer anderen Schnittstelle oder Schnittstellen erbt. Finden Sie unter [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie die `Inherits`-Anweisung verwenden. Die Namen der Schnittstellen, die von denen diese Schnittstelle abgeleitet wird.|  
|`modifiers`|Dies ist optional. Entsprechende Modifizierer für den Schnittstellenmember an, die definiert wird.|  
|`Property`|Dies ist optional. Definiert eine Eigenschaft, die ein Member der Schnittstelle ist.|  
|`Function`|Dies ist optional. Definiert eine `Function` Prozedur, die ein Member der Schnittstelle ist.|  
|`Sub`|Dies ist optional. Definiert eine `Sub` Prozedur, die ein Member der Schnittstelle ist.|  
|`Event`|Dies ist optional. Definiert ein Ereignis, das ein Member der Schnittstelle ist.|  
|`Interface`|Dies ist optional. Definiert eine Schnittstelle, die in dieser Schnittstelle geschachtelt ist. Definition der geschachtelten Schnittstelle muss beendet, und eine `End Interface` Anweisung.|  
|`Class`|Dies ist optional. Definiert eine Klasse, die ein Member der Schnittstelle ist. Die Elementdefinition für die Klasse muss beendet, und eine `End Class` Anweisung.|  
|`Structure`|Dies ist optional. Definiert eine Struktur, die ein Member der Schnittstelle ist. Die Definition für das Element Struktur muss beendet, und eine `End Structure` Anweisung.|  
|`membername`|Erforderlich für jede Eigenschaft, Prozedur, Ereignis, Schnittstelle, Klasse oder Struktur als Member der Schnittstelle definiert. Der Name des Members.|  
|`End Interface`|Beendet die `Interface`-Definition.|  
  
## <a name="remarks"></a>Hinweise  
 Ein *Schnittstelle* definiert eine Menge von Elementen, z. B. Eigenschaften und Prozeduren, die Klassen und Strukturen implementiert werden können. Die Schnittstelle definiert nur die Signaturen der Member und nicht ihre interne Ausführung.  
  
 Eine Klasse oder Struktur implementiert die Schnittstelle durch Bereitstellen von Code für jeden von der Schnittstelle definierten Member. Abschließend, wenn die Anwendung eine Instanz aus dieser Klasse oder Struktur erstellt, ein Objekt vorhanden ist und im Arbeitsspeicher ausgeführt wird. Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) und [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 `Interface` kann nur auf Namespace- oder Modulebene verwendet werden. Dies bedeutet, dass die *Deklarationskontext* für eine Schnittstelle muss eine Quelldatei, Namespace, Klasse, Struktur, Modul oder Schnittstelle, und nicht mit einer Prozedur oder eines Blocks. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Der Standard für Schnittstellen ["Friend"](../../../visual-basic/language-reference/modifiers/friend.md) Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Schachteln von Schnittstellen.** Sie können eine Schnittstelle innerhalb einer anderen definieren. Die äußere Schnittstelle wird aufgerufen, die *, die Schnittstelle enthält*, und die interne Schnittstelle aufgerufen wird eine *geschachtelte Schnittstelle*.  
  
-   **Memberdeklaration.** Wenn Sie eine Eigenschaft oder Prozedur als Member einer Schnittstelle deklarieren, definieren Sie nur die *Signatur* , Eigenschaft oder Prozedur. Dies schließt den Elementtyp (Eigenschaft oder Prozedur), ihre Parameter und Parametertypen und ihren Rückgabetyp. Aus diesem Grund verwendet der Elementdefinition nur eine Codezeile, und abschließende Anweisungen wie `End Function` oder `End Property` sind in einer Schnittstelle nicht gültig.  
  
     Wenn Sie eine Enumeration oder Struktur oder eine geschachtelte Klasse oder Schnittstelle definieren, ist es im Gegensatz dazu muss ihrer Datenmember einbezogen.  
  
-   **Member-Modifizierer.** Sie können keine Zugriffsmodifizierer beim Definieren von Modulmembern, und auch können Sie angeben, [Shared](../../../visual-basic/language-reference/modifiers/shared.md) oder einen anderen Prozedurmodifizierer außer [überlädt](../../../visual-basic/language-reference/modifiers/overloads.md). Sie können einen beliebigen Member mit deklarieren [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md), und Sie können [Standard](../../../visual-basic/language-reference/modifiers/default.md) beim Definieren einer Eigenschaft als auch [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) oder [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   **Vererbung.** Wenn die Benutzeroberfläche verwendet die [Anweisung erbt](../../../visual-basic/language-reference/statements/inherits-statement.md), können Sie eine oder mehrere Basisschnittstellen angeben. Sie können von zwei Schnittstellen erben, auch wenn sie jeweils ein Element mit demselben Namen definieren. In diesem Fall muss der implementierende Code Namensqualifikation verwenden, um die Member anzugeben implementiert wird.  
  
     Eine Schnittstelle kann nicht von einer anderen Schnittstelle mit einer stärker einschränkende Zugriffsebene erben. Z. B. eine `Public` Schnittstelle kann nicht Vererben eine `Friend` Schnittstelle.  
  
     Eine Schnittstelle kann nicht von einer Schnittstelle, die in ihr geschachtelt erben.  
  
-   **-Implementierung.** Wenn einer Klasse verwendet die [implementiert](../../../visual-basic/language-reference/statements/implements-clause.md) Anweisung, um diese Schnittstelle implementieren, muss jedes in der Schnittstelle definierten Member implementieren. Darüber hinaus muss jeder Signatur in der implementierende Code die entsprechende Signatur in der Schnittstelle definierten genau entsprechen. Der Name des Elements in der implementierende Code müssen allerdings nicht den Membernamen gemäß Definition in der Schnittstelle übereinstimmen.  
  
     Bei der Implementierung von einer Prozedur wird einer Klasse kann nicht es angeben, dass die Prozedur als `Shared`.  
  
-   **Standardeigenschaft.** Geben Sie eine Schnittstelle kann höchstens eine Eigenschaft als seine *Standardeigenschaft*, die ohne den Namen der Eigenschaft verwiesen werden kann. Sie geben eine solche Eigenschaft deklarieren Sie es mit der [Standard](../../../visual-basic/language-reference/modifiers/default.md) Modifizierer.  
  
     Beachten Sie, dass dies bedeutet, dass eine Schnittstelle eine Standardeigenschaft definieren kann, nur dann, wenn sie keine erbt.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zugriffsebene.** Alle Schnittstellenmember verfügen implizit über [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) Zugriff. Sie können keine Zugriffsmodifizierer verwenden, wenn Sie ein Element zu definieren. Eine Klasse implementiert die Schnittstelle kann jedoch eine Zugriffsebene für jeden implementierten Member deklarieren.  
  
     Wenn Sie eine Instanz der Klasse zu einer Variablen zuweisen, kann die Zugriffsebene des Membern abhängig, ob der Datentyp der Variablen für die zugrunde liegende Schnittstelle oder die implementierende Klasse ist. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
     [!code-vb[VbVbalrStatements#39](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_1.vb)]  
  
     Wenn der Zugriff auf Klassenmember über `varAsInterface`, alle öffentlichen Zugriff haben. Jedoch, wenn der Zugriff auf Member über `varAsClass`, die `Sub` Prozedur `doSomething` privaten Zugriff hat.  
  
-   **Bereich.** Eine Schnittstelle ist der Gültigkeitsbereich der Namespace, Klasse, Struktur oder Modul.  
  
     Der Gültigkeitsbereich jeder Schnittstellenmember ist die gesamte Schnittstelle.  
  
-   **Lebensdauer.** Eine Schnittstelle verwendet selbst keine Lebensdauer, und ihre Member. Wenn eine Klasse eine Schnittstelle und ein Objekt implementiert wird, dass die Klasse, das Objekt eine Lebensdauer in der Anwendung hat, in dem er ausgeführt wird, als eine Instanz erstellt. Weitere Informationen finden Sie unter "Lifetime" in [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Interface` Anweisung, um eine Schnittstelle mit dem Namen definieren `thisInterface`, die implementiert werden muss, mit einer `Property` Anweisung und eine `Function` Anweisung.  
  
 [!code-vb[VbVbalrStatements#40](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_2.vb)]  
  
 Beachten Sie, dass die `Property` und `Function` Anweisungen führen Blöcke Endung `End Property` und `End Function` innerhalb der Benutzeroberfläche. Die Schnittstelle definiert nur die Signaturen von Membern. Die vollständige `Property` und `Function` Blöcke angezeigt werden, in einer Klasse, die implementiert `thisInterface`.  
  
## <a name="see-also"></a>Siehe auch  
 [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)  
 [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)  
 [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Varianz in generischen Schnittstellen](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
