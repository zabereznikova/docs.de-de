---
title: "Generic Procedures in Visual Basic | Microsoft Docs"
ms.custom: ""
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
  - "generic methods, type inference"
  - "generics [Visual Basic], type inference"
  - "procedures, generic"
  - "generic procedures"
  - "type inference, generics"
  - "generic methods"
  - "type inference"
  - "generics [Visual Basic], procedures"
  - "generic procedures, type inference"
ms.assetid: 95577b28-137f-4d5c-a149-919c828600e5
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Generic Procedures in Visual Basic
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine *generische Prozedur* oder auch *generische Methode* ist eine Prozedur, die mit mindestens einem Typparameter definiert ist.  Dadurch können bei jedem Aufruf der Prozedur die Datentypen im aufrufenden Code an die aktuellen Anforderungen angepasst werden.  
  
 Eine Prozedur erhält ihren generischen Charakter nicht einfach aufgrund der Definition innerhalb einer generischen Klasse oder einer generischen Struktur.  Vielmehr muss die Prozedur neben den eventuell vorhandenen normalen Parametern mindestens einen Typparameter entgegennehmen, um generisch zu sein.  Eine generische Klasse oder Struktur kann Prozeduren beinhalten, die nicht generisch sind, und eine nicht generische Klasse oder Struktur oder ein nicht generisches Modul kann generische Prozeduren enthalten.  
  
 Typparameter können in einer generischen Prozedur in der normalen Parameterliste, im eventuell vorhandenen Rückgabetyp sowie innerhalb des Prozedurcodes verwendet werden.  
  
## Typableitung  
 Sie können eine generische Prozedur ohne Angabe eines Typarguments aufrufen.  Bei dieser Art des Aufrufs versucht der Compiler, die richtigen Datentypen zu bestimmen, die für die Übergabe an die Typparameter der Prozedur benötigt werden.  Dies wird als *Typableitung* bezeichnet.  Das folgende Codebeispiel zeigt einen Aufruf, bei dem der Compiler ableitet, dass dem Typparameter `t` der Typ `String` übergeben werden muss.  
  
 [!code-vb[VbVbalrDataTypes#15](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_1.vb)]  
  
 Wenn der Compiler die Typargumente nicht aus dem Kontext des Aufrufs ableiten kann, wird ein Fehler erzeugt.  Eine mögliche Ursache für einen solchen Fehler ist beispielsweise die Nichtübereinstimmung eines Arrayrangs.  Angenommen, Sie haben einen normalen Parameter als Array eines Typparameters definiert.  Wenn Sie die generische Prozedur mit einem Array aufrufen, das über einen abweichenden Rang verfügt \(Anzahl der Dimensionen\), bewirkt die Nichtübereinstimmung, dass die Typableitung fehlschlägt.  Das folgende Codebeispiel zeigt einen Aufruf, bei dem einer Prozedur, die ein eindimensionales Array erwartet, ein zweidimensionales Array übergeben wird.  
  
 `Public Sub demoSub(Of t)(ByVal arg() As t)`  
  
 `End Sub`  
  
 `Public Sub callDemoSub()`  
  
 `Dim twoDimensions(,) As Integer`  
  
 `demoSub(twoDimensions)`  
  
 `End Sub`  
  
 Sie können die Typableitung nur aufrufen, indem Sie sämtliche Typargumente weglassen.  Wenn Sie ein Typargument angeben, müssen alle anderen Typargumente ebenfalls angegeben werden.  
  
 Die Typableitung wird nur für generische Prozeduren unterstützt.  Die Typableitung kann nicht für generische Klassen, Strukturen, Schnittstellen oder Delegaten aufgerufen werden.  
  
## Beispiel  
  
### Beschreibung  
 Im folgenden Beispiel wird eine generische `Function`\-Prozedur definiert, um ein bestimmtes Element in einem Array zu suchen.  Sie definiert einen Typparameter und verwendet diesen zur Konstruktion der beiden Parameter in der Parameterliste.  
  
### Code  
 [!code-vb[VbVbalrDataTypes#14](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_2.vb)]  
  
### Kommentare  
 Für das vorangehende Beispiel ist die Möglichkeit erforderlich, `searchValue` mit jedem Element von `searchArray` zu vergleichen.  Um dies zu garantieren, wird der Typparameter `T` dahingehend eingeschränkt, dass die <xref:System.IComparable%601>\-Schnittstelle implementiert werden muss.  Im Code wird anstelle des Operators `=` die <xref:System.IComparable%601.CompareTo%2A>\-Methode verwendet, da nicht garantiert werden kann, dass das für `T` angegebene Typargument den Operator `=` unterstützt.  
  
 Sie können die `findElement`\-Prozedur mit folgendem Code testen.  
  
 [!code-vb[VbVbalrDataTypes#13](../../../../visual-basic/language-reference/data-types/codesnippet/VisualBasic/generic-procedures_3.vb)]  
  
 Die vorangehenden Aufrufe von `MsgBox` bewirken nacheinander die Anzeige von "0", "1" und "\-1".  
  
## Siehe auch  
 [Generische Typen in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Gewusst wie: Definieren einer Klasse, die für unterschiedliche Datentypen die gleiche Funktionalität bereitstellen kann](../../../../visual-basic/programming-guide/language-features/data-types/how-to-define-a-class-that-can-provide-identical-functionality.md)   
 [Gewusst wie: Verwenden einer generischen Klasse](../../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)   
 [Procedures](../../../../visual-basic/programming-guide/language-features/procedures/index.md)   
 [Procedure Parameters and Arguments](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Type List](../../../../visual-basic/language-reference/statements/type-list.md)   
 [Parameter List](../../../../visual-basic/language-reference/statements/parameter-list.md)