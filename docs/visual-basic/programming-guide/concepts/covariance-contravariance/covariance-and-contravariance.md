---
title: Kovarianz und Kontravarianz (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: 59224c46-9931-466b-8c6e-3648c3e609c6
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
ms.openlocfilehash: b785e298c5ba38a8e3d8cc549b2dcf2df1ef6bd8
ms.lasthandoff: 03/13/2017

---
# <a name="covariance-and-contravariance-visual-basic"></a>Kovarianz und Kontravarianz (Visual Basic)
Aktivieren in Visual Basic Kovarianz und Kontravarianz implizite verweiskonvertierung für Arraytypen, Delegattypen und generische Typargumente. Kovarianz erhält die Zuweisungskompatibilität und Kontravarianz wird sie rückgängig gemacht.  
  
 Der folgende Code veranschaulicht den Unterschied zwischen Zuweisungskompatibilität, Kovarianz und Kontravarianz.  
  
```vb  
' Assignment compatibility.   
Dim str As String = "test"  
' An object of a more derived type is assigned to an object of a less derived type.   
Dim obj As Object = str  
  
' Covariance.   
Dim strings As IEnumerable(Of String) = New List(Of String)()  
' An object that is instantiated with a more derived type argument   
' is assigned to an object instantiated with a less derived type argument.   
' Assignment compatibility is preserved.   
Dim objects As IEnumerable(Of Object) = strings  
  
' Contravariance.             
' Assume that there is the following method in the class:   
' Shared Sub SetObject(ByVal o As Object)  
' End Sub  
Dim actObject As Action(Of Object) = AddressOf SetObject  
  
' An object that is instantiated with a less derived type argument   
' is assigned to an object instantiated with a more derived type argument.   
' Assignment compatibility is reversed.   
Dim actString As Action(Of String) = actObject  
```  
  
 Kovarianz für Arrays ermöglicht die implizite Konvertierung eines Arrays eines stärker abgeleiteten Typs in ein Array eines weniger stark abgeleiteten Typs. Dieser Vorgang ist jedoch nicht typsicher, wie im folgenden Codebeispiel gezeigt.  
  
```vb  
Dim array() As Object = New String(10) {}  
' The following statement produces a run-time exception.  
' array(0) = 10  
```  
  
 Unterstützung von Kovarianz und Kontravarianz für Methodengruppen ermöglicht Methodensignaturen und Delegattypen zu vergleichen. Auf diese Weise können Sie Delegaten nicht nur Methoden zuweisen, die übereinstimmende Signaturen, sondern auch Methoden, die zurückgeben, stärker Typen (Kovarianz) oder die abgeleiteten Parameter annehmen, die weniger stark abgeleiteten Typen (Kontravarianz sind) als vom Delegattyp angegeben wurde. Weitere Informationen finden Sie unter [Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md) und [Verwenden von Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md).  
  
 Das folgende Codebeispiel zeigt die Unterstützung von Kovarianz und Kontravarianz für Methodengruppen.  
  
```vb  
Shared Function GetObject() As Object  
    Return Nothing  
End Function  
  
Shared Sub SetObject(ByVal obj As Object)  
End Sub  
  
Shared Function GetString() As String  
    Return ""  
End Function  
  
Shared Sub SetString(ByVal str As String)  
  
End Sub  
  
Shared Sub Test()  
    ' Covariance. A delegate specifies a return type as object,  
    ' but you can assign a method that returns a string.  
    Dim del As Func(Of Object) = AddressOf GetString  
  
    ' Contravariance. A delegate specifies a parameter type as string,  
    ' but you can assign a method that takes an object.  
    Dim del2 As Action(Of String) = AddressOf SetObject  
End Sub  
```  
  
 Unterstützen Sie in .NET Framework 4 oder höher Visual Basic Kovarianz und Kontravarianz in generischen Schnittstellen und Delegaten und ermöglichen Sie die implizite Konvertierung generischer Typparameter. Weitere Informationen finden Sie unter [Varianz in generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md) und [Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).  
  
 Das folgende Codebeispiel zeigt die implizite verweiskonvertierung bei generischen Schnittstellen.  
  
```vb  
Dim strings As IEnumerable(Of String) = New List(Of String)  
Dim objects As IEnumerable(Of Object) = strings  
```  
  
 Eine generische Schnittstelle oder ein Delegat wird aufgerufen, *Variante* Wenn generischen Parameter kovariant deklariert werden oder kontravariant. Visual Basic können Sie eigene Variante Schnittstellen und Delegaten erstellen. Weitere Informationen finden Sie unter [Erstellen von Varianten generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md) und [Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md).  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|Beschreibung|  
|-----------|-----------------|  
|[Varianz in generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-generic-interfaces.md)|Erläutert Ko- und Kontravarianz in generischen Schnittstellen und enthält eine Liste der Varianten generischen Schnittstellen in .NET Framework.|  
|[Erstellen von Varianten generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)|Zeigt, wie benutzerdefinierte Variante Schnittstellen erstellt.|  
|[Verwenden von Varianz in Schnittstellen für generische Auflistungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)|Beschreibt, wie Kovarianz und Kontravarianz in unterstützen die <xref:System.Collections.Generic.IEnumerable%601>und <xref:System.IComparable%601>Schnittstellen können Sie Code wiederverwenden.</xref:System.IComparable%601> </xref:System.Collections.Generic.IEnumerable%601>|  
|[Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)|Beschreibt Kovarianz und Kontravarianz in generischen und nicht generischen Delegaten und enthält eine Liste der Varianten generischen Delegaten in .NET Framework.|  
|[Verwenden von Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-delegates.md)|Veranschaulicht die Unterstützung von Kovarianz und Kontravarianz in nicht generischen Delegaten zu verwenden, um Methodensignaturen und Delegattypen zu entsprechen.|  
|[Verwenden von Varianz für die Aktion generischen Delegaten Func und (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-for-func-and-action-generic-delegates.md)|Beschreibt, wie Kovarianz und Kontravarianz in unterstützen die `Func` und `Action` Delegaten können Sie die Wiederverwendung von Code dar.|
