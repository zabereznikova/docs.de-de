---
title: Varianz in generischen Schnittstellen (C#) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 4828a8f9-48c0-4128-9749-7fcd6bf19a06
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 4c4f3ab00b4de2a6f38858dd5f332db3d47eb85b
ms.lasthandoff: 03/13/2017

---
# <a name="variance-in-generic-interfaces-c"></a>Varianz in generischen Schnittstellen (C#)
In .NET Framework 4 wurde die Varianzunterstützung für mehrere vorhandene generische Schnittstellen eingeführt. Die Varianzunterstützung lässt eine implizite Konvertierung von Klassen zu, die diese Schnittstellen implementieren. Die folgenden Schnittstellen sind jetzt variant:  
  
-   <xref:System.Collections.Generic.IEnumerable%601> (T ist kovariant)  
  
-   <xref:System.Collections.Generic.IEnumerator%601> (T ist kovariant)  
  
-   <xref:System.Linq.IQueryable%601> (T ist kovariant)  
  
-   <xref:System.Linq.IGrouping%602> (`TKey` und `TElement` sind kovariant)  
  
-   <xref:System.Collections.Generic.IComparer%601> (T ist kontravariant)  
  
-   <xref:System.Collections.Generic.IEqualityComparer%601> (T ist kontravariant)  
  
-   <xref:System.IComparable%601> (T ist kontravariant)  
  
 Kovarianz ermöglicht einer Methode, stärker abgeleitete Rückgabetypen zu verwenden, als durch die generischen Typparameter der Schnittstelle definiert sind. Betrachten Sie diese generischen Schnittstellen zur Veranschaulichung der Kovarianzfunktionen: `IEnumerable<Object>` und `IEnumerable<String>`. Die Schnittstelle `IEnumerable<Object>` wird nicht von der Schnittstelle `IEnumerable<String>` geerbt. Allerdings erbt der Typ `String` den Typ `Object`. In einigen Fällen können Sie vielleicht auch die Objekte dieser Schnittstellen einander zuweisen. Dies wird im folgenden Codebeispiel gezeigt.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 In früheren Versionen des .NET Frameworks verursacht dieser Code einen Kompilierfehler mit `Option Strict On` in C#. Jetzt können Sie aber `strings` anstelle von `objects` verwenden, wie im vorherigen Beispiel gezeigt wurde, da die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle kovariant ist.  
  
 Kontravarianz ermöglicht einer Methode, Argumenttypen zu verwenden, die weniger stark abgeleitet sind als durch die generischen Parameter der Schnittstelle angegeben. Nehmen Sie zur Veranschaulichung der Kontravarianz an, dass Sie eine `BaseComparer`-Klasse zum Vergleich von Instanzen der `BaseClass`-Klasse erstellt haben. Die `BaseComparer`-Klasse implementiert die `IEqualityComparer<BaseClass>`-Schnittstelle. Da die Schnittstelle <xref:System.Collections.Generic.IEqualityComparer%601> jetzt kontravariant ist, können Sie `BaseComparer` verwenden, um Instanzen von Klassen zu vergleichen, die die Klasse `BaseClass` erben. Dies wird im folgenden Codebeispiel gezeigt.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
 Weitere Beispiele finden Sie unter [Using Variance in Interfaces for Generic Collections (C#) (Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md).  
  
 Varianz in generischen Typparametern wird nur für Referenztypen unterstützt. Werttypen unterstützen keine Varianz. Beispielweise kann `IEnumerable<int>` nicht implizit in `IEnumerable<object>` konvertiert werden, da Ganzzahlen durch Werttypen dargestellt werden.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 Es ist auch wichtig zu beachten, dass Klassen, die variante Schnittstellen implementieren, trotzdem noch invariant sind. Obwohl <xref:System.Collections.Generic.List%601> z.B. die kovariante Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie `List<Object>` nicht implizit in `List<String>` konvertieren. Dies wird im folgenden Codebeispiel veranschaulicht.  
  
```cs  
// The following line generates a compiler error  
// because classes are invariant.  
// List<Object> list = new List<String>();  
  
// You can use the interface object instead.  
IEnumerable<Object> listObjects = new List<String>();  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Using Variance in Interfaces for Generic Collections (C#) (Verwenden von Varianz in Schnittstellen für generische Auflistungen (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/using-variance-in-interfaces-for-generic-collections.md)   
 [Creating Variant Generic Interfaces (C#) (Erstellen von varianten generischen Schnittstellen (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/creating-variant-generic-interfaces.md)   
 [Generic Interfaces (Generische Schnittstellen)](http://msdn.microsoft.com/library/88bf5b04-d371-4edb-ba38-01ec7cabaacf)   
 [Variance in Delegates (C#) (Varianz bei Delegaten (C#))](../../../../csharp/programming-guide/concepts/covariance-contravariance/variance-in-delegates.md)
