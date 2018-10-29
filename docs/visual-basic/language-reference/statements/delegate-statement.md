---
title: Delegate-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Delegate
helpviewer_keywords:
- delegate keyword [Visual Basic]
- Delegate statement [Visual Basic]
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
ms.openlocfilehash: 4718c0a6e332d644a7f54c79246df95f841058d0
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2018
ms.locfileid: "50199772"
---
# <a name="delegate-statement"></a>Delegate-Anweisung
Wird verwendet, um einen Delegaten zu deklarieren. Ein Delegat ist ein Verweistyp, der auf verweist eine `Shared` -Methode eines Typs oder um eine Instanzmethode eines Objekts. Jede Prozedur mit passenden Parameter und Rückgabetypen kann verwendet werden, um eine Instanz dieser Delegatklasse erstellen. Die Prozedur kann anschließend über die Delegatinstanz aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`attrlist`|Dies ist optional. Liste der Attribute, die für diesen Delegaten gelten. Mehrere Attribute werden durch Kommas getrennt. Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").|  
|`accessmodifier`|Dies ist optional. Gibt an, welcher Code auf den Delegaten zugreifen kann. Einer der folgenden Werte ist möglich:<br /><br /> - [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md). Jeglicher Code, der das Element zugreifen kann, das der Delegat deklariert kann darauf zugreifen.<br />-   [Geschützte](../../../visual-basic/language-reference/modifiers/protected.md). Nur Code innerhalb der Klasse des Delegaten oder eine abgeleitete Klasse kann darauf zugreifen.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md). Nur Code innerhalb der gleichen Assembly kann es sich um den Delegaten zugreifen.<br />- [Private](../../../visual-basic/language-reference/modifiers/private.md). Nur Code innerhalb des Elements, das der Delegat deklariert kann darauf zugreifen.<br /><br /> - [Protected Friend](../../language-reference/modifiers/protected-friend.md) nur Code innerhalb der Klasse des Delegaten, einer abgeleiteten Klasse oder derselben Assembly auf den Delegaten zugreifen kann. <br />- [Private Protected](../../language-reference/modifiers/private-protected.md) nur Code innerhalb der Klasse des Delegaten oder in einer abgeleiteten Klasse in der gleichen Assembly der Delegat zugreifen kann. |  
|`Shadows`|Dies ist optional. Gibt an, dass dieser Delegat wird ausgeblendet, ein identisch benanntes Programmierelement oder einen Satz überladener Elemente in einer Basisklasse erneut deklariert. Sie können ein Shadowing von jedem deklarierten Element mit einer anderen Art vornehmen.<br /><br /> Ein schattiertes Element steht in der abgeleiteten Klasse, die es spiegelt, nicht zur Verfügung, und zwar mit Ausnahme von dem Punkt, wo nicht auf das Shadowing-Element zugriffen werden kann. Z. B. wenn ein `Private` Element führt Shadowing für eine Basisklasse-Element, Code, der keine Berechtigung zum Zugriff auf die `Private` Element greift stattdessen auf das Basisklasse-Element.|  
|`Sub`|Optional, doch entweder `Sub` oder `Function` muss angezeigt werden. Diese Prozedur als Delegat deklariert `Sub` Prozedur, die keinen Wert zurückgibt.|  
|`Function`|Optional, doch entweder `Sub` oder `Function` muss angezeigt werden. Diese Prozedur als Delegat deklariert `Function` Prozedur, die einen Wert zurückgibt.|  
|`name`|Erforderlich. Der Name des Delegattyps; folgt standardmäßige variablennamenskonventionen.|  
|`typeparamlist`|Dies ist optional. Liste der Typparameter für diesen Delegaten. Es sind mehrere Typparameter durch Kommas getrennt. Optional, jeden von Typparameter kann deklariert werden Variante mit `In` und `Out` generische Modifizierer. Muss die [Typliste](../../../visual-basic/language-reference/statements/type-list.md) in Klammern, und stellen sie vor der `Of` Schlüsselwort.|  
|`parameterlist`|Dies ist optional. Liste von Parametern, die an die Prozedur übergeben werden, wenn sie aufgerufen wird. Setzen Sie die [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md) in Klammern angegeben.|  
|`type`|Erforderlich, wenn Sie angeben, ein `Function` Verfahren. Der Datentyp des Rückgabewerts.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Delegate` -Anweisung definiert die Typen für Parameter und Rückgabetypen einer Delegatklasse. Jede Prozedur mit passenden Parametern und Rückgabetypen kann verwendet werden, um eine Instanz dieser Delegatklasse erstellen. Die Prozedur kann dann später aufgerufen werden über die Delegatinstanz durch Aufrufen des Delegaten `Invoke` Methode.  
  
 Delegaten können an den Namespace, Modul, Klasse oder Struktur auf, aber nicht innerhalb einer Prozedur deklariert werden.  
  
 Jede Delegatklasse definiert einen Konstruktor, dem die Spezifikation einer Objektmethode übergeben wird. Ein Argument für einen Delegatkonstruktor muss ein Verweis auf eine Methode oder ein Lambda-Ausdruck sein.  
  
 Verwenden Sie die folgende Syntax, um einen Verweis auf eine Methode festzulegen:  
  
 `AddressOf` [`expression`.]`methodname`  
  
 Der Typ von `expression` muss zur Kompilierungszeit der Name einer Klasse oder Schnittstelle sein, die eine Methode des angegebenen Namens enthält, deren Signatur mit der Signatur der Delegatklasse übereinstimmt. Bei `methodname` kann es sich um eine freigegebene Methode oder um eine Instanzmethode handeln. Der `methodname` ist nicht optional, selbst dann nicht, wenn Sie einen Delegaten für die Standardmethode der Klasse erstellen.  
  
 Verwenden Sie die folgende Syntax, um einen Lambda-Ausdruck festzulegen:  
  
 `Function` ([`parm` As `type`, `parm2` As `type2`, ...]) `expression`  
  
 Die Signatur der Funktion muss mit der des Delegattyps übereinstimmen. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Weitere Informationen zu Delegaten finden Sie unter [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Delegate` Anweisung, um einen Delegaten zu deklarieren, für das Arbeiten mit zwei Zahlen und eine Zahl zurückgegeben. Die `DelegateTest` -Methode akzeptiert eine Instanz eines Delegaten dieses Typs und wird verwendet, um Sie für Paare von Zahlen verwendet werden.  
  
 [!code-vb[VbVbalrDelegates#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)  
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)  
 [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)  
 [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)  
 [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Kovarianz und Kontravarianz](../../programming-guide/concepts/covariance-contravariance/index.md)  
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)  
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
