---
title: Property Statement
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
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
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 558b62dd8c676532355ef12134ad8cb803b70796
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="property-statement"></a>Property Statement
Deklariert den Namen einer Eigenschaft und den Eigenschaftenprozeduren, die zum Speichern und Abrufen des Werts der Eigenschaft.  
  
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
  
     Dies ist optional. Liste der Attribute, die für diese Eigenschaft gelten oder `Get` oder `Set` Prozedur. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `Default`  
  
     Dies ist optional. Gibt an, dass diese Eigenschaft ist die Standardeigenschaft für die Klasse oder Struktur, die auf dem sie definiert ist. Standardeigenschaften können müssen Parameter annehmen und festgelegt und ohne den Namen der Eigenschaft abgerufen werden. Wenn Sie die Eigenschaft als deklarieren `Default`, können keine `Private` auf die Eigenschaft oder eine der Eigenschaftenprozeduren.  
  
-   `accessmodifier`  
  
     Optional Klicken Sie auf die `Property` Anweisung und höchstens eines der `Get` und `Set` Anweisungen. Einer der folgenden Werte ist möglich:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
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
  
     Dies ist optional. Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `ReadOnly`  
  
     Dies ist optional. Finden Sie unter [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WriteOnly`  
  
     Dies ist optional. Finden Sie unter [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   `Iterator`  
  
     Dies ist optional. Finden Sie unter [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Erforderlich. Der Name der Eigenschaft. Finden Sie unter [deklarierte Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `parameterlist`  
  
     Dies ist optional. Liste der Namen lokaler Variablen darstellt, die Parameter dieser Eigenschaft und mögliche zusätzliche Parameter der `Set` Prozedur. Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).  
  
-   `returntype`  
  
     Erforderlich, wenn `Option``Strict` ist `On`. Der Datentyp der von dieser Eigenschaft zurückgegebene Wert.  
  
-   `Implements`  
  
     Dies ist optional. Gibt an, dass diese Eigenschaft implementiert wird, eine oder mehrere Eigenschaften, die jeweils in einer Schnittstelle implementiert, die durch diese Eigenschaft enthaltende Klasse oder Struktur definiert. Finden Sie unter [Anweisung implementiert](../../../visual-basic/language-reference/statements/implements-statement.md).  
  
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
  
     Dies ist optional. Erforderlich, wenn die Eigenschaft gekennzeichnet ist `WriteOnly`. Startet eine `Get` Eigenschaftenprozedur, der verwendet wird, um den Wert der Eigenschaft zurückzugeben.  
  
-   `statements`  
  
     Dies ist optional. Block von Anweisungen für die Ausführung innerhalb der `Get` oder `Set` Prozedur.  
  
-   `End Get`  
  
     Beendet die `Get` -Eigenschaftenprozedur.  
  
-   `Set`  
  
     Dies ist optional. Erforderlich, wenn die Eigenschaft gekennzeichnet ist `ReadOnly`. Startet eine `Set` Eigenschaftenprozedur, die zum Speichern des Werts der Eigenschaft verwendet wird.  
  
-   `End Set`  
  
     Beendet die `Set` -Eigenschaftenprozedur.  
  
-   `End Property`  
  
     Beendet die Definition dieser Eigenschaft.  
  
## <a name="remarks"></a>Hinweise  
 Die `Property` -Anweisung führt die Deklaration einer Eigenschaft. Eine Eigenschaft aufweisen kann eine `Get` Prozedur (schreibgeschützt), eine `Set` Prozedur (lesegeschützt) oder beide (Lese-/ Schreibzugriff). Sie lassen die `Get` und `Set` Verfahren, wenn Sie eine automatisch implementierte Eigenschaft verwenden. Weitere Informationen finden Sie unter [Automatisch implementierte Eigenschaften](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
 Sie können `Property` nur auf Klassenebene. Dies bedeutet, dass die *Deklarationskontext* für eine Eigenschaft muss eine Klasse, Struktur, Modul oder Schnittstelle, und nicht mit einer Quelldatei, Namespace, Prozedur oder Block. Weitere Informationen finden Sie unter [Deklarationskontexte und Standardzugriffsebenen](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Standardmäßig verwenden Eigenschaften öffentlicher Zugriff. Sie können die Zugriffsebene für eine Eigenschaft mit einem Zugriffsmodifizierer anpassen, auf die `Property` -Anweisung, und Sie können optional auch anpassen, eine der Eigenschaftenprozeduren auf eine restriktivere Zugriffsebene.  
  
 Visual Basic übergibt die Parameter für die `Set` Prozedur während der eigenschaftenzuweisungen. Wenn Sie keine Parameter für angeben `Set`, der integrierten Entwicklungsumgebung (IDE) verwendet einen impliziten Parameter mit dem Namen `value`. Dieser Parameter enthält den Wert der Eigenschaft zugewiesen werden soll. In der Regel speichern den Wert in einer privaten lokalen Variable und gibt es immer die `Get` Prozedur aufgerufen wird.  
  
## <a name="rules"></a>Regeln  
  
-   **Gemischte Zugriffsebenen.** Wenn Sie eine Eigenschaft mit Lese-/ Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene angeben, entweder die `Get` oder `Set` Prozedur, aber nicht beides. Wenn in diesem Fall muss die Zugriffsebene der Prozedur restriktiver ist als die Zugriffsebene der Eigenschaft. Z. B., wenn die Eigenschaft deklariert wird `Friend`, Sie können deklarieren, die `Set` Prozedur `Private`, aber nicht `Public`.  
  
     Wenn Sie definieren eine `ReadOnly` oder `WriteOnly` -Eigenschaft, die einzelne Eigenschaftenprozedur (`Get` oder `Set`bzw.) stellt alle von der Eigenschaft. Eine andere Zugriffsebene für eine solche Prozedur nicht deklariert werden, da hierdurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
-   **Der Rückgabetyp.** Die `Property` -Anweisung kann den Datentyp des zurückgegebenen Werts deklarieren. Sie können einen beliebigen Datentyp aufweisen oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.  
  
     Wenn Sie keinen angeben `returntype`, gibt die Eigenschaft `Object`.  
  
-   **-Implementierung.** Wenn diese Eigenschaft verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur benötigen eine `Implements` Anweisung unmittelbar nach seiner `Class` oder `Structure` Anweisung. Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`. Jedoch den Namen, die mit dem eine Schnittstelle definiert die `Property` (in `definedname`) muss nicht in den Namen dieser Eigenschaft entsprechen (im `name`).  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zurückgeben aus einer Eigenschaftenprozedur.** Wenn die `Get` oder `Set` Prozedur werden an den aufrufenden Code zurückgibt, die Ausführung wird fortgeführt, mit der Anweisung nach der Anweisung, die sie aufgerufen hat.  
  
     Die `Exit Property` und `Return` Anweisungen bewirken, dass eine sofortige Beendigung einer Eigenschaftenprozedur. Eine beliebige Anzahl von `Exit Property` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie können kombinieren `Exit Property` und `Return` Anweisungen.  
  
-   **Der Rückgabewert.** Zurückzugebenden einen Wert aus einer `Get` Prozedur, Sie können entweder weisen den Namen der Eigenschaft den Wert oder fügen Sie ihn in eine `Return` Anweisung. Im folgende Beispiel weist den Rückgabewert des Eigenschaftennamens `quoteForTheDay` und verwendet dann die `Exit Property` -Anweisung zurückgegeben.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#28](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     Bei Verwendung von `Exit Property` ohne Zuweisen eines Werts zur `name`die `Get` Prozedur gibt den Standardwert für den Datentyp der Eigenschaft zurück.  
  
     Die `Return` Anweisung zur gleichen Zeit weist der `Get` Prozedur zurückgeben, Wert und Beenden der Prozedur. Das folgende Beispiel zeigt dies.  
  
     [!code-vb[VbVbalrStatements#27](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements#29](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel deklariert eine Eigenschaft in einer Klasse.  
  
 [!code-vb[VbVbalrStatements#51](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Automatisch implementierte Eigenschaften](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)  
 [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)  
 [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md)  
 [Default](../../../visual-basic/language-reference/modifiers/default.md)
