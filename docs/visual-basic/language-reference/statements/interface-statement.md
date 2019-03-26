---
title: Interface-Anweisung (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: f65875caa16bfe00866cc3cd6fd0c0b22b034576
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56970531"
---
# <a name="interface-statement-visual-basic"></a>Interface-Anweisung (Visual Basic)
Deklariert den Namen einer Schnittstelle, und führt die Definitionen der Elemente, die die Schnittstelle enthält.  
  
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
|`attributelist`|Dies ist optional. Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Dies ist optional. Einer der folgenden Werte ist möglich:<br /><br /> -   [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-  [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br/>- [Privat geschützt](../../language-reference/modifiers/private-protected.md)<br /><br /> Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Dies ist optional. Finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Erforderlich. Der Name dieser Schnittstelle. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Dies ist optional. Gibt an, dass dies eine generische Schnittstelle ist.|  
|`typelist`|Erforderlich, wenn Sie die [von](../../../visual-basic/language-reference/statements/of-clause.md) Schlüsselwort. Die Liste der Typparameter für diese Schnittstelle. Optional, jeden von Typparameter kann deklariert werden Variante mit `In` und `Out` generische Modifizierer. Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Dies ist optional. Gibt an, dass diese Schnittstelle die Attribute und die Member einer anderen Schnittstelle oder Schnittstellen erbt. Finden Sie unter [Inherits-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie die `Inherits`-Anweisung verwenden. Die Namen der Schnittstellen, die von denen diese Schnittstelle abgeleitet wird.|  
|`modifiers`|Dies ist optional. Entsprechende Modifizierer für den Schnittstellenmember definiert wird.|  
|`Property`|Dies ist optional. Definiert eine Eigenschaft, die ein Member der Schnittstelle ist.|  
|`Function`|Dies ist optional. Definiert eine `Function` Prozedur, die ein Member der Schnittstelle ist.|  
|`Sub`|Dies ist optional. Definiert eine `Sub` Prozedur, die ein Member der Schnittstelle ist.|  
|`Event`|Dies ist optional. Definiert ein Ereignis, das ein Member der Schnittstelle ist.|  
|`Interface`|Dies ist optional. Definiert eine Schnittstelle, die in dieser Schnittstelle geschachtelt ist. Die geschachtelte Schnittstellendefinition muss beendet, und ein `End Interface` Anweisung.|  
|`Class`|Dies ist optional. Definiert eine Klasse, die ein Member der Schnittstelle ist. Die Definition der Member-Klasse muss beendet, und ein `End Class` Anweisung.|  
|`Structure`|Dies ist optional. Definiert eine Struktur, die ein Member der Schnittstelle ist. Die Strukturdefinition des Members muss beendet, und ein `End Structure` Anweisung.|  
|`membername`|Erforderlich für jede Eigenschaft, Prozedur, Ereignis, Schnittstelle, Klasse oder der Struktur, die als Member der Schnittstelle definiert. Der Name des Members.|  
|`End Interface`|Beendet die `Interface`-Definition.|  
  
## <a name="remarks"></a>Hinweise  
 Ein *Schnittstelle* definiert eine Menge von Elementen, aus, wie z. B. Eigenschaften und Prozeduren, die Klassen und Strukturen implementiert werden können. Die Schnittstelle definiert nur die Signaturen der Mitglieder und nicht die interne Funktionsweise.  
  
 Eine Klasse oder Struktur implementiert die Schnittstelle, indem Sie Code für jeden von der Schnittstelle definierten Member angeben. Schließlich, wenn die Anwendung eine Instanz von dieser Klasse oder Struktur erstellt, ein Objekt vorhanden ist und wird im Arbeitsspeicher ausgeführt. Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) und [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 `Interface` kann nur auf Namespace- oder Modulebene verwendet werden. Dies bedeutet, dass die *Deklarationskontext* für eine Schnittstelle, eine Quelldatei, Namespace, Klasse, Struktur, Modul oder Schnittstelle sein muss, und eine Prozedur oder der Block nicht möglich. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Der Standard für Schnittstellen [Friend](../../../visual-basic/language-reference/modifiers/friend.md) Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Schachteln von Schnittstellen.** Sie können eine Schnittstelle in einer anderen definieren. Die äußere Schnittstelle heißt die *, die Schnittstelle enthält*, und die interne Schnittstelle heißt eine *geschachtelte Schnittstelle*.  
  
-   **Memberdeklaration.** Wenn Sie eine Eigenschaft oder Prozedur als Member einer Schnittstelle deklarieren, definieren Sie nur die *Signatur* einer Eigenschaft oder Prozedur. Dies schließt den Elementtyp (Eigenschaft oder Prozedur), Parameter und Parametertypen und der Rückgabetyp. Aus diesem Grund verwendet der Elementdefinition nur eine Codezeile, und abschließende Anweisungen wie `End Function` oder `End Property` sind in einer Schnittstelle nicht gültig.  
  
     Wenn Sie eine Enumeration oder eine Struktur oder eine geschachtelte Klasse oder Schnittstelle definieren, ist es im Gegensatz dazu erforderlich, ihrer Datenmember enthalten.  
  
-   **Member-Modifizierer.** Sie können keine Zugriffsmodifizierer können nicht verwenden, beim definieren, können Sie auch angeben [Shared](../../../visual-basic/language-reference/modifiers/shared.md) oder einen anderen Prozedurmodifizierer außer [Überladungen](../../../visual-basic/language-reference/modifiers/overloads.md). Sie können einen beliebigen Member mit deklarieren [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md), und Sie können [Standard](../../../visual-basic/language-reference/modifiers/default.md) beim Definieren einer Eigenschaft sowie [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) oder [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   **Vererbung.** Wenn die Schnittstelle verwendet die [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md), Sie können einem oder mehreren Basisschnittstellen angeben. Sie können über zwei Schnittstellen erben, auch wenn sie jeweils einen Member mit demselben Namen definieren. Wenn Sie dies tun, muss der implementierende Code Namensqualifikation verwenden Sie zum Angeben von der Members implementiert wird.  
  
     Eine Schnittstelle kann nicht von einer anderen Schnittstelle mit einer stärker einschränkende Zugriffsebene erben. Z. B. eine `Public` Schnittstelle kann nicht erben von einem `Friend` Schnittstelle.  
  
     Eine Schnittstelle kann nicht von einer Schnittstelle, die in ihr geschachtelt ist, erben.  
  
-   **-Implementierung.** Wenn eine Klasse verwendet die [implementiert](../../../visual-basic/language-reference/statements/implements-clause.md) Anweisung, um diese Schnittstelle implementiert, muss jede in der Schnittstelle definierten Member implementieren. Darüber hinaus muss für jede Signatur in der implementierende Code genau die entsprechenden Signatur, die in der Schnittstelle definierten übereinstimmen. Allerdings muss der Name des Elements in der implementierende Code keine entsprechen den Namen des Members in der Schnittstelle definiert.  
  
     Beim Implementieren einer Klasse ist einer Prozedur, kann nicht es angeben, dass die Prozedur als `Shared`.  
  
-   **Standardeigenschaft.** Geben Sie eine Schnittstelle kann höchstens eine Eigenschaft als seine *Standardeigenschaft*, die ohne den Eigenschaftennamen verwiesen werden kann. Sie geben eine solche Eigenschaft deklarieren Sie es mit der [Standard](../../../visual-basic/language-reference/modifiers/default.md) Modifizierer.  
  
     Beachten Sie, dass dies bedeutet, dass eine Schnittstelle eine Standardeigenschaft definieren kann, nur dann, wenn sie keine erbt.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zugriffsebene.** Alle Schnittstellenmember verfügen implizit über [öffentliche](../../../visual-basic/language-reference/modifiers/public.md) Zugriff. Sie können keine Zugriffsmodifizierer nicht verwenden, wenn ein Element definieren. Allerdings kann eine Klasse implementiert die Schnittstelle eine Zugriffsebene für jeden implementierten Member deklarieren.  
  
     Wenn Sie eine Instanz der Klasse zu einer Variablen zuweisen, kann die Zugriffsebene der Member davon abhängen, ob der Datentyp der Variablen für die zugrunde liegende Schnittstelle oder die implementierende Klasse ist. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
     [!code-vb[VbVbalrStatements#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#39)]  
  
     Wenn Sie Zugriff auf Klassenmember über `varAsInterface`, sie verfügen über öffentlichen Zugriff. Jedoch wenn Sie Zugriff auf Member über `varAsClass`, `Sub` Prozedur `doSomething` privaten Zugriff hat.  
  
-   **Bereich.** Eine Schnittstelle ist der Gültigkeitsbereich der Namespace, Klasse, Struktur oder Modul.  
  
     Der Gültigkeitsbereich jeder Schnittstellenmember ist die gesamte Schnittstelle.  
  
-   **Lifetime.** Eine Schnittstelle ist nicht selbst haben eine Lebensdauer, noch ihre Member. Wenn eine Klasse eine Schnittstelle und einem Objekt implementiert wird, dass die Klasse, die das Objekt eine Lebensdauer innerhalb der Anwendung hat in dem er ausgeführt wird als eine Instanz erstellt. Weitere Informationen finden Sie unter "Lebensdauer" in [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Interface` Anweisung, um eine Schnittstelle, die mit dem Namen definieren `thisInterface`, die implementiert werden muss, mit einer `Property` Anweisung und eine `Function` Anweisung.  
  
 [!code-vb[VbVbalrStatements#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#40)]  
  
 Beachten Sie, dass die `Property` und `Function` Anweisungen führen Blöcke Endung `End Property` und `End Function` innerhalb der Schnittstelle. Die Schnittstelle definiert nur die Signaturen von Membern. Die vollständige `Property` und `Function` Blöcke angezeigt, in einer Klasse, die implementiert `thisInterface`.  
  
## <a name="see-also"></a>Siehe auch
- [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
- [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md)
- [Module-Anweisung](../../../visual-basic/language-reference/statements/module-statement.md)
- [Structure-Anweisung](../../../visual-basic/language-reference/statements/structure-statement.md)
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Varianz in generischen Schnittstellen](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)
- [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
