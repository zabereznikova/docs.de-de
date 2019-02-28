---
title: Lebensdauer in Visual Basic
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
ms.openlocfilehash: 15fb6895836de95d37081c44973f455622da178e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976043"
---
# <a name="lifetime-in-visual-basic"></a>Lebensdauer in Visual Basic
Die *Lebensdauer* eines deklarierten Elements ist den Zeitraum, während die It für die Verwendung verfügbar ist. Variablen sind nur Elemente, die deren Lebensdauer. Zu diesem Zweck der Compiler behandelt Prozedurparameter, und Funktionsergebnis ist als spezielle Fälle von Variablen. Die Lebensdauer einer Variablen stellt die Zeitspanne, in dem sie einen Wert enthalten kann. Der Wert kann während seiner Lebensdauer ändern, aber sie enthält immer einen Wert.  
  
## <a name="different-lifetimes"></a>Unterschiedliche Lebensdauer  
 Ein *Membervariable* (auf Modulebene außerhalb einer Prozedur deklariert) in der Regel hat die gleiche Lebensdauer wie das Element in der sie deklariert ist. Eine nicht freigegebene Variable, die in einer Klasse oder Struktur deklariert ist vorhanden, als eine separate Kopie für jede Instanz der Klasse oder Struktur, die in der sie deklariert ist. Jede dieser Variablen hat die gleiche Lebensdauer wie die Instanz. Allerdings eine `Shared` Variable hat nur eine Lebensdauer, die für die gesamte Zeit in der Regel dauert die Anwendung ausgeführt wird.  
  
 Ein *lokale Variable* (innerhalb einer Prozedur deklariert) vorhanden ist, nur während der Ausführung der Prozedur, die in der sie deklariert ist. Dies gilt auch, um die Parameter der Prozedur und eine Funktion zurück. Wenn diese Prozedur anderen Prozeduren aufgerufen wird, behalten jedoch die lokalen Variablen ihre Werte während die aufgerufenen Verfahren ausgeführt werden.  
  
## <a name="beginning-of-lifetime"></a>Beginn der Lebensdauer  
 Lebensdauer einer lokalen Variablen beginnt, wenn es sich bei die Prozedur Eintritte in der sie deklariert ist. Jede lokale Variable auf den Standardwert für seinen Datentyp initialisiert wird, sobald das Verfahren beginnt ausgeführt wird. Wenn die Prozedur trifft eine `Dim` Anweisung, die ursprünglichen Werte gibt an, wird dieser Variablen auf die Werte, selbst wenn Ihr Code bereits andere Werte werden zugewiesen hat.  
  
 Jedes Element einer Struktur-Variable wird initialisiert, als handele es sich um eine separate Variable. Auf ähnliche Weise wird jedes Element einer Arrayvariablen einzeln initialisiert werden.  
  
 Variablen, die in einem Block innerhalb einer Prozedur deklariert (z. B. eine `For` Schleife), die beim Einstieg in die Prozedur initialisiert werden. Diese Initialisierungen werden wirksam, und zwar unabhängig davon, ob Ihr Code den Block einmal ausgeführt wird.  
  
## <a name="end-of-lifetime"></a>Ende der Lebensdauer  
 Wenn eine Prozedur beendet wird, die Werte der zugehörigen lokalen Variablen werden nicht beibehalten, und Visual Basic gibt ihren Speicher frei. Beim nächsten der Prozedur aufrufen, alle zugehörigen lokalen Variablen neu erstellt und initialisiert.  
  
 Wenn eine Instanz einer Klasse oder Struktur beendet wird, verlieren die nicht freigegebenen Variablen, deren Speicher und ihre Werte. Jede neue Instanz der Klasse oder Struktur erstellt und initialisiert seine nicht freigegebenen Variablen. Allerdings `Shared` Variablen werden beibehalten, bis die Anwendung beendet wird.  
  
## <a name="extension-of-lifetime"></a>Erweiterung der Lebensdauer  
 Wenn Sie eine lokale Variable mit deklarieren die `Static` -Schlüsselwort, seine Lebensdauer ist länger als die Ausführungszeit des Verfahrens. Die folgende Tabelle zeigt, wie wie lange der Prozedurdeklaration eine `Static` Variable vorhanden ist.  
  
|Prozedurspeicherort und Freigabe|Beginnt die Lebensdauer der statische Variablen|Die Lebensdauer der statischen Variablen endet|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|In einem Modul (standardmäßig freigegeben)|Beim ersten wird die Prozedur aufgerufen.|Wenn Ihre Anwendung nicht mehr ausgeführt|  
|In einer Klasse `Shared` (der Prozedur ist nicht auf einen Instanzmember)|Beim ersten der Prozedur auf eine bestimmte Instanz oder auf die Klasse oder Struktur aufrufen Namens der Speichermomentaufnahme|Wenn Ihre Anwendung nicht mehr ausgeführt|  
|In einer Instanz einer Klasse nicht `Shared` (Prozedur ist ein Instanzmember)|Beim ersten wird die Prozedur auf die jeweilige Instanz aufgerufen.|Wenn die Instanz für die Garbagecollection (GC) freigegeben wird|  
  
## <a name="static-variables-of-the-same-name"></a>Statische Variablen mit dem gleichen Namen  
 Sie können statische Variablen mit dem gleichen Namen in mehr als eine Prozedur deklarieren. Wenn Sie dies tun, berücksichtigt Visual Basic-Compiler jede dieser Variablen, die als separates Element auf. Die Initialisierung von einer dieser Variablen wirkt sich nicht auf die Werte der anderen aus. Dasselbe gilt, wenn Sie eine Prozedur mit einem Satz von Überladungen definieren und deklarieren Sie eine statische Variable mit dem gleichen Namen in jeder Überladung.  
  
## <a name="containing-elements-for-static-variables"></a>Die Elemente für statische Variablen enthält.  
 Sie können eine statische lokale Variable innerhalb einer Klasse, d. h. innerhalb einer Prozedur in dieser Klasse deklarieren. Sie können nicht jedoch eine statische lokale Variable in einer Struktur als einen Strukturmember oder als lokale Variable einer Prozedur innerhalb dieser Struktur deklarieren.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel deklariert eine Variable mit dem [statische](../../../../visual-basic/language-reference/modifiers/static.md) Schlüsselwort. (Beachten Sie, die Sie nicht benötigen die `Dim` Schlüsselwort bei der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) verwendet einen Modifizierer, z. B. `Static`.)  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrKeywords#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/class7.vb#13)]  
  
### <a name="comments"></a>Kommentare  
 Im vorherigen Beispiel, die Variable `applesSold` bleibt nach dem Verfahren `runningTotal` an den aufrufenden Code zurückgibt. Das nächste Mal `runningTotal` aufgerufen wird, `applesSold` behält den zuvor berechneten Wert.  
  
 Wenn `applesSold` deklariert wurde ohne `Static`, die gesammelten Werte nicht über Aufrufe hinweg beibehalten werden würde `runningTotal`. Das nächste Mal `runningTotal` aufgerufen wurde, `applesSold` wird neu erstellt und mit 0 (null) initialisiert wurden und `runningTotal` einfach zurückgegeben hätte den gleichen Wert, mit denen er aufgerufen wurde.  
  
### <a name="compiling-the-code"></a>Kompilieren des Codes  
 Sie können den Wert einer statischen lokalen Variablen als Teil der Deklaration initialisieren. Wenn Sie ein Array sein deklarieren `Static`, Sie können sein Rang (Anzahl der Dimensionen), die Länge jeder Dimension, und die Werte der einzelnen Elemente initialisieren.  
  
### <a name="security"></a>Sicherheit  
 Im vorherigen Beispiel können Sie die gleiche Lebensdauer erzeugen, indem deklarieren `applesSold` auf Modulebene. Wenn Sie den Bereich einer Variablen auf diese Weise geändert, jedoch müsste die Prozedur nicht mehr exklusiven Zugriff darauf. Da andere Prozeduren zugegriffen werden konnte `applesSold` und ändern Sie seinen Wert, die laufende Summe ist möglicherweise unzuverlässig und der Code möglicherweise schwieriger zu warten.  
  
## <a name="see-also"></a>Siehe auch
- [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)
- [Nothing](../../../../visual-basic/language-reference/nothing.md)
- [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
- [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Static](../../../../visual-basic/language-reference/modifiers/static.md)
