---
title: Interface-Anweisung (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: 68590702835e47e5f0f2e0380bc0fe4017d5eb15
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582670"
---
# <a name="interface-statement-visual-basic"></a>Interface-Anweisung (Visual Basic)
Deklariert den Namen einer Schnittstelle und führt die Definitionen der Member ein, aus denen die Schnittstelle besteht.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
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
|`attributelist`|Optional. Siehe [Attribut Liste](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Optional. Kann einen der folgenden Werte annehmen:<br /><br /> -   [öffentlich](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [geschützt](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   -[Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privat](../../../visual-basic/language-reference/modifiers/private.md)<br />-  [geschützter Freund](../../language-reference/modifiers/protected-friend.md)<br/>-  ([Privat geschützt](../../language-reference/modifiers/private-protected.md) )<br /><br /> Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Optional. Siehe [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Erforderlich. Der Name dieser Schnittstelle. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Optional. Gibt an, dass dies eine generische Schnittstelle ist.|  
|`typelist`|Erforderlich, wenn Sie das [of](../../../visual-basic/language-reference/statements/of-clause.md) -Schlüsselwort verwenden. Liste der Typparameter für diese Schnittstelle. Optional kann jeder Typparameter als Variant deklariert werden, indem `In` und `Out` generische Modifizierer verwendet werden. Siehe [Typliste](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Optional. Gibt an, dass diese Schnittstelle die Attribute und Member einer anderen Schnittstelle oder Schnittstellen erbt. Siehe [erbt-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie die `Inherits`-Anweisung verwenden. Die Namen der Schnittstellen, von denen diese Schnittstelle abgeleitet ist.|  
|`modifiers`|Optional. Geeignete modifiziererer für den Schnittstellenmember, der definiert wird.|  
|`Property`|Optional. Definiert eine Eigenschaft, die ein Member der-Schnittstelle ist.|  
|`Function`|Optional. Definiert eine `Function` Prozedur, die ein Member der-Schnittstelle ist.|  
|`Sub`|Optional. Definiert eine `Sub` Prozedur, die ein Member der-Schnittstelle ist.|  
|`Event`|Optional. Definiert ein Ereignis, das ein Member der-Schnittstelle ist.|  
|`Interface`|Optional. Definiert eine Schnittstelle, die in dieser Schnittstelle geschachtelt ist. Die Definition der Definition für die-Schnittstelle muss mit einer `End Interface`-Anweisung beendet werden.|  
|`Class`|Optional. Definiert eine Klasse, die ein Member der-Schnittstelle ist. Die Definition der Element Klasse muss mit einer `End Class`-Anweisung beendet werden.|  
|`Structure`|Optional. Definiert eine-Struktur, die ein Member der-Schnittstelle ist. Die Definition der Elementstruktur muss mit einer `End Structure`-Anweisung beendet werden.|  
|`membername`|Erforderlich für jede Eigenschaft, Prozedur, jedes Ereignis, jede Schnittstelle, jede Klasse oder Struktur, die als Member der-Schnittstelle definiert ist. Der Name des Members.|  
|`End Interface`|Beendet die `Interface`-Definition.|  
  
## <a name="remarks"></a>Hinweise  
 Eine *Schnittstelle* definiert einen Satz von Membern, z. b. Eigenschaften und Prozeduren, die von Klassen und Strukturen implementiert werden können. Die-Schnittstelle definiert nur die Signaturen der Elemente und nicht Ihre internen Abläufe.  
  
 Eine Klasse oder Struktur implementiert die-Schnittstelle durch Bereitstellen von Code für jeden von der-Schnittstelle definierten Member. Wenn die Anwendung schließlich eine Instanz aus dieser Klasse oder Struktur erstellt, ist ein Objekt vorhanden, das im Arbeitsspeicher ausgeführt wird. Weitere Informationen finden Sie unter [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) und [Schnittstellen](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 `Interface` kann nur auf Namespace- oder Modulebene verwendet werden. Dies bedeutet, dass der *Deklarations Kontext* für eine Schnittstelle eine Quelldatei, ein Namespace, eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein muss und keine Prozedur oder kein Block sein kann. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Schnittstellen haben standardmäßig den [Friend](../../../visual-basic/language-reference/modifiers/friend.md) -Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regeln  
  
- **Schachtelungs Schnittstellen.** Sie können eine Schnittstelle innerhalb einer anderen definieren. Die äußere Schnittstelle wird als *enthaltende Schnitt*Stelle bezeichnet, und die innere Schnittstelle wird als geschachtelte *Schnitt*Stelle bezeichnet.  
  
- **Member-Deklaration.** Wenn Sie eine Eigenschaft oder Prozedur als Member einer Schnittstelle deklarieren, definieren Sie nur die *Signatur* dieser Eigenschaft oder Prozedur. Dies schließt den Elementtyp (Eigenschaft oder Prozedur), seine Parameter und die Parametertypen und den Rückgabetyp ein. Aus diesem Grund wird in der Element Definition nur eine Codezeile verwendet, und abschließende Anweisungen, wie z. b. `End Function` oder `End Property`, sind in einer Schnittstelle nicht gültig.  
  
     Wenn Sie hingegen eine Enumeration oder Struktur oder eine Klasse oder Schnittstelle definieren, ist es erforderlich, ihre Datenmember einzubeziehen.  
  
- **Member-modifiziererer.** Sie können keine Zugriffsmodifizierer verwenden, wenn Sie Modulmember definieren, und Sie können auch keinen frei [gegebenen](../../../visual-basic/language-reference/modifiers/shared.md) oder einen Modifizierer mit Ausnahme von [über Ladungen](../../../visual-basic/language-reference/modifiers/overloads.md) Sie können einen beliebigen Member mit Shadowing deklarieren, und Sie können [Standard](../../../visual-basic/language-reference/modifiers/default.md) Werte [verwenden, wenn](../../../visual-basic/language-reference/modifiers/shadows.md)Sie eine Eigenschaft definieren, ebenso wie " [Schreib](../../../visual-basic/language-reference/modifiers/writeonly.md)geschützt [" oder "](../../../visual-basic/language-reference/modifiers/readonly.md) schreiben".  
  
- **Vererbung.** Wenn die Schnittstelle die [erbt-Anweisung](../../../visual-basic/language-reference/statements/inherits-statement.md)verwendet, können Sie eine oder mehrere Basis Schnittstellen angeben. Sie können von zwei Schnittstellen erben, auch wenn Sie jeweils einen Member mit demselben Namen definieren. Wenn Sie dies tun, muss der implementierende Code die namens Qualifizierung verwenden, um anzugeben, welcher Member implementiert wird.  
  
     Eine Schnittstelle kann nicht von einer anderen Schnittstelle mit einer restriktiveren Zugriffsebene erben. Beispielsweise kann eine `Public`-Schnittstelle nicht von einer `Friend`-Schnittstelle erben.  
  
     Eine Schnittstelle kann nicht von einer Schnittstelle erben, die darin geschachtelt ist.  
  
- **Ausführungs.** Wenn eine Klasse [die implementierte-Anweisung verwendet](../../../visual-basic/language-reference/statements/implements-clause.md) , um diese Schnittstelle zu implementieren, muss Sie jedes in der Schnittstelle definierte Element implementieren. Darüber hinaus muss jede Signatur im implementierenden Code genau mit der entsprechenden Signatur übereinstimmen, die in dieser Schnittstelle definiert ist. Allerdings muss der Name des Members im implementierenden Code nicht mit dem in der Schnittstelle definierten Elementnamen identisch sein.  
  
     Wenn eine Klasse eine Prozedur implementiert, kann Sie die Prozedur nicht als `Shared` festlegen.  
  
- **Standard Eigenschaft.** Eine Schnittstelle kann höchstens eine Eigenschaft als *Standard Eigenschaft*angeben, auf die ohne Verwendung des Eigenschafts namens verwiesen werden kann. Sie geben eine solche Eigenschaft an, indem Sie Sie mit dem [Standardmodifizierer](../../../visual-basic/language-reference/modifiers/default.md) deklarieren.  
  
     Beachten Sie, dass eine Schnittstelle eine Standard Eigenschaft nur definieren kann, wenn Sie None erbt.  
  
## <a name="behavior"></a>Verhalten  
  
- **Zugriffsebene.** Alle Schnittstellenmember haben implizit [öffentlichen](../../../visual-basic/language-reference/modifiers/public.md) Zugriff. Sie können keinen Zugriffsmodifizierer verwenden, wenn Sie einen Member definieren. Allerdings kann eine Klasse, die die-Schnittstelle implementiert, eine Zugriffsebene für jedes implementierte Element deklarieren.  
  
     Wenn Sie einer Variablen eine Klasseninstanz zuweisen, kann die Zugriffsebene der Member davon abhängen, ob der Datentyp der Variablen die zugrunde liegende Schnittstelle oder die implementierende Klasse ist. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
     [!code-vb[VbVbalrStatements#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#39)]  
  
     Wenn Sie über `varAsInterface` auf Klassenmember zugreifen, haben Sie alle öffentlichen Zugriff. Wenn Sie jedoch über `varAsClass` auf Member zugreifen, hat die `Sub` Prozedur `doSomething` privaten Zugriff.  
  
- **Umfang.** Eine Schnittstelle befindet sich im Gültigkeitsbereich des Namespace, der Klasse, der Struktur oder des Moduls.  
  
     Der Gültigkeitsbereich aller Schnittstellenmember ist die gesamte Schnittstelle.  
  
- **Amtszeit.** Eine Schnittstelle hat selbst keine Lebensdauer und auch keine Member. Wenn eine Klasse eine Schnittstelle implementiert und ein Objekt als Instanz dieser Klasse erstellt wird, verfügt das Objekt über eine Gültigkeitsdauer innerhalb der Anwendung, in der es ausgeführt wird. Weitere Informationen finden Sie unter "Lebensdauer" in [Class-Anweisung](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Interface`-Anweisung verwendet, um eine Schnittstelle mit dem Namen `thisInterface` zu definieren, die mit einer `Property`-Anweisung und einer `Function`-Anweisung implementiert werden muss.  
  
 [!code-vb[VbVbalrStatements#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#40)]  
  
 Beachten Sie, dass die `Property`-und `Function`-Anweisungen keine Blöcke mit `End Property` und `End Function` in der Schnittstelle bereitstellen. Die-Schnittstelle definiert nur die Signaturen ihrer Member. Die vollständigen `Property` und `Function` Blöcke werden in einer Klasse angezeigt, die `thisInterface` implementiert.  
  
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
