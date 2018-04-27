---
title: Lebensdauer in Visual Basic
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- static variables [Visual Basic], lifetime
- static variables [Visual Basic], Visual Basic
- declared elements [Visual Basic], lifetime
- Shared variable lifetime [Visual Basic]
- lifetime [Visual Basic], declared elements
- lifetime [Visual Basic], Visual Basic
- lifetime [Visual Basic]
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 14a75a2c3af52f63051d02df9341faf19c3b76c7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="lifetime-in-visual-basic"></a>Lebensdauer in Visual Basic
Die *Lebensdauer* eines deklarierten Elements ist der Zeitraum, während die It für die Verwendung verfügbar ist. Variablen werden nur Elemente, die deren Lebensdauer. Zu diesem Zweck wird der Compiler behandelt Prozedurparameter und Funktionsrückgaben als Sonderfälle von Variablen. Die Lebensdauer einer Variablen stellt die Zeitspanne, die dem Objekt einen Wert enthalten darf. Der Wert kann während seiner gesamten Lebensdauer ändern, aber er enthält immer einen Wert.  
  
## <a name="different-lifetimes"></a>Unterschiedliche Lebensdauer  
 Ein *Membervariable* (auf Modulebene außerhalb einer Prozedur deklariert) in der Regel hat die gleiche Lebensdauer wie das Element in der sie deklariert ist. Eine nicht freigegebene Variable in einer Klasse oder Struktur deklariert ist vorhanden, als separate Kopie für jede Instanz der Klasse oder Struktur, die in der sie deklariert ist. Jede dieser Variablen hat dieselbe Lebensdauer wie ihre Instanz. Allerdings eine `Shared` Variable hat nur eine Lebensdauer, die für die gesamte Zeit reicht die Anwendung ausgeführt wird.  
  
 Ein *lokale Variable* (innerhalb einer Prozedur deklariert) vorhanden ist, nur während der Ausführung der Prozedur, die in der sie deklariert ist. Dies gilt auch, um die Parameter der Prozedur und jede Funktionsrückgabe. Wenn diese Prozedur anderen Prozeduren aufruft, behalten jedoch die lokalen Variablen ihre Werte während der aufgerufenen Prozeduren ausgeführt werden.  
  
## <a name="beginning-of-lifetime"></a>Der Anfang der Lebensdauer  
 Lebensdauer einer lokalen Variablen beginnt, wenn die Prozedur steuerungseingänge in der sie deklariert ist. Jede lokale Variable wird auf den Standardwert für seinen Datentyp initialisiert, sobald die Prozedur beginnt ausgeführt wird. Wenn die Prozedur trifft eine `Dim` Anweisung, die Anfangswerte angibt, wird diese Variablen auf diese Werte, auch wenn der Code bereits andere Werte werden zugewiesen hat.  
  
 Jedes Mitglied eine Strukturvariable wird initialisiert, als handele es sich um eine separate Variable. Auf ähnliche Weise wird jedes Element einer Arrayvariablen einzeln initialisiert.  
  
 Variablen in einem Block innerhalb einer Prozedur deklariert (z. B. eine `For` Schleife) beim Einstieg in die Prozedur initialisiert werden. Diese Initialisierungen werden wirksam, und zwar unabhängig davon, ob Code den Block jemals ausgeführt wird.  
  
## <a name="end-of-lifetime"></a>Ende der Lebensdauer  
 Wenn eine Prozedur beendet wird, die Werte ihrer lokalen Variablen werden nicht beibehalten und Visual Basic gibt ihren Speicher frei. Das nächste Mal der Prozedur aufrufen sind alle lokalen Variablen neuem erstellt und erneut initialisiert.  
  
 Wenn eine Instanz einer Klasse oder Struktur beendet wird, verlieren ihre nicht freigegebenen Variablen ihren Speicher und deren Werte. Jede neue Instanz der Klasse oder Struktur erstellt und initialisiert deren nicht freigegebenen Variablen. Allerdings `Shared` Variablen werden beibehalten, bis die Anwendung beendet wird.  
  
## <a name="extension-of-lifetime"></a>Erweiterung der Lebensdauer  
 Wenn Sie eine lokale Variable mit deklarieren die `Static` -Schlüsselwort, dessen Lebensdauer ist länger dauert als die Ausführung der Prozedur. Die folgende Tabelle zeigt, wie wie lange der Prozedurdeklaration eine `Static` Variable vorhanden ist.  
  
|Prozedurspeicherort und freigeben|Beginnt die Lebensdauer der statischen Variablen|Die Lebensdauer der statischen Variablen endet|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|In einem Modul (standardmäßig freigegeben)|Das erste Mal wird die Prozedur aufgerufen.|Wenn die Anwendung beendet wird|  
|In einer Klasse `Shared` (der Prozedur ist nicht auf einen Instanzmember)|Das erste Mal wird die Prozedur auf eine bestimmte Instanz oder der Name der Klasse oder Struktur selbst aufgerufen|Wenn die Anwendung beendet wird|  
|In einer Instanz einer Klasse nicht `Shared` (Prozedur ist ein Instanzmember)|Die Prozedur, auf die jeweilige Instanz aufgerufen wird zum ersten Mal|Wenn die Instanz freigegeben wird, für die Garbagecollection (GC)|  
  
## <a name="static-variables-of-the-same-name"></a>Statische Variablen mit dem gleichen Namen  
 Sie können statische Variablen mit dem gleichen Namen in mehr als eine Prozedur deklarieren. Wenn Sie so vorgehen, berücksichtigt Visual Basic-Compiler jede dieser Variablen für ein einzelnes Element sein. Die Initialisierung einer dieser Variablen wirkt sich nicht auf die Werte der anderen aus. Dasselbe gilt, wenn Sie eine Prozedur mit einer Reihe von Überladungen definieren und deklarieren Sie eine statische Variable mit dem gleichen Namen in jeder Überladung.  
  
## <a name="containing-elements-for-static-variables"></a>Enthält Elemente für statische Variablen  
 Sie können eine statische lokale Variable innerhalb einer Klasse, d. h. innerhalb einer Prozedur in dieser Klasse deklarieren. Allerdings kann keine statische lokale Variablen in einer Struktur als Member einer Struktur oder als lokale Variable einer Prozedur innerhalb dieser Struktur deklariert werden.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel deklariert eine Variable mit dem [statische](../../../../visual-basic/language-reference/modifiers/static.md) Schlüsselwort. (Beachten Sie, die Sie nicht benötigen die `Dim` Schlüsselwort bei der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) verwendet einen Modifizierer, z. B. `Static`.)  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrKeywords#13](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]  
  
### <a name="comments"></a>Kommentare  
 Im vorherigen Beispiel, die Variable `applesSold` weiterhin nach wie vor vorhanden `runningTotal` an den aufrufenden Code zurückgibt. Das nächste Mal `runningTotal` aufgerufen wird, `applesSold` den zuvor berechneten Wert beibehält.  
  
 Wenn `applesSold` deklariert wurde ohne `Static`, die gesammelten Werte würde in den Aufrufen nicht beibehalten werden `runningTotal`. Das nächste Mal `runningTotal` aufgerufen wurde, `applesSold` würde neu erstellt und mit 0 (null) initialisiert wurden und `runningTotal` einfach zurückgegeben hätte den gleichen Wert, mit denen er aufgerufen wurde.  
  
### <a name="compiling-the-code"></a>Kompilieren des Codes  
 Sie können den Wert einer statischen lokalen Variablen als Teil der Deklaration initialisiert werden. Wenn Sie ein Array zu deklarieren `Static`, können Sie deren Rang (Anzahl der Dimensionen), die Länge jeder Dimension und die Werte der einzelnen Elemente initialisieren.  
  
### <a name="security"></a>Sicherheit  
 Im vorherigen Beispiel können Sie dieselbe Lebensdauer erzeugen, indem deklarieren `applesSold` auf Modulebene. Wenn Sie den Bereich einer Variablen auf diese Weise geändert, jedoch müssten die Prozedur nicht mehr exklusiven Zugriff darauf. Da andere Prozeduren zugreifen konnte `applesSold` und dessen Wert, der laufenden Summe ist möglicherweise nicht zuverlässig und der Code möglicherweise schwieriger zu verwalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Shared](../../../../visual-basic/language-reference/modifiers/shared.md)  
 [Nothing](../../../../visual-basic/language-reference/nothing.md)  
 [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)  
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)  
 [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)
