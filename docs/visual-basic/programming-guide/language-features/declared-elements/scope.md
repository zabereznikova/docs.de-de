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
ms.openlocfilehash: d6692379626d787b728d6e92bd447c4a96e6680e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656294"
---
# <a name="scope-in-visual-basic"></a>Gültigkeitsbereich in Visual Basic
Die *Bereich* eines deklarierten Elements ist die Menge des gesamten Codes, die darauf verweisen kann, ohne seinen Namen qualifizieren oder durch Verfügbarmachen einer [Imports-Anweisung (.NET Namespace und Typ)](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md). Ein Element kann in einem der folgenden Ebenen Bereich aufweisen:  
  
|Ebene|Beschreibung|  
|-----------|-----------------|  
|Blockbereich|Verfügbar nur innerhalb des Codes blockiert, in dem sie deklariert ist|  
|Prozedurbereich|Verfügbar für sämtlichen Code innerhalb der Prozedur, die in der sie deklariert ist|  
|Modulbereich|Verfügbar für sämtlichen Code innerhalb das Modul, Klasse oder Struktur, die in der sie deklariert ist|  
|Namespace-Gültigkeitsbereich|Verfügbar für den gesamten Code im Namespace, in dem sie deklariert ist|  
  
 Diese Ebenen Bereich Status aus dem engsten (Block) auf den umfassendsten (Namespace), in denen *engsten Gültigkeitsbereich* bedeutet, dass die kleinste Menge der Code, der auf das Element ohne Qualifizierung verweisen kann. Weitere Informationen finden Sie unter "Ebenen Scope" auf dieser Seite.  
  
## <a name="specifying-scope-and-defining-variables"></a>Festlegen des Gültigkeitsbereichs und Definieren von Variablen  
 Wenn Sie deklariert werden, geben Sie den Bereich eines Elements. Der Bereich kann die folgenden Faktoren abhängig:  
  
-   Die Region (Block, Prozedur, Modul, Klasse oder Struktur), in der Sie das Element deklariert werden  
  
-   Der Namespace, die die Deklaration des Elements enthält.  
  
-   Die Zugriffsebene, die Sie für das Element deklarieren  
  
 Gehen Sie sorgfältig vor, wenn Sie Variablen mit dem gleichen Namen, aber andere Bereiche definieren, da dies zu erheblichen kann zu unerwarteten Ergebnissen führen. Weitere Informationen finden Sie unter [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md).  
  
## <a name="levels-of-scope"></a>Ebenen des Gültigkeitsbereichs  
 Ein Programmierelement ist verfügbar in der Region, in der Sie deklariert werden. Der gesamte Code in der gleichen Region kann auf das Element verweisen, ohne dessen Namen zu qualifizieren.  
  
### <a name="block-scope"></a>Blockbereich  
 Ein Block ist eine Reihe von Anweisungen eingefasst initiiert und beendet deklarationsanweisungen, wie z. B. die folgenden:  
  
-   `Do` und `Loop`  
  
-   `For` [`Each`] und `Next`  
  
-   `If` und `End If`  
  
-   `Select` und `End Select`  
  
-   `SyncLock` und `End SyncLock`  
  
-   `Try` und `End Try`  
  
-   `While` und `End While`  
  
-   `With` und `End With`  
  
 Wenn Sie eine Variable innerhalb eines Blocks zu deklarieren, können Sie es nur innerhalb dieses Blocks verwenden. Im folgenden Beispiel, den Bereich der ganzzahligen Variablen `cube` wird der Block zwischen `If` und `End If`, und Sie können nicht mehr beziehen sich auf `cube` Wenn die Ausführung aus dem Block übergeben.  
  
```  
If n < 1291 Then  
    Dim cube As Integer  
    cube = n ^ 3  
End If  
```  
  
> [!NOTE]
>  Auch wenn der Gültigkeitsbereich einer Variablen auf einen Block beschränkt ist, ist seine Lebensdauer immer noch der gesamten Prozedur. Wenn Sie den Block während der Prozedur mehr als einmal eingeben, behält jede Blockvariable seinen ursprünglichen Wert. Um unerwartete Ergebnisse in einem solchen Fall zu vermeiden, ist es ratsam, Block Variablen am Anfang des Blocks zu initialisieren.  
  
### <a name="procedure-scope"></a>Prozedurbereich  
 Ein Element innerhalb einer Prozedur deklariert ist nicht außerhalb dieser Prozedur verfügbar. Nur die Prozedur, die die Deklaration enthält können. Variablen, die auf dieser Ebene werden auch bezeichnet als *lokale Variablen*. Sie deklarieren sie mit der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md)mit oder ohne die [statische](../../../../visual-basic/language-reference/modifiers/static.md) Schlüsselwort.  
  
 Verfahren und der Blockbereich sind eng miteinander verknüpft. Wenn Sie eine Variable innerhalb einer Prozedur deklarieren, jedoch außerhalb aller Blöcke innerhalb der Prozedur, können Sie die Variable als Blockbereich, wobei der Block die gesamte Prozedur ist vorstellen.  
  
> [!NOTE]
>  Alle lokalen Elemente, auch wenn sie sind `Static` Variablen sind privat, an die Prozedur in der sie angezeigt werden. Sie können nicht deklariert werden alle-Element mithilfe der [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) Schlüsselwort innerhalb einer Prozedur.  
  
### <a name="module-scope"></a>Modulbereich  
 Der Einfachheit halber einen einzelnen Ausdruck *Modulebene* gilt gleichermaßen für Module, Klassen und Strukturen. Sie können Elemente auf dieser Ebene platzieren der deklarationsanweisung außerhalb von Prozeduren oder Block, jedoch innerhalb das Modul, Klasse oder Struktur deklarieren.  
  
 Wenn Sie eine Deklaration auf Modulebene vornehmen, bestimmt die Zugriffsebene, die Sie auswählen, den Bereich an. Der Namespace, der das Modul, Klasse oder Struktur enthält, wirkt sich auch auf den Bereich aus.  
  
 Elemente, die für die Sie deklarieren [Private](../../../../visual-basic/language-reference/modifiers/private.md) Zugriffsebene zur Verfügung stehen, um jede Prozedur in diesem Modul, jedoch nicht zu jedem Code in einem anderen Modul. Die `Dim` Anweisung auf Modulebene standardmäßig `Private` , wenn Sie keine Zugriffsebenen-Schlüsselwörter verwenden. Allerdings möglich den Bereich und die erforderlichen Zugriffsebenen leichter mithilfe der `Private` -Schlüsselwort in der `Dim` Anweisung.  
  
 Im folgenden Beispiel können alle im Modul definierte Prozeduren verweisen, der Zeichenfolgenvariablen `strMsg`. Wenn die zweite Prozedur aufgerufen wird, zeigt er den Inhalt der Zeichenfolgenvariablen `strMsg` in einem Dialogfeld.  
  
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
  
### <a name="namespace-scope"></a>Namespace-Gültigkeitsbereich  
 Wenn Sie ein Element an das Modul mit deklarieren die ["Friend"](../../../../visual-basic/language-reference/modifiers/friend.md) oder [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md) -Schlüsselwort verwenden, steht es für alle Prozeduren in der gesamten den Namespace, in dem das Element deklariert wird. Mit der folgenden Änderung im vorhergehenden Beispiel, die Zeichenfolgenvariable `strMsg` können von Code an einer beliebigen Stelle in den Namespace der Deklaration bezeichnet werden.  
  
```  
' Include this declaration at module level (not inside any procedure).  
Public strMsg As String  
```  
  
 Namespace-Gültigkeitsbereich enthält geschachtelte Namespaces. Ein Element innerhalb eines Namespaces zur Verfügung steht auch auf in allen Namespaces, die in diesem Namespace geschachtelt.  
  
 Wenn Ihr Projekt keine enthält [Namespace-Anweisung](../../../../visual-basic/language-reference/statements/namespace-statement.md)s, alles im Projekt befindet sich im gleichen Namespace. In diesem Fall kann der Namespace-Gültigkeitsbereich als Projektumfang betrachtet werden. `Public` Elemente in einem Modul, Klasse oder Struktur stehen auch zu einem Projekt, die ihr Projekt verweist.  
  
## <a name="choice-of-scope"></a>Auswahl eines Bereichs  
 Wenn Sie eine Variable deklarieren, sollten Sie die folgenden Punkte bedenken bei der Auswahl des Bereichs.  
  
### <a name="advantages-of-local-variables"></a>Vorteile von lokalen Variablen  
 Lokale Variablen sind eine gute Wahl für alle Arten von temporären Berechnung folgende Gründe vorliegen:  
  
-   **Vermeidung von Namenskonflikten.** Namen lokaler Variable sind nicht anfällig für in Konflikt stehen. Sie können z. B. mehrere unterschiedliche Verfahren, die eine Variable Namens enthält erstellen `intTemp`. Solange jeder `intTemp` wird deklariert als lokale Variable, jede Prozedur erkennt nur ihre eigene Version der `intTemp`. Jede Prozedur ändern, kann den Wert in der lokalen `intTemp` ohne `intTemp` Variablen in anderen Prozeduren.  
  
-   **Speicherverbrauch.** Lokale Variablen belegt Arbeitsspeicher nur, wenn die Prozedur ausgeführt wird. Ihre Arbeitsspeicher wird freigegeben, wenn die Prozedur an den aufrufenden Code zurückgibt. Im Gegensatz dazu [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) und [statische](../../../../visual-basic/language-reference/modifiers/static.md) Variablen Arbeitsspeicherressourcen beanspruchen, bis die Anwendung beendet wird, werden daher nur bei Bedarf verwendet. *Instanzvariablen* belegt Arbeitsspeicher während ihrer Instanz vorhanden weiterhin, sodass sie weniger effizient als lokale Variablen, aber möglicherweise effizienter als `Shared` oder `Static` Variablen.  
  
### <a name="minimizing-scope"></a>Minimieren des Gültigkeitsbereichs  
 Wenn Sie eine Variable oder Konstante deklarieren, wird es im Allgemeinen als guter Programmierstil, um den Bereich so eng wie möglich zu machen (Blockbereich ist die engste). Dies hilft, Speicherplatz zu sparen und minimiert die Wahrscheinlichkeit des Codes, die fälschlicherweise auf die falsche Variable verweisen. Ebenso sollten Sie eine Variable deklarieren [statische](../../../../visual-basic/language-reference/modifiers/static.md) nur wenn Objektwerts zwischen Prozeduraufrufe beibehalten werden muss.  
  
## <a name="see-also"></a>Siehe auch  
 [Merkmale deklarierter Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)  
 [Gewusst wie: Steuern des Gültigkeitsbereichs einer Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-control-the-scope-of-a-variable.md)  
 [Lebensdauer in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Zugriffsebenen in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)  
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
