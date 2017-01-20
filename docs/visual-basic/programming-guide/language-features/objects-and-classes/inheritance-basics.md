---
title: "Inheritance Basics (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "derived classes, inheritance"
  - "MyClass keyword, using"
  - "MyBase keyword, using"
  - "Inherits statement, inheritance"
  - "overriding, Overridable keyword"
  - "MustInherit keyword, using"
  - "Overrides keyword, using"
  - "inheritance"
  - "MustInherit classes"
  - "MustOverride keyword, using"
  - "classes [Visual Basic], derived"
  - "NotInheritable keyword, using"
  - "base classes, extending properties and methods"
  - "NotOverridable keyword, using"
  - "base classes, inheritance"
  - "abstract classes, inheritance"
  - "overriding, Overrides keyword"
ms.assetid: dfc8deba-f5b3-4d1d-a937-7cb826446fc5
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Inheritance Basics (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Mit der `Inherits`–Anweisung wird eine neue Klasse, eine so genannte *abgeleitete Klasse*, deklariert, die auf einer vorhandenen Klasse, der *Basisklasse*, basiert.  Abgeleitete Klassen erben die in der Basisklasse definierten Eigenschaften, Methoden, Ereignisse, Felder und Konstanten und können diese erweitern.  Im folgenden Abschnitt werden einige Vererbungsregeln sowie die Modifizierer beschrieben, die Sie zum Ändern der Vererbungs\- oder Erbungsart für Klassen verwenden können.  
  
-   Standardmäßig können alle Klassen vererbt werden, es sei denn, sie sind durch das Schlüsselwort `NotInheritable` gekennzeichnet.  Klassen können von anderen Klassen in Ihrem Projekt oder von Klassen in anderen Assemblys erben, auf die das Projekt verweist.  
  
-   Im Gegensatz zu Sprachen, für die eine Mehrfachvererbung zulässig ist, sind in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] nur einfache Vererbungen in Klassen möglich, d. h. abgeleitete Klassen können nur eine Basisklasse haben.  Obwohl die Mehrfachvererbung in Klassen nicht zulässig ist, können Klassen mehrfache Schnittstellen implementieren, was die gleiche Wirkung hat.  
  
-   Wenn Sie vermeiden möchten, dass eingeschränkte Elemente in einer Basisklasse verfügbar werden, muss der Zugriffstyp einer abgeleiteten Klasse ebenso eingeschränkt oder eingeschränkter als die Basisklasse sein.  Eine `Public`\-Klasse kann z. B. keine `Friend`\-Klasse oder keine `Private`\-Klasse vererben, und eine `Friend`\-Klasse kann keine `Private`\-Klasse vererben.  
  
## Vererbungsmodifizierer  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] führt folgende Anweisungen und Modifizierer auf Klassenebene zur Unterstützung der Vererbung ein:  
  
-   `Inherits`\-Anweisung: Gibt die Basisklasse an.  
  
-   `NotInheritable`\-Modifizierer: Verhindert, dass Programmierer die Klasse als Basisklasse verwenden.  
  
-   `MustInherit`\-Modifizierer: Gibt an, dass die Klasse nur als Basisklasse verwendet werden soll.  Instanzen der `MustInherit`\-Klassen können nicht direkt, sondern nur als Basisklasseninstanzen einer abgeleiteten Klasse erstellt werden.  \(Andere Programmiersprachen wie z. B. C\+\+ und C\# verwenden den Begriff *abstrakte Klasse*, um eine solche Klasse zu beschreiben\).  
  
## Überschreiben von Eigenschaften und Methoden in abgeleiteten Klassen  
 Standardmäßig erbt eine abgeleitete Klasse Eigenschaften und Methoden von ihrer Basisklasse.  Wenn für eine geerbte Eigenschaft oder Methode in der abgeleiteten Klasse ein anderes Verhalten erforderlich ist, kann sie *überschrieben* werden.  Das heißt, Sie können eine neue Implementierung der Methode in der abgeleiteten Klasse definieren.  Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:  
  
-   `Overridable`: Ermöglicht, dass eine Eigenschaft oder Methode in einer Klasse in einer abgeleiteten Klasse überschrieben wird.  
  
-   `Overrides`: Überschreibt eine `Overridable`\-Eigenschaft oder Overridable\-Methode, die in der Basisklasse definiert ist.  
  
-   `NotOverridable`\- verhindert, dass eine Eigenschaft oder eine Methode in einer erbenden Klasse überschrieben wird.  Standardmäßig sind `Public`\-Methoden `NotOverridable`.  
  
-   `MustOverride`: Eine abgeleitete Klasse muss die Eigenschaft oder Methode überschreiben.  Wenn das `MustOverride`\-Schlüsselwort verwendet wird, besteht die Methodendefinition nur aus den Anweisungen `Sub`, `Function` oder `Property`.  Andere Anweisungen sind nicht zulässig, und insbesondere gibt es keine `End Sub`\-Anweisung oder `End Function`\-Anweisung.  `MustOverride`\-Methoden müssen in `MustInherit`\-Klassen deklariert werden.  
  
 Angenommen, Sie möchten Klassen definieren, um die Gehaltsliste zu verwalten.  Sie können eine allgemeine `Payroll`\-Klasse \(Gehaltslistenklasse\) definieren, die eine `RunPayroll`\-Methode enthält, mit der das Gehalt für eine typische Woche berechnet wird.  Sie können anschließend `Payroll` als Basisklasse für eine spezialisiertere `BonusPayroll`\-Klasse verwenden, die beim Verteilen der Mitarbeiterboni verwendet wird.  
  
 Die `BonusPayroll`\-Klasse kann die `PayEmployee`\-Methode erben und überschreiben, die in der `Payroll`\-Basisklasse definiert ist.  
  
 Im folgenden Beispiel wird eine `Payroll,`\-Basisklasse sowie eine abgeleitete Klasse mit dem Namen `BonusPayroll` definiert, die eine geerbte `PayEmployee`\-Methode überschreibt.  Eine Prozedur mit dem Namen `RunPayroll` erstellt ein `Payroll`\-Objekt und leitet dieses zusammen mit einem `BonusPayroll`\-Objekt an die `Pay`\-Funktion weiter, die die `PayEmployee`\-Methode beider Objekte ausführt.  
  
 [!code-vb[VbVbalrOOP#28](../../../../visual-basic/misc/codesnippet/VisualBasic/VbVbalrOOP/OOP.vb#28)]  
  
## Das MyBase\-Schlüsselwort  
 Das `MyBase`\-Schlüsselwort verhält sich wie eine Objektvariable, die auf die Basisklasse der aktuellen Instanz einer Klasse verweist.  `MyBase` wird häufig für den Zugriff auf Basisklassenmember verwendet, die in einer abgeleiteten Klasse überschrieben werden oder für die ein Shadowing durchgeführt wird.  Insbesondere `MyBase.New` dient dazu, Basisklassenkonstruktoren aus einem abgeleiteten Klassenkonstruktor explizit aufzurufen.  
  
 Angenommen, Sie entwerfen z. B. eine abgeleitete Klasse, die eine aus einer Basisklasse geerbten Methode überschreibt.  Die überschriebene Methode kann die Methode in der Basisklasse aufrufen und den Rückgabewert wie im folgenden Codefragment ändern:  
  
 [!code-vb[VbVbalrOOP#109](../../../../visual-basic/misc/codesnippet/VisualBasic/VbVbalrOOP/OOP.vb#109)]  
  
 Die folgende Liste beschreibt die Einschränkungen bei der Verwendung von `MyBase`:  
  
-   `MyBase` bezieht sich auf die unmittelbare Basisklasse und deren geerbte Member.  Damit kann nicht auf `Private`\-Member in der Klasse zugegriffen werden.  
  
-   `MyBase` ist ein Schlüsselwort, kein wirkliches Objekt.  Es ist nicht möglich, `MyBase` einer Variablen zuzuweisen, einer Prozedur zu übergeben oder in einem `Is`\-Vergleich zu verwenden.  
  
-   Die Methode, von der `MyBase` qualifiziert wird, muss nicht in der unmittelbaren Basisklasse festgelegt sein, sondern kann auch in einer indirekt geerbten Basisklasse definiert werden.  Damit ein von `MyBase` gekennzeichneter Verweis ordnungsgemäß kompiliert wird, muss in einer Basisklasse eine Methode enthalten sein, die dem Namen und den Typen der Parameter entspricht, die im Aufruf angezeigt werden.  
  
-   Mit `MyBase` können Sie die `MustOverride`\-Basisklassenmethoden nicht aufrufen.  
  
-   `MyBase` kann nicht verwendet werden, um sich selbst zu qualifizieren.  Daher ist der folgende Code nicht gültig:  
  
     `MyBase.MyBase.BtnOK_Click()`  
  
-   `MyBase` kann nicht in Modulen verwendet werden.  
  
-   Mit `MyBase` können Sie nicht auf als `Friend` gekennzeichnete Basisklassenmember zugreifen, wenn sich die Basisklasse in einer anderen Assembly befindet.  
  
 Weitere Informationen und ein weiteres Beispiel finden Sie unter [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md).  
  
## Das MyClass\-Schlüsselwort  
 Das `MyClass`\-Schlüsselwort verhält sich wie eine Objektvariable, die auf die aktuelle Klasseninstanz gemäß der ursprünglichen Implementierung verweist.  `MyClass` ähnelt `Me`, allerdings wird jeder Aufruf einer Methode oder Eigenschaft unter Verwendung von `MyClass` so behandelt, als wäre die Methode oder Eigenschaft als [NotOverridable](../../../../visual-basic/language-reference/modifiers/notoverridable.md) deklariert.  Daher wird die Methode oder Eigenschaft nicht durch das Überschreiben in einer abgeleiteten Klasse beeinflusst.  
  
-   `MyClass` ist ein Schlüsselwort, kein wirkliches Objekt.  Es ist nicht möglich, `MyClass` einer Variablen zuzuweisen, einer Prozedur zu übergeben oder in einem `Is`\-Vergleich zu verwenden.  
  
-   `MyClass` bezieht sich auf die enthaltene Klasse und deren geerbte Member.  
  
-   `MyClass` kann als Qualifizierer für `Shared`\-Member verwendet werden.  
  
-   Das `MyClass`\-Schlüsselwort kann nicht innerhalb einer `Shared`\-Methode verwendet werden. Es kann jedoch innerhalb einer Instanzenmethode angegeben werden, um auf einen freigegebenen Member einer Klasse zuzugreifen.  
  
-   `MyClass` kann nicht in Standardmodulen verwendet werden.  
  
-   Mit `MyClass` kann eine Methode qualifiziert werden, die in einer Basisklasse definiert ist und die keine Implementierung der in dieser Klasse enthaltenen Methode aufweist.  Ein solcher Verweis hat dieselbe Bedeutung wie `MyBase.`*Methode*.  
  
 Im folgenden Beispiel werden das `Me`\-Schlüsselwort und das `MyClass`\-Schlüsselwort miteinander verglichen.  
  
```  
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
  
 Obwohl `testMethod` durch `derivedClass` überschrieben wird, hebt das `MyClass`\-Schlüsselwort in `useMyClass` diese Wirkung auf. Der Compiler löst daraufhin den Aufruf an die Basisklassenversion von `testMethod` auf.  
  
## Siehe auch  
 [Inherits Statement](../../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)