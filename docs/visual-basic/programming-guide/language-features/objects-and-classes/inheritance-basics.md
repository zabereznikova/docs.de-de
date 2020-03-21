---
title: Grundlagen der Vererbung
ms.date: 07/20/2015
helpviewer_keywords:
- derived classes [Visual Basic], inheritance
- MyClass keyword [Visual Basic], using
- MyBase keyword [Visual Basic], using
- Inherits statement [Visual Basic], inheritance
- overriding, Overridable keyword
- MustInherit keyword [Visual Basic], using
- Overrides keyword [Visual Basic], using
- inheritance
- MustInherit classes [Visual Basic]
- MustOverride keyword [Visual Basic], using
- classes [Visual Basic], derived
- NotInheritable keyword [Visual Basic], using
- base classes [Visual Basic], extending properties and methods [Visual Basic]
- NotOverridable keyword [Visual Basic], using
- base classes [Visual Basic], inheritance
- abstract classes [Visual Basic], inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
ms.openlocfilehash: 89fcf2a14d8938d536aa72628218242811baa1a2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401460"
---
# <a name="inheritance-basics-visual-basic"></a>Grundlagen der Vererbung (Visual Basic)

Die `Inherits` Anweisung wird verwendet, um eine neue Klasse zu deklarieren, die als *abgeleitete Klasse*bezeichnet wird, basierend auf einer vorhandenen Klasse, die als *Basisklasse*bezeichnet wird. Abgeleitete Klassen erben und können die Eigenschaften, Methoden, Ereignisse, Felder und Konstanten erweitern, die in der Basisklasse definiert sind. Im folgenden Abschnitt werden einige der Regeln für die Vererbung und die Modifikatoren beschrieben, mit denen Sie die Art und Weise ändern können, wie Klassen erben oder vererbt werden:

- Standardmäßig sind alle Klassen vererbbar, `NotInheritable` es sei denn, sie werden mit dem Schlüsselwort markiert. Klassen können von anderen Klassen in Ihrem Projekt oder von Klassen in anderen Assemblys erben, auf die das Projekt verweist.

- Im Gegensatz zu Sprachen, die eine mehrfache Vererbung ermöglichen, lässt Visual Basic nur eine einzelne Vererbung in Klassen zu. Das heißt, abgeleitete Klassen können nur eine Basisklasse haben. Obwohl mehrere Vererbungen in Klassen nicht zulässig sind, können Klassen mehrere Schnittstellen implementieren, wodurch die gleichen Ziele effektiv erreicht werden können.

- Um zu verhindern, dass eingeschränkte Elemente in einer Basisklasse angezeigt werden, muss der Zugriffstyp einer abgeleiteten Klasse gleich oder restriktiver sein als die Basisklasse. Beispielsweise kann `Public` eine Klasse keine `Friend` oder `Private` eine Klasse `Friend` erben, und eine `Private` Klasse kann keine Klasse erben.

## <a name="inheritance-modifiers"></a>Vererbungsmodifizierer

Visual Basic führt die folgenden Anweisungen und Modifikatoren auf Klassenebene ein, um die Vererbung zu unterstützen:

- `Inherits`anweisung – Gibt die Basisklasse an.

- `NotInheritable`modifier – Verhindert, dass Programmierer die Klasse als Basisklasse verwenden.

- `MustInherit`modifier – Gibt an, dass die Klasse nur für die Verwendung als Basisklasse vorgesehen ist. Instanzen `MustInherit` von Klassen können nicht direkt erstellt werden. Sie können nur als Basisklasseninstanzen einer abgeleiteten Klasse erstellt werden. (Andere Programmiersprachen, wie z. B. C++ und C, verwenden den Begriff *abstrakte Klasse,* um eine solche Klasse zu beschreiben.)

## <a name="overriding-properties-and-methods-in-derived-classes"></a>Überschreiben von Eigenschaften und Methoden in abgeleiteten Klassen

Standardmäßig erbt eine abgeleitete Klasse Eigenschaften und Methoden von ihrer Basisklasse. Wenn sich eine geerbte Eigenschaft oder Methode in der abgeleiteten Klasse anders verhalten muss, kann sie *überschrieben*werden. Das heißt, Sie können eine neue Implementierung der Methode in der abgeleiteten Klasse definieren. Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:

- `Overridable`– Ermöglicht das Übersteuern einer Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse.

- `Overrides`– Überschreibt `Overridable` eine Eigenschaft oder Methode, die in der Basisklasse definiert ist.

- `NotOverridable`– Verhindert, dass eine Eigenschaft oder Methode in einer erbenden Klasse überschrieben wird. Standardmäßig sind `Public` `NotOverridable`Methoden .

- `MustOverride`– Erfordert, dass eine abgeleitete Klasse die Eigenschaft oder Methode überschreibt. Wenn `MustOverride` das Schlüsselwort verwendet wird, besteht `Sub` `Function`die `Property` Methodendefinition nur aus der , oder Anweisung. Es sind keine anderen Aussagen zulässig, und insbesondere gibt es keine `End Sub` oder `End Function` Keine Aussage. `MustOverride`Methoden müssen in `MustInherit` Klassen deklariert werden.

Angenommen, Sie möchten Klassen definieren, um die Lohnabrechnung zu behandeln. Sie können eine `Payroll` generische Klasse `RunPayroll` definieren, die eine Methode enthält, die die Lohnabrechnung für eine typische Woche berechnet. Sie können `Payroll` dann als Basisklasse für `BonusPayroll` eine spezialisiertere Klasse verwendet werden, die bei der Verteilung von Mitarbeiterboni verwendet werden könnte.

Die `BonusPayroll` Klasse kann die in der `PayEmployee` Basisklasse `Payroll` definierte Methode erben und überschreiben.

Im folgenden Beispiel werden eine `Payroll,` Basisklasse und `BonusPayroll`eine abgeleitete Klasse definiert, die eine geerbte Methode `PayEmployee`überschreibt. Eine `RunPayroll`Prozedur, , erstellt `Payroll` und übergibt dann ein Objekt und ein `BonusPayroll` Objekt an eine Funktion, `Pay`die die `PayEmployee` Methode beider Objekte ausführt.

[!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]

## <a name="the-mybase-keyword"></a>Das MyBase-Schlüsselwort

Das `MyBase` Schlüsselwort verhält sich wie eine Objektvariable, die auf die Basisklasse der aktuellen Instanz einer Klasse verweist. `MyBase`wird häufig für den Zugriff auf Basisklassenmember verwendet, die in einer abgeleiteten Klasse überschrieben oder überschattet werden. Insbesondere wird `MyBase.New` verwendet, um explizit einen Basisklassenkonstruktor von einem abgeleiteten Klassenkonstruktor aufzurufen.

Angenommen, Sie entwerfen eine abgeleitete Klasse, die eine von der Basisklasse geerbte Methode überschreibt. Die überschriebene Methode kann die Methode in der Basisklasse aufrufen und den Rückgabewert ändern, wie im folgenden Codefragment gezeigt:

[!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]

In der folgenden Liste `MyBase`werden Einschränkungen bei der Verwendung beschrieben:

- `MyBase`bezieht sich auf die unmittelbare Basisklasse und ihre geerbten Member. Sie kann nicht `Private` für den Zugriff auf Member in der Klasse verwendet werden.

- `MyBase`ist ein Schlüsselwort, kein echtes Objekt. `MyBase`kann nicht einer Variablen zugewiesen, an Prozeduren `Is` übergeben oder in einem Vergleich verwendet werden.

- Die methode, die qualifiziert ist, `MyBase` muss nicht in der unmittelbaren Basisklasse definiert werden. Sie kann stattdessen in einer indirekt geerbten Basisklasse definiert werden. Damit ein Verweis, `MyBase` der durch die korrekte Kompilierung qualifiziert ist, qualifiziert ist, muss eine Basisklasse eine Methode enthalten, die dem Namen und den Typen von Parametern entspricht, die im Aufruf angezeigt werden.

- Sie können `MyBase` keine `MustOverride` Basisklassenmethoden aufrufen.

- `MyBase`kann nicht verwendet werden, um sich zu qualifizieren. Daher ist der folgende Code ungültig:

  `MyBase.MyBase.BtnOK_Click()`

- `MyBase`kann nicht in Modulen verwendet werden.

- `MyBase`kann nicht für den Zugriff auf `Friend` Basisklassenmember verwendet werden, die so gekennzeichnet sind, als ob sich die Basisklasse in einer anderen Assembly befindet.

Weitere Informationen und ein weiteres Beispiel finden Sie unter [Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird.](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)

## <a name="the-myclass-keyword"></a>Das MyClass-Schlüsselwort

Das `MyClass` Schlüsselwort verhält sich wie eine Objektvariable, die auf die aktuelle Instanz einer Klasse verweist, wie sie ursprünglich implementiert wurde. `MyClass`ähnelt `Me`, aber jede Methode `MyClass` und jeder Eigenschaftsaufruf wird so behandelt, als ob die Methode oder Eigenschaft [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md)wäre. Daher wird die Methode oder Eigenschaft nicht durch Das Überschreiben in einer abgeleiteten Klasse beeinflusst.

- `MyClass`ist ein Schlüsselwort, kein echtes Objekt. `MyClass`kann nicht einer Variablen zugewiesen, an Prozeduren `Is` übergeben oder in einem Vergleich verwendet werden.

- `MyClass`bezieht sich auf die enthaltende Klasse und ihre geerbten Member.

- `MyClass`kann als Qualifizierer für `Shared` Mitglieder verwendet werden.

- `MyClass`kann nicht innerhalb `Shared` einer Methode verwendet werden, sondern kann innerhalb einer Instanzmethode verwendet werden, um auf einen freigegebenen Member einer Klasse zuzugreifen.

- `MyClass`kann nicht in Standardmodulen verwendet werden.

- `MyClass`kann verwendet werden, um eine Methode zu qualifizieren, die in einer Basisklasse definiert ist und die keine Implementierung der in dieser Klasse bereitgestellten Methode enthält. Ein solcher Verweis hat `MyBase.`die gleiche Bedeutung wie *Methode*.

Im folgenden Beispiel `Me` `MyClass`werden vergleicht und .

```vb
Class baseClass
    Public Overridable Sub testMethod()
        MsgBox("Base class string")
    End Sub
    Public Sub useMe()
        ' The following call uses the calling class's method, even if
        ' that method is an override.
        Me.testMethod()
    End Sub
    Public Sub useMyClass()
        ' The following call uses this instance's method and not any
        ' override.
        MyClass.testMethod()
    End Sub
End Class
Class derivedClass : Inherits baseClass
    Public Overrides Sub testMethod()
        MsgBox("Derived class string")
    End Sub
End Class
Class testClasses
    Sub startHere()
        Dim testObj As derivedClass = New derivedClass()
        ' The following call displays "Derived class string".
        testObj.useMe()
        ' The following call displays "Base class string".
        testObj.useMyClass()
    End Sub
End Class
```

Obwohl `derivedClass` überschrieben `testMethod`wird, hebt das `MyClass` Schlüsselwort in `useMyClass` die Auswirkungen des Überschreibens auf, `testMethod`und der Compiler löst den Aufruf der Basisklassenversion von auf.

## <a name="see-also"></a>Weitere Informationen

- [Inherits Statement](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
