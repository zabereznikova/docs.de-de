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
ms.openlocfilehash: 9225e5fd9fa35ae06414018a109f66515f99363f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33655188"
---
# <a name="inheritance-basics-visual-basic"></a>Grundlagen der Vererbung (Visual Basic)
Die `Inherits` Anweisung wird verwendet, um eine neue Klasse mit dem Namen zu deklarieren einer *abgeleitete Klasse*basierend auf einer vorhandenen Klasse, die als bezeichnet eine *Basisklasse*. Abgeleitete Klassen erben, und erweitern können, die Eigenschaften, Methoden, Ereignisse, Felder und Konstanten, die in der Basisklasse definiert. Der folgende Abschnitt beschreibt einige der Regeln für die Vererbung, und der Modifizierer, die Sie verwenden können, so ändern Sie die Möglichkeit Klassen erben oder geerbt werden:  
  
-   Standardmäßig alle Klassen geerbt, es sei denn, die mit gekennzeichnet werden die `NotInheritable` Schlüsselwort. Klassen können von anderen Klassen in Ihrem Projekt oder von Klassen in anderen Assemblys, die das Projekt verweist auf erben.  
  
-   Im Gegensatz zu den Sprachen, die mehrfache Vererbung zu ermöglichen, ermöglicht Visual Basic nur einfache Vererbung in Klassen. abgeleitete Klassen können also nur eine Basisklasse haben. Jedoch in Klassen keine mehrfache Vererbung zulässig ist, können Klassen mehrere Schnittstellen implementieren, die effektiv die gleichen enden ausführen können.  
  
-   Um zu verhindern, eingeschränkte Elemente in einer Basisklasse verfügbar machen, muss von einer abgeleiteten Klasse der Zugriffstyp restriktiver ist als seine Basisklasse oder gleich sein. Z. B. eine `Public` Klasse kann nicht geerbt werden eine `Friend` oder ein `Private` -Klasse, und ein `Friend` Klasse kann nicht geerbt werden eine `Private` Klasse.  
  
## <a name="inheritance-modifiers"></a>Von Vererbungsmodifizierern  
 Visual Basic führt die folgenden Anweisungen aus auf Klassenebene und -Modifizierern zur Unterstützung der Vererbung:  
  
-   `Inherits` Anweisung – gibt die Basisklasse.  
  
-   `NotInheritable` Modifizierer – verhindert, dass Programmierer die Klasse als Basisklasse verwenden.  
  
-   `MustInherit` Modifizierer – gibt an, dass die Klasse zur Verwendung als Basisklasse nur vorgesehen ist. Instanzen von `MustInherit` Klassen können nicht direkt erstellt werden; sie können nur erstellt werden als base Klasseninstanzen einer abgeleiteten Klasse. (Anderer Programmiersprachen vergleichbar, z. B. C++ und c#, mithilfe des Begriffs *abstrakte Klasse* um eine solche Klasse zu beschreiben.)  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a>Überschreiben von Eigenschaften und Methoden in abgeleiteten Klassen  
 Standardmäßig erbt eine abgeleitete Klasse Eigenschaften und Methoden von ihrer Basisklasse. Besitzt eine geerbte Eigenschaft oder Methode in der abgeleiteten Klasse unterschiedlich Verhalten möglich *überschreiben*. Das heißt, können Sie eine neue Implementierung der Methode in der abgeleiteten Klasse definieren. Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:  
  
-   `Overridable` – Ermöglicht einer Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben werden.  
  
-   `Overrides` – Überschreibt eine `Overridable` Eigenschaft oder Methode in der Basisklasse definiert.  
  
-   `NotOverridable` – Verhindert, dass eine Eigenschaft oder Methode in einer erbenden Klasse überschrieben wird. Standardmäßig `Public` Methoden sind `NotOverridable`.  
  
-   `MustOverride` – Erfordert, dass es sich bei eine abgeleitete Klasse außer Kraft setzen der Eigenschaft oder Methode. Wenn die `MustOverride` Schlüsselwort verwendet wird, besteht die Methodendefinition nur die `Sub`, `Function`, oder `Property` Anweisung. Keine weiteren Anweisungen sind zulässig und insbesondere besteht keine `End Sub` oder `End Function` Anweisung. `MustOverride` Methoden müssen deklariert werden, `MustInherit` Klassen.  
  
 Angenommen Sie, Sie definieren von Klassen, um Gehaltsdaten verarbeiten möchten. Sie können einen generischen definieren `Payroll` Klasse enthält eine `RunPayroll` Methode, die für eine typische Woche Payroll berechnet. Anschließend können Sie `Payroll` als Basisklasse für ein spezialisierter `BonusPayroll` -Klasse, die verwendet werden können, wenn Mitarbeiterboni verteilt.  
  
 Die `BonusPayroll` Klasse erben kann, und überschreiben die `PayEmployee` in der Basisklasse definierte Methode `Payroll` Klasse.  
  
 Das folgende Beispiel definiert eine Basisklasse `Payroll,` und eine abgeleitete Klasse `BonusPayroll`, die eine geerbte Methode überschreibt `PayEmployee`. Eine Prozedur `RunPayroll`, erstellt und übergibt dann eine `Payroll` Objekt und ein `BonusPayroll` -Objekt an eine Funktion `Pay`, ausführt, die `PayEmployee` -Methode der beiden Objekte.  
  
 [!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a>MyBase-Schlüsselwort  
 Die `MyBase` Schlüsselwort verhält sich wie eine Objektvariable, die auf die Basisklasse der aktuellen Instanz einer Klasse verweist. `MyBase` Member der Basisklasse zuzugreifen, die überschrieben werden, oder in einer abgeleiteten Klasse schattiert wird häufig verwendet werden. Insbesondere `MyBase.New` wird verwendet, um explizit einen Basisklassenkonstruktor vom Konstruktor einer abgeleiteten Klasse aufrufen.  
  
 Nehmen Sie beispielsweise an, dass Sie eine abgeleitete Klasse entwerfen, die eine Methode, die von der Basisklasse vererbt überschreibt. Die überschriebene Methode kann die Methode in der Basisklasse aufrufen und den Rückgabewert zu ändern, wie im folgenden Codefragment gezeigt:  
  
 [!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 Die folgende Liste beschreibt die Einschränkungen zur Verwendung von `MyBase`:  
  
-   `MyBase` bezieht sich auf die unmittelbare Basisklasse und deren geerbte Member. Kann nicht verwendet werden für den Zugriff auf `Private` Member in der Klasse.  
  
-   `MyBase` ist ein Schlüsselwort, kein echtes Objekt. `MyBase` einer Variablen zugewiesen, in der Prozedur zu übergeben oder verwendet werden kann kein `Is` Vergleich.  
  
-   Die Methode, die `MyBase` qualifiziert keinen direkten Basisklasse; definiert werden möglicherweise stattdessen in einer indirekt geerbte Basisklasse definiert werden. Ein Verweis von qualifizierten `MyBase` um ordnungsgemäß zu kompilieren, einige Basisklasse muss eine Methode enthalten den Namen und Typen der Parameter, die im Aufruf angezeigt werden.  
  
-   Sie können keine `MyBase` Aufrufen `MustOverride` -Klasse, Methoden basieren.  
  
-   `MyBase` kann nicht verwendet werden, um sich selbst zu qualifizieren. Aus diesem Grund ist der folgende Code ungültig:  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   `MyBase` kann nicht in Modulen verwendet werden.  
  
-   `MyBase` kann nicht verwendet werden, um Zugriff auf Basisklassenmember, die als markiert sind `Friend` ist die Basisklasse in einer anderen Assembly.  
  
 Weitere Informationen und ein weiteres Beispiel finden Sie unter [Vorgehensweise: Zugriff auf eine Variable Hidden durch eine abgeleitete Klasse](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
## <a name="the-myclass-keyword"></a>MyClass-Schlüsselwort  
 Die `MyClass` Schlüsselwort verhält sich wie eine Objektvariable, die auf die aktuelle Instanz einer Klasse, die als ursprünglich verweist. `MyClass` ähnelt `Me`, aber alle Methoden und Eigenschaften, die in Aufrufen `MyClass` wird behandelt, als wäre die Methode oder Eigenschaft [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Aus diesem Grund ist die Methode oder Eigenschaft nicht betroffen von in einer abgeleiteten Klasse überschreiben.  
  
-   `MyClass` ist ein Schlüsselwort, kein echtes Objekt. `MyClass` einer Variablen zugewiesen, in der Prozedur zu übergeben oder verwendet werden kann kein `Is` Vergleich.  
  
-   `MyClass` bezieht sich auf die enthaltende Klasse und deren geerbte Member.  
  
-   `MyClass` Dient als Qualifizierer für `Shared` Elemente.  
  
-   `MyClass` kann nicht verwendet werden, in einem `Shared` -Methode, jedoch können in einer Instanzmethode verwendet werden, um einen freigegebenen Member einer Klasse zuzugreifen.  
  
-   `MyClass` kann nicht in standard-Modulen verwendet werden.  
  
-   `MyClass` kann verwendet werden, auf eine Methode, die in einer Basisklasse definiert ist, und ohne Implementierung der Methode in dieser Klasse bereitgestellten, kennzeichnen. Durch einen solchen Verweis hat die gleiche Bedeutung wie `MyBase.` *Methode*.  
  
 Das folgende Beispiel vergleicht `Me` und `MyClass`.  
  
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
  
 Obwohl `derivedClass` überschreibt `testMethod`, `MyClass` -Schlüsselwort in `useMyClass` hebt den Auswirkungen der überschreiben, und der Compiler löst den Aufruf die Basisklassenversion von `testMethod`.  
  
## <a name="see-also"></a>Siehe auch  
 [Inherits-Anweisung](../../../../visual-basic/language-reference/statements/inherits-statement.md)  
 [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
