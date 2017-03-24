---
title: Lebensdauer in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- static variables, lifetime
- static variables, Visual Basic
- declared elements, lifetime
- Shared variable lifetime
- lifetime, declared elements
- lifetime, Visual Basic
- lifetime
ms.assetid: bd91e390-690a-469a-9946-8dca70bc14e7
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: fa0cbdf4a8fe5e8fc41e4e4f373c79451fb7b75f
ms.lasthandoff: 03/13/2017

---
# <a name="lifetime-in-visual-basic"></a>Lebensdauer in Visual Basic
Die *Lebensdauer* eines deklarierten Elements ist der Zeitraum der sie verwendet werden kann. Variablen sind die einzigen Elemente, die Lebensdauer haben. Zu diesem Zweck behandelt der Compiler Prozedurparameter und Funktionsrückgaben als Sonderfälle von Variablen. Die Lebensdauer einer Variablen ist der Zeitraum in dem sie einen Wert enthalten kann. Der Wert kann während ihrer Lebensdauer ändern, aber er enthält immer einen Wert.  
  
## <a name="different-lifetimes"></a>Unterschiedliche Lebensdauer  
 Ein *Membervariable* (auf Modulebene, außerhalb einer Prozedur deklariert) hat in der Regel die gleiche Lebensdauer wie das Element, in dem sie deklariert ist. Eine nicht freigegebene Variable in einer Klasse oder Struktur deklariert ist vorhanden, als separate Kopie für jede Instanz der Klasse oder Struktur, in der sie deklariert ist. Jede dieser Variablen hat die gleiche Lebensdauer wie ihre Instanz. Allerdings eine `Shared` Variable hat nur eine Lebensdauer, die über die gesamte Zeit reicht die Anwendung ausgeführt wird.  
  
 Ein *lokale Variable* (deklariert in einer Prozedur) vorhanden ist, nur während der Ausführung der Prozedur, in der sie deklariert ist. Dies gilt auch, um die Parameter der Prozedur und eine Funktion zurück. Wenn die Prozedur andere Prozeduren aufruft, behalten jedoch die lokalen Variablen ihre Werte während der aufgerufenen Prozeduren ausgeführt werden.  
  
## <a name="beginning-of-lifetime"></a>Anfang der Lebensdauer  
 Lebensdauer einer lokalen Variablen beginnt bei einem Wechsel Steuerelement die Prozedur in der sie deklariert ist. Jede lokale Variable wird auf den Standardwert für seinen Datentyp initialisiert, sobald die Prozedur beginnt ausgeführt wird. Wenn die Prozedur trifft eine `Dim` Anweisung, die Anfangswerte angibt, wird diese Variablen auf diese Werte, auch wenn der Code bereits andere Werte dafür zugewiesen hat.  
  
 Jeder Member einer Strukturvariablen wird wie eine separate Variable initialisiert. Auf ähnliche Weise wird jedes Element einer Arrayvariablen einzeln initialisiert.  
  
 Variablen, die in einem Block innerhalb einer Prozedur deklariert (z. B. eine `For` Schleife) werden beim Eintritt in die Prozedur initialisiert. Diese Initialisierungen werden wirksam, und zwar unabhängig davon, ob der Code den Block jemals ausgeführt wird.  
  
## <a name="end-of-lifetime"></a>Ende der Lebensdauer  
 Wenn eine Prozedur beendet wird, werden die Werte ihrer lokalen Variablen nicht erhalten, und [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gibt ihren Speicher frei. Beim nächsten der Prozedur aufrufen werden alle lokalen Variablen neuem erstellt und erneut initialisiert.  
  
 Wenn eine Instanz einer Klasse oder Struktur beendet wird, verlieren die nicht freigegebenen Variablen ihren Arbeitsspeicher und ihre Werte. Jede neue Instanz der Klasse oder Struktur erstellt und initialisiert die nicht freigegebenen Variablen. Allerdings `Shared` Variablen bleiben erhalten, bis die Anwendung beendet wird.  
  
## <a name="extension-of-lifetime"></a>Erweiterung der Lebensdauer  
 Wenn Sie deklarieren, dass eine lokale Variable mit der `Static` -Schlüsselwort, dessen Lebensdauer ist länger als die Ausführungszeit des Verfahrens. Die folgende Tabelle zeigt, wie die Prozedurdeklaration wie lange bestimmt ein `Static` Variable vorhanden ist.  
  
|Prozedurspeicherort und Freigabe|Lebensdauer der statischen Variablen beginnt|Lebensdauer der statischen Variablen endet|  
|------------------------------------|-------------------------------------|-----------------------------------|  
|In einem Modul (standardmäßig freigegeben)|Das erste Mal wird die Prozedur aufgerufen.|Wenn die Anwendung beendet wird|  
|In einer Klasse `Shared` (Prozedur ist kein Instanzmember)|Nennen Sie beim ersten der Prozedur für eine bestimmte Instanz oder für die Klasse oder Struktur Aufruf selbst|Wenn die Anwendung beendet wird|  
|In einer Instanz einer Klasse nicht `Shared` (Prozedur ist ein Instanzmember)|Beim ersten wird die Prozedur auf die jeweilige Instanz aufgerufen.|Wenn die Instanz für die Garbagecollection (GC) freigegeben wird|  
  
## <a name="static-variables-of-the-same-name"></a>Statische Variablen mit demselben Namen  
 Sie können statische Variablen mit dem gleichen Namen in mehr als eine Prozedur deklarieren. Wenn Sie dies tun, die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler betrachtet jede dieser Variablen für ein einzelnes Element sein. Die Initialisierung einer dieser Variablen wirkt sich nicht auf die Werte der anderen aus. Dasselbe gilt, wenn Sie eine Prozedur mit einer Reihe von Überladungen und deklarieren Sie eine statische Variable mit dem gleichen Namen in jeder Überladung.  
  
## <a name="containing-elements-for-static-variables"></a>Enthaltende Elemente für statische Variablen  
 Sie können eine statische lokale Variable innerhalb einer Klasse, d. h. innerhalb einer Prozedur in dieser Klasse deklarieren. Sie können nicht jedoch eine statische lokale Variable in einer Struktur als Member einer Struktur oder als lokale Variable einer Prozedur innerhalb dieser Struktur deklarieren.  
  
## <a name="example"></a>Beispiel  
  
### <a name="description"></a>Beschreibung  
 Das folgende Beispiel deklariert eine Variable mit dem [statische](../../../../visual-basic/language-reference/modifiers/static.md) Schlüsselwort. (Beachten Sie, die Sie nicht benötigen die `Dim` Schlüsselwort bei der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) ein Modifizierer wie z. B. verwendet `Static`.)  
  
### <a name="code"></a>Code  
 [!code-vb[VbVbalrKeywords&#13;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/lifetime_1.vb)]  
  
### <a name="comments"></a>Kommentare  
 Im vorhergehenden Beispiel die Variable `applesSold` bleibt nach dem Verfahren `runningTotal` an den aufrufenden Code zurückgegeben. Das nächste Mal `runningTotal` aufgerufen wird, `applesSold` den zuvor berechneten Wert beibehält.  
  
 Wenn `applesSold` deklariert wurde ohne `Static`, würden die gesammelten Werte nicht für Aufrufe von erhalten werden `runningTotal`. Das nächste Mal `runningTotal` aufgerufen wurde, `applesSold` wird neu erstellt und mit 0 initialisiert wurden und `runningTotal` einfach zurückgegeben hätte den gleichen Wert, mit denen er aufgerufen wurde.  
  
### <a name="compiling-the-code"></a>Kompilieren des Codes  
 Sie können den Wert einer statischen lokalen Variablen als Teil der Deklaration initialisiert werden. Wenn Sie ein Array zu deklarieren, `Static`, initialisieren Sie sein Rang (Anzahl der Dimensionen), die Länge jeder Dimension und die Werte der einzelnen Elemente.  
  
### <a name="security"></a>Sicherheit  
 Im vorhergehenden Beispiel können Sie dieselbe Lebensdauer erzeugen, indem Sie deklarieren `applesSold` auf Modulebene. Wenn Sie den Gültigkeitsbereich einer Variablen auf diese Weise geändert, jedoch müssten die Prozedur nicht mehr exklusiv auf. Andere Prozeduren zugegriffen `applesSold` und ändern Sie dessen Wert, die laufende Summe möglicherweise unzuverlässig, und der Code möglicherweise schwieriger zu verwalten.  
  
## <a name="see-also"></a>Siehe auch  
 [Freigegebene](../../../../visual-basic/language-reference/modifiers/shared.md)   
 [Nothing](../../../../visual-basic/language-reference/nothing.md)   
 [Namen deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Gültigkeitsbereich in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Variablen](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Deklaration von Objektvariablen](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)
