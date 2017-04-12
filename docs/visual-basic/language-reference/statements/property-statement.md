---
title: Property-Anweisung | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.PropertySet
- vb.Property
- vb.PropertyGet
dev_langs:
- VB
helpviewer_keywords:
- Property statement
- default modifier
- property procedures, Property statements
- Property keyword
ms.assetid: 3155edaf-8ebd-45c6-9cef-11d5d2dc8d38
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 87cb32c12ab3238508a6a4bb114306909e409dda
ms.lasthandoff: 03/13/2017

---
# <a name="property-statement"></a>Property Statement
Deklariert den Namen einer Eigenschaft sowie die Eigenschaftenprozeduren zum Speichern und Abrufen des Werts der Eigenschaft.  
  
## <a name="syntax"></a>Syntax  
  
```  
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
  
     Optional. Liste der Attribute, die für diese Eigenschaft gelten oder `Get` oder `Set` Verfahren. Finden Sie unter [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
-   `Default`  
  
     Optional. Gibt an, dass diese Eigenschaft ist die Standardeigenschaft für die Klasse oder Struktur, in der sie definiert ist. Standardeigenschaften können müssen Parameter akzeptieren und festgelegt und ohne den Eigenschaftsnamen abgerufen werden. Wenn Sie die Eigenschaft als deklarieren `Default`, können keine `Private` für die Eigenschaft noch für eine ihrer Eigenschaftenprozeduren.  
  
-   `accessmodifier`  
  
     Optional Klicken Sie auf die `Property` -Anweisung und für höchstens eine der der `Get` und `Set` Anweisungen. Einer der folgenden Werte ist möglich:  
  
    -   [Public](../../../visual-basic/language-reference/modifiers/public.md)  
  
    -   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
    -   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
    -   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
    -   `Protected Friend`  
  
     Finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
-   `propertymodifiers`  
  
     Optional. Einer der folgenden Werte ist möglich:  
  
    -   [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)  
  
    -   [Overrides](../../../visual-basic/language-reference/modifiers/overrides.md)  
  
    -   [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)  
  
    -   [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)  
  
    -   [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)  
  
    -   `MustOverride Overrides`  
  
    -   `NotOverridable Overrides`  
  
-   `Shared`  
  
     Optional. Finden Sie unter [freigegebenen](../../../visual-basic/language-reference/modifiers/shared.md).  
  
-   `Shadows`  
  
     Optional. Finden Sie unter [Schatten](../../../visual-basic/language-reference/modifiers/shadows.md).  
  
-   `ReadOnly`  
  
     Optional. Finden Sie unter [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
-   `WriteOnly`  
  
     Optional. Finden Sie unter [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   `Iterator`  
  
     Optional. Finden Sie unter [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
-   `name`  
  
     Erforderlich. Der Name der Eigenschaft. Finden Sie unter [deklarierten Elementnamen](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
-   `parameterlist`  
  
     Optional. Liste der Namen lokaler Variablen, die die Parameter dieser Eigenschaft und mögliche zusätzliche Parameter der darstellen der `Set` Verfahren. Finden Sie unter [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md).  
  
-   `returntype`  
  
     Erforderlich, wenn `Option``Strict` ist `On`. Der Datentyp des von dieser Eigenschaft zurückgegebenen Werts.  
  
-   `Implements`  
  
     Optional. Gibt an, dass diese Eigenschaft implementiert eine oder mehrere Eigenschaften, die jeweils in einer Schnittstelle implementiert, die von dieser Eigenschaft enthaltenden Klasse oder Struktur definiert. Finden Sie unter [Anweisung implementiert](../../../visual-basic/language-reference/statements/implements-statement.md).  
  
-   `implementslist`  
  
     Erforderlich, wenn `Implements` angegeben wird. Liste der implementierten Eigenschaften.  
  
     `implementedproperty [ , implementedproperty ... ]`  
  
     Jede `implementedproperty` weist folgende Syntax und Bestandteile auf:  
  
     `interface.definedname`  
  
    |Segment|Beschreibung|  
    |---|---|  
    |`interface`|Erforderlich. Name der Schnittstelle implementiert, die von dieser Eigenschaft der enthaltenden Klasse oder Struktur.|  
    |`definedname`|Erforderlich. Name, mit dem die Eigenschaft, in definiert ist `interface`.|  
  
-   `Get`  
  
     Optional. Erforderlich, wenn die Eigenschaft markiert ist `WriteOnly`. Startet eine `Get` Property-Prozedur, die verwendet wird, um den Wert der Eigenschaft zurückzugeben.  
  
-   `statements`  
  
     Optional. Block von Anweisungen für die Ausführung innerhalb der `Get` oder `Set` Verfahren.  
  
-   `End Get`  
  
     Beendet die `Get` Property-Prozeduren.  
  
-   `Set`  
  
     Optional. Erforderlich, wenn die Eigenschaft markiert ist `ReadOnly`. Startet eine `Set` Property-Prozedur, die zum Speichern des Werts der Eigenschaft verwendet wird.  
  
-   `End Set`  
  
     Beendet die `Set` Property-Prozeduren.  
  
-   `End Property`  
  
     Beendet die Definition dieser Eigenschaft.  
  
## <a name="remarks"></a>Hinweise  
 Die `Property` -Anweisung führt die Deklaration einer Eigenschaft. Eine Eigenschaft haben eine `Get` Verfahren (schreibgeschützt), eine `Set` -Prozedur (lesegeschützt) oder beide (Lese-/ Schreibzugriff). Sie lassen die `Get` und `Set` Verfahren, wenn Sie eine automatisch implementierte Eigenschaft verwenden. Weitere Informationen finden Sie unter [automatisch implementierte Eigenschaften](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md).  
  
 Sie können `Property` nur auf Klassenebene. Dies bedeutet, dass die *Deklarationskontext* für eine Eigenschaft eine Klasse, Struktur, Modul oder Schnittstelle sein muss und darf keine Quelldatei, Namespace, Prozedur oder Block. Weitere Informationen finden Sie unter [Deklarationskontexte und Zugriffsebenen standardmäßig](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Standardmäßig verwenden die Eigenschaften öffentlicher Zugriff. Sie können die Zugriffsebene einer Eigenschaft mit einem Zugriffsmodifizierer anpassen, auf die `Property` -Anweisung, und Sie können optional auch anpassen, eine ihrer Eigenschaftenprozeduren auf eine restriktivere Zugriffsebene festlegen.  
  
 Visual Basic übergibt einen Parameter an die `Set` Prozedur während der Eigenschaften. Wenn Sie keine Parameter für bieten `Set`, die integrierte Entwicklungsumgebung (IDE) verwendet einen impliziten Parameter mit dem Namen `value`. Dieser Parameter enthält den Wert der Eigenschaft zugewiesen werden. In der Regel speichern Sie diesen Wert in einer privaten lokalen Variablen und gibt es immer die `Get` Prozedur aufgerufen wird.  
  
## <a name="rules"></a>Regeln  
  
-   **Gemischte Zugriffsebenen.** Wenn Sie eine Eigenschaft mit Lese-/ Schreibzugriff definieren, können Sie optional eine andere Zugriffsebene angeben, entweder für die `Get` oder `Set` Verfahren, aber nicht beide. Wenn Sie dies tun, muss die Zugriffsebene der Prozedur restriktiver als die Zugriffsebene der Eigenschaft sein. Beispielsweise, wenn die Eigenschaft deklariert wird `Friend`, können Sie deklarieren die `Set` Prozedur `Private`, aber nicht `Public`.  
  
     Definieren einer `ReadOnly` oder `WriteOnly` -Eigenschaft, die Eigenschaftenprozedur (`Get` oder `Set`bzw.) alle der Eigenschaft darstellt. Sie können nicht für eine Prozedur, eine andere Zugriffsebene deklarieren, da hierdurch zwei Zugriffsebenen für die Eigenschaft festgelegt werden.  
  
-   **Der Rückgabetyp.** Die `Property` -Anweisung kann den Datentyp des zurückgegebenen Werts deklarieren. Sie können einen beliebigen Datentyp oder den Namen einer Enumeration, Struktur, Klasse oder Schnittstelle angeben.  
  
     Wenn Sie keinen angeben `returntype`, gibt die Eigenschaft `Object`.  
  
-   **-Implementierung.** Wenn diese Eigenschaft verwendet die `Implements` -Schlüsselwort, der enthaltenden Klasse oder Struktur benötigen eine `Implements` -Anweisung unmittelbar nach seiner `Class` oder `Structure` Anweisung. Die `Implements` -Anweisung muss jede Schnittstelle, die im angegebenen enthalten `implementslist`. Allerdings den Namen, mit dem eine Schnittstelle definiert, die `Property` (in `definedname`) muss nicht identisch mit dem Namen dieser Eigenschaft werden (in `name`).  
  
## <a name="behavior"></a>Verhalten  
  
-   **Zurückgeben einer Eigenschaftenprozedur.** Wenn die `Get` oder `Set` -Prozedur zum aufrufenden Code zurückkehrt, die Ausführung wird fortgesetzt, mit der Anweisung nach der Anweisung, die sie aufgerufen.  
  
     Die `Exit Property` und `Return` -Anweisung führen zur unmittelbare Beendigung einer Eigenschaftenprozedur. Eine beliebige Anzahl von `Exit Property` und `Return` Anweisungen können an beliebiger Stelle in der Prozedur, und Sie kombinieren können `Exit Property` und `Return` Anweisungen.  
  
-   **Der Rückgabewert.** Zum Zurückgeben eines Werts aus einer `Get` Verfahren, Sie können entweder den Wert der Eigenschaftenname zuweisen oder ihn in eine `Return` Anweisung. Das folgende Beispiel weist den Rückgabewert dem Eigenschaftennamen `quoteForTheDay` und verwendet dann die `Exit Property` -Anweisung zurückgegeben.  
  
     [!code-vb[VbVbalrStatements&#27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements&#28;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_2.vb)]  
  
     Bei Verwendung von `Exit Property` ohne Zuweisen eines Werts zur `name`der `Get` Prozedur gibt den Standardwert für den Datentyp der Eigenschaft zurück.  
  
     Die `Return` Anweisung zur gleichen Zeit weist der `Get` Prozedur zurück und beendet die Prozedur. Das folgende Beispiel zeigt dies.  
  
     [!code-vb[VbVbalrStatements&#27;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_1.vb)]  
  
     [!code-vb[VbVbalrStatements&#29;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_3.vb)]  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine Eigenschaft in einer Klasse deklariert.  
  
 [!code-vb[VbVbalrStatements&51;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/property-statement_4.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Automatisch implementierte Eigenschaften](../../../visual-basic/programming-guide/language-features/procedures/auto-implemented-properties.md)   
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Get-Anweisung](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Set-Anweisung](../../../visual-basic/language-reference/statements/set-statement.md)   
 [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md)   
 [Default](../../../visual-basic/language-reference/modifiers/default.md)
