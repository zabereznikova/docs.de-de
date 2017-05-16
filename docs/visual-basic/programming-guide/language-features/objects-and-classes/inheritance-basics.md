---
title: Grundlagen der Vererbung (Visual Basic) | Microsoft-Dokumentation
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
- derived classes, inheritance
- MyClass keyword, using
- MyBase keyword, using
- Inherits statement, inheritance
- overriding, Overridable keyword
- MustInherit keyword, using
- Overrides keyword, using
- inheritance
- MustInherit classes
- MustOverride keyword, using
- classes [Visual Basic], derived
- NotInheritable keyword, using
- base classes, extending properties and methods
- NotOverridable keyword, using
- base classes, inheritance
- abstract classes, inheritance
- overriding, Overrides keyword
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
caps.latest.revision: 23
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 58aee9f8c348eb06daec2b8c9e332f3f2775bcb6
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="inheritance-basics-visual-basic"></a>Grundlagen der Vererbung (Visual Basic)
Die `Inherits` -Anweisung verwendet, um eine neue Klasse namens deklarieren eine *abgeleitete Klasse*, basierend auf einer vorhandenen Klasse, eine *Basisklasse*. Abgeleitete Klassen erben und erweitern können, die Eigenschaften, Methoden, Ereignisse, Felder und Konstanten, die in der Basisklasse definiert. Im folgenden Abschnitt werden einige der Regeln für die Vererbung, und die Parameter auf, die Sie verwenden können, so ändern Sie die Möglichkeit Klassen erben oder geerbt werden:  
  
-   Standardmäßig sind alle Klassen vererbt, es sei denn, mit dem `NotInheritable` Schlüsselwort. Klassen können von anderen Klassen in Ihrem Projekt oder von Klassen in anderen Assemblys, die das Projekt verweist auf erben.  
  
-   Im Gegensatz zu den Sprachen, die mehrere Vererbungen zu ermöglichen [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] können nur einfache Vererbung in Klassen, abgeleitete Klassen können nur eine Basisklasse, also aufweisen. Mehrfache Vererbung in Klassen nicht zulässig ist, können Klassen mehrere Schnittstellen implementieren, die effektiv desselben erreichen können.  
  
-   Um zu verhindern, dass eingeschränkte Elemente in einer Basisklasse verfügbar machen, muss der Zugriffstyp einer abgeleiteten Klasse restriktiver als die Basisklasse oder gleich sein. Z. B. eine `Public` Klasse erben kann kein `Friend` oder ein `Private` -Klasse, und ein `Friend` Klasse kann nicht geerbt eine `Private` Klasse.  
  
## <a name="inheritance-modifiers"></a>Vererbungsmodifizierer  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]führt die folgenden auf Klassenebene-Anweisungen und Modifizierer für die Vererbung unterstützen:  
  
-   `Inherits`Anweisung: Gibt die Basisklasse an.  
  
-   `NotInheritable`Modifizierer – verhindert, dass Programmierer die Klasse als Basisklasse verwenden.  
  
-   `MustInherit`Modifizierer – gibt an, dass die Klasse nur als Basisklasse verwendet werden soll. Instanzen von `MustInherit` Klassen können nicht direkt erstellt werden; sie können nur erstellt werden als base Klasseninstanzen einer abgeleiteten Klasse. (Andere Programmiersprachen wie C++ und c# verwenden den Begriff *abstrakte Klasse* um eine solche Klasse zu beschreiben.)  
  
## <a name="overriding-properties-and-methods-in-derived-classes"></a>Überschreiben von Eigenschaften und Methoden in abgeleiteten Klassen  
 Standardmäßig erbt eine abgeleitete Klasse Eigenschaften und Methoden von ihrer Basisklasse. Besitzt eine geerbte Eigenschaft oder Methode in der abgeleiteten Klasse anders Verhalten möglich *überschreiben*. Das heißt, können Sie eine neue Implementierung der Methode in der abgeleiteten Klasse definieren. Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:  
  
-   `Overridable`– Ermöglicht eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben werden.  
  
-   `Overrides`– Überschreibt eine `Overridable` Eigenschaft oder Methode in der Basisklasse definiert.  
  
-   `NotOverridable`– Verhindert, dass eine Eigenschaft oder Methode in einer erbenden Klasse überschrieben wird. In der Standardeinstellung `Public` Methoden sind `NotOverridable`.  
  
-   `MustOverride`– Muss eine abgeleitete Klasse überschreiben, die Eigenschaft oder Methode. Wenn die `MustOverride` Schlüsselwort verwendet wird, besteht aus der Definition der Methode lediglich die `Sub`, `Function`, oder `Property` Anweisung. Keine weiteren Anweisungen sind zulässig, und insbesondere ist keine `End Sub` oder `End Function` Anweisung. `MustOverride`Methoden müssen deklariert werden, `MustInherit` Klassen.  
  
 Angenommen Sie, Sie möchten zum Definieren von Klassen, um die Gehaltsliste zu verwalten. Sie definieren eine generische `Payroll` Klasse enthält eine `RunPayroll` -Methode, die Gehaltsdaten für eine normale Woche berechnet. Sie können dann `Payroll` als Basisklasse für eine spezielle `BonusPayroll` -Klasse, die beim Verteilen der Mitarbeiterboni verwendet.  
  
 Die `BonusPayroll` Klasse erben und außer Kraft setzen, kann der `PayEmployee` in der Basisklasse definierte Methode `Payroll` Klasse.  
  
 Das folgende Beispiel definiert eine Basisklasse `Payroll,` und einer abgeleiteten Klasse `BonusPayroll`, die eine geerbte Methode, überschreibt `PayEmployee`. Eine Prozedur `RunPayroll`, erstellt und übergibt eine `Payroll` Objekt und ein `BonusPayroll` -Objekt an eine Funktion `Pay`, ausgeführt wird, die `PayEmployee` -Methode beider Objekte.  
  
 [!code-vb[VbVbalrOOP&#28;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_1.vb)]  
  
## <a name="the-mybase-keyword"></a>MyBase-Schlüsselwort  
 Das `MyBase` -Schlüsselwort verhält sich wie eine Objektvariable, die auf die Basisklasse der aktuellen Instanz einer Klasse verweist. `MyBase`Member der Basisklasse zugreifen, die überschrieben werden, oder in einer abgeleiteten Klasse gespiegelt wird häufig verwendet werden. Insbesondere `MyBase.New` wird verwendet, um einen Basisklassenkonstruktor aus einem abgeleiteten Klassenkonstruktor explizit aufzurufen.  
  
 Nehmen wir beispielsweise an, dass Sie eine abgeleitete Klasse entwerfen, die eine von der Basisklasse geerbten Methode überschreibt. Die überschriebene Methode kann die Methode in der Basisklasse aufrufen und den Rückgabewert zu ändern, wie im folgenden Codefragment gezeigt:  
  
 [!code-vb[VbVbalrOOP&#109;](../../../../visual-basic/misc/codesnippet/VisualBasic/inheritance-basics_2.vb)]  
  
 Die folgende Liste beschreibt die Einschränkungen zur Verwendung von `MyBase`:  
  
-   `MyBase`bezieht sich auf die unmittelbare Basisklasse und deren geerbte Member. Kann nicht verwendet werden für den Zugriff auf `Private` Member in der Klasse.  
  
-   `MyBase`ist ein Schlüsselwort, kein wirkliches Objekt. `MyBase`einer Variablen zugewiesen, in der Prozedur zu übergeben oder in verwendet werden kann kein `Is` Vergleich.  
  
-   Die Methode, die `MyBase` qualifiziert muss nicht in der unmittelbaren Basisklasse; definiert werden sie möglicherweise stattdessen in einer indirekt geerbten Basisklasse definiert werden. Ein Verweis von qualifizierten `MyBase` ordnungsgemäß kompiliert wird, muss die Basisklasse enthalten einer Methode mit dem Namen und Typen der Parameter, die im Aufruf angezeigt werden.  
  
-   Sie können keine `MyBase` Aufrufen `MustOverride` Klassenmethoden basieren.  
  
-   `MyBase`kann verwendet werden, um sich selbst zu qualifizieren. Daher ist der folgende Code ungültig:  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   `MyBase`kann nicht in Modulen verwendet werden.  
  
-   `MyBase`kann nicht verwendet werden, um den Zugriff auf Basisklassenmember, die als markiert sind `Friend` ist die Basisklasse in einer anderen Assembly.  
  
 Weitere Informationen und ein weiteres Beispiel finden Sie unter [Gewusst wie: Zugriff auf eine Variable Hidden durch eine abgeleitete Klasse](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
## <a name="the-myclass-keyword"></a>MyClass-Schlüsselwort  
 Das `MyClass` -Schlüsselwort verhält sich wie eine Objektvariable, die auf die aktuelle Instanz einer Klasse, die gemäß der ursprünglichen Implementierung verweist. `MyClass`ähnelt `Me`, aber alle Methoden und Eigenschaften, die in Aufrufen `MyClass` wird behandelt, als wäre die Methode oder Eigenschaft [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md). Aus diesem Grund ist die Methode oder Eigenschaft nicht betroffen in einer abgeleiteten Klasse überschreiben.  
  
-   `MyClass`ist ein Schlüsselwort, kein wirkliches Objekt. `MyClass`einer Variablen zugewiesen, in der Prozedur zu übergeben oder in verwendet werden kann kein `Is` Vergleich.  
  
-   `MyClass`bezieht sich auf die enthaltene Klasse und deren geerbte Member.  
  
-   `MyClass`kann verwendet werden, als Qualifizierer für `Shared` Elemente.  
  
-   `MyClass`kann nicht verwendet werden, in eine `Shared` -Methode, aber innerhalb einer Instanzmethode Zugriff auf einen freigegebenen Member einer Klasse verwendet werden können.  
  
-   `MyClass`kann nicht in Standardmodulen verwendet werden.  
  
-   `MyClass`kann verwendet werden, qualifizieren Sie eine Methode in einer Basisklasse definiert ist und die keine Implementierung der in dieser Klasse enthaltenen Methode aufweist. Durch einen solchen Verweis hat dieselbe Bedeutung wie `MyBase.` *Methode*.  
  
 Im folgenden Beispiel werden `Me` und `MyClass`.  
  
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
  
 Obwohl `derivedClass` überschreibt `testMethod`, `MyClass` Schlüsselwort in `useMyClass` wird überschrieben, und der Compiler löst den Aufruf von die Basisklassenversion von `testMethod`.  
  
## <a name="see-also"></a>Siehe auch  
 [Inherits-Anweisung](../../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)

