---
title: Iteratoren (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: f26b5c1e-fe9d-4004-b287-da7919d717ae
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
ms.openlocfilehash: 4ea1e21bd8cc392889c477e78338384ed05d4cbb
ms.lasthandoff: 03/13/2017

---
# <a name="iterators-visual-basic"></a>Iteratoren (Visual Basic)
Ein *Iterator* Sammlungen schrittweise, wie z. B. aufgelistet und arrays verwendet werden können.  
  
 Ein Iterator-Methode oder `get` Accessor führt eine benutzerdefinierte Iteration durch eine Auflistung. Eine Iterator-Methode verwendet die [ergeben](../../../visual-basic/language-reference/statements/yield-statement.md) Anweisung, um jedes Element einzeln nacheinander zurückzugeben. Wenn eine `Yield` -Anweisung erreicht ist, wird die aktuelle Position im Code gespeichert. Die Ausführung wird von diesem Speicherort das nächste Mal neu gestartet, wenn, das die Iteratorfunktion aufgerufen wird.  
  
 Sie erzeugen einen Iterator aus dem Clientcode, indem eine [für jeden... Nächste](../../../visual-basic/language-reference/statements/for-each-next-statement.md) -Anweisung oder mithilfe einer LINQ-Abfrage.  
  
 Im folgenden Beispiel wird die erste Iteration des der `For Each` Schleife wird die Ausführung fortsetzen der `SomeNumbers` Iterator-Methode, bis die erste `Yield` -Anweisung erreicht wird. Diese Iteration gibt einen Wert von 3 zurück, und die aktuelle Position in der Iteratormethode beibehalten wird. Bei der nächsten Iteration der Schleife, in der Iteratormethode Ausführung fortgesetzt, wo er unterbrochen wurde, erneut angehalten werden, wenn er erreicht eine `Yield` Anweisung. Diese Iteration gibt den Wert 5 zurück, und die aktuelle Position in der Iteratormethode ist erneut beibehalten. Die Schleife abgeschlossen wird, wenn das Ende der Iteratormethode erreicht ist.  
  
```vb  
Sub Main()  
    For Each number As Integer In SomeNumbers()  
        Console.Write(number & " ")  
    Next  
    ' Output: 3 5 8  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function SomeNumbers() As System.Collections.IEnumerable  
    Yield 3  
    Yield 5  
    Yield 8  
End Function  
```  
  
 Der Rückgabetyp einer Methode Iterator oder `get` Accessor kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable>  
  
 Sie können eine `Exit Function` oder `Return` Anweisung, um die Iteration zu beenden.  
  
 Eine Visual Basic-Iterator-Funktion oder `get` Accessor-Deklaration enthält ein [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) Modifizierer.  
  
 Iteratoren wurden in Visual Basic in Visual Studio 2012 eingeführt.  
  
 **Inhalt**  
  
-   [Einfacher Iterator](#BKMK_SimpleIterator)  
  
-   [Erstellen einer Auflistungsklasse](#BKMK_CollectionClass)  
  
-   [Try-Blöcke](#BKMK_TryBlocks)  
  
-   [Anonyme Methoden](#BKMK_AnonymousMethods)  
  
-   [Verwenden von Iteratoren mit einer generischen Liste](#BKMK_GenericList)  
  
-   [Informationen zur Syntax](#BKMK_SyntaxInformation)  
  
-   [Technische Implementierung](#BKMK_Technical)  
  
-   [Verwendung von Iteratoren](#BKMK_UseOfIterators)  
  
> [!NOTE]
>  Bei allen Beispielen in diesem Thema außer der einfachen Iterator Beispiel gehören [Importe](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) -Anweisungen für die `System.Collections` und `System.Collections.Generic` Namespaces.  
  
##  <a name="BKMK_SimpleIterator"></a>Einfacher Iterator  
 Im folgende Beispiel verfügt über ein einzelnes `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife. In `Main`, jede Iteration der `For Each` Anweisungstext erstellt einen Aufruf an die Iteratorfunktion, der auf die nächste übergeht `Yield` Anweisung.  
  
```vb  
Sub Main()  
    For Each number As Integer In EvenSequence(5, 18)  
        Console.Write(number & " ")  
    Next  
    ' Output: 6 8 10 12 14 16 18  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function EvenSequence(  
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _  
As System.Collections.Generic.IEnumerable(Of Integer)  
  
    ' Yield even numbers in the range.  
    For number As Integer = firstNumber To lastNumber  
        If number Mod 2 = 0 Then  
            Yield number  
        End If  
    Next  
End Function  
```  
  
##  <a name="BKMK_CollectionClass"></a>Erstellen einer Auflistungsklasse  
 Im folgenden Beispiel die `DaysOfTheWeek` -Klasse implementiert die <xref:System.Collections.IEnumerable>Schnittstelle, erfordert eine <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.IEnumerable> Der Compiler ruft implizit die `GetEnumerator` -Methode, die eine <xref:System.Collections.IEnumerator>.</xref:System.Collections.IEnumerator> zurückgibt  
  
 Die `GetEnumerator` -Methode gibt jede Zeichenfolge eine gleichzeitig mit der `Yield` -Anweisung und eine `Iterator` -Modifizierer ist in der Funktionsdeklaration.  
  
```vb  
Sub Main()  
    Dim days As New DaysOfTheWeek()  
    For Each day As String In days  
        Console.Write(day & " ")  
    Next  
    ' Output: Sun Mon Tue Wed Thu Fri Sat  
    Console.ReadKey()  
End Sub  
  
Private Class DaysOfTheWeek  
    Implements IEnumerable  
  
    Public days =  
        New String() {"Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"}  
  
    Public Iterator Function GetEnumerator() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        ' Yield each day of the week.  
        For i As Integer = 0 To days.Length - 1  
            Yield days(i)  
        Next  
    End Function  
End Class  
```  
  
 Das folgende Beispiel erstellt eine `Zoo` -Klasse, die eine Auflistung von Elementen enthält.  
  
 Die `For Each` -Anweisung, um die Klasseninstanz verweist (`theZoo`) ruft implizit die `GetEnumerator` Methode. Die `For Each` -Anweisungen, die auf die `Birds` und `Mammals` Eigenschaften verwenden die `AnimalsForType` mit dem Namen Iterator-Methode.  
  
```vb  
Sub Main()  
    Dim theZoo As New Zoo()  
  
    theZoo.AddMammal("Whale")  
    theZoo.AddMammal("Rhinoceros")  
    theZoo.AddBird("Penguin")  
    theZoo.AddBird("Warbler")  
  
    For Each name As String In theZoo  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Whale Rhinoceros Penguin Warbler  
  
    For Each name As String In theZoo.Birds  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Penguin Warbler  
  
    For Each name As String In theZoo.Mammals  
        Console.Write(name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: Whale Rhinoceros  
  
    Console.ReadKey()  
End Sub  
  
Public Class Zoo  
    Implements IEnumerable  
  
    ' Private members.  
    Private animals As New List(Of Animal)  
  
    ' Public methods.  
    Public Sub AddMammal(ByVal name As String)  
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Mammal})  
    End Sub  
  
    Public Sub AddBird(ByVal name As String)  
        animals.Add(New Animal With {.Name = name, .Type = Animal.TypeEnum.Bird})  
    End Sub  
  
    Public Iterator Function GetEnumerator() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        For Each theAnimal As Animal In animals  
            Yield theAnimal.Name  
        Next  
    End Function  
  
    ' Public members.  
    Public ReadOnly Property Mammals As IEnumerable  
        Get  
            Return AnimalsForType(Animal.TypeEnum.Mammal)  
        End Get  
    End Property  
  
    Public ReadOnly Property Birds As IEnumerable  
        Get  
            Return AnimalsForType(Animal.TypeEnum.Bird)  
        End Get  
    End Property  
  
    ' Private methods.  
    Private Iterator Function AnimalsForType( _  
    ByVal type As Animal.TypeEnum) As IEnumerable  
        For Each theAnimal As Animal In animals  
            If (theAnimal.Type = type) Then  
                Yield theAnimal.Name  
            End If  
        Next  
    End Function  
  
    ' Private class.  
    Private Class Animal  
        Public Enum TypeEnum  
            Bird  
            Mammal  
        End Enum  
  
        Public Property Name As String  
        Public Property Type As TypeEnum  
    End Class  
End Class  
```  
  
##  <a name="BKMK_TryBlocks"></a>Try-Blöcke  
 Visual Basic ermöglicht eine `Yield` -Anweisung in der `Try` -Block eine [versuchen... Catch... Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Ein `Try` blockieren, die eine `Yield` -Anweisung kann verfügen `Catch` blockiert, und kann einen `Finally` Block.  
  
 Das folgende Beispiel schließt `Try`, `Catch`, und `Finally` eines Iterator-Funktion blockiert. Die `Finally` Block in der Iteratorfunktion ausgeführt wird, bevor die `For Each` Iteration abgeschlossen ist.  
  
```vb  
Sub Main()  
    For Each number As Integer In Test()  
        Console.WriteLine(number)  
    Next  
    Console.WriteLine("For Each is done.")  
  
    ' Output:  
    '  3  
    '  4  
    '  Something happened. Yields are done.  
    '  Finally is called.  
    '  For Each is done.  
    Console.ReadKey()  
End Sub  
  
Private Iterator Function Test() As IEnumerable(Of Integer)  
    Try  
        Yield 3  
        Yield 4  
        Throw New Exception("Something happened. Yields are done.")  
        Yield 5  
        Yield 6  
    Catch ex As Exception  
        Console.WriteLine(ex.Message)  
    Finally  
        Console.WriteLine("Finally is called.")  
    End Try  
End Function  
```  
  
 Ein `Yield` Anweisung kann nicht innerhalb einer `Catch` Block oder ein `Finally` Block.  
  
 Wenn die `For Each` Text (anstelle der Iteratormethode) eine Ausnahme auslöst, ein `Catch` -Block in der Iteratorfunktion wird nicht ausgeführt, aber ein `Finally` Block in der Iteratorfunktion ausgeführt wird. Ein `Catch` Block innerhalb einer Iteratorfunktion nur Ausnahmen abzufangen, die innerhalb der Iteratorfunktion auftreten.  
  
##  <a name="BKMK_AnonymousMethods"></a>Anonyme Methoden  
 In Visual Basic kann eine anonyme Funktion ein Iteratorfunktion. Dies wird anhand des folgenden Beispiels veranschaulicht.  
  
```vb  
Dim iterateSequence = Iterator Function() _  
                      As IEnumerable(Of Integer)  
                          Yield 1  
                          Yield 2  
                      End Function  
  
For Each number As Integer In iterateSequence()  
    Console.Write(number & " ")  
Next  
' Output: 1 2  
Console.ReadKey()  
```  
  
 Das folgende Beispiel enthält eine nicht-Iterator-Methode, die die Argumente überprüft. Die Methode gibt das Ergebnis eines anonymen Iterators, der die Elemente der Auflistung beschreibt.  
  
```vb  
Sub Main()  
    For Each number As Integer In GetSequence(5, 10)  
        Console.Write(number & " ")  
    Next  
    ' Output: 5 6 7 8 9 10  
    Console.ReadKey()  
End Sub  
  
Public Function GetSequence(ByVal low As Integer, ByVal high As Integer) _  
As IEnumerable  
    ' Validate the arguments.  
    If low < 1 Then  
        Throw New ArgumentException("low is too low")  
    End If  
    If high > 140 Then  
        Throw New ArgumentException("high is too high")  
    End If  
  
    ' Return an anonymous iterator function.  
    Dim iterateSequence = Iterator Function() As IEnumerable  
                              For index = low To high  
                                  Yield index  
                              Next  
                          End Function  
    Return iterateSequence()  
End Function  
```  
  
 Wenn Überprüfung stattdessen innerhalb der Iteratorfunktion ist, kann nicht die Überprüfung ausgeführt werden, bis zum Beginn der ersten Iteration der der `For Each` Text.  
  
##  <a name="BKMK_GenericList"></a>Verwenden von Iteratoren mit einer generischen Liste  
 Im folgenden Beispiel die `Stack(Of T)` generische Klasse implementiert die <xref:System.Collections.Generic.IEnumerable%601>generische Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601> Die `Push` Methode weist Werte in ein Array vom Typ `T`. Die <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>-Methode gibt die Array von Werten mit der `Yield` Anweisung.</xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>  
  
 Zusätzlich zu den generischen <xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A>-Methode, die nicht generische <xref:System.Collections.IEnumerable.GetEnumerator%2A>Methode muss auch implementiert werden.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.Generic.IEnumerable%601.GetEnumerator%2A> Grund hierfür ist, <xref:System.Collections.Generic.IEnumerable%601>erbt von <xref:System.Collections.IEnumerable>.</xref:System.Collections.IEnumerable> </xref:System.Collections.Generic.IEnumerable%601> Die nicht generische Implementierung orientiert sich an die generische Implementierung.  
  
 Im Beispiel wird die benannte Iteratoren unterstützen verschiedene Methoden, die gleiche Sammlung von Daten durchlaufen. Diese Iteratoren benannten sind die `TopToBottom` und `BottomToTop` Eigenschaften, und die `TopN` Methode.  
  
 Die `BottomToTop` Eigenschaftendeklaration enthält die `Iterator` Schlüsselwort.  
  
```vb  
Sub Main()  
    Dim theStack As New Stack(Of Integer)  
  
    ' Add items to the stack.  
    For number As Integer = 0 To 9  
        theStack.Push(number)  
    Next  
  
    ' Retrieve items from the stack.  
    ' For Each is allowed because theStack implements  
    ' IEnumerable(Of Integer).  
    For Each number As Integer In theStack  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3 2 1 0  
  
    ' For Each is allowed, because theStack.TopToBottom  
    ' returns IEnumerable(Of Integer).  
    For Each number As Integer In theStack.TopToBottom  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3 2 1 0  
  
    For Each number As Integer In theStack.BottomToTop  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 0 1 2 3 4 5 6 7 8 9   
  
    For Each number As Integer In theStack.TopN(7)  
        Console.Write("{0} ", number)  
    Next  
    Console.WriteLine()  
    ' Output: 9 8 7 6 5 4 3  
  
    Console.ReadKey()  
End Sub  
  
Public Class Stack(Of T)  
    Implements IEnumerable(Of T)  
  
    Private values As T() = New T(99) {}  
    Private top As Integer = 0  
  
    Public Sub Push(ByVal t As T)  
        values(top) = t  
        top = top + 1  
    End Sub  
  
    Public Function Pop() As T  
        top = top - 1  
        Return values(top)  
    End Function  
  
    ' This function implements the GetEnumerator method. It allows  
    ' an instance of the class to be used in a For Each statement.  
    Public Iterator Function GetEnumerator() As IEnumerator(Of T) _  
        Implements IEnumerable(Of T).GetEnumerator  
  
        For index As Integer = top - 1 To 0 Step -1  
            Yield values(index)  
        Next  
    End Function  
  
    Public Iterator Function GetEnumerator1() As IEnumerator _  
        Implements IEnumerable.GetEnumerator  
  
        Yield GetEnumerator()  
    End Function  
  
    Public ReadOnly Property TopToBottom() As IEnumerable(Of T)  
        Get  
            Return Me  
        End Get  
    End Property  
  
    Public ReadOnly Iterator Property BottomToTop As IEnumerable(Of T)  
        Get  
            For index As Integer = 0 To top - 1  
                Yield values(index)  
            Next  
        End Get  
    End Property  
  
    Public Iterator Function TopN(ByVal itemsFromTop As Integer) _  
        As IEnumerable(Of T)  
  
        ' Return less than itemsFromTop if necessary.  
        Dim startIndex As Integer =  
            If(itemsFromTop >= top, 0, top - itemsFromTop)  
  
        For index As Integer = top - 1 To startIndex Step -1  
            Yield values(index)  
        Next  
    End Function  
End Class  
  
```  
  
##  <a name="BKMK_SyntaxInformation"></a>Informationen zur Syntax  
 Ein Iterator kann als Methode auftreten oder `get` Accessor. Ein Iterator kann nicht in ein Ereignis, Instanzkonstruktor, statischen Konstruktor oder Destruktor statische auftreten.  
  
 Eine implizite Konvertierung muss vorhanden sein, über den Typ des Ausdrucks in der `Yield` Anweisung in den Rückgabetyp des Iterators.  
  
 In Visual Basic eine Iteratormethode keine `ByRef` Parameter.  
  
 In Visual Basic "Yield" ist ein reserviertes Wort und hat eine besondere Bedeutung nur bei Verwendung in einem `Iterator` Methode oder `get` Accessor.  
  
##  <a name="BKMK_Technical"></a>Technische Implementierung  
 Obwohl einen Iterator als Methode geschrieben wird, übersetzt der Compiler es in einer geschachtelten Klasse, tatsächlich einen Zustandsautomaten. Diese Klasse verfolgt des die Position des Iterators, wie lange der `For Each...Next` -Schleife im Clientcode fortgesetzt wird.  
  
 Um zu sehen, was geschieht, können Sie das Tool Ildasm.exe verwenden, um die Microsoft intermediate Language-Code anzuzeigen, der für eine Iteratormethode generiert wird.  
  
 Beim Erstellen eines Iterators für eine [Klasse](../../../csharp/language-reference/keywords/class.md) oder [Struktur](../../../csharp/language-reference/keywords/struct.md), Sie müssen nicht die gesamte Implementierung <xref:System.Collections.IEnumerator>Schnittstelle.</xref:System.Collections.IEnumerator> Wenn der Compiler den Iterator erkennt, generiert er automatisch die `Current`, `MoveNext`, und `Dispose` Methoden der <xref:System.Collections.IEnumerator>oder <xref:System.Collections.Generic.IEnumerator%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator>  
  
 Bei jedem Durchlauf von der `For Each…Next` Schleife (oder dem direkten Aufruf von `IEnumerator.MoveNext`), der nächste Iterator Codetext wird fortgesetzt, nach der vorherigen `Yield` Anweisung. Es setzt zur nächsten `Yield` Anweisung, bis das Ende des Iterators erreicht ist, oder bis ein `Exit Function` oder `Return` -Anweisung auftritt.  
  
 Iteratoren unterstützen nicht die <xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName>Methode.</xref:System.Collections.IEnumerator.Reset%2A?displayProperty=fullName> Zum erneuten durchlaufen ab dem Anfang müssen Sie einen neuen Iterator abrufen.  
  
 Weitere Informationen finden Sie unter der [Visual Basic Language Specification](../../../visual-basic/reference/language-specification.md).  
  
##  <a name="BKMK_UseOfIterators"></a>Verwendung von Iteratoren  
 Iteratoren ermöglichen es Ihnen, die Einfachheit der Verwaltung einer `For Each` auf, wenn Sie komplexen Code zum Auffüllen einer Liste Sequenz verwenden müssen. Dies kann nützlich sein, wenn Sie Folgendes tun möchten:  
  
-   Ändern der Reihenfolge nach dem ersten `For Each` Schleifeniteration.  
  
-   Laden eine umfangreiche Liste vor der ersten Iteration der vollständig zu verhindern eine `For Each` Schleife. Ein Beispiel ist die ausgelagerten Fetch einen Batch von Zeilen der Tabelle zu laden. Ein weiteres Beispiel ist die <xref:System.IO.DirectoryInfo.EnumerateFiles%2A>-Methode, die Iteratoren in .NET Framework implementiert.</xref:System.IO.DirectoryInfo.EnumerateFiles%2A>  
  
-   Erstellen der Liste im Iterator zu kapseln. In der Iteratormethode Sie erstellen die Liste und führt dann jedes Ergebnis in einer Schleife.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic></xref:System.Collections.Generic>   
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 [Für jede... Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [Yield-Anweisung](../../../visual-basic/language-reference/statements/yield-statement.md)   
 [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md)
