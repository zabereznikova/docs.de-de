---
title: Sammlungen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: get-started-article
dev_langs:
- VB
ms.assetid: 5f7749f3-aaf2-4319-b63c-bfa72e1e2b7a
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: b3c8de3e22075d576f86bcd4eb599946740ebe16
ms.lasthandoff: 03/13/2017

---
# <a name="collections-visual-basic"></a>Sammlungen (Visual Basic)
Für eine Vielzahl von Anwendungen sollten Sie Gruppen von miteinander verwandten Objekten erstellen und verwalten. Zum Gruppieren von Objekten gibt es zwei Möglichkeiten: das Erstellen von Objektarrays und das Erstellen von Auflistungen von Objekten.  
  
 Arrays am besten zum Erstellen und Arbeiten mit einer festen Anzahl von Objekten mit starkem Typ geeignet. Weitere Informationen zu Arrays finden Sie unter [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
 Auflistungen ermöglichen ein flexibleres Arbeiten mit Objektgruppen. Im Gegensatz zu Arrays kann sich die Gruppe von Objekten, mit denen Sie arbeiten, in Abhängigkeit von den sich ändernden Anforderungen der Anwendung dynamisch vergrößern bzw. verkleinern. Bei einigen Auflistungen können Sie jedem Objekt, das Sie in die Auflistung einfügen, einen Schlüssel zuweisen, sodass das Objekt anhand des Schlüssels schnell abgerufen werden kann.  
  
 Eine Auflistung ist eine Klasse. Daher müssen Sie eine Instanzen der Klasse deklarieren, bevor Sie dieser Auflistung Elemente hinzufügen können.  
  
 Wenn die Auflistung Elemente eines Datentyps enthält, können Sie eine der Klassen in der <xref:System.Collections.Generic?displayProperty=fullName>Namespace.</xref:System.Collections.Generic?displayProperty=fullName> Eine generische Auflistung erzwingt Typsicherheit, sodass der Auflistung kein anderer Datentyp hinzugefügt werden kann. Wenn Sie ein Element aus einer generischen Auflistung abrufen, brauchen Sie dessen Datentyp nicht zu bestimmen oder zu konvertieren.  
  
> [!NOTE]
>  Bei den Beispielen in diesem Thema enthalten [Importe](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) -Anweisungen für die `System.Collections.Generic` und `System.Linq` Namespaces.  
  
 **Inhalt**  
  
-   [Verwenden einer einfachen Auflistung](#BKMK_SimpleCollection)  
  
-   [Arten von Sammlungen](#BKMK_KindsOfCollections)  
  
    -   [System.Collections.Generic-Klassen](#BKMK_Generic)  
  
    -   [System.Collections.Concurrent-Klassen](#BKMK_Concurrent)  
  
    -   [System.Collections-Klassen](#BKMK_Collections)  
  
    -   [Visual Basic-Auflistungsklasse](#BKMK_VisualBasic)  
  
-   [Implementieren einer Auflistung von Schlüssel-Wert-Paaren](#BKMK_KeyValuePairs)  
  
-   [Verwenden von LINQ zum Zugriff auf eine Auflistung](#BKMK_LINQ)  
  
-   [Sortieren einer Auflistung](#BKMK_Sorting)  
  
-   [Definieren einer benutzerdefinierten Auflistung](#BKMK_CustomCollection)  
  
-   [Iteratoren](#BKMK_Iterators)  
  
<a name="BKMK_SimpleCollection"></a>
## <a name="using-a-simple-collection"></a>Verwenden einer einfachen Auflistung  
 In den Beispielen in diesem Abschnitt verwenden Sie die generischen <xref:System.Collections.Generic.List%601>-Klasse, die Sie mit eine stark typisierte Liste von Objekten arbeiten kann.</xref:System.Collections.Generic.List%601>  
  
 Das folgende Beispiel erstellt eine Liste von Zeichenfolgen und durchläuft dann die Zeichenfolgen unter Verwendung einer [für jede... Nächste](../../../visual-basic/language-reference/statements/for-each-next-statement.md) Anweisung.  
  
```vb  
' Create a list of strings.  
Dim salmons As New List(Of String)  
salmons.Add("chinook")  
salmons.Add("coho")  
salmons.Add("pink")  
salmons.Add("sockeye")  
  
' Iterate through the list.  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 Wenn der Inhalt einer Auflistung im Voraus bekannt sind, können Sie eine *Auflistungsinitialisierer* zum Initialisieren der Auflistung. Weitere Informationen finden Sie unter [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md).  
  
 Das folgende Beispiel entspricht dem vorherigen Beispiel, außer dass ein Auflistungsinitialisierer verwendet wird, um der Auflistung Elemente hinzuzufügen.  
  
```vb  
' Create a list of strings by using a  
' collection initializer.  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 Sie können eine [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) -Anweisung statt einer `For Each` Anweisung zum Durchlaufen einer Auflistung. Sie erreichen dies, indem Sie durch die Indexposition auf die Auflistungselemente zugreifen. Der Index der Elemente beginnt mit 0 und endet an der Elementanzahl minus 1.  
  
 Im folgenden Beispiel werden die Elemente einer Auflistung unter Verwendung von `For…Next` anstelle von `For Each` durchlaufen.  
  
```vb  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
For index = 0 To salmons.Count - 1  
    Console.Write(salmons(index) & " ")  
Next  
'Output: chinook coho pink sockeye  
```  
  
 Im folgenden Beispiel wird ein Element aus der Auflistung entfernt, indem das zu entfernende Objekt angegeben wird.  
  
```vb  
' Create a list of strings by using a  
' collection initializer.  
Dim salmons As New List(Of String) From  
    {"chinook", "coho", "pink", "sockeye"}  
  
' Remove an element in the list by specifying  
' the object.  
salmons.Remove("coho")  
  
For Each salmon As String In salmons  
    Console.Write(salmon & " ")  
Next  
'Output: chinook pink sockeye  
```  
  
 Im folgenden Beispiel werden alle Elemente aus einer generischen Liste entfernt. Statt eine `For Each` -Anweisung, eine [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) -Anweisung verwendet, die Elemente in absteigender Reihenfolge durchläuft. Grund hierfür ist die <xref:System.Collections.Generic.List%601.RemoveAt%2A>Methode bewirkt, dass Elemente nach einem entfernten Element einen niedrigeren Indexwert haben.</xref:System.Collections.Generic.List%601.RemoveAt%2A>  
  
```vb  
Dim numbers As New List(Of Integer) From  
    {0, 1, 2, 3, 4, 5, 6, 7, 8, 9}  
  
' Remove odd numbers.  
For index As Integer = numbers.Count - 1 To 0 Step -1  
    If numbers(index) Mod 2 = 1 Then  
        ' Remove the element by specifying  
        ' the zero-based index in the list.  
        numbers.RemoveAt(index)  
    End If  
Next  
  
' Iterate through the list.  
' A lambda expression is placed in the ForEach method  
' of the List(T) object.  
numbers.ForEach(  
    Sub(number) Console.Write(number & " "))  
' Output: 0 2 4 6 8  
```  
  
 Für den Typ der Elemente in den <xref:System.Collections.Generic.List%601>Sie können auch eine eigene Klasse definieren</xref:System.Collections.Generic.List%601> Im folgenden Beispiel die `Galaxy` Klasse, die von der <xref:System.Collections.Generic.List%601>im Code definiert ist.</xref:System.Collections.Generic.List%601>  
  
```vb  
Private Sub IterateThroughList()  
    Dim theGalaxies As New List(Of Galaxy) From  
        {  
            New Galaxy With {.Name = "Tadpole", .MegaLightYears = 400},  
            New Galaxy With {.Name = "Pinwheel", .MegaLightYears = 25},  
            New Galaxy With {.Name = "Milky Way", .MegaLightYears = 0},  
            New Galaxy With {.Name = "Andromeda", .MegaLightYears = 3}  
        }  
  
    For Each theGalaxy In theGalaxies  
        With theGalaxy  
            Console.WriteLine(.Name & "  " & .MegaLightYears)  
        End With  
    Next  
  
    ' Output:  
    '  Tadpole  400  
    '  Pinwheel  25  
    '  Milky Way  0  
    '  Andromeda  3  
End Sub  
  
Public Class Galaxy  
    Public Property Name As String  
    Public Property MegaLightYears As Integer  
End Class  
```  
  
<a name="BKMK_KindsOfCollections"></a>
## <a name="kinds-of-collections"></a>Arten von Auflistungen   
 Viele allgemeine Auflistungen werden von .NET Framework bereitgestellt. Jeder Auflistungstyp ist für einen speziellen Zweck ausgelegt.  
  
 Einige der häufig verwendeten Auflistungsklassen werden in diesem Abschnitt beschrieben:  
  
-   @System.Collections.Generic-Klassen  
  
-   @System.Collections.Concurrent-Klassen  
  
-   @System.Collections-Klassen  
  
-   Visual Basic-`Collection`sklasse  
  
<a name="BKMK_Generic"></a>
### <a name="systemcollectionsgeneric-classes"></a>System.Collections.Generic-Klassen  

 Erstellen einer generischen Auflistung können Sie mithilfe einer der Klassen in der <xref:System.Collections.Generic>Namespace.</xref:System.Collections.Generic> Eine generische Auflistung ist sinnvoll, wenn jedes Element der Auflistung zum gleichen Datentyp gehört. Eine generische Auflistung erzwingt eine starke Typisierung, da ihr nur Elemente des gewünschten Datentyps hinzugefügt werden können.  
  
 Die folgende Tabelle enthält einige der häufig verwendeten Klassen von der <xref:System.Collections.Generic?displayProperty=fullName>Namespace:</xref:System.Collections.Generic?displayProperty=fullName>  
  
|Klasse|Beschreibung|  
|---|---|  
|<xref:System.Collections.Generic.Dictionary%602></xref:System.Collections.Generic.Dictionary%602>|Stellt eine Auflistung von Schlüssel-Wert-Paaren dar, deren Reihenfolge anhand des Schlüssels bestimmt wird.|  
|<xref:System.Collections.Generic.List%601></xref:System.Collections.Generic.List%601>|Stellt eine Liste von Objekten dar, auf die über einen Index zugegriffen werden kann. Stellt Methoden zum Durchsuchen, Sortieren und Bearbeiten von Listen bereit.|  
|<xref:System.Collections.Generic.Queue%601></xref:System.Collections.Generic.Queue%601>|Stellt eine FIFO-Auflistung (First In, First Out) von Objekten dar.|  
|<xref:System.Collections.Generic.SortedList%602></xref:System.Collections.Generic.SortedList%602>|Stellt eine Auflistung von Schlüssel-Wert-Paaren, die auf Grundlage der zugeordneten Schlüssel sortiert <xref:System.Collections.Generic.IComparer%601>Implementierung.</xref:System.Collections.Generic.IComparer%601>|  
|<xref:System.Collections.Generic.Stack%601></xref:System.Collections.Generic.Stack%601>|Stellt eine LIFO-Auflistung (Last In, First Out) von Objekten dar.|  
  
 Weitere Informationen finden Sie unter [häufig verwendete Auflistungstypen](http://msdn.microsoft.com/library/f5d4c6a4-0d7b-4944-a9fb-3b12d9ebfd55), [Auswählen einer Auflistungsklasse](../../../standard/collections/selecting-a-collection-class.md), und <xref:System.Collections.Generic?displayProperty=fullName>.</xref:System.Collections.Generic?displayProperty=fullName>  
  
<a name="BKMK_Concurrent"></a>
### <a name="systemcollectionsconcurrent-classes"></a>System.Collections.Concurrent-Klassen   
 In .NET Framework 4 oder höher, die Auflistungen in der <xref:System.Collections.Concurrent>Namespace effiziente threadsichere Operationen für den Zugriff auf Auflistungselemente aus mehreren Threads bereit.</xref:System.Collections.Concurrent>  
  
 Die Klassen in der <xref:System.Collections.Concurrent>Namespace sollte verwendet werden, anstatt die entsprechenden Typen in der <xref:System.Collections.Generic?displayProperty=fullName>und <xref:System.Collections?displayProperty=fullName>Namespaces, wenn mehrere Threads gleichzeitig auf die Auflistung zugreifen.</xref:System.Collections?displayProperty=fullName> </xref:System.Collections.Generic?displayProperty=fullName> </xref:System.Collections.Concurrent> Weitere Informationen finden Sie unter [threadsichere Auflistungen](../../../standard/collections/threadsafe/index.md) und <xref:System.Collections.Concurrent>.</xref:System.Collections.Concurrent>  
  
 Einige Klassen, die der <xref:System.Collections.Concurrent>Namespace sind <xref:System.Collections.Concurrent.BlockingCollection%601>, <xref:System.Collections.Concurrent.ConcurrentDictionary%602>, <xref:System.Collections.Concurrent.ConcurrentQueue%601>, und <xref:System.Collections.Concurrent.ConcurrentStack%601>.</xref:System.Collections.Concurrent.ConcurrentStack%601> </xref:System.Collections.Concurrent.ConcurrentQueue%601> </xref:System.Collections.Concurrent.ConcurrentDictionary%602> </xref:System.Collections.Concurrent.BlockingCollection%601> </xref:System.Collections.Concurrent>  
  
<a name="BKMK_Collections"></a>
### <a name="systemcollections-classes"></a>System.Collections-Klassen    
 Die Klassen in der <xref:System.Collections?displayProperty=fullName>Namespace nicht speichern Elemente als speziell typisierte Objekte, sondern als Objekte vom Typ `Object`.</xref:System.Collections?displayProperty=fullName>  
  
 Wann immer möglich, sollten Sie die generischen Auflistungen im Verwenden der <xref:System.Collections.Generic?displayProperty=fullName>Namespace oder die <xref:System.Collections.Concurrent>anstelle der älteren Typen im Namespace der `System.Collections` Namespace.</xref:System.Collections.Concurrent> </xref:System.Collections.Generic?displayProperty=fullName>  
  
 In der folgenden Tabelle werden einige der häufig verwendeten Klassen im `System.Collections`-Namespace aufgelistet:  
  
|Klasse|Beschreibung|  
|---|---|  
|<xref:System.Collections.ArrayList></xref:System.Collections.ArrayList>|Stellt ein Array von Objekten dar, das je nach Bedarf dynamisch vergrößert wird.|  
|<xref:System.Collections.Hashtable></xref:System.Collections.Hashtable>|Stellt eine Auflistung von Schlüssel-Wert-Paaren dar, die auf Grundlage des Hashcodes des Schlüssels geordnet sind.|  
|<xref:System.Collections.Queue></xref:System.Collections.Queue>|Stellt eine FIFO-Auflistung (First In, First Out) von Objekten dar.|  
|<xref:System.Collections.Stack></xref:System.Collections.Stack>|Stellt eine LIFO-Auflistung (Last In, First Out) von Objekten dar.|  
  
 Die <xref:System.Collections.Specialized>Namespace bietet spezialisierte und stark typisierte Auflistungsklassen, z. B. zeichenfolgenauflistungen und verknüpfte Listen und Wörterbücher.</xref:System.Collections.Specialized>  

<a name="BKMK_VisualBasic"></a> 
###  <a name="visual-basic-collection-class"></a>Visual Basic-Auflistungsklasse  
 Sie können die Visual Basic <xref:Microsoft.VisualBasic.Collection>für den Zugriff auf eine Auflistung, indem Sie entweder einen numerischen Index oder eine Klasse `String` Schlüssel.</xref:Microsoft.VisualBasic.Collection> Sie können einem Auflistungsobjekt Elemente entweder mit oder ohne Angabe eines Schlüssels hinzufügen. Wenn Sie ein Element ohne einen Schlüssel hinzufügen, müssen Sie seinen numerischen Index verwenden, um darauf zuzugreifen.  
  
 Die Visual Basic-Klasse `Collection` speichert alle Elemente als `Object`-Typ, damit Elemente eines beliebigen Datentyps hinzugefügt werden können. Es gibt keine Vorkehrung, die das Hinzufügen ungeeigneter Datentypen verhindert.  
  
 Wenn Sie die Visual Basic-Klasse `Collection` verwenden, hat das erste Element in einer Auflistung einen Index von 1. Dies unterscheidet sich von den .NET Framework-Auflistungsklassen, deren Startindex 0 ist.  
  
 Wann immer möglich, sollten Sie die generischen Auflistungen im Verwenden der <xref:System.Collections.Generic?displayProperty=fullName>Namespace oder die <xref:System.Collections.Concurrent>Namespace anstelle der Visual Basic `Collection` Klasse</xref:System.Collections.Concurrent> </xref:System.Collections.Generic?displayProperty=fullName>  
  
 Weitere Informationen finden Sie unter <xref:Microsoft.VisualBasic.Collection>.</xref:Microsoft.VisualBasic.Collection>  
  
<a name="BKMK_KeyValuePairs"></a>
## <a name="implementing-a-collection-of-keyvalue-pairs"></a>Implementieren einer Auflistung von Schlüssel/Wert-Paaren   
 Die <xref:System.Collections.Generic.Dictionary%602>generische Auflistung können Sie den Zugriff auf Elemente in einer Auflistung mithilfe des Schlüssels der einzelnen Elemente.</xref:System.Collections.Generic.Dictionary%602> Jede Hinzufügung zum Wörterbuch besteht aus einem Wert und dem zugeordneten Schlüssel. Ein Wert kann anhand des zugehörigen Schlüssels schnell abgerufen werden, da die `Dictionary`-Klasse in Form einer Hashtabelle implementiert ist.  
  
 Das folgende Beispiel erstellt eine `Dictionary`-Auflistung und durchläuft das Wörterbuch unter Verwendung einer `For Each`-Anweisung.  
  
```vb  
Private Sub IterateThroughDictionary()  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    For Each kvp As KeyValuePair(Of String, Element) In elements  
        Dim theElement As Element = kvp.Value  
  
        Console.WriteLine("key: " & kvp.Key)  
        With theElement  
            Console.WriteLine("values: " & .Symbol & " " &  
                .Name & " " & .AtomicNumber)  
        End With  
    Next  
End Sub  
  
Private Function BuildDictionary() As Dictionary(Of String, Element)  
    Dim elements As New Dictionary(Of String, Element)  
  
    AddToDictionary(elements, "K", "Potassium", 19)  
    AddToDictionary(elements, "Ca", "Calcium", 20)  
    AddToDictionary(elements, "Sc", "Scandium", 21)  
    AddToDictionary(elements, "Ti", "Titanium", 22)  
  
    Return elements  
End Function  
  
Private Sub AddToDictionary(ByVal elements As Dictionary(Of String, Element),  
ByVal symbol As String, ByVal name As String, ByVal atomicNumber As Integer)  
    Dim theElement As New Element  
  
    theElement.Symbol = symbol  
    theElement.Name = name  
    theElement.AtomicNumber = atomicNumber  
  
    elements.Add(Key:=theElement.Symbol, value:=theElement)  
End Sub  
  
Public Class Element  
    Public Property Symbol As String  
    Public Property Name As String  
    Public Property AtomicNumber As Integer  
End Class  
```  
  
 Wenn stattdessen ein Auflistungsinitialisierer zum Erstellen der `Dictionary`-Auflistung verwendet werden soll, können Sie die `BuildDictionary`- und `AddToDictionary`-Methoden durch die folgende Methode ersetzen.  
  
```vb  
Private Function BuildDictionary2() As Dictionary(Of String, Element)  
    Return New Dictionary(Of String, Element) From  
        {  
            {"K", New Element With  
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},  
            {"Ca", New Element With  
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},  
            {"Sc", New Element With  
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},  
            {"Ti", New Element With  
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}  
        }  
End Function  
```  
  
 Im folgenden Beispiel wird die <xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A>-Methode und der <xref:System.Collections.Generic.Dictionary%602.Item%2A>-Eigenschaft des `Dictionary` zum Auffinden ein Element mit Schlüssel.</xref:System.Collections.Generic.Dictionary%602.Item%2A> </xref:System.Collections.Generic.Dictionary%602.ContainsKey%2A> Die `Item` Eigenschaft ermöglicht den Zugriff auf ein Element in der `elements` -Auflistung mithilfe der `elements(symbol)` Code in Visual Basic.  
  
```vb  
Private Sub FindInDictionary(ByVal symbol As String)  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    If elements.ContainsKey(symbol) = False Then  
        Console.WriteLine(symbol & " not found")  
    Else  
        Dim theElement = elements(symbol)  
        Console.WriteLine("found: " & theElement.Name)  
    End If  
End Sub  
```  
  
 Das folgende Beispiel verwendet die <xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>Methode Auffinden ein Element mit Schlüssel.</xref:System.Collections.Generic.Dictionary%602.TryGetValue%2A>  
  
```vb  
Private Sub FindInDictionary2(ByVal symbol As String)  
    Dim elements As Dictionary(Of String, Element) = BuildDictionary()  
  
    Dim theElement As Element = Nothing  
    If elements.TryGetValue(symbol, theElement) = False Then  
        Console.WriteLine(symbol & " not found")  
    Else  
        Console.WriteLine("found: " & theElement.Name)  
    End If  
End Sub  
```  
  
<a name="BKMK_LINQ"></a> 
##  <a name="using-linq-to-access-a-collection"></a>Verwenden von LINQ zum Zugriff auf eine Auflistung  
 LINQ (Language-Integrated Query) kann verwendet werden, um auf Auflistungen zuzugreifen. LINQ-Abfragen stellen Filter-, Sortier- und Gruppierungsfunktionen bereit. Weitere Informationen finden Sie unter [erste Schritte mit LINQ in Visual Basic](../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md).  
  
 Im folgenden Beispiel wird eine LINQ-Abfrage für eine generische `List` ausgeführt. Die LINQ-Abfrage gibt eine andere Auflistung zurück, die die Ergebnisse enthält.  
  
```vb  
Private Sub ShowLINQ()  
    Dim elements As List(Of Element) = BuildList()  
  
    ' LINQ Query.  
    Dim subset = From theElement In elements  
                  Where theElement.AtomicNumber < 22  
                  Order By theElement.Name  
  
    For Each theElement In subset  
        Console.WriteLine(theElement.Name & " " & theElement.AtomicNumber)  
    Next  
  
    ' Output:  
    '  Calcium 20  
    '  Potassium 19  
    '  Scandium 21  
End Sub  
  
Private Function BuildList() As List(Of Element)  
    Return New List(Of Element) From  
        {  
            {New Element With  
                {.Symbol = "K", .Name = "Potassium", .AtomicNumber = 19}},  
            {New Element With  
                {.Symbol = "Ca", .Name = "Calcium", .AtomicNumber = 20}},  
            {New Element With  
                {.Symbol = "Sc", .Name = "Scandium", .AtomicNumber = 21}},  
            {New Element With  
                {.Symbol = "Ti", .Name = "Titanium", .AtomicNumber = 22}}  
        }  
End Function  
  
Public Class Element  
    Public Property Symbol As String  
    Public Property Name As String  
    Public Property AtomicNumber As Integer  
End Class  
```  
  
 <a name="BKMK_Sorting"></a> 
## <a name="sorting-a-collection"></a>Sortieren einer Auflistung  
 Das folgende Beispiel zeigt ein Verfahren zum Sortieren einer Auflistung. Im Beispiel werden Instanzen von sortiert die `Car` -Klasse, die in eine <xref:System.Collections.Generic.List%601>.</xref:System.Collections.Generic.List%601> gespeichert sind Die `Car` -Klasse implementiert die <xref:System.IComparable%601>-Schnittstelle, die erfordert, dass die <xref:System.IComparable%601.CompareTo%2A>-Methode implementiert werden.</xref:System.IComparable%601.CompareTo%2A> </xref:System.IComparable%601>  
  
 Jeder Aufruf von der <xref:System.IComparable%601.CompareTo%2A>-Methode führt einen einzelnen Vergleich, der für die Sortierung verwendet wird.</xref:System.IComparable%601.CompareTo%2A> Vom Benutzer erstellter Code in der `CompareTo`-Methode gibt einen Wert für jeden Vergleich des aktuellen Objekts mit einem anderen Objekt zurück. Der zurückgegebene Wert ist kleiner als Null, wenn das aktuelle Objekt kleiner ist als das andere Objekt, größer als Null, wenn das aktuelle Objekt größer als das andere Objekt ist und Null, wenn beide Objekt gleich groß sind. Dies ermöglicht es Ihnen, in dem Code die Kriterien für größer als, kleiner als und gleich zu definieren.  
  
 In der `ListCars`-Methode sortiert die `cars.Sort()`-Anweisung die Liste. Dieser Aufruf der <xref:System.Collections.Generic.List%601.Sort%2A>Methode der <xref:System.Collections.Generic.List%601>bewirkt, dass die `CompareTo` automatisch für die aufzurufende Methode der `Car` Objekte in der `List`.</xref:System.Collections.Generic.List%601> </xref:System.Collections.Generic.List%601.Sort%2A>  
  
```vb  
Public Sub ListCars()  
  
    ' Create some new cars.  
    Dim cars As New List(Of Car) From  
    {  
        New Car With {.Name = "car1", .Color = "blue", .Speed = 20},  
        New Car With {.Name = "car2", .Color = "red", .Speed = 50},  
        New Car With {.Name = "car3", .Color = "green", .Speed = 10},  
        New Car With {.Name = "car4", .Color = "blue", .Speed = 50},  
        New Car With {.Name = "car5", .Color = "blue", .Speed = 30},  
        New Car With {.Name = "car6", .Color = "red", .Speed = 60},  
        New Car With {.Name = "car7", .Color = "green", .Speed = 50}  
    }  
  
    ' Sort the cars by color alphabetically, and then by speed  
    ' in descending order.  
    cars.Sort()  
  
    ' View all of the cars.  
    For Each thisCar As Car In cars  
        Console.Write(thisCar.Color.PadRight(5) & " ")  
        Console.Write(thisCar.Speed.ToString & " ")  
        Console.Write(thisCar.Name)  
        Console.WriteLine()  
    Next  
  
    ' Output:  
    '  blue  50 car4  
    '  blue  30 car5  
    '  blue  20 car1  
    '  green 50 car7  
    '  green 10 car3  
    '  red   60 car6  
    '  red   50 car2  
End Sub  
  
Public Class Car  
    Implements IComparable(Of Car)  
  
    Public Property Name As String  
    Public Property Speed As Integer  
    Public Property Color As String  
  
    Public Function CompareTo(ByVal other As Car) As Integer _  
        Implements System.IComparable(Of Car).CompareTo  
        ' A call to this method makes a single comparison that is  
        ' used for sorting.  
  
        ' Determine the relative order of the objects being compared.  
        ' Sort by color alphabetically, and then by speed in  
        ' descending order.  
  
        ' Compare the colors.  
        Dim compare As Integer  
        compare = String.Compare(Me.Color, other.Color, True)  
  
        ' If the colors are the same, compare the speeds.  
        If compare = 0 Then  
            compare = Me.Speed.CompareTo(other.Speed)  
  
            ' Use descending order for speed.  
            compare = -compare  
        End If  
  
        Return compare  
    End Function  
End Class  
```  
  
<a name="BKMK_CustomCollection"></a> 
## <a name="defining-a-custom-collection"></a>Definieren einer benutzerdefinierten Auflistung  
 Sie können eine Auflistung definieren, durch die Implementierung der <xref:System.Collections.Generic.IEnumerable%601>oder <xref:System.Collections.IEnumerable>Schnittstelle.</xref:System.Collections.IEnumerable> </xref:System.Collections.Generic.IEnumerable%601> Weitere Informationen finden Sie unter [enumerieren einer Auflistung](http://msdn.microsoft.com/en-us/71807ea7-9180-48a6-916f-35a5251d477f).  
  
 Obwohl Sie eine benutzerdefinierte Auflistung definieren können, ist es besser, um Auflistungen zu verwenden, die in .NET Framework, die in beschriebenen enthalten sind [Arten von Auflistungen](http://msdn.microsoft.com/library/e76533a9-5033-4a0b-b003-9c2be60d185b) weiter oben in diesem Thema.  
  
 Im folgenden Beispiel wird die benutzerdefinierte Auflistungsklasse `AllColors` definiert. Diese Klasse implementiert die <xref:System.Collections.IEnumerable>-Schnittstelle, die erfordert, dass die <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode implementiert werden.</xref:System.Collections.IEnumerable.GetEnumerator%2A> </xref:System.Collections.IEnumerable>  
  
 Die `GetEnumerator`-Methode gibt eine Instanz der `ColorEnumerator`-Klasse zurück. `ColorEnumerator`implementiert die <xref:System.Collections.IEnumerator>-Schnittstelle, die erfordert, dass die <xref:System.Collections.IEnumerator.Current%2A>Eigenschaft <xref:System.Collections.IEnumerator.MoveNext%2A>-Methode und <xref:System.Collections.IEnumerator.Reset%2A>-Methode implementiert werden.</xref:System.Collections.IEnumerator.Reset%2A> </xref:System.Collections.IEnumerator.MoveNext%2A> </xref:System.Collections.IEnumerator.Current%2A> </xref:System.Collections.IEnumerator>  
  
```vb  
Public Sub ListColors()  
    Dim colors As New AllColors()  
  
    For Each theColor As Color In colors  
        Console.Write(theColor.Name & " ")  
    Next  
    Console.WriteLine()  
    ' Output: red blue green  
End Sub  
  
' Collection class.  
Public Class AllColors  
    Implements System.Collections.IEnumerable  
  
    Private _colors() As Color =  
    {  
        New Color With {.Name = "red"},  
        New Color With {.Name = "blue"},  
        New Color With {.Name = "green"}  
    }  
  
    Public Function GetEnumerator() As System.Collections.IEnumerator _  
        Implements System.Collections.IEnumerable.GetEnumerator  
  
        Return New ColorEnumerator(_colors)  
  
        ' Instead of creating a custom enumerator, you could  
        ' use the GetEnumerator of the array.  
        'Return _colors.GetEnumerator  
    End Function  
  
    ' Custom enumerator.  
    Private Class ColorEnumerator  
        Implements System.Collections.IEnumerator  
  
        Private _colors() As Color  
        Private _position As Integer = -1  
  
        Public Sub New(ByVal colors() As Color)  
            _colors = colors  
        End Sub  
  
        Public ReadOnly Property Current() As Object _  
            Implements System.Collections.IEnumerator.Current  
            Get  
                Return _colors(_position)  
            End Get  
        End Property  
  
        Public Function MoveNext() As Boolean _  
            Implements System.Collections.IEnumerator.MoveNext  
            _position += 1  
            Return (_position < _colors.Length)  
        End Function  
  
        Public Sub Reset() Implements System.Collections.IEnumerator.Reset  
            _position = -1  
        End Sub  
    End Class  
End Class  
  
' Element class.  
Public Class Color  
    Public Property Name As String  
End Class  
```  
  
<a name="BKMK_Iterators"></a>
##  <a name="iterators"></a>Iteratoren  
 Ein *Iterator* wird verwendet, um eine benutzerdefinierte Iteration durch eine Auflistung auszuführen. Ein Iterator kann eine Methode oder ein `get`-Accessor sein. Ein Iterator verwendet eine [ergeben](../../../visual-basic/language-reference/statements/yield-statement.md) -Anweisung jedes Element der Auflistung zu einem Zeitpunkt zurückgegeben.  
  
 Sie rufen den Iterator mithilfe einer [für jede... Nächste](../../../visual-basic/language-reference/statements/for-each-next-statement.md) Anweisung. Jede Iteration der `For Each`-Schleife ruft den Iterator auf. Wenn eine `Yield` -Anweisung im Iterator erreicht ist, ein Ausdruck zurückgegeben wird und die aktuelle Position im Code beibehalten wird. Wenn der Iterator das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 Weitere Informationen finden Sie unter [Iteratoren (Visual Basic)](../../../visual-basic/programming-guide/concepts/iterators.md).  
  
 Im folgenden Beispiel wird eine Iteratormethode verwendet. Die Iteratormethode verfügt über eine `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife. In der `ListEvenNumbers` -Methode, jede Iteration der der `For Each` Text-Anweisung erzeugt einen Aufruf der Iteratormethode, der auf die nächste übergeht `Yield` Anweisung.  
  
```vb  
Public Sub ListEvenNumbers()  
    For Each number As Integer In EvenSequence(5, 18)  
        Console.Write(number & " ")  
    Next  
    Console.WriteLine()  
    ' Output: 6 8 10 12 14 16 18  
End Sub  
  
Private Iterator Function EvenSequence(  
ByVal firstNumber As Integer, ByVal lastNumber As Integer) _  
As IEnumerable(Of Integer)  
  
' Yield even numbers in the range.  
    For number = firstNumber To lastNumber  
        If number Mod 2 = 0 Then  
            Yield number  
        End If  
    Next  
End Function  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)   
 [Programmierkonzepte (Visual Basic)](../../../visual-basic/programming-guide/concepts/index.md)   
 [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [LINQ to Objects (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)   
 [Paralleles LINQ (PLINQ)](http://msdn.microsoft.com/library/3d4d0cd3-bde4-490b-99e7-f4e41be96455)   
 [Auflistungen und Datenstrukturen](../../../standard/collections/index.md)   
 [Erstellen und Bearbeiten von Sammlungen](http://msdn.microsoft.com/en-us/2065398e-eb1a-4821-9188-75f16e42e069)   
 [Auswählen einer Auflistungsklasse](../../../standard/collections/selecting-a-collection-class.md)   
 [Vergleiche und Sortiervorgänge in Sammlungen](../../../standard/collections/comparisons-and-sorts-within-collections.md)   
 [Verwenden von generischen Auflistungen](../../../standard/collections/when-to-use-generic-collections.md)
