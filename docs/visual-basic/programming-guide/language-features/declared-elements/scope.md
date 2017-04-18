---
title: "Gültigkeitsbereich in Visual Basic | Microsoft-Dokumentation"
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
- module scope
- scope, levels
- module level
- procedures, scope
- declared elements, scope
- namespaces, scope
- scope, declared elements
- scope, about scope
- levels of scope
- block scope
- scope, Visual Basic
- procedure scope
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
caps.latest.revision: 17
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
ms.openlocfilehash: 28e096f9e35a4981d66752f204ed57b25116e8c8
ms.lasthandoff: 03/13/2017

---
# <a name="scope-in-visual-basic"></a>Gültigkeitsbereich in Visual Basic
Die *Bereich* eines deklarierten Elements ist ein Satz von Code, die darauf verweisen kann, ohne seinen Namen qualifizieren oder durch Verfügbarmachen, einer [Imports-Anweisung (.NET Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md). Ein Element kann an einem der folgenden Ebenen Bereich aufweisen:  
  
|Ebene|Beschreibung|  
|-----------|-----------------|  
|Blockbereich|Verfügbar nur innerhalb des Codes blockieren, in dem sie deklariert ist|  
|Prozedurbereich|Für sämtlichen Code innerhalb der Prozedur, in der sie deklariert ist, verfügbar|  
|Modulbereich|Für den gesamten Code im Modul, Klasse oder Struktur, in der sie deklariert ist, verfügbar|  
|Namespace-Bereich|Für den gesamten Code im Namespace, in dem sie deklariert ist, verfügbar|  
  
 Diese Ebenen des Gültigkeitsbereichs steigern vom engsten (Block) auf den längsten (Namespace), wobei *engsten Gültigkeitsbereich* bedeutet, dass die kleinste Menge der Code, der ohne Qualifizierung auf dieses Element verweisen kann. Weitere Informationen finden Sie unter "Ebenen des Gültigkeitsbereichs" auf dieser Seite.  
  
## <a name="specifying-scope-and-defining-variables"></a>Festlegen des Gültigkeitsbereichs und Definieren von Variablen  
 Sie geben den Umfang eines Elements, wenn Sie deklariert werden. Der Bereich kann von folgenden Faktoren abhängen:  
  
-   Die Region (Block, Prozedur, Modul, Klasse oder Struktur), in der Sie das Element deklarieren  
  
-   Der Namespace, die die Deklaration des Elements enthält.  
  
-   Die Zugriffsebene, die Sie für das Element deklarieren  
  
 Gehen Sie sorgfältig vor, wenn Sie Variablen mit demselben Namen, aber andere Bereiche definieren, da dies kann zu unerwarteten Ergebnissen führen. Weitere Informationen finden Sie unter [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="levels-of-scope"></a>Ebenen des Gültigkeitsbereichs  
 Ein Programmierelement steht innerhalb der Region, in der Sie deklariert werden. Der gesamte Code in der gleichen Region kann auf das Element verweisen, ohne dessen Namen zu qualifizieren.  
  
### <a name="block-scope"></a>Blockbereich  
 Ein Block ist eine Gruppe von Anweisungen, die innerhalb der starten und Beenden von deklarationsanweisungen, wie z. B. die folgenden:  
  
-   `Do` und `Loop`  
  
-   `For`[`Each`] and`Next`  
  
-   `If` und `End If`  
  
-   `Select` und `End Select`  
  
-   `SyncLock` und `End SyncLock`  
  
-   `Try` und `End Try`  
  
-   `While` und `End While`  
  
-   `With` und `End With`  
  
 Wenn Sie eine Variable innerhalb eines Blocks zu deklarieren, können Sie es nur innerhalb dieses Blocks. Im folgenden Beispiel den Bereich der ganzzahligen Variable `cube` der Block zwischen `If` und `End If`, und Sie können nicht mehr verweisen `cube` bei Ausführung aus dem Block weitergegeben.  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  Auch wenn der Gültigkeitsbereich einer Variablen auf einen Block beschränkt ist, ist seine Lebensdauer immer noch die gesamte Prozedur. Wenn Sie den Block mehrmals während des Verfahrens eingeben, behält jede Blockvariable den vorhergehenden Wert. Um unerwartete Ergebnisse in einem solchen Fall zu vermeiden, ist es ratsam, Block Variablen am Anfang des Blocks zu initialisieren.  
  
### <a name="procedure-scope"></a>Prozedurbereich  
 Ein Element innerhalb einer Prozedur ist nicht außerhalb dieser Prozedur verfügbar. Nur die Prozedur, die die Deklaration enthält können. Elemente auf dieser Ebene werden auch bekannt als *lokale Variablen*. Sie deklarieren sie mit der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)mit oder ohne den [statische](../../../../visual-basic/language-reference/modifiers/static.md) Schlüsselwort.  
  
 Verfahren und der Blockbereich sind eng miteinander verknüpft. Wenn Sie eine Variable innerhalb einer Prozedur, aber außerhalb aller Blöcke in dieser Prozedur deklarieren, können Sie sich vorstellen der Variablen Blockbereich, wobei der Block die gesamte Prozedur ist.  
  
> [!NOTE]
>  Alle lokalen Elemente, auch wenn sie sind `Static` Variablen, für die Prozedur, in der sie erscheinen, privat sind. Kann nicht deklariert werden jedem Element mithilfe der [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) Schlüsselwort innerhalb einer Prozedur.  
  
### <a name="module-scope"></a>Modulbereich  
 Der Einfachheit halber der Begriff *Modulebene* gilt gleichermaßen für Module, Klassen und Strukturen. Sie können Elemente auf dieser Ebene die Deklaration-Anweisung außerhalb jeder Prozedur oder eines Blocks jedoch in Modul, Klasse oder Struktur deklarieren.  
  
 Wenn Sie eine Deklaration auf Modulebene vornehmen, bestimmt die Zugriffsebene, die Sie wählen den Bereich. Der Namespace, der das Modul, Klasse oder Struktur enthält, wirkt sich auch auf den Bereich aus.  
  
 Elemente, für die Sie deklarieren [Private](../../../../visual-basic/language-reference/modifiers/private.md) Zugriffsebene auf alle Prozeduren in diesem Modul, jedoch nicht für den gesamten Code in einem anderen Modul verfügbar sind. Die `Dim` -Anweisung auf Modulebene Standardwert `Private` , wenn Sie keine Zugriffsebenen-Schlüsselwörter verwenden. Allerdings Sie können den Gültigkeitsbereich und Zugriffsebene deutlicher über stellen die `Private` -Schlüsselwort in der `Dim` Anweisung.  
  
 Im folgenden Beispiel können alle im Modul definierte Prozeduren finden Sie in der Zeichenfolgenvariablen `strMsg`. Wenn die zweite Prozedur aufgerufen wird, wird es zeigt den Inhalt der Zeichenfolgenvariablen `strMsg` in einem Dialogfeld.  
  
```  
' Put the following declaration at module level (not in any procedure).  
Private strMsg As String  
' Put the following Sub procedure in the same module.  
Sub initializePrivateVariable()  
    strMsg = "This variable cannot be used outside this module."  
End Sub  
' Put the following Sub procedure in the same module.  
Sub usePrivateVariable()  
    MsgBox(strMsg)  
End Sub  
```  
  
### <a name="namespace-scope"></a>Namespace-Bereich  
 Wenn Sie ein Element an das Modul mit deklarieren die [Freund](../../../../visual-basic/language-reference/modifiers/friend.md) oder [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort, steht es allen Prozeduren des gesamten Namespace, in dem das Element deklariert wird. Durch die folgende Änderung zum vorherigen Beispiel, die Zeichenfolgenvariable `strMsg` können durch Code an einer beliebigen Stelle im Namespace der Deklaration bezeichnet werden.  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 Namespace-Bereich enthält geschachtelte Namespaces. Ein Element innerhalb eines Namespace verfügbar ist auch in jedem innerhalb dieses Namespace geschachtelten Namespace verfügbar.  
  
 Wenn das Projekt keine enthält [Namespace-Anweisung](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, alles im Projekt ist im selben Namespace. In diesem Fall kann der Namespacebereich als Projektumfang betrachtet werden. `Public`Elemente in einem Modul, Klasse oder Struktur stehen auch jedem Projekt, das auf ihr Projekt verweist.  
  
## <a name="choice-of-scope"></a>Auswahl des Gültigkeitsbereichs  
 Wenn Sie eine Variable deklarieren, sollten Sie die folgenden Punkte bedenken bei der Auswahl des Gültigkeitsbereichs.  
  
### <a name="advantages-of-local-variables"></a>Vorteile von lokalen Variablen  
 Lokale Variablen sind eine gute Wahl für alle Arten von temporären Berechnung aus den folgenden Gründen:  
  
-   **Vermeidung von Namenskonflikten.** Namen lokaler Variable sind nicht anfällig für in Konflikt stehen. Sie können z. B. mehrere verschiedene Prozeduren, die eine Variable namens erstellen `intTemp`. Solange jeder `intTemp` wird als deklariert eine lokale Variable, erkennen die einzelnen Prozeduren nur ihre eigene Version der `intTemp`. Jede Prozedur ändern, kann den Wert in der lokalen `intTemp` ohne `intTemp` -Variablen in anderen Prozeduren.  
  
-   **Speicherverbrauch.** Lokale Variablen belegen Arbeitsspeicher nur, wenn ihre Prozedur aktiv ist. Ihre Speicher wird freigegeben, wenn die Prozedur an den aufrufenden Code zurückgegeben. Im Gegensatz dazu [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) und [statische](../../../../visual-basic/language-reference/modifiers/static.md) Variablen Speicherressourcen beanspruchen, bis die Anwendung beendet wird, werden daher nur bei Bedarf verwendet. *Instanzvariablen* verbrauchen Speicher während ihrer Instanz vorhanden weiterhin, sodass sie weniger effizient als lokale Variablen, aber möglicherweise effizienter als `Shared` oder `Static` Variablen.  
  
### <a name="minimizing-scope"></a>Minimieren des Gültigkeitsbereichs  
 Wenn Sie eine Variable oder Konstante deklarieren, ist es im Allgemeinen guter Programmierstil, den Bereich so eng wie möglich machen (Blockbereich ist der engste). Dadurch wird Speicherplatz gespart und minimiert die Wahrscheinlichkeit des Codes fälschlicherweise auf die falsche Variable verweisen. Ebenso sollten Sie eine Variable deklarieren [statische](../../../../visual-basic/language-reference/modifiers/static.md) nur wenn es ihr Wert über mehrere Prozeduraufrufe hinweg erhalten bleiben muss.  
  
## <a name="see-also"></a>Siehe auch  
 [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)   
 [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
