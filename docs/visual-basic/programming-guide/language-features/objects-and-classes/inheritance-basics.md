---
title: Grundlagen der Vererbung (Visual Basic)
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
ms.openlocfilehash: 5e4b8511145e758bf3d6328141be0e526965dccf
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826573"
---
# <a name="inheritance-basics-visual-basic"></a>Grundlagen der Vererbung (Visual Basic)
Die `Inherits` -Anweisung verwendet, um eine neue Klasse namens deklariert eine *abgeleitete Klasse*basierend auf einer vorhandenen Klasse, die als bezeichnet ein *Basisklasse*. Abgeleitete Klassen erben, und erweitern können, die Eigenschaften, Methoden, Ereignissen, Felder und Konstanten, die in der Basisklasse definiert. Der folgende Abschnitt beschreibt einige der Regeln für die Vererbung, und die Modifizierer, die Sie verwenden können, so ändern Sie die Möglichkeit Klassen erben oder geerbt werden:  
  
-   Standardmäßig sind alle Klassen geerbt, es sei denn, mit der `NotInheritable` Schlüsselwort. Klassen können erben, von anderen Klassen in Ihrem Projekt oder von Klassen in anderen Assemblys, die auf Ihr Projekt verweist.  
  
-   Im Gegensatz zu Sprachen, die mehrere Vererbungen zu ermöglichen, ermöglicht Visual Basic nur die einfache Vererbung in Klassen; abgeleitete Klassen können, also nur eine Basisklasse haben. Obwohl mehrfache Vererbung in Klassen nicht zulässig ist, können Klassen mehrere Schnittstellen implementieren, die effektiv die gleichen enden erreichen können.  
  
-   Um zu verhindern, eingeschränkte Elemente in einer Basisklasse verfügbar zu machen, muss der Zugriffstyp in einer abgeleiteten Klasse restriktiver ist als die Basisklasse oder gleich sein. Z. B. eine `Public` Klasse kann nicht geerbt werden eine `Friend` oder `Private` -Klasse, und ein `Friend` Klasse kann nicht geerbt werden eine `Private` Klasse.  
  
## <a name="inheritance-modifiers"></a>Von Vererbungsmodifizierern  
 Visual Basic führt die folgenden Anweisungen aus auf Klassenebene und -Modifizierern zur Unterstützung von Vererbung:  
  
-   `Inherits` Anweisung – gibt die Basisklasse an.  
  
-   `NotInheritable` Modifizierer, verhindert, dass Programmierer die Klasse als Basisklasse verwenden.  
  
-   `MustInherit` Modifizierer – gibt an, dass die Klasse für die Verwendung nur als Basisklasse verwendet werden soll. Instanzen von `MustInherit` Klassen können nicht direkt erstellt werden; sie können nur erstellt werden als base-Klasseninstanzen einer abgeleiteten Klasse. (Andere Programmiersprachen wie C++ und C#, verwenden den Begriff *abstrakte Klasse* eine solche Klasse beschrieben.)  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a>Überschreiben von Eigenschaften und Methoden in abgeleiteten Klassen  
 Standardmäßig erbt eine abgeleitete Klasse Eigenschaften und Methoden der Basisklasse an. Wenn eine geerbte Eigenschaft oder Methode verfügt, in der abgeleiteten Klasse anders als gewohnt Verhalten möglich *überschreiben*. Das heißt, können Sie eine neue Implementierung der Methode in der abgeleiteten Klasse definieren. Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:  
  
-   `Overridable` – Eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben werden können.  
  
-   `Overrides` – Überschreibt eine `Overridable` Eigenschaft oder Methode, die in der Basisklasse definiert.  
  
-   `NotOverridable` – Verhindert, dass eine Eigenschaft oder Methode in einer erbenden Klasse überschrieben wird. In der Standardeinstellung `Public` Methoden sind `NotOverridable`.  
  
-   `MustOverride` – Erfordert, dass es sich bei eine abgeleitete Klasse außer Kraft setzen der Eigenschaft oder Methode. Wenn die `MustOverride` -Schlüsselwort wird verwendet, die Definition der Methode besteht aus nur die `Sub`, `Function`, oder `Property` Anweisung. Keine weiteren Anweisungen zulässig ist, und insbesondere besteht keine `End Sub` oder `End Function` Anweisung. `MustOverride` Methoden müssen deklariert werden, `MustInherit` Klassen.  
  
 Nehmen wir an, dass Sie Klassen zum Behandeln von Gehaltsabrechnungen definieren möchten. Sie können einen generischen definieren `Payroll` Klasse enthält eine `RunPayroll` -Methode, die Gehaltsabrechnungen für eine typische Woche berechnet. Sie können dann `Payroll` als Basisklasse für ein spezialisierter `BonusPayroll` -Klasse, die bei der Verteilung von Mitarbeiterboni verwendet werden kann.  
  
 Die `BonusPayroll` Klasse erben kann, und außer Kraft setzen, die `PayEmployee` in der Basisklasse definierte Methode `Payroll` Klasse.  
  
 Das folgende Beispiel definiert eine Basisklasse, `Payroll,` und einer abgeleiteten Klasse `BonusPayroll`, die eine geerbte Methode, überschreibt `PayEmployee`. Eine Prozedur `RunPayroll`, erstellt und übergibt dann eine `Payroll` Objekt und ein `BonusPayroll` Objekt, das eine Funktion, `Pay`, ausführt, die `PayEmployee` -Methode der beiden Objekte.  
  
 [!code-vb[VbVbalrOOP#28](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#28)]  
  
## <a name="the-mybase-keyword"></a>The MyBase Keyword  
 Die `MyBase` -Schlüsselwort verhält sich wie eine Objektvariable, die auf die Basisklasse der aktuellen Instanz einer Klasse verweist. `MyBase` Member der Basisklasse zuzugreifen, die überschrieben werden, oder in einer abgeleiteten Klasse schattiert wird häufig verwendet werden. Insbesondere `MyBase.New` wird verwendet, um explizit einen Basisklassenkonstruktor aus Konstruktor einer abgeleiteten Klasse aufrufen.  
  
 Nehmen wir beispielsweise an, dass Sie eine abgeleitete Klasse entwerfen, die eine Methode, die von der Basisklasse geerbt überschreibt. Die überschriebene Methode kann die Methode in der Basisklasse aufrufen und den zurückgegebenen Wert ändern, wie im folgenden Codefragment gezeigt:  
  
 [!code-vb[VbVbalrOOP#109](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#109)]  
  
 Die folgende Liste beschreibt die Einschränkungen zur Verwendung von `MyBase`:  
  
-   `MyBase` bezieht sich auf den direkten Basisklassen und dessen geerbte Member. Es kann nicht verwendet werden für den Zugriff auf `Private` Member in der Klasse.  
  
-   `MyBase` ist ein Schlüsselwort, kein wirkliches Objekt. `MyBase` einer Variablen zugewiesen, in der Prozedur zu übergeben oder im verwendet werden kann keinem `Is` Vergleich.  
  
-   Die Methode, die `MyBase` ist qualifiziert, muss nicht in direkten Basisklasse; definiert werden sie möglicherweise stattdessen in einer indirekt geerbte Basisklasse definiert. In der Reihenfolge für einen Verweis von qualifizierten `MyBase` um ordnungsgemäß zu kompilieren, muss die Basisklasse enthalten einer Methode, die mit dem Namen und Typen der Parameter, die im Aufruf angezeigt werden.  
  
-   Sie können keine `MyBase` Aufrufen `MustOverride` -Klasse, Methoden basieren.  
  
-   `MyBase` kann nicht verwendet werden, um sich zu qualifizieren. Aus diesem Grund ist der folgende Code ungültig:  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   `MyBase` kann nicht in Modulen verwendet werden.  
  
-   `MyBase` kann nicht verwendet werden, um der Member der Basisklasse zuzugreifen, die als markiert sind `Friend` ist die Basisklasse in einer anderen Assembly.  
  
 Weitere Informationen und ein weiteres Beispiel finden Sie [Vorgehensweise: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
## <a name="the-myclass-keyword"></a>MyClass-Schlüsselwort  
 Die `MyClass` -Schlüsselwort verhält sich wie eine Objektvariable, die auf die aktuelle Instanz einer Klasse, wie Sie ursprünglich implementiert verweist. `MyClass` ähnelt `Me`, aber alle Methoden und Eigenschaften, die in Aufrufen `MyClass` wird behandelt, als wäre die Methode oder Eigenschaft [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Aus diesem Grund wird die Methode oder Eigenschaft nicht betroffen von in einer abgeleiteten Klasse überschreiben.  
  
-   `MyClass` ist ein Schlüsselwort, kein wirkliches Objekt. `MyClass` einer Variablen zugewiesen, in der Prozedur zu übergeben oder im verwendet werden kann keinem `Is` Vergleich.  
  
-   `MyClass` bezieht sich auf die enthaltende Klasse und deren geerbte Member.  
  
-   `MyClass` kann verwendet werden, als Qualifizierer für `Shared` Member.  
  
-   `MyClass` kann nicht verwendet werden, in einem `Shared` -Methode, aber innerhalb einer Instanzmethode verwendet werden können, um Zugriff auf einen freigegebenen Member einer Klasse.  
  
-   `MyClass` kann nicht in den Standardmodulen verwendet werden.  
  
-   `MyClass` kann verwendet werden, um eine Methode, die in einer Basisklasse definiert ist, und ohne Implementierung der Methode, die in dieser Klasse bereitgestellten, qualifiziert. Ein solchen Verweis verfügt über die gleiche Bedeutung wie `MyBase.` *Methode*.  
  
 Im folgenden Beispiel wird `Me` und `MyClass`.  
  
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
  
 Obwohl `derivedClass` überschreibt `testMethod`, `MyClass` -Schlüsselwort in `useMyClass` hebt den Auswirkungen der überschreiben und der Compiler löst den Aufruf die Basisklassenversion von `testMethod`.  
  
## <a name="see-also"></a>Siehe auch

- [Inherits-Anweisung](../../../../visual-basic/language-reference/statements/inherits-statement.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
