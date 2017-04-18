---
title: Delegate-Anweisung | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Delegate
dev_langs:
- VB
helpviewer_keywords:
- delegate keyword
- Delegate statement
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
caps.latest.revision: 27
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
ms.openlocfilehash: 9ac9e28c82f8a6b5a9c1398961d831c956a649e0
ms.lasthandoff: 03/13/2017

---
# <a name="delegate-statement"></a>Delegate-Anweisung
Deklarieren einen Delegaten verwendet. Ein Delegat ist ein Verweistyp, der sich auf eine `Shared` -Methode eines Typs oder auf eine Instanzenmethode eines Objekts. Jede Prozedur mit identischen Parameter-und Rückgabetypen kann zum Erstellen einer Instanz dieser Delegatklasse verwendet werden. Die Prozedur kann anschließend über die Delegatinstanz aufgerufen werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`attrlist`|Optional. Liste der Attribute, die für diesen Delegaten zutreffen. Mehrere Attribute werden durch Kommas getrennt. Setzen Sie die [Attributliste](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern ("`<`"und"`>`").|  
|`accessmodifier`|Optional. Gibt an, welcher Code auf den Delegaten zugreifen kann. Einer der folgenden Werte ist möglich:<br /><br /> -   [Öffentliche](../../../visual-basic/language-reference/modifiers/public.md). Jeglicher Code, der das Element zugreifen kann, das den Delegaten deklariert, kann darauf zugreifen.<br />-   [Geschützte](../../../visual-basic/language-reference/modifiers/protected.md). Nur Code innerhalb der Klasse des Delegaten oder eine abgeleitete Klasse kann darauf zugreifen.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md). Nur Code innerhalb der gleichen Assembly kann auf den Delegaten zugreifen.<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md). Nur Code innerhalb des Elements, das den Delegaten deklariert, kann darauf zugreifen.<br /><br /> Sie können angeben, `Protected Friend` Zugriff von Code innerhalb der Klasse des Delegaten, einer abgeleiteten Klasse oder der gleichen Assembly zu aktivieren.|  
|`Shadows`|Optional. Gibt an, dass dieser Delegat erneut deklariert und ein Programmierelement mit derselben Bezeichnung oder eine Gruppe überladener Elemente in einer Basisklasse ausgeblendet. Sie können ein Shadowing von jedem deklarierten Element mit einer anderen Art vornehmen.<br /><br /> Ein schattiertes Element steht in der abgeleiteten Klasse, die es spiegelt, nicht zur Verfügung, und zwar mit Ausnahme von dem Punkt, wo nicht auf das Shadowing-Element zugriffen werden kann. Z. B. wenn ein `Private` überschattet Element eine Basisklasse, Code, der keine Berechtigung zum Zugriff auf die `Private` Element Element der Basisklasse stattdessen zugreift.|  
|`Sub`|Optional, doch entweder `Sub` oder `Function` muss angezeigt werden. Deklariert diese Prozedur als Delegat `Sub` Prozedur, die keinen Wert zurückgibt.|  
|`Function`|Optional, doch entweder `Sub` oder `Function` muss angezeigt werden. Deklariert diese Prozedur als Delegat `Function` Prozedur, die einen Wert zurückgibt.|  
|`name`|Erforderlich. Name des Delegattyps; folgt standard Namenskonventionen für Variable.|  
|`typeparamlist`|Optional. Liste mit Typparametern für diesen Delegaten. Mehrere Parameter werden durch Kommas getrennt. Optional, einzelnen Typparameter kann als Variant deklariert werden mit `In` und `Out` generischer Modifizierer. Muss die [Liste](../../../visual-basic/language-reference/statements/type-list.md) in Klammern, und führen Sie es mit der `Of` Schlüsselwort.|  
|`parameterlist`|Optional. Liste der Parameter, die an die Prozedur übergeben werden, wenn sie aufgerufen wird. Setzen Sie die [Parameterliste](../../../visual-basic/language-reference/statements/parameter-list.md) in Klammern.|  
|`type`|Erforderlich, wenn Sie angeben, einen `Function` Verfahren. Der Datentyp des Rückgabewerts.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Delegate` -Anweisung definiert die Parameter- und Rückgabetypen einer Delegatklasse. Jede Prozedur mit identischen Parametern und Rückgabetypen kann zum Erstellen einer Instanz dieser Delegatklasse verwendet werden. Die Prozedur kann dann später aufgerufen werden über die Delegatinstanz Aufrufen des Delegaten `Invoke` Methode.  
  
 Delegaten können an den Namespace, Modul, Klasse oder Strukturebene, aber nicht innerhalb einer Prozedur deklariert werden.  
  
 Jede Delegatklasse definiert einen Konstruktor, dem die Spezifikation einer Objektmethode übergeben wird. Ein Argument für einen Delegatkonstruktor muss ein Verweis auf eine Methode oder ein Lambda-Ausdruck sein.  
  
 Um einen Verweis auf eine Methode anzugeben, verwenden Sie die folgende Syntax:  
  
 `AddressOf` [`expression`.]`methodname`  
  
 Der Kompilierzeit-Typ, der die `expression` muss der Name einer Klasse oder eine Schnittstelle, die eine Methode mit dem angegebenen Namen enthält, deren Signatur mit die Signatur der Delegatklasse übereinstimmt. Die `methodname` kann entweder eine freigegebene Methode oder eine Instanzmethode sein. Die `methodname` ist nicht optional, selbst wenn Sie einen Delegaten für die Standardmethode der Klasse erstellen.  
  
 Um einen Lambda-Ausdruck anzugeben, verwenden Sie die folgende Syntax:  
  
 `Function`([`parm` As `type`, `parm2` As `type2`, ...])`expression`  
  
 Die Signatur der Funktion muss der Typ des Delegaten übereinstimmen. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Weitere Informationen über Delegaten finden Sie unter [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `Delegate` -Anweisung ein Delegat deklariert, mit dem zwei Zahlen und eine Zahl zurückgegeben. Die `DelegateTest` Methode akzeptiert eine Instanz eines Delegaten dieses Typs und wird verwendet, um Paare von Zahlen ausgeführt werden.  
  
 [!code-vb[VbVbalrDelegates&14;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [AddressOf-Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)   
 [Delegaten](../../../visual-basic/programming-guide/language-features/delegates/index.md)   
 [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Kovarianz und Kontravarianz](http://msdn.microsoft.com/library/a58cc086-276f-4f91-a366-85b7f95f38b8)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Auschecken](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)
