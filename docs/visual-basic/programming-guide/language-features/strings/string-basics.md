---
title: Grundlagen zu Zeichenfolgen
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
ms.openlocfilehash: 44736f4db9977d9f69a0571cc80fa327dcf96581
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072508"
---
# <a name="string-basics-in-visual-basic"></a>Grundlagen zu Zeichenfolgen in Visual Basic

Der `String`-Datentyp stellt eine Reihe von Zeichen dar (wobei jedes Zeichen wiederum eine Instanz des `Char`-Datentyps darstellt). In diesem Thema werden die grundlegenden Konzepte von Zeichen folgen in Visual Basic vorgestellt.  
  
## <a name="string-variables"></a>Zeichenfolgenvariablen  

 Einer Instanz einer Zeichenfolge kann ein Literalwert zugewiesen werden, der eine Reihe von Zeichen darstellt. Beispiel:  
  
 [!code-vb[VbVbalrStrings#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#63)]  
  
 Eine `String`-Variable kann auch einen beliebigen Ausdruck annehmen, der eine Zeichenfolge ergibt. Beispiele werden unten gezeigt:  
  
 [!code-vb[VbVbalrStrings#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#64)]  
  
 Jedes Literal, das einer `String`-Variable zugewiesen ist, muss in Anführungszeichen eingeschlossen werden („“). Dies bedeutet, dass ein Anführungszeichen in einer Zeichenfolge nicht durch ein Anführungszeichen dargestellt werden kann. Beispielsweise verursacht der folgende Code einen Compilerfehler:  
  
 [!code-vb[VbVbalrStrings#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#65)]  
  
 Dieser Code verursacht einen Fehler, da der Compiler die Zeichenfolge nach dem zweiten Anführungszeichen beendet, und der Rest der Zeichenfolge wird als Code interpretiert. Um dieses Problem zu beheben, interpretiert Visual Basic zwei Anführungszeichen in einem zeichenfolgenliteralformat als ein Anführungszeichen in der Zeichenfolge. Das folgende Beispiel zeigt die korrekte Methode zum Einschließen eines Anführungszeichens in eine Zeichenfolge:  
  
 [!code-vb[VbVbalrStrings#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#66)]  
  
 Im vorherigen Beispiel werden die beiden Anführungszeichen, die vor dem Wort `Look` vorhanden sind, zu einem Anführungszeichen in der Zeichenfolge. Die drei Anführungszeichen am Ende der Zeile stellen ein Anführungszeichen in der Zeichenfolge und das Abschlusszeichen der Zeichenfolge dar.  
  
 Zeichenfolgenliterale können mehrere Zeilen enthalten:  
  
```vb  
Dim x = "hello  
world"  
```  
  
 Die resultierende Zeichenfolge enthält Zeilenumbruchsequenzen, die Sie in Ihrem Zeichenfolgenliteral (vbcr, vbcrlf usw.) verwendet haben.  Sie müssen nicht mehr die bisherige Problemumgehung verwenden:  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
```  
  
## <a name="characters-in-strings"></a>Zeichen in Zeichenfolgen  

 Eine Zeichenfolge kann als eine Reihe von `Char`-Werten betrachtet werden, und der `String`-Typ verfügt über integrierte Funktionen, mit denen Sie zahlreiche Bearbeitungen an einer Zeichenfolge vornehmen können, die den durch Arrays zulässigen Bearbeitungen ähneln. Wie bei allen Arrays in .NET Framework handelt es sich hierbei um null basierte Arrays. Sie möchten möglicherweise auf ein bestimmtes Zeichen in einer Zeichenfolge durch die `Chars`-Eigenschaft verweisen, die eine Möglichkeit bietet, auf ein Zeichen durch die Position zuzugreifen, in der es in der Zeichenfolge auftritt. Beispiel:  
  
 [!code-vb[VbVbalrStrings#67](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#67)]  
  
 Im obigen Beispiel gibt die `Chars`-Eigenschaft der Zeichenfolge das vierte Zeichen in der Zeichenfolge zurück, wobei es sich um `D` handelt, und weist dieses `myChar` zu. Sie können auch die Länge einer bestimmten Zeichenfolge durch die `Length`-Eigenschaft abrufen. Wenn Sie mehrere Bearbeitungen hinsichtlich des Arraytyps an einer Zeichenfolge durchführen müssen, können Sie sie in ein Array von `Char`-Instanzen mit der `ToCharArray`-Funktion der Zeichenfolge konvertieren. Beispiel:  
  
 [!code-vb[VbVbalrStrings#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#68)]  
  
 Die Variable `myArray` enthält jetzt ein Array von `Char`-Werten, die jeweils ein Zeichen aus `myString` darstellen.  
  
## <a name="the-immutability-of-strings"></a>Die Unveränderlichkeit von Zeichenfolgen  

 Eine Zeichenfolge ist *unveränderlich*, was bedeutet, dass der Wert nicht geändert werden kann, nachdem er erstellt wurde. Sie können einer Zeichenfolgenvariablen trotzdem mehr als einen Wert zuweisen. Betrachten Sie das folgende Beispiel:  
  
 [!code-vb[VbVbalrStrings#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#69)]  
  
 Hier wird eine Zeichenfolgenvariable erstellt, ein Wert zugewiesen, und dann wird der Wert geändert.  
  
 Genauer gesagt wird in der ersten Zeile eine Instanz des Typs `String` erstellt und der Wert `This string is immutable` zugewiesen. In der zweiten Zeile des Beispiels wird eine neue Instanz erstellt und der Wert `Or is it?` zugewiesen. Die Zeichenfolgenvariable verwirft den Verweis auf die erste Instanz und speichert einen Verweis auf die neue Instanz.  
  
 Im Gegensatz zu anderen systeminternen Datentypen ist `String` ein Verweistyp. Wenn eine Variable des Verweistyps als Argument an eine Funktion oder Unterroutine übergeben wird, wird ein Verweis auf die Speicheradresse, wo die Daten gespeichert werden, anstelle des tatsächlichen Werts der Zeichenfolge übergeben. Damit bleibt der Name der Variable im vorherigen Beispiel gleich, aber es wird auf eine neue und andere Instanz der `String`-Klasse verwiesen, die den neuen Wert enthält.  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in Zeichenfolgen in Visual Basic](introduction-to-strings.md)
- [String-Datentyp](../../../language-reference/data-types/string-data-type.md)
- [Char-Datentyp](../../../language-reference/data-types/char-data-type.md)
- [Grundlegende Zeichenfolgenoperationen](../../../../standard/base-types/basic-string-operations.md)
