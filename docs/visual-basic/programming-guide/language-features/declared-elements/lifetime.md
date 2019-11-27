---
title: Lebensdauer
ms.date: 07/20/2015
helpviewer_keywords:
- static variables [Visual Basic], lifetime
- static variables [Visual Basic], Visual Basic
- declared elements [Visual Basic], lifetime
- Shared variable lifetime [Visual Basic]
- lifetime [Visual Basic], declared elements
- lifetime [Visual Basic], Visual Basic
- lifetime [Visual Basic]
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
ms.openlocfilehash: 05a39388e8aa9681af60cf86a3df8346d744b69e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345315"
---
# <a name="lifetime-in-visual-basic"></a>Lebensdauer in Visual Basic
Die *Lebensdauer* eines deklarierten Elements ist die Zeitspanne, in der es zur Verwendung verfügbar ist. Variablen sind die einzigen Elemente, die die Lebensdauer haben. Zu diesem Zweck behandelt der Compiler Prozedur Parameter, und die Funktion gibt als Sonderfälle von Variablen zurück. Die Lebensdauer einer Variablen stellt den Zeitraum dar, in dem ein Wert gespeichert werden kann. Der Wert kann sich über seine Lebensdauer ändern, aber er hat immer einen Wert.  
  
## <a name="different-lifetimes"></a>Andere Lebensdauer  
 Eine *Member-Variable* (auf Modulebene, außerhalb einer Prozedur deklariert) hat normalerweise die gleiche Lebensdauer wie das Element, in dem Sie deklariert ist. Eine nicht freigegebene Variable, die in einer Klasse oder Struktur deklariert wurde, ist für jede Instanz der Klasse oder Struktur, in der Sie deklariert ist, als separate Kopie vorhanden. Jede dieser Variablen hat die gleiche Lebensdauer wie Ihre Instanz. Eine `Shared` Variable hat jedoch nur eine einzige Lebensdauer, die für den gesamten Zeitpunkt der Ausführung der Anwendung gilt.  
  
 Eine *lokale Variable* (innerhalb einer Prozedur deklariert) ist nur vorhanden, während die Prozedur, in der Sie deklariert ist, ausgeführt wird. Dies gilt auch für die Parameter der Prozedur und für jede Funktions Rückgabe. Wenn diese Prozedur jedoch andere Prozeduren aufruft, behalten die lokalen Variablen ihre Werte bei, während die aufgerufenen Prozeduren ausgeführt werden.  
  
## <a name="beginning-of-lifetime"></a>Beginn der Lebensdauer  
 Die Lebensdauer einer lokalen Variablen beginnt, wenn das Steuerelement in die Prozedur eintritt, in der es deklariert ist. Jede lokale Variable wird mit dem Standardwert für ihren Datentyp initialisiert, sobald die Prozedur ausgeführt wird. Wenn die Prozedur auf eine `Dim` Anweisung trifft, die Anfangswerte angibt, legt Sie diese Variablen auf diese Werte fest, auch wenn Ihr Code bereits andere Werte zugewiesen hätte.  
  
 Jeder Member einer Struktur Variablen wird initialisiert, als ob es sich um eine separate Variable handelt. Ebenso wird jedes Element einer Array Variablen einzeln initialisiert.  
  
 Variablen, die innerhalb einer Prozedur innerhalb einer Prozedur deklariert werden (z. b. eine `For` Schleife), werden beim Eintrag der Prozedur initialisiert. Diese Initialisierungen treten in Kraft, unabhängig davon, ob Ihr Code den Block jemals ausführt.  
  
## <a name="end-of-lifetime"></a>Ende der Lebensdauer  
 Wenn eine Prozedur beendet wird, werden die Werte der lokalen Variablen nicht beibehalten, und Visual Basic ihren Speicher frei. Wenn Sie die Prozedur das nächste Mal aufzurufen, werden alle Ihre lokalen Variablen seedmethode erstellt und erneut initialisiert.  
  
 Wenn eine Instanz einer Klasse oder Struktur beendet wird, verlieren die nicht freigegebenen Variablen Ihren Arbeitsspeicher und ihre Werte. Jede neue Instanz der Klasse oder Struktur erstellt und initialisiert die nicht freigegebenen Variablen. `Shared` Variablen bleiben jedoch erhalten, bis die Ausführung der Anwendung beendet wird.  
  
## <a name="extension-of-lifetime"></a>Erweiterung der Lebensdauer  
 Wenn Sie eine lokale Variable mit dem `Static`-Schlüsselwort deklarieren, ist Ihre Lebensdauer länger als die Ausführungszeit der Prozedur. In der folgenden Tabelle wird gezeigt, wie die Prozedur Deklaration bestimmt, wie lange eine `Static` Variable vorhanden ist.  
  
|Speicherort und Freigabe der Prozedur|Die Lebensdauer der statischen Variablen beginnt|Lebensdauer statischer Variablen endet|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|In einem Modul (standardmäßig freigegeben)|Wenn die Prozedur zum ersten Mal aufgerufen wird|Wenn die Ausführung der Anwendung beendet wird|  
|In einer Klasse `Shared` (Prozedur kein Instanzmember)|Wenn die Prozedur zum ersten Mal entweder für eine bestimmte Instanz oder für den Klassen-oder Struktur Namen selbst aufgerufen wird.|Wenn die Ausführung der Anwendung beendet wird|  
|In einer Instanz einer Klasse nicht `Shared` (Prozedur ist ein Instanzmember)|Wenn die Prozedur zum ersten Mal für die jeweilige Instanz aufgerufen wird|Wenn die Instanz für Garbage Collection (GC) freigegeben wird|  
  
## <a name="static-variables-of-the-same-name"></a>Statische Variablen mit demselben Namen  
 Sie können statische Variablen mit demselben Namen in mehr als einer Prozedur deklarieren. Wenn Sie dies tun, berücksichtigt der Visual Basic-Compiler jede dieser Variablen als separates Element. Die Initialisierung einer dieser Variablen wirkt sich nicht auf die Werte der anderen aus. Dasselbe gilt, wenn Sie eine Prozedur mit einer Reihe von über Ladungen definieren und eine statische Variable mit demselben Namen in jeder Überladung deklarieren.  
  
## <a name="containing-elements-for-static-variables"></a>Enthaltende Elemente für statische Variablen  
 Sie können eine statische lokale Variable innerhalb einer Klasse deklarieren, d. h. innerhalb einer Prozedur in dieser Klasse. Es ist jedoch nicht möglich, eine statische lokale Variable innerhalb einer Struktur zu deklarieren, entweder als Strukturmember oder als lokale Variable einer Prozedur innerhalb dieser Struktur.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Im folgenden Beispiel wird eine Variable mit dem [static](../../../../visual-basic/language-reference/modifiers/static.md) -Schlüsselwort deklariert. (Beachten Sie, dass Sie das `Dim`-Schlüsselwort nicht benötigen, wenn die [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) einen Modifizierer wie `Static`verwendet.)  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrKeywords#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#13)]  
  
### <a name="comments"></a>Comments  
 Im vorherigen Beispiel ist die Variable `applesSold` weiterhin vorhanden, nachdem die Prozedur `runningTotal` an den aufrufenden Code zurückgegeben hat. Wenn `runningTotal` das nächste Mal aufgerufen wird, behält `applesSold` den zuvor berechneten Wert bei.  
  
 Wenn `applesSold` ohne Verwendung `Static`deklariert wurde, werden die vorherigen akkumulierten Werte nicht über Aufrufe von `runningTotal`hinweg beibehalten. Beim nächsten Aufruf von `runningTotal` wurden `applesSold` neu erstellt und auf 0 initialisiert, und `runningTotal` hätte einfach denselben Wert zurückgegeben, mit dem Sie aufgerufen wurde.  
  
### <a name="compiling-the-code"></a>Kompilieren des Codes  
 Sie können den Wert einer statischen lokalen Variablen als Teil der Deklaration initialisieren. Wenn Sie ein Array als `Static`deklarieren, können Sie den Rang (Anzahl der Dimensionen), die Länge jeder Dimension und die Werte der einzelnen Elemente initialisieren.  
  
### <a name="security"></a>Sicherheit  
 Im vorherigen Beispiel können Sie die gleiche Lebensdauer schaffen, indem Sie `applesSold` auf Modulebene deklarieren. Wenn Sie den Gültigkeitsbereich einer Variablen auf diese Weise geändert haben, hat die Prozedur jedoch keinen exklusiven Zugriff mehr. Da andere Prozeduren auf `applesSold` zugreifen und deren Wert ändern können, kann die laufende Summe unzuverlässig sein, und der Code kann schwieriger zu warten sein.  
  
## <a name="see-also"></a>Siehe auch

- [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Bereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
