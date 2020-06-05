---
title: Interface-Anweisung
ms.date: 05/12/2018
f1_keywords:
- vb.Interface
helpviewer_keywords:
- interface statement [Visual Basic]
- interfaces [Visual Basic], interface definition
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
ms.openlocfilehash: 02d258084aaaa53dcc559cfaa0dec27556351037
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404485"
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
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`attributelist`|Dies ist optional. Siehe [Attribut Liste](attribute-list.md).|  
|`accessmodifier`|Optional. Kann eines der folgenden Elemente sein:<br /><br /> -   [Publikums](../modifiers/public.md)<br />-   [Gebieten](../modifiers/protected.md)<br />-   [Kollegen](../modifiers/friend.md)<br />-   [Private](../modifiers/private.md)<br />-  [Geschützter Freund](../modifiers/protected-friend.md)<br/>- [Privat geschützt](../modifiers/private-protected.md)<br /><br /> Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Optional. Siehe [Shadows](../modifiers/shadows.md).|  
|`name`|Erforderlich. Der Name dieser Schnittstelle. Siehe [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Optional. Gibt an, dass dies eine generische Schnittstelle ist.|  
|`typelist`|Erforderlich, wenn Sie das [of](of-clause.md) -Schlüsselwort verwenden. Liste der Typparameter für diese Schnittstelle. Optional kann jeder Typparameter mithilfe von `In` und `Out` generischen modifizierervariablen als Variant deklariert werden. Siehe [Typliste](type-list.md).|  
|`Inherits`|Optional. Gibt an, dass diese Schnittstelle die Attribute und Member einer anderen Schnittstelle oder Schnittstellen erbt. Siehe [erbt-Anweisung](inherits-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie die `Inherits`-Anweisung verwenden. Die Namen der Schnittstellen, von denen diese Schnittstelle abgeleitet ist.|  
|`modifiers`|Optional. Geeignete modifiziererer für den Schnittstellenmember, der definiert wird.|  
|`Property`|Optional. Definiert eine Eigenschaft, die ein Member der-Schnittstelle ist.|  
|`Function`|Optional. Definiert eine `Function` Prozedur, die ein Member der-Schnittstelle ist.|  
|`Sub`|Optional. Definiert eine `Sub` Prozedur, die ein Member der-Schnittstelle ist.|  
|`Event`|Optional. Definiert ein Ereignis, das ein Member der-Schnittstelle ist.|  
|`Interface`|Optional. Definiert eine Schnittstelle, die in dieser Schnittstelle geschachtelt ist. Die Definition der Definition für die-Schnittstelle muss mit einer- `End Interface` Anweisung enden.|  
|`Class`|Optional. Definiert eine Klasse, die ein Member der-Schnittstelle ist. Die Member-Klassendefinition muss mit einer-Anweisung beendet werden `End Class` .|  
|`Structure`|Optional. Definiert eine-Struktur, die ein Member der-Schnittstelle ist. Die Definition der Elementstruktur muss mit einer-Anweisung beendet werden `End Structure` .|  
|`membername`|Erforderlich für jede Eigenschaft, Prozedur, jedes Ereignis, jede Schnittstelle, jede Klasse oder Struktur, die als Member der-Schnittstelle definiert ist. Der Name des Elements.|  
|`End Interface`|Beendet die `Interface`-Definition.|  
  
## <a name="remarks"></a>Bemerkungen  
 Eine *Schnittstelle* definiert einen Satz von Membern, z. b. Eigenschaften und Prozeduren, die von Klassen und Strukturen implementiert werden können. Die-Schnittstelle definiert nur die Signaturen der Elemente und nicht Ihre internen Abläufe.  
  
 Eine Klasse oder Struktur implementiert die-Schnittstelle durch Bereitstellen von Code für jeden von der-Schnittstelle definierten Member. Wenn die Anwendung schließlich eine Instanz aus dieser Klasse oder Struktur erstellt, ist ein Objekt vorhanden, das im Arbeitsspeicher ausgeführt wird. Weitere Informationen finden Sie unter [Objekte und Klassen](../../programming-guide/language-features/objects-and-classes/index.md) und [Schnittstellen](../../programming-guide/language-features/interfaces/index.md).  
  
 `Interface` kann nur auf Namespace- oder Modulebene verwendet werden. Dies bedeutet, dass der *Deklarations Kontext* für eine Schnittstelle eine Quelldatei, ein Namespace, eine Klasse, eine Struktur, ein Modul oder eine Schnittstelle sein muss und keine Prozedur oder kein Block sein kann. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](declaration-contexts-and-default-access-levels.md).  
  
 Schnittstellen haben standardmäßig den [Friend](../modifiers/friend.md) -Zugriff. Sie können ihre Zugriffsebenen mit den Zugriffsmodifizierern anpassen. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regeln  
  
- **Schachtelungs Schnittstellen.** Sie können eine Schnittstelle innerhalb einer anderen definieren. Die äußere Schnittstelle wird als *enthaltende Schnitt*Stelle bezeichnet, und die innere Schnittstelle wird als geschachtelte *Schnitt*Stelle bezeichnet.  
  
- **Memberdeklaration.** Wenn Sie eine Eigenschaft oder Prozedur als Member einer Schnittstelle deklarieren, definieren Sie nur die *Signatur* dieser Eigenschaft oder Prozedur. Dies schließt den Elementtyp (Eigenschaft oder Prozedur), seine Parameter und die Parametertypen und den Rückgabetyp ein. Aus diesem Grund verwendet die Element Definition nur eine Codezeile, und abschließende Anweisungen wie `End Function` oder `End Property` sind in einer Schnittstelle nicht gültig.  
  
     Wenn Sie hingegen eine Enumeration oder Struktur oder eine Klasse oder Schnittstelle definieren, ist es erforderlich, ihre Datenmember einzubeziehen.  
  
- **Member-modifiziererer.** Sie können keine Zugriffsmodifizierer verwenden, wenn Sie Modulmember definieren, und Sie können auch keinen frei [gegebenen](../modifiers/shared.md) oder einen Modifizierer mit Ausnahme von [über Ladungen](../modifiers/overloads.md) Sie können einen beliebigen Member mit Shadowing deklarieren, und Sie können [Standard](../modifiers/default.md) Werte [verwenden, wenn](../modifiers/shadows.md)Sie eine Eigenschaft definieren, ebenso wie " [Schreib](../modifiers/writeonly.md)geschützt [" oder "](../modifiers/readonly.md) schreiben".  
  
- **Vererbung.** Wenn die Schnittstelle die [erbt-Anweisung](inherits-statement.md)verwendet, können Sie eine oder mehrere Basis Schnittstellen angeben. Sie können von zwei Schnittstellen erben, auch wenn Sie jeweils einen Member mit demselben Namen definieren. Wenn Sie dies tun, muss der implementierende Code die namens Qualifizierung verwenden, um anzugeben, welcher Member implementiert wird.  
  
     Eine Schnittstelle kann nicht von einer anderen Schnittstelle mit einer restriktiveren Zugriffsebene erben. Beispielsweise kann eine- `Public` Schnittstelle nicht von einer- `Friend` Schnittstelle erben.  
  
     Eine Schnittstelle kann nicht von einer Schnittstelle erben, die darin geschachtelt ist.  
  
- **Ausführungs.** Wenn eine Klasse [die implementierte-Anweisung verwendet](implements-clause.md) , um diese Schnittstelle zu implementieren, muss Sie jedes in der Schnittstelle definierte Element implementieren. Darüber hinaus muss jede Signatur im implementierenden Code genau mit der entsprechenden Signatur übereinstimmen, die in dieser Schnittstelle definiert ist. Allerdings muss der Name des Members im implementierenden Code nicht mit dem in der Schnittstelle definierten Elementnamen identisch sein.  
  
     Wenn eine Klasse eine Prozedur implementiert, kann Sie die Prozedur nicht als festlegen `Shared` .  
  
- **Standard Eigenschaft.** Eine Schnittstelle kann höchstens eine Eigenschaft als *Standard Eigenschaft*angeben, auf die ohne Verwendung des Eigenschafts namens verwiesen werden kann. Sie geben eine solche Eigenschaft an, indem Sie Sie [Default](../modifiers/default.md) mit dem Standardmodifizierer deklarieren.  
  
     Beachten Sie, dass eine Schnittstelle eine Standard Eigenschaft nur definieren kann, wenn Sie None erbt.  
  
## <a name="behavior"></a>Verhalten  
  
- **Zugriffsebene.** Alle Schnittstellenmember haben implizit [öffentlichen](../modifiers/public.md) Zugriff. Sie können keinen Zugriffsmodifizierer verwenden, wenn Sie einen Member definieren. Allerdings kann eine Klasse, die die-Schnittstelle implementiert, eine Zugriffsebene für jedes implementierte Element deklarieren.  
  
     Wenn Sie einer Variablen eine Klasseninstanz zuweisen, kann die Zugriffsebene der Member davon abhängen, ob der Datentyp der Variablen die zugrunde liegende Schnittstelle oder die implementierende Klasse ist. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
     [!code-vb[VbVbalrStatements#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#39)]  
  
     Wenn Sie über auf Klassenmember zugreifen `varAsInterface` , haben Sie alle öffentlichen Zugriff. Wenn Sie jedoch über auf Member zugreifen `varAsClass` , `Sub` verfügt die Prozedur über `doSomething` private Zugriffsrechte.  
  
- **Umfang.** Eine Schnittstelle befindet sich im Gültigkeitsbereich des Namespace, der Klasse, der Struktur oder des Moduls.  
  
     Der Gültigkeitsbereich aller Schnittstellenmember ist die gesamte Schnittstelle.  
  
- **Amtszeit.** Eine Schnittstelle hat selbst keine Lebensdauer und auch keine Member. Wenn eine Klasse eine Schnittstelle implementiert und ein Objekt als Instanz dieser Klasse erstellt wird, verfügt das Objekt über eine Gültigkeitsdauer innerhalb der Anwendung, in der es ausgeführt wird. Weitere Informationen finden Sie unter "Lebensdauer" in [Class-Anweisung](class-statement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Interface` -Anweisung verwendet, um eine Schnittstelle mit dem Namen zu definieren `thisInterface` , die mit einer `Property` -Anweisung und einer-Anweisung implementiert werden muss `Function` .  
  
 [!code-vb[VbVbalrStatements#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#40)]  
  
 Beachten Sie, dass die `Property` -und- `Function` Anweisungen keine Blöcke einführen, `End Property` die mit und `End Function` innerhalb der-Schnittstelle enden. Die-Schnittstelle definiert nur die Signaturen ihrer Member. Die vollständigen `Property` -und- `Function` Blöcke werden in einer Klasse angezeigt, die implementiert `thisInterface` .  
  
## <a name="see-also"></a>Weitere Informationen

- [Schnittstellen](../../programming-guide/language-features/interfaces/index.md)
- [Class-Anweisung](class-statement.md)
- [Module-Anweisung](module-statement.md)
- [Structure Statement](structure-statement.md)
- [Property Statement](property-statement.md)
- [Function-Anweisung](function-statement.md)
- [Sub-Anweisung](sub-statement.md)
- [Generische Typen in Visual Basic (Visual Basic)](../../programming-guide/language-features/data-types/generic-types.md)
- [Abweichungen bei generischen Schnittstellen](../../programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)
- [Geben Sie in](../modifiers/in-generic-modifier.md)
- [Vorgenommen](../modifiers/out-generic-modifier.md)
