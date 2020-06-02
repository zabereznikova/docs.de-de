---
title: Shared
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
ms.openlocfilehash: bc63de4bda1e8e605e25fbe293686c187dd4d005
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290992"
---
# <a name="shared-visual-basic"></a>Shared (Visual Basic)

Gibt an, dass mindestens ein deklariertes Programmier Element einer Klasse oder Struktur sehr groß zugeordnet ist, nicht mit einer bestimmten Instanz der Klasse oder Struktur.

## <a name="when-to-use-shared"></a>Verwendungszwecke von Shared

Wenn Sie ein Member einer Klasse oder Struktur freigeben, ist es für jede Instanz verfügbar und nicht für *nicht freigegebene*, wobei jede Instanz eine eigene Kopie beibehält. Dies ist beispielsweise hilfreich, wenn der Wert einer Variablen für die gesamte Anwendung gilt. Wenn Sie diese Variable als deklarieren `Shared` , greifen alle Instanzen auf denselben Speicherort zu, und wenn eine Instanz den Wert der Variablen ändert, greifen alle Instanzen auf den aktualisierten Wert zu.

Durch die Freigabe wird die Zugriffsebene eines Members nicht geändert. Beispielsweise kann ein Klassenmember freigegeben und privat (nur innerhalb der Klasse zugänglich) oder nicht freigegeben und öffentlich sein. Weitere Informationen finden Sie unter [Zugriffsebenen in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).

## <a name="rules"></a>Regeln

- **Deklarationskontext.** Sie können `Shared` nur auf Modulebene verwenden. Dies bedeutet, dass der Deklarations Kontext für ein- `Shared` Element eine Klasse oder Struktur sein muss und weder eine Quelldatei, ein Namespace noch eine Prozedur sein darf.

- **Kombinierte Modifizierer.** Sie können nicht `Shared` zusammen mit [über](../../../visual-basic/language-reference/modifiers/overrides.md)schreibungen, [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md), [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)oder [static](../../../visual-basic/language-reference/modifiers/static.md) in derselben Deklaration angeben.

- **Den.** Sie greifen auf ein frei gegebenes Element zu, indem Sie es mit seinem Klassen-oder Struktur Namen qualifizieren, nicht mit dem Variablennamen einer bestimmten Instanz der Klasse oder Struktur. Sie müssen nicht einmal eine Instanz einer Klasse oder Struktur erstellen, um auf die freigegebenen Member zuzugreifen.

     Im folgenden Beispiel wird die von der-Struktur verfügbar gemachte freigegebene Prozedur aufgerufen <xref:System.Double.IsNaN%2A> <xref:System.Double> .

     ```vb
     If Double.IsNaN(result) Then Console.WriteLine("Result is mathematically undefined.")
     ```

- **Implizite Freigabe.** Sie können den- `Shared` Modifizierer nicht in einer Konstanten [Anweisung](../../../visual-basic/language-reference/statements/const-statement.md)verwenden, aber Konstanten werden implizit freigegeben. Ebenso ist es nicht möglich, einen Member eines Moduls oder einer Schnittstelle so zu deklarieren `Shared` , dass Sie implizit freigegeben werden.

## <a name="behavior"></a>Verhalten

- **Speicher.** Eine freigegebene Variable oder ein frei gegebenes Ereignis wird im Arbeitsspeicher nur einmal gespeichert, unabhängig davon, wie viele oder wenige Instanzen Sie von der Klasse oder Struktur erstellen. Entsprechend enthält eine freigegebene Prozedur oder Eigenschaft nur einen Satz von lokalen Variablen.

- **Zugreifen über eine Instanzvariable.** Sie können auf ein frei gegebenes Element zugreifen, indem Sie es mit dem Namen einer Variablen qualifizieren, die eine bestimmte Instanz der Klasse oder Struktur enthält. Obwohl dies in der Regel erwartungsgemäß funktioniert, generiert der Compiler eine Warnmeldung und ermöglicht den Zugriff über den Klassen-oder Struktur Namen anstelle der Variablen.

- **Zugreifen über einen Instanzausdruck.** Wenn Sie über einen Ausdruck, der eine Instanz der Klasse oder Struktur zurückgibt, auf ein frei gegebenes Element zugreifen, übernimmt der Compiler den Zugriff über den Klassen-oder Struktur Namen, anstatt den Ausdruck auszuwerten. Dies führt zu unerwarteten Ergebnissen, wenn Sie den Ausdruck zum Ausführen anderer Aktionen und zum Zurückgeben der Instanz vorgesehen haben. Dies wird anhand des folgenden Beispiels veranschaulicht.
  
    ```vb
    Sub Main()
        ' The following line is the preferred way to access Total.
        ShareTotal.Total = 10

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of through
        ' the variable instanceVar. This works as expected and adds
        ' 100 to Total.
        Dim instanceVar As New ShareTotal
        instanceVar.Total += 100

        ' The following line generates a compiler warning message and
        ' accesses total through class ShareTotal instead of calling
        ' ReturnClass(). This adds 1000 to total but does not work as
        ' expected, because the WriteLine in ReturnClass() does not run.
        Console.WriteLine("Value of total is " & CStr(ShareTotal.Total))
        ReturnClass().Total += 1000
    End Sub

    Public Function ReturnClass() As ShareTotal
        Console.WriteLine("Function ReturnClass() called")
        Return New ShareTotal
    End Function

    Public Class ShareTotal
        Public Shared Property Total As Integer
    End Class
    ```

     Im vorherigen Beispiel generiert der Compiler eine Warnmeldung, wenn der Code über eine-Instanz auf die freigegebene Eigenschaft zugreift `Total` . In jedem Fall wird der Zugriff direkt über die-Klasse gewährt, und es werden keine `ShareTotal` -Instanzen verwendet. Im Fall des beabsichtigten Aufrufs der Prozedur `ReturnClass` bedeutet dies, dass nicht einmal ein Aufruf von generiert wird `ReturnClass` , sodass die zusätzliche Aktion zum Anzeigen von "Function returnClass ()" nicht ausgeführt wird.

Der `Shared`-Modifizierer kann in folgenden Kontexten verwendet werden:

- [Dim-Anweisung](../statements/dim-statement.md)
- [Event-Anweisung](../statements/event-statement.md)
- [Function-Anweisung](../statements/function-statement.md)
- [Operator Statement](../operator-statement.md)
- [Property Statement](../property-statement.md)
- [Sub-Anweisung](../sub-statement.md)
  
## <a name="see-also"></a>Siehe auch

- [Shadows](shadows.md)
- [Kum](static.md)
- [Lebensdauer in Visual Basic](../../programming-guide/language-features/declared-elements/lifetime.md)
- [Verfahren](../../programming-guide/language-features/procedures/index.md)
- [Strukturen](../../programming-guide/language-features/data-types/structures.md)
- [Objekte und Klassen](../../programming-guide/language-features/objects-and-classes/index.md)
