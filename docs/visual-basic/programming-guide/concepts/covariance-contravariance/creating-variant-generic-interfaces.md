---
title: Erstellen von Varianten generischen Schnittstellen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: d4037dd2-dfe9-4811-9150-93d4e8b20113
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 324e2a906e84950aa9019bbf68a524458492646e
ms.lasthandoff: 03/13/2017

---
# <a name="creating-variant-generic-interfaces-visual-basic"></a>Erstellen von Varianten generischen Schnittstellen (Visual Basic)
Sie können deklarieren, generischen Typparametern in Schnittstellen als kovariant oder kontravariant. *Kovarianz* ermöglicht Schnittstellenmethoden, stärker abgeleitete Rückgabetypen zu verwenden, als durch die generischen Typparameter definiert. *Kontravarianz* ermöglicht Schnittstellenmethoden Argumenttypen zu verwenden, die weniger stark abgeleitet sind, als durch die generischen Parameter angegeben. Eine generische Schnittstelle mit ko- oder kontravarianten generischen Typparametern heißt *Variante*.  
  
> [!NOTE]
>  Varianz-Unterstützung für mehrere vorhandene generische Schnittstellen wurde in .NET Framework 4 eingeführt. Die Liste der Varianten Schnittstellen in .NET Framework finden Sie unter [Varianz in generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md).  
  
## <a name="declaring-variant-generic-interfaces"></a>Deklarieren von Varianten generischen Schnittstellen  
 Sie können Variante generische Schnittstellen deklarieren, indem die `in` und `out` Schlüsselwörter für generische Typparameter.  
  
> [!IMPORTANT]
>  `ByRef`-Parameter in Visual Basic nicht Variant-Wert. Varianz unterstützt Werttypen auch nicht.  
  
 Sie können einen generischen Typparameter kovariant deklarieren, indem die `out` Schlüsselwort. Der kovariante Typ muss Folgendes erfüllen:  
  
-   Der Typ wird nur als Rückgabetyp von Schnittstellenmethoden verwendet und nicht als Typ von Methodenargumenten verwendet. Dies wird im folgenden Beispiel, in dem veranschaulicht den Typ `R` als kovariant deklariert ist.  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Function GetSomething() As R  
        ' The following statement generates a compiler error.  
        ' Sub SetSomething(ByVal sampleArg As R)  
    End Interface  
    ```  
  
     Es gibt allerdings eine Ausnahme zu dieser Regel. Wenn Sie einen kontravarianten generischen Delegaten als Methodenparameter angegeben haben, können Sie den Typ als einen generischen Typparameter für den Delegaten verwenden. Dies wird durch den Typ veranschaulicht `R` im folgenden Beispiel. Weitere Informationen finden Sie unter [Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) und [mithilfe von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md).  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        Sub DoSomething(ByVal callback As Action(Of R))  
    End Interface  
    ```  
  
-   Der Typ wird nicht als generische Einschränkung für die Schnittstellenmethoden verwendet. Dies wird im folgenden Code veranschaulicht.  
  
    ```vb  
    Interface ICovariant(Of Out R)  
        ' The following statement generates a compiler error  
        ' because you can use only contravariant or invariant types  
        ' in generic contstraints.  
        ' Sub DoSomething(Of T As R)()  
    End Interface  
    ```  
  
 Sie können einen generischen Typparameter als Kontravariante deklarieren, indem die `in` Schlüsselwort. Der kontravariante Typ kann nur als Typ von Methodenargumenten und nicht als Rückgabetyp von Schnittstellenmethoden verwendet werden. Der kontravariante Typ kann auch für generische Einschränkungen verwendet werden. Der folgende Code zeigt, wie eine kontravariante Schnittstelle deklariert und eine generische Einschränkung für eine seiner Methoden verwenden.  
  
```vb  
Interface IContravariant(Of In A)  
    Sub SetSomething(ByVal sampleArg As A)  
    Sub DoSomething(Of T As A)()  
    ' The following statement generates a compiler error.  
    ' Function GetSomething() As A  
End Interface  
```  
  
 Es ist auch möglich, Kovarianz und Kontravarianz in derselben Schnittstelle, aber für unterschiedliche Typparameter unterstützen, wie im folgenden Codebeispiel gezeigt.  
  
```vb  
Interface IVariant(Of Out R, In A)  
    Function GetSomething() As R  
    Sub SetSomething(ByVal sampleArg As A)  
    Function GetSetSomething(ByVal sampleArg As A) As R  
End Interface  
```  
  
 In Visual Basic können Sie Ereignisse in Varianten Schnittstellen deklarieren, ohne den Delegattyp anzugeben. Außerdem eine Variante Schnittstelle kann jedoch keine geschachtelten Klassen, Enumerationen und Strukturen, Schnittstellen geschachtelt haben. Dies wird im folgenden Code veranschaulicht.  
  
```vb  
Interface ICovariant(Of Out R)  
    ' The following statement generates a compiler error.  
    ' Event SampleEvent()  
    ' The following statement specifies the delegate type and   
    ' does not generate an error.  
    Event AnotherEvent As EventHandler  
  
    ' The following statements generate compiler errors,  
    ' because a variant interface cannot have  
    ' nested enums, classes, or structures.  
  
    'Enum SampleEnum : test : End Enum  
    'Class SampleClass : End Class  
    'Structure SampleStructure : Dim value As Integer : End Structure  
  
    ' Variant interfaces can have nested interfaces.  
    Interface INested : End Interface  
End Interface  
```  
  
## <a name="implementing-variant-generic-interfaces"></a>Implementieren von Varianten generischen Schnittstellen  
 Variante generische Schnittstellen in Klassen zu implementieren, mit der gleichen Syntax, die für invariante Schnittstellen verwendet wird. Im folgenden Codebeispiel wird veranschaulicht, wie eine kovariante Schnittstelle in einer generischen Klasse implementiert wird.  
  
```vb  
Interface ICovariant(Of Out R)  
    Function GetSomething() As R  
End Interface  
  
Class SampleImplementation(Of R)  
    Implements ICovariant(Of R)  
    Public Function GetSomething() As R _  
    Implements ICovariant(Of R).GetSomething  
        ' Some code.  
    End Function  
End Class  
```  
  
 Klassen, die Variante Schnittstellen zu implementieren sind unveränderlich. Betrachten Sie hierzu den folgenden Beispielcode:  
  
```vb  
 The interface is covariant.  
Dim ibutton As ICovariant(Of Button) =  
    New SampleImplementation(Of Button)  
Dim iobj As ICovariant(Of Object) = ibutton  
  
' The class is invariant.  
Dim button As SampleImplementation(Of Button) =  
    New SampleImplementation(Of Button)  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim obj As SampleImplementation(Of Object) = button  
```  
  
## <a name="extending-variant-generic-interfaces"></a>Erweitern von Varianten generischen Schnittstellen  
 Wenn Sie eine Variante generische Schnittstelle erweitern, müssen Sie die `in` und `out` Schlüsselwörter explizit angeben, ob Varianz von der abgeleitete Schnittstelle unterstützt. Der Compiler leitet sich nicht auf die Abweichung von der Schnittstelle aus, der erweitert wird. Betrachten Sie beispielsweise die folgenden Schnittstellen.  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T)  
End Interface  
  
Interface IExtCovariant(Of Out T)  
    Inherits ICovariant(Of T)  
End Interface  
```  
  
 In der `Invariant(Of T)` Schnittstelle, die generischen Typparameter `T` ist unveränderlich, während in `IExtCovariant (Of Out T)`der Typparameter ist kovariant, obwohl beide Schnittstellen die gleiche Schnittstelle erweitern. Die gleiche Regel gilt für kontravariante generische Typparameter.  
  
 Sie können eine Schnittstelle, die die Schnittstelle, in dem der generische Typparameter, erweitert erstellen `T` ist kovariant sowie die Schnittstelle mit dem kontravarianten in der erweiternden Schnittstelle den generische Typparameter `T` ist unveränderlich. Dies wird im folgenden Codebeispiel veranschaulicht.  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
Interface IContravariant(Of In T)  
End Interface  
  
Interface IInvariant(Of T)  
    Inherits ICovariant(Of T), IContravariant(Of T)  
End Interface  
```  
  
 Jedoch, wenn ein generischer Typparameter `T` ist kovariant in einer Schnittstelle deklariert, Deklaration kann nicht über kontravariante in der erweiternden Schnittstelle (oder umgekehrt). Dies wird im folgenden Codebeispiel veranschaulicht.  
  
```vb  
Interface ICovariant(Of Out T)  
End Interface  
  
' The following statements generate a compiler error.  
' Interface ICoContraVariant(Of In T)  
'     Inherits ICovariant(Of T)  
' End Interface  
```  
  
### <a name="avoiding-ambiguity"></a>Vermeiden von Mehrdeutigkeit  
 Wenn Sie eine Variante generische Schnittstellen implementieren, kann Varianz manchmal zu Mehrdeutigkeit führen. Dies sollte vermieden werden.  
  
 Wenn Sie explizit die gleiche Variante generische Schnittstelle mit unterschiedlichen generischen Typparametern in einer Klasse implementieren, können sie z. B. Mehrdeutigkeit erstellen. Der Compiler einen Fehler in diesem Fall erzeugt, aber es ist nicht angegeben, welche Implementierung zur Laufzeit ausgewählt wird. Dies kann zu schwer erkennbaren Fehlern im Code führen. Betrachten Sie das folgende Codebeispiel.  
  
> [!NOTE]
>  Mit `Option Strict Off`, Visual Basic generiert eine Warnung der Compiler, wenn eine Implementierung von mehrdeutiger vorhanden ist. Mit `Option Strict On`, Visual Basic wird ein Compilerfehler generiert.  
  
```vb  
' Simple class hierarchy.  
Class Animal  
End Class  
  
Class Cat  
    Inherits Animal  
End Class  
  
Class Dog  
    Inherits Animal  
End Class  
  
' This class introduces ambiguity  
' because IEnumerable(Of Out T) is covariant.  
Class Pets  
    Implements IEnumerable(Of Cat), IEnumerable(Of Dog)  
  
    Public Function GetEnumerator() As IEnumerator(Of Cat) _  
        Implements IEnumerable(Of Cat).GetEnumerator  
        Console.WriteLine("Cat")  
        ' Some code.  
    End Function  
  
    Public Function GetEnumerator1() As IEnumerator(Of Dog) _  
        Implements IEnumerable(Of Dog).GetEnumerator  
        Console.WriteLine("Dog")  
        ' Some code.  
    End Function  
  
    Public Function GetEnumerator2() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
        ' Some code.  
    End Function  
End Class  
  
Sub Main()  
    Dim pets As IEnumerable(Of Animal) = New Pets()  
    pets.GetEnumerator()  
End Sub  
```  
  
 In diesem Beispiel ist nicht angegeben wie die `pets.GetEnumerator` Methode wählt zwischen `Cat` und `Dog`. Dies kann Probleme im Code verursachen.  
  
## <a name="see-also"></a>Siehe auch  
 [Varianz in generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)   
 [Verwenden von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)
