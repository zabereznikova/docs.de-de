---
title: "Parameter List (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Visual Basic code, procedures"
  - "parameters, Visual Basic"
  - "parameters, lists"
  - "parameter lists"
  - "Visual Basic code, parameter lists"
  - "arguments [Visual Basic], Visual Basic"
  - "procedures, parameter lists"
ms.assetid: 5d737319-0c34-4df9-a23d-188fc840becd
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# Parameter List (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Gibt die Parameter an, die eine Prozedur bei ihrem Aufruf erwartet.  Mehrere Parameter werden durch Komma voneinander getrennt.  Im Folgenden ist die Syntax für einen Parameter dargestellt.  
  
## Syntax  
  
```  
[ <attributelist> ] [ Optional ] [{ ByVal | ByRef }] [ ParamArray ]   
parametername[( )] [ As parametertype ] [ = defaultvalue ]  
```  
  
## Teile  
 `attributelist`  
 Optional.  Liste der Attribute, die für diesen Parameter zutreffen.  Schließen Sie die [Attribute List](../../../visual-basic/language-reference/statements/attribute-list.md) in spitzen Klammern \("`<`" und "`>`"\) ein.  
  
 `Optional`  
 Optional.  Gibt an, dass dieser Parameter beim Aufruf der Prozedur nicht erforderlich ist.  
  
 `ByVal`  
 Optional.  Gibt an, dass die Prozedur das dem entsprechenden Argument zugrunde liegende Variablenelement im Aufrufcode weder ersetzen noch neu zuweisen kann.  
  
 `ByRef`  
 Optional.  Gibt an, dass die Prozedur das zugrunde liegende Variablenelement im Aufrufcode genauso ändern kann wie der Aufrufcode selbst.  
  
 `ParamArray`  
 Optional.  Gibt an, dass der letzte Parameter in der Parameterliste ein optionales Array aus Elementen mit dem angegebenen Datentyp ist.  Vom Aufrufcode kann hierdurch eine beliebige Anzahl von Argumenten an die Prozedur übergeben werden.  
  
 `parametername`  
 Erforderlich.  Name der lokalen Variablen, die den Parameter darstellt.  
  
 `parametertype`  
 Erforderlich, wenn `Option Strict` den Wert `On` aufweist.  Datentyp der lokalen Variable, die den Parameter darstellt.  
  
 `defaultvalue`  
 Erforderlich für `Optional`\-Parameter.  Jede beliebige Konstante bzw. jeder beliebige Konstantenausdruck, die bzw. der als Datentyp des Parameters ausgewertet wird.  Beim `Object`\-Datentyp oder einer Klasse, einer Schnittstelle, einem Array oder einer Struktur kann der Standardwert nur `Nothing` sein.  
  
## Hinweise  
 Parameter werden von runden Klammern umgeben und durch Kommas getrennt.  Ein Parameter kann mit jedem Datentyp deklariert werden.  Wenn Sie keinen Wert für `parametertype` angeben, wird standardmäßig `Object` verwendet.  
  
 Wenn der Aufrufcode die Prozedur aufruft, übergibt er ein *Argument* an jeden erforderlichen Parameter.  Weitere Informationen finden Sie unter [Differences Between Parameters and Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-parameters-and-arguments.md).  
  
 Das Argument, das der Aufrufcode an jeden Parameter übergibt, ist ein Zeiger auf ein zugrunde liegendes Element im Aufrufcode.  Wenn dieses Element ein *nicht variables Element* \(Konstante, Literal, Enumeration oder Ausdruck\) ist, kann es nicht durch Code geändert werden.  Wenn es sich um ein *variables Element* \(deklarierte Variable, Feld, Eigenschaft, Arrayelement oder Strukturelement\) handelt, kann es vom Aufrufcode geändert werden.  Weitere Informationen finden Sie unter [Differences Between Modifiable and Nonmodifiable Arguments](../../../visual-basic/programming-guide/language-features/procedures/differences-between-modifiable-and-nonmodifiable-arguments.md).  
  
 Wenn ein variables Element mit `ByRef` übergeben wird, kann die Prozedur es ebenfalls ändern.  Weitere Informationen finden Sie unter [Differences Between Passing an Argument By Value and By Reference](../../../visual-basic/programming-guide/language-features/procedures/differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
## Regeln  
  
-   **Runde Klammern.** Wenn Sie eine Parameterliste angeben, müssen Sie die Liste zwischen runde Klammern setzen.  Wenn keine Parameter vorhanden sind, können Sie trotzdem runde Klammern verwenden, die eine leere Liste enthalten.  Dies verbessert die Lesbarkeit des Codes, weil dadurch deutlich wird, dass es sich bei dem Element um eine Prozedur handelt.  
  
-   **Optionale Parameter.** Wenn Sie den `Optional`\-Modifizierer für einen Parameter verwenden, müssen alle nachfolgenden Parameter in der Liste ebenfalls optional und mit dem `Optional`\-Modifizierer deklariert sein.  
  
     Jede optionale Parameterdeklaration muss die `defaultvalue`\-Klausel angeben.  
  
     Weitere Informationen finden Sie unter [Optional Parameters](../../../visual-basic/programming-guide/language-features/procedures/optional-parameters.md).  
  
-   **Parameterarrays.** Sie müssen `ByVal` für einen `ParamArray`\-Parameter angeben.  
  
     `Optional` und `ParamArray` dürfen nicht zusammen in einer Parameterliste angegeben werden.  
  
     Weitere Informationen hierzu finden Sie unter [Parameter Arrays](../../../visual-basic/programming-guide/language-features/procedures/parameter-arrays.md).  
  
-   **Übergabemechanismus.** Der Standardmechanismus für jedes Argument ist `ByVal`. Dies bedeutet, dass die Prozedur das zugrunde liegende variable Element nicht ändern kann.  Wenn das Element jedoch ein Referenztyp ist, kann die Prozedur den Inhalt oder die Member des zugrunde liegenden Objekts auch dann ändern, wenn sie das Objekt selbst nicht ersetzen oder neu zuweisen kann.  
  
-   **Parameternamen.** Wenn der Datentyp des Parameters ein Array ist, muss, müssen direkt im Anschluss an `parametername` runde Klammern angegeben werden.  Weitere Informationen zu Parameternamen finden Sie unter [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
## Beispiel  
 Das folgenden Beispiel zeigt eine `Function`\-Prozedur, die zwei Parameter definiert.  
  
 [!code-vb[VbVbalrStatements#2](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/parameter-list_1.vb)]  
  
## Siehe auch  
 <xref:System.Runtime.InteropServices.DllImportAttribute>   
 [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)   
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)