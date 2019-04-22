---
title: Property-Anweisung (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
helpviewer_keywords:
- Property statement [Visual Basic]
- default modifier
- property procedures [Visual Basic], Property statements
- Property keyword [Visual Basic]
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
ms.openlocfilehash: 7b2d388cbcd1995178adf4102520ecaa1c9b1889
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58814188"
---
# <a name="property-statement"></a>Property Statement
Deklariert den Namen einer Eigenschaft sowie die Eigenschaftenprozeduren zum Speichern und Abrufen des Werts der Eigenschaft verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ] [ Iterator ]  
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
    [ <attributelist> ] [ accessmodifier ] Get  
        [ statements ]  
    End Get  
    [ <attributelist> ] [ accessmodifier ] Set ( ByVal value As returntype [, parameterlist ] )  
        [ statements ]  
    End Set  
End Property  
- or -  
[ <attributelist> ] [ Default ] [ accessmodifier ]   
[ propertymodifiers ] [ Shared ] [ Shadows ] [ ReadOnly | WriteOnly ]   
Property name ( [ parameterlist ] ) [ As returntype ] [ Implements implementslist ]  
```  
  
## <a name="parts"></a>Teile  
  
-   `attributelist`  
  
     Dies ist optional. Liste der Attribute, die für diese Eigenschaft gelten oder `Get` oder `Set` Verfahren. Finden Sie unter [Liste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `Default`  
  
     Dies ist optional. Gibt an, dass diese Eigenschaft ist die Standardeigenschaft für die Klasse oder Struktur, die auf dem sie definiert ist. Standardeigenschaften können muss Parameter annehmen und festgelegt und ohne Angabe der Namen der Eigenschaft abgerufen werden. Wenn Sie die Eigenschaft als deklarieren `Default`, können keine `Private` auf die Eigenschaft oder einer der Eigenschaftenprozeduren.  
  
-   `accessmodifier`  
  
     Optional Klicken Sie auf die `Property` Anweisung und höchstens die `Get` und `Set` Anweisungen. Einer der folgenden Werte ist möglich:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    - [Protected Friend](../../language-reference/modifiers/protected-friend.md) 

    - [Private Protected](../../language-reference/modifiers/private-protected.md)
  
     Siehe [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `propertymodifiers`  
  
     Dies ist optional. Einer der folgenden Werte ist möglich:  
  
    -   [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Dies ist optional. Finden Sie unter [freigegebene](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Dies ist optional. Finden Sie unter [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `ReadOnly`  
  
     Dies ist optional. Finden Sie unter [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WriteOnly`  
  
     Dies ist optional. Finden Sie unter [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   `Iterator`  
  
     Dies ist optional. Finden Sie unter [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Erforderlich. Der Name der Eigenschaft. Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `parameterlist`  
  
     Dies ist optional. Liste der Namen lokaler Variablen darstellt, die Parameter dieser Eigenschaft, und mögliche zusätzliche Parameter, der die `Set` Verfahren. Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).  
  
-   `returntype`  
  
     Erforderlich, wenn `Option Strict` ist `On`. Der Datentyp des von dieser Eigenschaft zurückgegebenen Werts.  
  
-   `Implements`  
  
     Dies ist optional. Gibt an, dass diese Eigenschaft implementiert wird, eine oder mehrere Eigenschaften, die jeweils in einer Schnittstelle implementiert, die von dieser Eigenschaft enthaltende Klasse oder Struktur definiert. Finden Sie unter [Anweisung implementiert](../../../visual-basic/language-reference/statements/implements-statement.md).  
  
-   `implementslist`  
  
     Erforderlich, wenn `Implements` angegeben wird. Liste der Eigenschaften, die implementiert wird.  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     Jede `implementedproperty` weist folgende Syntax und Bestandteile auf:  
  
     `interface.definedname`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`interface`|Erforderlich. Name einer Schnittstelle implementiert, die von dieser Eigenschaft der enthaltenden Klasse oder Struktur.|  
    |`definedname`|Erforderlich. Mit dem die Eigenschaft, im definiert ist Namen `interface`.|  
  
-   `Get`  
  
     Dies ist optional. Erforderlich, wenn die Eigenschaft markiert ist `WriteOnly`. Startet eine `Get` Eigenschaftenprozedur, die verwendet wird, um den Wert der Eigenschaft zurückzugeben.  
  
-   `statements`  
  
     Dies ist optional. Block von Anweisungen für die Ausführung innerhalb der `Get` oder `Set` Verfahren.  
  
-   `End Get`  
  
     Beendet die `Get` Eigenschaftenprozedur.  
  
-   `Set`  
  
     Dies ist optional. Erforderlich, wenn die Eigenschaft markiert ist `ReadOnly`. Startet eine `Set` Eigenschaftenprozedur, die zum Speichern des Werts der Eigenschaft verwendet wird.  
  
-   `End Set`  
  
     Beendet die `Set` Eigenschaftenprozedur.  
  
-   `End Property`  
  
     Beendet die Definition dieser Eigenschaft.  
  
## <a name="remarks"></a>Hinweise  
 Die `Property` -Anweisung führt die Deklaration einer Eigenschaft. Eine Eigenschaft haben eine `Get` Verfahren (schreibgeschützt), eine `Set` Prozedur (lesegeschützt) oder beide (Lese-/ Schreibzugriff). Können Sie weglassen der `Get` und `Set` Verfahren, wenn Sie eine automatisch implementierte Eigenschaft zu verwenden. Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
 Sie können `Property` nur auf Klassenebene. Dies bedeutet, dass die *Deklarationskontext* für eine Eigenschaft eine Klasse, Struktur, Modul oder Schnittstelle sein muss und darf nicht, eine Quelldatei, Namespace, Prozedur oder Block sein. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Standardmäßig verwenden Eigenschaften öffentlicher Zugriff. Sie können die Zugriffsebene für eine Eigenschaft mit einem Zugriffsmodifizierer anpassen, auf die `Property` -Anweisung, und Sie können optional anpassen, einer der Eigenschaftenprozeduren zu einer stärker einschränkende Zugriffsebene.  
  
 Visual Basic übergibt einen Parameter für die `Set` Prozedur während der eigenschaftenzuweisungen. Wenn Sie keine Parameter für angeben `Set`, die integrierte Entwicklungsumgebung (IDE) verwendet einen impliziten Parameter mit dem Namen `value`. Dieser Parameter enthält den Wert der Eigenschaft zugewiesen werden soll. In der Regel diesen Wert in einer privaten lokalen Variable speichern und zurückgeben immer die `Get` Prozedur aufgerufen wird.  
  
## <a name="rules"></a>Regeln  
  
-   **Gemischte Zugriffsebenen.** Wenn Sie eine Eigenschaft mit Lese-/ Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene angeben, entweder die `Get` oder `Set` Prozedur, aber nicht beides. Wenn Sie dies tun, muss die Zugriffsebene der Prozedur restriktiver ist als die Zugriffsebene der Eigenschaft. Z. B., wenn die Eigenschaft deklariert ist `Friend`, Sie können deklarieren, die `Set` Prozedur `Private`, aber nicht `Public`.  
  
     Wenn Sie definieren eine `ReadOnly` oder `WriteOnly` -Eigenschaft, die Eigenschaftenprozedur (`Get` oder `Set`bzw.) stellt alle von der Eigenschaft. Sie können nicht für eine Prozedur, eine andere Zugriffsebene deklarieren, da es sich bei, der zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
-   **Der Rückgabetyp.** Die `Property` Anweisung kann deklarieren, den den Datentyp des zurückgegebenen Werts. Sie können einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.  
  
     Wenn Sie keinen angeben `returntype`, gibt die Eigenschaft `Object`.  
  
-   **-Implementierung.** Wenn diese Eigenschaft verwendet die `Implements` -Schlüsselwort, die enthaltende Klasse oder Struktur müssen ein `Implements` Anweisung unmittelbar nach seiner `Class` oder `Structure` Anweisung. Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`. Jedoch den Namen, die mit dem eine Schnittstelle definiert die `Property` (in `definedname`) muss nicht der Name dieser Eigenschaft identisch sein (in `name`).  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zurückgeben einer Eigenschaftenprozedur.** Wenn die `Get` oder `Set` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgesetzt, mit der Anweisung nach der Anweisung, die sie aufgerufen.  
  
     Die `Exit Property` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung einer Eigenschaftenprozedur. Eine beliebige Anzahl von `Exit Property` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Property` und `Return` Anweisungen.  
  
-   **Der Rückgabewert.** Zum Zurückgeben eines Werts aus einer `Get` Verfahren, Sie können entweder weisen Sie den Wert an den Eigenschaftennamen oder nehmen Sie diese in einem `Return` Anweisung. Das folgende Beispiel weist den Rückgabewert an den Eigenschaftennamen `quoteForTheDay` und verwendet dann die `Exit Property` -Anweisung zurückgegeben.  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#28)]  
  
     Bei Verwendung von `Exit Property` ohne Zuweisen eines Werts zu `name`, `Get` Prozedur gibt den Standardwert für den Datentyp der Eigenschaft zurück.  
  
     Die `Return` Anweisung zur gleichen Zeit weist der `Get` Prozedur zurückgeben, Wert und Beenden der Prozedur. Das folgende Beispiel zeigt dies.  
  
     [!code-vb[VbVbalrStatements#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#27)]  
  
     [!code-vb[VbVbalrStatements#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#29)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine Eigenschaft in einer Klasse.  
  
 [!code-vb[VbVbalrStatements#51](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#51)]  
  
## <a name="see-also"></a>Siehe auch

- [Automatisch implementierte Eigenschaften](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)
- [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)
- [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md)
- [Default](../../../visual-basic/language-reference/modifiers/default.md)
