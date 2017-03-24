---
title: "Gewusst wie: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
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
ms.openlocfilehash: 166eb731d41e009c374ba55f929eed302793ecd0
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a>Gewusst wie: Hinzufügen von benutzerdefinierten Methoden zu LINQ-Abfragen (Visual Basic)
Sie können den Satz von Methoden, mit denen Sie für die LINQ-Abfragen durch Hinzufügen von Erweiterungsmethoden zum Erweitern der <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601> Zusätzlich zu den standardmäßigen Mittel- oder Höchstwerte, können Sie z. B. eine benutzerdefinierte aggregate-Methode, um einen einzelnen Wert aus einer Sequenz von Werten berechnen erstellen. Sie können auch eine Methode erstellen, die als benutzerdefinierter Filter oder spezifische Datentransformation für eine Sequenz von Werten und eine neue Sequenz zurückgibt. Beispiele für solche Methoden sind <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, und <xref:System.Linq.Enumerable.Reverse%2A>.</xref:System.Linq.Enumerable.Reverse%2A> </xref:System.Linq.Enumerable.Skip%2A> </xref:System.Linq.Enumerable.Distinct%2A>  
  
 Beim Erweitern der <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle können Sie die benutzerdefinierten Methoden auf jede aufzählbare Auflistung anwenden.</xref:System.Collections.Generic.IEnumerable%601> Weitere Informationen finden Sie unter [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
## <a name="adding-an-aggregate-method"></a>Hinzufügen einer Aggregate-Methode  
 Eine aggregierte Methode berechnet einen einzelnen Wert aus einer Gruppe von Werten. LINQ stellt mehrere Aggregatmethoden, einschließlich <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, und <xref:System.Linq.Enumerable.Max%2A>.</xref:System.Linq.Enumerable.Max%2A> </xref:System.Linq.Enumerable.Min%2A> </xref:System.Linq.Enumerable.Average%2A> Sie können eigene aggregate-Methode erstellen, indem Sie eine Erweiterungsmethode zum Hinzufügen der <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601>  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie eine Erweiterungsmethode namens erstellen `Median` berechnet ein Wendepunkt für eine Sequenz von Zahlen vom Typ `double`.  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module LINQExtension  
  
    ' Extension method for the IEnumerable(of T) interface.   
    ' The method accepts only values of the Double type.  
    <Extension()>   
    Function Median(ByVal source As IEnumerable(Of Double)) As Double  
        If source.Count = 0 Then  
            Throw New InvalidOperationException("Cannot compute median for an empty set.")  
        End If  
  
        Dim sortedSource = From number In source   
                           Order By number  
  
        Dim itemIndex = sortedSource.Count \ 2  
  
        If sortedSource.Count Mod 2 = 0 Then  
            ' Even number of items in list.  
            Return (sortedSource(itemIndex) + sortedSource(itemIndex - 1)) / 2  
        Else  
            ' Odd number of items in list.  
            Return sortedSource(itemIndex)  
        End If  
    End Function  
End Module  
```  
  
 Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung aufrufen, auf die gleiche Weise, die Sie andere aggregate Methoden aus Aufrufen der <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle.</xref:System.Collections.Generic.IEnumerable%601>  
  
> [!NOTE]
>  In Visual Basic können Sie entweder einen Methodenaufruf oder die Standardabfragesyntax für verwenden die `Aggregate` oder `Group By` Klausel. Weitere Informationen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md) und [Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md).  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie die `Median` Methode für ein Array vom Typ `double`.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
### <a name="overloading-an-aggregate-method-to-accept-various-types"></a>Überladen einer Aggregatmethode zum Akzeptieren verschiedener Typen  
 Aggregate-Methode können überladen werden, sodass diese Sequenzen verschiedener Typen akzeptiert. Die Standardmethode ist eine Überladung für jeden Typ erstellen. Ein anderer Ansatz ist das Erstellen eine Überladung, die einen generischen Typ annimmt und mit einem Delegaten in einen bestimmten Typ zu konvertieren. Sie können auch beide Methoden kombinieren.  
  
#### <a name="to-create-an-overload-for-each-type"></a>So erstellen Sie eine Überladung für jeden Typ  
 Sie können eine bestimmte Überladung für jeden Typ erstellen, die Sie unterstützen möchten. Das folgende Codebeispiel zeigt eine Überladung von der `Median` Methode für die `integer` Typ.  
  
<CodeContentPlaceHolder>3</CodeContentPlaceHolder>  
 Sie können nun Aufrufe der `Median` Überladungen für beide `integer` und `double` Typen, wie im folgenden Code gezeigt:  
  
<CodeContentPlaceHolder>4</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>5</CodeContentPlaceHolder>  
<CodeContentPlaceHolder>6</CodeContentPlaceHolder>  
#### <a name="to-create-a-generic-overload"></a>So erstellen Sie eine generische Überladung  
 Sie können auch eine Überladung erstellen, die eine Sequenz generischer Objekte akzeptiert. Diese Überladung nimmt einen Delegaten als Parameter und verwendet, um eine Sequenz von Objekten eines generischen Typs in einen bestimmten Typ zu konvertieren.  
  
 Der folgende Code zeigt eine Überladung von der `Median` Methode, die die <xref:System.Func%602>-Delegaten als Parameter.</xref:System.Func%602> Dieser Delegat nimmt ein Objekt des generischen Typs T und gibt ein Objekt vom Typ `double`.  
  
```vb  
' Generic overload.  
  
<Extension()>   
Function Median(Of T)(ByVal source As IEnumerable(Of T),   
                      ByVal selector As Func(Of T, Double)) As Double  
    Return Aggregate num In source Select selector(num) Into med = Median()  
End Function  
```  
  
 Sie können jetzt Aufrufen der `Median` -Methode für eine Sequenz von Objekten eines beliebigen Typs. Wenn der Typ keinen eigenen Überladung, müssen Sie einen Delegatparameter übergeben. In Visual Basic können Sie zu diesem Zweck einen Lambda-Ausdruck. Auch bei Verwendung der `Aggregate` oder `Group By` -Klausel anstelle der Methodenaufruf, können Sie jeder Wert oder Ausdruck, der im Gültigkeitsbereich dieser Klausel übergeben.  
  
 Im folgenden Beispielcode veranschaulicht das Aufrufen der `Median` -Methode für ein Array von ganzen Zahlen und ein Array von Zeichenfolgen. Für Zeichenfolgen wird der Median für die Längen der Zeichenfolgen im Array berechnet. Das Beispiel zeigt, wie übergeben der <xref:System.Func%602>Delegieren Parameter, um die `Median` Methode für jeden Fall.</xref:System.Func%602>  
  
<CodeContentPlaceHolder>8</CodeContentPlaceHolder>  
## <a name="adding-a-method-that-returns-a-collection"></a>Hinzufügen einer Methode, die eine Auflistung zurückgibt.  
 Sie können erweitern die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle mit einer benutzerdefinierten Abfrage-Methode, die eine Sequenz von Werten zurückgibt.</xref:System.Collections.Generic.IEnumerable%601> In diesem Fall muss die Methode eine Auflistung des Typs <xref:System.Collections.Generic.IEnumerable%601>.</xref:System.Collections.Generic.IEnumerable%601> zurückgeben Solche Methoden können verwendet werden, um Filter oder Datentransformationen auf eine Sequenz von Werten anzuwenden.  
  
 Das folgende Beispiel zeigt, wie eine Erweiterungsmethode mit dem Namen erstellt `AlternateElements` jedes andere Element in einer Auflistung, beginnend mit dem ersten Element zurückgibt.  
  
<CodeContentPlaceHolder>9</CodeContentPlaceHolder>  
 Sie können diese Erweiterungsmethode für jede aufzählbare Auflistung aufrufen, wie Sie auch andere Methoden Aufrufen der <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle, wie im folgenden Code gezeigt:</xref:System.Collections.Generic.IEnumerable%601>  
  
```vb  
Dim strings() As String = {"a", "b", "c", "d", "e"}  
  
Dim query = strings.AlternateElements()  
  
For Each element In query  
    Console.WriteLine(element)  
Next  
  
' This code produces the following output:  
'  
' a  
' c  
' e  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601>   
 [Erweiterungsmethoden](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
