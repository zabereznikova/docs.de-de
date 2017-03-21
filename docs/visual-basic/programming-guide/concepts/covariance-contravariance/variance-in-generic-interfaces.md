---
title: Varianz in generischen Schnittstellen (Visual Basic) | Microsoft-Dokumentation
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
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
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
ms.openlocfilehash: c53c27bdb085213046553fc4b08f11336880a7c2
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-generic-interfaces-visual-basic"></a>Varianz in generischen Schnittstellen (Visual Basic)
Varianz-Unterstützung für mehrere vorhandene generische Schnittstellen wurde in .NET Framework 4 eingeführt. Varianz-Unterstützung ermöglicht die implizite Konvertierung von Klassen, die diese Schnittstellen implementieren. Die folgenden Schnittstellen sind jetzt Variant:  
  
-   <xref:System.Collections.Generic.IEnumerable%601>(T ist kovariant)</xref:System.Collections.Generic.IEnumerable%601>  
  
-   <xref:System.Collections.Generic.IEnumerator%601>(T ist kovariant)</xref:System.Collections.Generic.IEnumerator%601>  
  
-   <xref:System.Linq.IQueryable%601>(T ist kovariant)</xref:System.Linq.IQueryable%601>  
  
-   <xref:System.Linq.IGrouping%602>(`TKey` und `TElement` sind kovariant)</xref:System.Linq.IGrouping%602>  
  
-   <xref:System.Collections.Generic.IComparer%601>(T ist kontravariant)</xref:System.Collections.Generic.IComparer%601>  
  
-   <xref:System.Collections.Generic.IEqualityComparer%601>(T ist kontravariant)</xref:System.Collections.Generic.IEqualityComparer%601>  
  
-   <xref:System.IComparable%601>(T ist kontravariant)</xref:System.IComparable%601>  
  
 Kovarianz unterstützt eine Methode mit einem stärker abgeleiteten Rückgabetyp, als durch den generischen Typparameter der Schnittstelle definiert. Die Kovarianzfunktion betrachten Sie zur Veranschaulichung folgenden generischen Schnittstellen: `IEnumerable(Of Object)` und `IEnumerable(Of String)`. Die `IEnumerable(Of String)` Schnittstelle erbt nicht die `IEnumerable(Of Object)` Schnittstelle. Allerdings die `String` Typ erbt die `Object` Typ, und in einigen Fällen Sie möglicherweise Objekte dieser Schnittstellen einander zuweisen möchten. Dies wird im folgenden Codebeispiel gezeigt.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 In früheren Versionen von .NET Framework, dieser Code verursacht einen Kompilierungsfehler in Visual Basic mit `Option Strict On`. Aber jetzt können Sie `strings` anstelle von `objects`, wie im vorherigen Beispiel dargestellt, da die <xref:System.Collections.Generic.IEnumerable%601>Schnittstelle ist kovariant.</xref:System.Collections.Generic.IEnumerable%601>  
  
 Kontravarianz unterstützt eine Methode von Argumenttypen, die weniger stark abgeleitet sind, als durch den generischen Parameter der Schnittstelle angegeben. Zur Veranschaulichung der Kontravarianz wird angenommen, Sie erstellt haben eine `BaseComparer` zum Vergleichen von Instanzen der Klasse die `BaseClass` Klasse. Die `BaseComparer`-Klasse implementiert die `IEqualityComparer(Of BaseClass)`-Schnittstelle. Da die <xref:System.Collections.Generic.IEqualityComparer%601>-Schnittstelle kontravariant ist, können Sie `BaseComparer` Instanzen von Klassen vergleichen, die erben die `BaseClass` Klasse</xref:System.Collections.Generic.IEqualityComparer%601> Dies wird im folgenden Codebeispiel gezeigt.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Weitere Beispiele finden Sie unter [Verwenden von Varianz in Schnittstellen für generische Auflistungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).  
  
 Varianz in generischen Schnittstellen ist nur für Verweistypen unterstützt. Werttypen unterstützen keine Varianz. Beispielsweise `IEnumerable(Of Integer)` kann implizit in konvertiert `IEnumerable(Of Object)`, da ganze Zahlen durch einen Werttyp dargestellt werden.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 Es ist auch wichtig zu beachten, dass Klassen, die Variante Schnittstellen implementieren, immer noch invariant sind. Z. B. zwar <xref:System.Collections.Generic.List%601>implementiert die Schnittstelle kovariante <xref:System.Collections.Generic.IEnumerable%601>, können nicht implizit konvertiert `List(Of Object)` , `List(Of String)`.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.Generic.List%601> Dies wird im folgenden Codebeispiel veranschaulicht.  
  
```vb  
' The following statement generates a compiler error  
' because classes are invariant.  
' Dim list As List(Of Object) = New List(Of String)  
  
' You can use the interface object instead.  
Dim listObjects As IEnumerable(Of Object) = New List(Of String)  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Varianz in Schnittstellen für generische Auflistungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)   
 [Erstellen von Varianten generischen Schnittstellen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)   
 [Generische Schnittstellen](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf)   
 [Varianz in Delegaten (Visual Basic)](../../../../visual-basic/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
