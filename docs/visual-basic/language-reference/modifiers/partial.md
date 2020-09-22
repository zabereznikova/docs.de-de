---
title: Partial
ms.date: 07/20/2015
f1_keywords:
- vb.Partial
- partial
helpviewer_keywords:
- structures [Visual Basic], partial
- classes [Visual Basic]
- partial, types [Visual Basic]
- partial, structures
- partial, classes [Visual Basic]
- classes [Visual Basic], partial
- Partial keyword [Visual Basic]
- type promotion
ms.assetid: 7adaef80-f435-46e1-970a-269fff63b448
ms.openlocfilehash: 2482facadd0e0528ed1b71df6edb4a447947a902
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90867780"
---
# <a name="partial-visual-basic"></a>Partial (Visual Basic)

Gibt an, dass eine Typdeklaration eine partielle Definition des Typs ist.  
  
 Mit dem `Partial`-Schlüsselwort können Sie die Typdefinition auf mehrere Deklarationen aufteilen. Sie können beliebig viele partielle Deklarationen in beliebig vielen verschiedenen Quelldateien verwenden. Alle Deklarationen müssen jedoch in der gleichen Assembly und dem gleichen Namespace enthalten sein.  
  
> [!NOTE]
> Visual Basic unterstützt *partielle Methoden*, die in der Regel in partiellen Klassen implementiert werden. Weitere Informationen finden Sie unter [partielle Methoden](../../programming-guide/language-features/procedures/partial-methods.md) und [unter Anweisung](../statements/sub-statement.md).  
  
## <a name="syntax"></a>Syntax  
  
```vb  
[ <attrlist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] _  
Partial { Class | Structure | Interface | Module } name [ (Of typelist) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ variabledeclarations ]  
    [ proceduredeclarations ]  
{ End Class | End Structure }  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`attrlist`|Dies ist optional. Liste der Attribute, die für diesen Typ gelten. Sie müssen die [Attribut Liste](../statements/attribute-list.md) in Spitze Klammern () einschließen `< >` .|  
|`accessmodifier`|Dies ist optional. Gibt an, welcher Code auf diesen Typ zugreifen kann. Siehe [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Dies ist optional. Siehe [Shadows](shadows.md).|  
|`MustInherit`|Dies ist optional. Siehe [MustInherit](mustinherit.md).|  
|`NotInheritable`|Dies ist optional. Siehe [notvererbt able](notinheritable.md).|  
|`name`|Erforderlich. Der Name dieses Typs. Muss mit dem Namen übereinstimmen, der in allen anderen partiellen Deklarationen desselben Typs definiert ist.|  
|`Of`|Dies ist optional. Gibt an, dass dies ein generischer Typ ist. Weitere Informationen finden Sie [unter generische Typen in Visual Basic](../../programming-guide/language-features/data-types/generic-types.md).|  
|`typelist`|Erforderlich, wenn Sie [verwenden.](../statements/of-clause.md) Siehe [Typliste](../statements/type-list.md).|  
|`Inherits`|Dies ist optional. Siehe [erbt-Anweisung](../statements/inherits-statement.md).|  
|`classname`|Erforderlich, wenn Sie `Inherits` verwenden. Der Name der Klasse oder Schnittstelle, von der diese Klasse abgeleitet wird.|  
|`Implements`|Dies ist optional. Siehe [implementierende Anweisung](../statements/implements-statement.md).|  
|`interfacenames`|Erforderlich, wenn Sie `Implements` verwenden. Die Namen der von diesem Typ implementierten Schnittstellen.|  
|`variabledeclarations`|Dies ist optional. Anweisungen, die zusätzliche Variablen und Ereignisse für den Typ definieren.|  
|`proceduredeclarations`|Dies ist optional. Anweisungen, die zusätzliche Prozeduren für den Typ deklarieren und definieren.|  
|`End Class` oder `End Structure`|Beendet diese partielle `Class`- oder `Structure`-Definition.|  
  
## <a name="remarks"></a>Bemerkungen  

 Visual Basic verwendet partielle Klassendefinitionen, um in jeweils eigenen Quelldateien generierten Code von Code zu trennen, der vom Benutzer erstellt wurde. Zum Beispiel definiert der **Windows Form-Designer** partielle Klassen für Steuerelemente, z.B. <xref:System.Windows.Forms.Form>. Sie sollten den generierten Code in diesen Steuerelementen nicht ändern.  
  
 Beim Erstellen eines partiellen Typs gelten alle Regeln für die Erstellung von Klassen, Strukturen, Schnittstellen und Modulen, beispielsweise diejenigen für die Verwendung und Vererbung von Modifizierern.  
  
## <a name="best-practices"></a>Empfehlungen  
  
- Normalerweise wird die Entwicklung eines einzelnen Typs nicht auf zwei oder mehr Deklarationen aufgeteilt. In der Regel benötigen Sie das `Partial`-Schlüsselwort daher nicht.  
  
- Zur besseren Lesbarkeit sollte jede partielle Deklaration eines Typs das `Partial`-Schlüsselwort enthalten. Der Compiler gestattet den Wegfall des Schlüsselworts nur bei höchstens einer partiellen Deklaration. Fällt es bei mehr als einer Deklaration weg, tritt ein Fehler auf.  
  
## <a name="behavior"></a>Verhalten  
  
- **Union von Deklarationen** Der Compiler behandelt den Typ als die Union all seiner partiellen Deklarationen. Jeder Modifizierer aus jeder partiellen Definition wird auf den gesamten Typ angewendet, und jeder Member aus jeder partiellen Definition steht dem gesamten Typ zur Verfügung.  
  
- **Typerweiterung nicht zulässig für partielle Typen in Modulen.** Wenn eine partielle Definition in einem Modul enthalten ist, ist automatisch keine Typerweiterung für diesen Typ möglich. In einem solchen Fall kann eine Reihe partieller Definitionen zu unerwarteten Ergebnissen und sogar zu Compilerfehlern führen. Weitere Informationen finden Sie unter [Typerweiterung](../../programming-guide/language-features/declared-elements/type-promotion.md).  
  
     Der Compiler führt partielle Definitionen nur zusammen, wenn ihre voll qualifizierten Pfade identisch sind.  
  
 Das `Partial`-Schlüsselwort kann in den folgenden Kontexten verwendet werden:  
  
 [Class-Anweisung](../statements/class-statement.md)  
  
 [Structure Statement](../statements/structure-statement.md)  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird die Definition der `sampleClass`-Klasse auf zwei Deklarationen aufgeteilt, die jeweils eine andere `Sub`-Prozedur definieren.  
  
 [!code-vb[VbVbalrKeywords#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#3)]  
  
 Die beiden partiellen Definitionen aus dem vorhergehenden Beispiel können in derselben Quelldatei oder in zwei unterschiedlichen Quelldateien enthalten sein.  
  
## <a name="see-also"></a>Weitere Informationen

- [Class-Anweisung](../statements/class-statement.md)
- [Structure Statement](../statements/structure-statement.md)
- [Typerweiterung](../../programming-guide/language-features/declared-elements/type-promotion.md)
- [Shadows](shadows.md)
- [Generische Typen in Visual Basic (Visual Basic)](../../programming-guide/language-features/data-types/generic-types.md)
- [Partielle Methoden](../../programming-guide/language-features/procedures/partial-methods.md)
