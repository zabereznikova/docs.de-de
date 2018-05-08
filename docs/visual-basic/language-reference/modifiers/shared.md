---
title: Shared (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Shared
helpviewer_keywords:
- Shared keyword [Visual Basic]
- members [Visual Basic], shared
- shared members
- nonshared
- shared [elements VB]
- elements [Visual Basic], shared
ms.assetid: 2bf7cf2c-b0dd-485e-8749-b5d674dab4cd
ms.openlocfilehash: b15dd08d69f372317b9140001e8072eeb66d44ab
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte Programmierelemente einer Klasse oder Struktur an größeren, und nicht mit einer bestimmten Instanz der Klasse oder Struktur zugeordnet sind.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="when-to-use-shared"></a>Verwendung von Shared  
 Einen Member einer Klasse oder Struktur Freigabe verfügbar gemacht, jede Instanz statt *nicht freigegebene*, wobei jede Instanz eine eigene Kopie beibehält. Dies ist beispielsweise hilfreich, der Wert einer Variablen für die gesamte Anwendung gilt. Wenn Sie diese Variable zu deklarieren `Shared`, klicken Sie dann alle Instanzen am gleichen Speicherort, und wenn eine Instanz den Wert der Variablen ändert, alle Instanzen auf zugreifen den aktualisierten Wert.  
  
 Freigeben, wird die Zugriffsebene eines Members nicht verändert. Ein Klassenmember kann z. B. freigegeben werden und in "Privat" (kann nur zugegriffen werden innerhalb der Klasse), oder nicht freigegeben und öffentlich. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Sie können `Shared` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarationskontext für eine `Shared` Element einer Klasse oder Struktur, und eine Quelldatei, Namespace oder Prozedur nicht möglich.  
  
-   **Kombinierte Modifizierer.** Sie können keine angeben `Shared` zusammen mit [überschreibt](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), oder [ Statische](../../../visual-basic/language-reference/modifiers/static.md) in der gleichen Deklaration.  
  
-   **Beim Zugriff auf.** Sie greifen auf eine freigegebene Element durch die Qualifizierung mit dem Namen Klasse oder Struktur, nicht mit dem Variablennamen einer bestimmten Instanz ihrer Klasse oder Struktur. Sie müssen auch keinen zum Erstellen einer Instanz einer Klasse oder Struktur, um ihre freigegebenen Member zuzugreifen.  
  
     Im folgenden Beispiel wird die freigegebene Prozedur <xref:System.Double.IsNaN%2A> verfügbar gemacht werden, indem Sie die <xref:System.Double> Struktur.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   **Implizite Freigabe.** Können keine der `Shared` -Modifizierer in einer [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md), aber Konstanten sind implizit freigegeben. Auf ähnliche Weise kann nicht Mitglied von einem Modul oder eine Schnittstelle sein deklariert `Shared`, aber sie werden implizit freigegeben.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Speicher.** Eine freigegebene Variable oder ein Ereignis wird nur einmal auf, unabhängig davon, wie viele Instanzen der Klasse oder Struktur erstellen im Arbeitsspeicher gespeichert werden. Auf ähnliche Weise werden für eine freigegebene Prozedur oder Eigenschaft nur einen Satz von lokalen Variablen enthält.  
  
-   **Zugreifen auf über eine Instanzvariable.** Es ist möglich, die Zugriff auf eine freigegebene Element durch die Qualifizierung mit dem Namen einer Variablen, die eine bestimmte Instanz ihrer Klasse oder Struktur enthält. Obwohl dies in der Regel funktioniert wie erwartet, wird der Compiler eine Warnung generiert, und führt den Zugriff über den Namen der Klasse oder Struktur anstelle der Variablen.  
  
-   **Zugriff über einen Instanzausdruck.** Wenn Sie ein freigegebene Element durch einen Ausdruck, die eine Instanz der Klasse oder Struktur zurückgegeben wird zuzugreifen, führt der Compiler den Zugriff durch den Namen der Klasse oder Struktur anstelle von Auswertung des Ausdrucks an. Dies erzeugt unerwartete Ergebnisse, wenn Sie den Ausdruck zum Ausführen von anderen Aktionen sowie das Zurückgeben der Instanz, für die Verwendung vorgesehen. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
    ```  
    Sub main()  
        shareTotal.total = 10  
        ' The preceding line is the preferred way to access total.  
        Dim instanceVar As New shareTotal  
        instanceVar.total += 100  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of through  
        ' the variable instanceVar. This works as expected and adds  
        ' 100 to total.  
        returnClass().total += 1000  
        ' The preceding line generates a compiler warning message and  
        ' accesses total through class shareTotal instead of calling  
        ' returnClass(). This adds 1000 to total but does not work as  
        ' expected, because the MsgBox in returnClass() does not run.  
        MsgBox("Value of total is " & CStr(shareTotal.total))  
    End Sub  
    Public Function returnClass() As shareTotal  
        MsgBox("Function returnClass() called")  
        Return New shareTotal  
    End Function  
    Public Class shareTotal  
        Public Shared total As Integer  
    End Class  
    ```  
  
     Im vorherigen Beispiel generiert der Compiler eine Warnung beide Zeitangaben, die der Code greift auf die freigegebene Variable `total` über eine Instanz. In jedem Fall den Zugriff direkt über die Klasse vereinfacht `shareTotal` und führt nicht dazu, dass eine Instanz verwenden. Im Fall von der beabsichtigten Aufruf der Prozedur `returnClass`, dies bedeutet, dass es selbst generiert keinen Aufruf von `returnClass`, sodass die zusätzliche Aktion zum Anzeigen von "Function returnClass() called" nicht ausgeführt wird.  
  
 Der `Shared`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Static](../../../visual-basic/language-reference/modifiers/static.md)  
 [Lebensdauer in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)  
 [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)  
 [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
