---
title: Gültigkeitsbereich in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- module scope [Visual Basic]
- scope [Visual Basic], levels
- module level
- procedures [Visual Basic], scope
- declared elements [Visual Basic], scope
- namespaces [Visual Basic], scope
- scope [Visual Basic], declared elements
- scope [Visual Basic], about scope
- levels of scope [Visual Basic]
- block scope [Visual Basic]
- scope [Visual Basic], Visual Basic
- procedure scope [Visual Basic]
ms.assetid: 208106fe-79c9-4eec-93c6-55f08548895f
ms.openlocfilehash: 6139af65958cefe43578f436204fa6836a71de0b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917838"
---
# <a name="scope-in-visual-basic"></a>Gültigkeitsbereich in Visual Basic
Die *Bereich* eines deklarierten Elements ist ein Satz von sämtlicher Code, die darauf verweisen kann, ohne seinen Namen qualifizieren oder durch Verfügbarmachen, einer [Imports-Anweisung (.NET-Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md). Ein Element kann eine der folgenden Ebenen Bereich sein:  
  
|Ebene|Beschreibung|  
|-----------|-----------------|  
|Blockbereich|Verfügbar nur in den Code blockieren, in dem sie deklariert ist|  
|Prozedurbereich|Verfügbar für sämtlichen Code innerhalb der Prozedur, die in der sie deklariert ist|  
|Modulbereich|Verfügbar für sämtlichen Code innerhalb der Module, Klasse oder Struktur, die in der sie deklariert ist|  
|Namespace-Bereich|Verfügbar für den gesamten Code in den Namespace, in dem sie deklariert ist|  
  
 Diese Ebenen des Status von engsten (Block) die größtmögliche (Namespace), Bereich, in denen *engsten Gültigkeitsbereich* bedeutet, dass die kleinste Menge der Code, der auf das Element ohne Qualifikation verweisen kann. Weitere Informationen finden Sie unter "Ebenen von Scope" auf dieser Seite.  
  
## <a name="specifying-scope-and-defining-variables"></a>Festlegen des Gültigkeitsbereichs und Definieren von Variablen  
 Wenn Sie sie deklarieren, geben Sie den Bereich eines Elements. Der Bereich kann auf folgenden Faktoren abhängen:  
  
- Die Region (Block, Prozedur, Modul, Klasse oder Struktur), in der Sie das Element deklarieren.  
  
- Der Namespace, enthält die Deklaration des Elements  
  
- Die Zugriffsebene, die Sie für das Element deklarieren.  
  
 Gehen Sie sorgfältig vor, wenn Sie Variablen mit dem gleichen Namen, aber anderen Bereich definieren, da dies kann zu unerwarteten Ergebnissen führen. Weitere Informationen finden Sie unter [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="levels-of-scope"></a>Bereichsebenen  
 Ein Programmierelement ist verfügbar in der Region, in der Sie sie deklarieren. Der gesamte Code in der gleichen Region kann auf das Element ohne Angabe ihres Namens verweisen.  
  
### <a name="block-scope"></a>Blockbereich  
 Ein Block ist ein Satz von eingefasst wird initiiert, und Beenden von deklarationsanweisungen, wie z. B. die folgenden Anweisungen:  
  
- `Do` und `Loop`  
  
- `For` [`Each`] und `Next`  
  
- `If` und `End If`  
  
- `Select` und `End Select`  
  
- `SyncLock` und `End SyncLock`  
  
- `Try` und `End Try`  
  
- `While` und `End While`  
  
- `With` und `End With`  
  
 Wenn Sie eine Variable in einem Block deklarieren, können Sie es nur innerhalb dieses Blocks. Im folgenden Beispiel ist der Bereich der ganzzahligen Variable `cube` der Block zwischen `If` und `End If`, und Sie können nicht mehr auf verweisen `cube` Wenn die Ausführung aus dem Block übergeben.  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  Auch wenn der Bereich einer Variablen auf einen Block beschränkt ist, ist seine Lebensdauer immer noch die gesamte Prozedur. Wenn Sie den Block während des Verfahrens mehrmals eingeben, behält jede Blockvariable seinen ursprünglichen Wert. Um unerwartete Ergebnisse in einem solchen Fall zu vermeiden, ist es klug, Block Variablen am Anfang des Blocks zu initialisieren.  
  
### <a name="procedure-scope"></a>Prozedurbereich  
 Ein Element innerhalb einer Prozedur ist nicht verfügbar ist, außerhalb dieser Prozedur. Nur die Prozedur, die die Deklaration enthält, können sie verwenden. Variablen, die auf dieser Ebene werden auch bezeichnet als *lokale Variablen*. Sie deklarieren sie mit der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)mit oder ohne die [statische](../../../../visual-basic/language-reference/modifiers/static.md) Schlüsselwort.  
  
 Verfahren und der Blockbereich sind eng miteinander verknüpft. Wenn Sie eine Variable innerhalb einer Prozedur deklarieren, aber außerhalb aller Blöcke in diesem Verfahren werden soll, stellen Sie sich die Variable als Blockbereich, wobei der Block für die gesamte Prozedur ist.  
  
> [!NOTE]
>  Alle lokalen Elemente, auch wenn sie `Static` Variablen sind privat für die Prozedur, die in der sie angezeigt werden. Kann nicht deklariert werden alle-Element mithilfe der [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) Schlüsselwort in einer Prozedur.  
  
### <a name="module-scope"></a>Modulbereich  
 Der Einfachheit halber einen einzelnen Ausdruck *auf Modulebene* gilt gleichermaßen für Module, Klassen und Strukturen. Sie können Elemente auf dieser Ebene platzieren der deklarationsanweisung außerhalb von Prozeduren oder blockieren, aber in das Modul, Klasse oder Struktur deklarieren.  
  
 Wenn Sie eine Deklaration auf Modulebene vornehmen, bestimmt die Zugriffsebene, die Sie auswählen, den Bereich an. Der Namespace, der das Modul, Klasse oder Struktur enthält, wirkt sich auch auf den Bereich aus.  
  
 Elemente, die für die Sie deklarieren [Private](../../../../visual-basic/language-reference/modifiers/private.md) Zugriffsebene zur Verfügung stehen, auf alle Prozeduren in diesem Modul, aber nicht auf Code in einem anderen Modul. Die `Dim` Anweisung auf Modulebene standardmäßig `Private` , wenn Sie keine Zugriffsebenen-Schlüsselwörter verwenden. Allerdings möglich den Bereich und die Zugriffsebene offensichtlicheren mithilfe der `Private` -Schlüsselwort in der `Dim` Anweisung.  
  
 Im folgenden Beispiel können alle im Modul definierte Prozeduren verweisen, der Zeichenfolgenvariablen `strMsg`. Wenn die zweite Prozedur aufgerufen wird, zeigt es den Inhalt der Zeichenfolgenvariablen `strMsg` in einem Dialogfeld.  
  
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
 Wenn Sie ein Element an das Modul mit deklarieren die [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) oder [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort, es wird für alle Prozeduren während des gesamten Namespace in der das Element deklariert wird. Durch die folgende Änderung zum vorherigen Beispiel die Zeichenfolgenvariable `strMsg` kann vom Code an einer beliebigen Stelle in den Namespace der Deklaration verwiesen werden.  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 Namespace-Gültigkeitsbereich enthält geschachtelte Namespaces. Ein Element in einem Namespace verfügbar ist auch in jedem Namespace, die in diesem Namespace geschachtelt verfügbar.  
  
 Wenn Ihr Projekt keine enthält [Namespace-Anweisung](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, alles im Projekt wird im selben Namespace. In diesem Fall kann der Namespace-Gültigkeitsbereich als Projektumfang betrachtet werden. `Public` Elemente in einem Modul, Klasse oder Struktur sind auch verfügbar, um Projekte, die ihr Projekt verweist.  
  
## <a name="choice-of-scope"></a>Auswahl des Bereichs  
 Wenn Sie eine Variable deklarieren, sollten Sie die folgenden Punkte bedenken bei der Auswahl ihres Bereichs.  
  
### <a name="advantages-of-local-variables"></a>Vorteile von lokalen Variablen  
 Lokale Variablen sind eine gute Wahl für alle Arten von temporären Berechnungen aus, die aus den folgenden Gründen:  
  
- **Namenskonflikt vermeiden.** Namen lokaler Variable sind nicht anfällig gegenüber in Konflikt stehen. Sie können z. B. mehrere unterschiedliche Verfahren, die eine Variable namens erstellen `intTemp`. Solange alle `intTemp` wird deklariert als lokale Variable, jede Prozedur erkennt nur ihre eigene Version der `intTemp`. Jede Prozedur ändern, kann den Wert in der lokalen `intTemp` ohne `intTemp` Variablen in anderen Prozeduren.  
  
- **Die Arbeitsspeichernutzung.** Lokale Variablen belegt Arbeitsspeicher nur, solange die Prozedur ausgeführt wird. Ihren Arbeitsspeicher wird freigegeben, wenn die Prozedur an den aufrufenden Code zurückgibt. Im Gegensatz dazu [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) und [statische](../../../../visual-basic/language-reference/modifiers/static.md) Variablen Speicherressourcen beanspruchen, bis die Anwendung beendet wird, werden Sie also nur bei Bedarf verwendet. *Instanzvariablen* belegt Arbeitsspeicher während ihrer Instanz vorhanden weiterhin, was weniger effizient als lokale Variablen, aber möglicherweise effizienter als die `Shared` oder `Static` Variablen.  
  
### <a name="minimizing-scope"></a>Bereich minimiert  
 Wenn Sie eine Variable oder Konstante zu deklarieren, wird es im Allgemeinen guter Programmierstil, um den Bereich so eng wie möglich zu machen (Blockbereich ist die geringstmögliche). Dadurch wird Speicherplatz gespart und minimiert die Wahrscheinlichkeit, dass Ihr Code, der fälschlicherweise die falsche Variable auf. Ebenso sollten Sie eine Variable deklarieren [statische](../../../../visual-basic/language-reference/modifiers/static.md) nur wenn den Wert zwischen den Prozeduraufrufen beibehalten werden muss.  
  
## <a name="see-also"></a>Siehe auch

- [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)
- [Vorgehensweise: Steuern des Gültigkeitsbereichs einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)
- [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)
- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
