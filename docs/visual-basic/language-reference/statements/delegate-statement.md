---
title: "Delegate Statement | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Delegate"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "delegate keyword"
  - "Delegate statement"
ms.assetid: f799c518-0817-40cc-ad0b-4da846fdba57
caps.latest.revision: 27
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 27
---
# Delegate Statement
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Wird zur Deklaration eines Delegaten verwendet.  Ein Delegat ist ein Referenztyp, der auf eine `Shared`\-Methode eines Typs oder auf eine Instanzenmethode eines Objekts verweist.  Jede Prozedur mit identischen Parameter\- und Rückgabetypen kann zum Erstellen einer Instanz dieser Delegatklasse verwendet werden.  Die Prozedur kann anschließend mittels der Delegatinstanz aufgerufen werden.  
  
## Syntax  
  
```  
[ <attrlist> ] [ accessmodifier ] _  
[ Shadows ] Delegate [ Sub | Function ] name [( Of typeparamlist )] [([ parameterlist ])] [ As type ]  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`attrlist`|Optional.  Liste der Attribute, die für diesen Delegaten zutreffen.  Mehrere Attribute werden durch Komma voneinander getrennt.  Schließen Sie die [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern \("`<`" und "`>`"\) ein.|  
|`accessmodifier`|Optional.  Gibt an, welcher Code auf den Delegaten zugreifen kann.  Einer der folgenden Werte ist möglich:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md).  Jeder Code, der auf das Element zugreifen kann, das den Delegaten deklariert, kann auf diesen zugreifen.<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md).  Nur Code innerhalb der Klasse des Delegaten oder innerhalb einer abgeleiteten Klasse kann auf den Delegaten zugreifen.<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md).  Nur Code innerhalb der gleichen Assembly kann auf den Delegaten zugreifen.<br />-   [Privat](../../../visual-basic/language-reference/modifiers/private.md).  Nur Code innerhalb des Elements, das den Delegaten deklariert, kann auf diesen zugreifen.<br /><br /> Sie können `Protected Friend` angeben, um den Zugriff von Code innerhalb der Klasse des Delegaten, innerhalb einer abgeleiteten Klasse oder innerhalb der gleichen Assembly zu ermöglichen.|  
|`Shadows`|Optional.  Gibt an, dass dieser Delegat ein Programmierelement mit der gleichen Bezeichnung oder eine Gruppe überladener Elemente in einer Basisklasse erneut deklariert und ausblendet.  Sie können mit jeder Art von deklarierten Elementen ein Shadowing einer anderen Art durchführen.<br /><br /> Ein Element, für das ein Shadowing durchgeführt wurde, ist innerhalb der abgeleiteten Klasse, die das Shadowing durchführt, nicht verfügbar, es sei denn, auf das Element, welches das Shadowing durchführt, kann nicht zugegriffen werden.  Wenn z. B. ein `Private`\-Element ein Shadowing eines Basisklassenelements durchführt, greift Code ohne Zugriffsberechtigung für das `Private`\-Element stattdessen auf das Basisklassenelement zu.|  
|`Sub`|Optional \(entweder muss `Sub` oder `Function` angegeben werden\).  Deklariert diese Prozedur als `Sub`\-Prozedur des Delegaten, die keinen Wert zurückgibt.|  
|`Function`|Optional \(entweder muss `Sub` oder `Function` angegeben werden\).  Deklariert diese Prozedur als `Function`\-Prozedur des Delegaten, die einen Wert zurückgibt.|  
|`name`|Erforderlich.  Name des Delegattyps; entspricht den Standardnamenskonventionen für Variablen.|  
|`typeparamlist`|Optional.  Liste mit Typparametern für diesen Delegaten.  Mehrere Typparameter werden durch Komma voneinander getrennt.  Optional kann jeder Typparameter mit dem generischen `In`\-Modifizierer und dem generischen `Out`\-Modifizierer als Variant deklariert werden.  Sie müssen die [Type List](../../../visual-basic/language-reference/statements/type-list.md) in Klammern einschließen und mit dem `Of`\-Schlüsselwort einleiten.|  
|`parameterlist`|Optional.  Liste mit Parametern, die an die Prozedur übergeben werden, wenn diese aufgerufen wird.  Sie müssen die [Parameter List](../../../visual-basic/language-reference/statements/parameter-list.md) in Klammern einschließen.|  
|`type`|Erforderlich, wenn Sie eine `Function`\-Prozedur angeben.  Datentyp des Rückgabewerts.|  
  
## Hinweise  
 Die `Delegate`\-Anweisung definiert die Parameter\- und Rückgabetypen einer Delegatklasse.  Jede Prozedur mit identischen Parameter\- und Rückgabetypen kann zum Erstellen einer Instanz dieser Delegatklasse verwendet werden.  Die Prozedur kann anschließend über die Delegatinstanz aufgerufen werden. Dazu rufen Sie die `Invoke`\-Methode des Delegaten auf.  
  
 Delegaten können auf Namespace\-, Modul\-, Klassen\- oder Strukturebene deklariert werden, jedoch nicht innerhalb einer Prozedur.  
  
 Jede Delegatklasse definiert einen Konstruktor, an den die Spezifikation einer Objektmethode übergeben wird.  Ein Argument für einen Delegatkonstruktor muss ein Verweis auf eine Methode oder ein Lambda\-Ausdruck sein.  
  
 Verwenden Sie die folgende Syntax, um einen Verweis auf eine Methode festzulegen:  
  
 `AddressOf` \[`expression`.\]`methodname`  
  
 Der Typ von `expression` muss zur Kompilierungszeit der Name einer Klasse oder Schnittstelle sein, die eine Methode des angegebenen Namens enthält, deren Signatur mit der Signatur der Delegatklasse übereinstimmt.  Mit `methodname` kann entweder eine freigegebene Methode oder eine Instanzenmethode angegeben werden.  `methodname` ist nicht optional, selbst dann nicht, wenn Sie einen Delegaten für die Standardmethode der Klasse erstellen.  
  
 Verwenden Sie die folgende Syntax, um einen Lambda\-Ausdruck festzulegen:  
  
 `Function` \(\[`parm` As `type`, `parm2` As `type2`, ...\]\) `expression`  
  
 Die Signatur der Funktion muss mit dem Delegattyp übereinstimmen.  Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 Weitere Informationen über Delegaten finden Sie unter [Delegates](../../../visual-basic/programming-guide/language-features/delegates/delegates.md).  
  
## Beispiel  
 Im folgenden Beispiel wird mit der `Delegate`\-Anweisung ein Delegat deklariert, mit dem zwei Zahlen bearbeitet werden und eine Zahl zurückgegeben wird.  Die `DelegateTest`\-Methode verwendet eine Instanz eines Delegaten dieses Typs und bearbeitet damit Zahlenpaare.  
  
 [!code-vb[VbVbalrDelegates#14](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/delegate-statement_1.vb)]  
  
## Siehe auch  
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Of](../../../visual-basic/language-reference/statements/of-clause.md)   
 [Delegates](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [Gewusst wie: Verwenden einer generischen Klasse](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Generische Typen in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Kovarianz und Kontravarianz](../Topic/Covariance%20and%20Contravariance%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)