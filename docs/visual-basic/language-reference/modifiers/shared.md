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
ms.openlocfilehash: 001baa8d3cbd294772bef634825c67ea13b23458
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54597280"
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)
Gibt an, dass eine oder mehrere deklarierte Programmierelemente einer Klasse oder Struktur, die in großen, und nicht mit einer bestimmten Instanz der Klasse oder Struktur zugeordnet sind.  
  
## <a name="remarks"></a>Hinweise  
  
## <a name="when-to-use-shared"></a>Verwendung freigegeben  
 Ein Member einer Klasse oder Struktur Freigabe verfügbar macht jede Instanz statt *nicht freigegebene*, wobei jede Instanz eine eigene Kopie verfügen. Dies ist beispielsweise hilfreich, der Wert einer Variablen für die gesamte Anwendung gilt. Wenn Sie diese Variable deklarieren `Shared`, klicken Sie dann alle Instanzen am gleichen Speicherort zugreifen, und wenn eine Instanz der Wert der Variablen ändert, greifen alle Instanzen auf den aktualisierten Wert.  
  
 Freigeben von wird die Zugriffsebene eines Members nicht geändert werden. Ein Klassenmember kann z. B. freigegeben werden und Private (nur von innerhalb der Klasse verfügbar), oder nicht freigegeben und öffentlich. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Regeln  
  
-   **Deklarationskontext.** Sie können `Shared` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarationskontext für eine `Shared` Element muss eine Klasse oder Struktur sein, und eine Quelldatei, Namespace oder Prozedur nicht möglich.  
  
-   **Kombinierte Modifizierer.** Sie können keine angeben `Shared` zusammen mit [überschreibt](../../../visual-basic/language-reference/modifiers/overrides.md), [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md), oder [ Statische](../../../visual-basic/language-reference/modifiers/static.md) in der gleichen Deklaration.  
  
-   **Zugriff auf.** Sie haben einen freigegebenen Elements durch die Qualifizierung mit dem Namen Klasse oder Struktur, die nicht mit dem Variablennamen, die einer bestimmten Instanz der Klasse oder Struktur zugreifen. Sie müssen auch keinen zum Erstellen einer Instanz einer Klasse oder Struktur auf freigegebenen Member zuzugreifen.  
  
     Im folgenden Beispiel wird die freigegebene Prozedur <xref:System.Double.IsNaN%2A> verfügbar gemacht werden, indem die <xref:System.Double> Struktur.  
  
     `If Double.IsNaN(result) Then MsgBox("Result is mathematically undefined.")`  
  
-   **Implizite freigeben.** Können keine der `Shared` -Modifizierer in einer [Const-Anweisung](../../../visual-basic/language-reference/statements/const-statement.md), aber Konstanten sind implizit freigegeben. Auf ähnliche Weise können Sie nicht Mitglied ein Modul oder eine Schnittstelle sein deklarieren `Shared`, aber sie werden implizit freigegeben.  
  
## <a name="behavior"></a>Verhalten  
  
-   **Speicher.** Eine freigegebene Variable oder ein Ereignis wird im Arbeitsspeicher gespeichert, nur nach dem, unabhängig davon, wie viele oder wenige Instanzen der Klasse oder Struktur erstellen. Analog dazu enthält ein gemeinsames Verfahren oder eine Eigenschaft nur einen Satz von lokalen Variablen.  
  
-   **Zugriff auf durch eine Instanzvariable.** Es ist möglich, die Zugriff auf einen freigegebenen Elements durch die Qualifizierung mit dem Namen einer Variablen, die eine bestimmte Instanz der Klasse oder Struktur enthält. Obwohl dies in der Regel funktioniert wie erwartet, kann der Compiler generiert eine Warnung angezeigt und führt den Zugriff über den Namen der Klasse oder Struktur anstelle der Variablen.  
  
-   **Zugriff auf durch einen Instanzausdruck.** Wenn Sie einen freigegebenen Elements durch einen Ausdruck, die eine Instanz ihrer Klasse oder Struktur zurückgibt zugreifen, wird der Compiler den Zugriff durch den Namen der Klasse oder Struktur, anstelle die Auswertung des Ausdrucks. Dies erzeugt unerwartete Ergebnisse, wenn das beabsichtigt ist des Ausdrucks, der andere Aktionen sowie die Instanz zurückgeben. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
    ```vb
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
  
     Im vorherigen Beispiel generiert der Compiler eine Warnmeldung an beide Male, die der Code greift auf die freigegebene Variable `total` durch eine Instanz. In jedem Fall vereinfacht den Zugriff direkt über die Klasse `shareTotal` und macht nicht zu einer beliebigen Instanz verwenden. Im Fall von der beabsichtigten Aufruf der Prozedur `returnClass`, dies bedeutet, dass Sie selbst generiert keinen Aufruf von `returnClass`, sodass die zusätzliche Aktion anzeigen von "Function returnClass() namens" nicht ausgeführt wird.  
  
 Der `Shared`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
 [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Event-Anweisung](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator-Anweisung](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub-Anweisung](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Siehe auch
- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Static](../../../visual-basic/language-reference/modifiers/static.md)
- [Lebensdauer in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Verfahren](../../../visual-basic/programming-guide/language-features/procedures/index.md)
- [Strukturen](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
