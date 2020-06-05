---
title: Abweichungen bei generischen Schnittstellen
ms.date: 07/20/2015
ms.assetid: cf4096d0-4bb3-45a9-9a6b-f01e29a60333
ms.openlocfilehash: df28a9f24518f24d1be89acba726da7dfbbf9570
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84375589"
---
# <a name="variance-in-generic-interfaces-visual-basic"></a>Variance in Generic Interfaces (Visual Basic) (Varianz in generischen Schnittstellen (Visual Basic))

In .NET Framework 4 wurde die Varianzunterstützung für mehrere vorhandene generische Schnittstellen eingeführt. Die Varianzunterstützung lässt eine implizite Konvertierung von Klassen zu, die diese Schnittstellen implementieren. Die folgenden Schnittstellen sind jetzt variant:

- <xref:System.Collections.Generic.IEnumerable%601> (T ist kovariant)

- <xref:System.Collections.Generic.IEnumerator%601> (T ist kovariant)

- <xref:System.Linq.IQueryable%601> (T ist kovariant)

- <xref:System.Linq.IGrouping%602> (`TKey` und `TElement` sind kovariant)

- <xref:System.Collections.Generic.IComparer%601> (T ist kontravariant)

- <xref:System.Collections.Generic.IEqualityComparer%601> (T ist kontravariant)

- <xref:System.IComparable%601> (T ist kontravariant)

Kovarianz ermöglicht einer Methode, stärker abgeleitete Rückgabetypen zu verwenden, als durch die generischen Typparameter der Schnittstelle definiert sind. Betrachten Sie diese generischen Schnittstellen zur Veranschaulichung der Kovarianzfunktionen: `IEnumerable(Of Object)` und `IEnumerable(Of String)`. Die Schnittstelle `IEnumerable(Of Object)` wird nicht von der Schnittstelle `IEnumerable(Of String)` geerbt. Allerdings erbt der Typ `String` den Typ `Object`. In einigen Fällen können Sie vielleicht auch die Objekte dieser Schnittstellen einander zuweisen. Dies wird im folgenden Codebeispiel gezeigt.

```vb
Dim strings As IEnumerable(Of String) = New List(Of String)
Dim objects As IEnumerable(Of Object) = strings
```

In früheren Versionen der .NET Framework verursacht dieser Code einen Kompilierungsfehler in Visual Basic mit `Option Strict On` . Jetzt können Sie aber `strings` anstelle von `objects` verwenden, wie im vorherigen Beispiel gezeigt wurde, da die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle kovariant ist.

Kontravarianz ermöglicht einer Methode, Argumenttypen zu verwenden, die weniger stark abgeleitet sind als durch die generischen Parameter der Schnittstelle angegeben. Nehmen Sie zur Veranschaulichung der Kontravarianz an, dass Sie eine `BaseComparer`-Klasse zum Vergleich von Instanzen der `BaseClass`-Klasse erstellt haben. Die `BaseComparer`-Klasse implementiert die `IEqualityComparer(Of BaseClass)`-Schnittstelle. Da die Schnittstelle <xref:System.Collections.Generic.IEqualityComparer%601> jetzt kontravariant ist, können Sie `BaseComparer` verwenden, um Instanzen von Klassen zu vergleichen, die die Klasse `BaseClass` erben. Dies wird im folgenden Codebeispiel gezeigt.

```vb
' Simple hierarchy of classes.
Class BaseClass
End Class

Class DerivedClass
    Inherits BaseClass
End Class

' Comparer class.
Class BaseComparer
    Implements IEqualityComparer(Of BaseClass)

    Public Function Equals1(ByVal x As BaseClass,
                            ByVal y As BaseClass) As Boolean _
                            Implements IEqualityComparer(Of BaseClass).Equals
        Return (x.Equals(y))
    End Function

    Public Function GetHashCode1(ByVal obj As BaseClass) As Integer _
        Implements IEqualityComparer(Of BaseClass).GetHashCode
        Return obj.GetHashCode
    End Function
End Class
Sub Test()
    Dim baseComparer As IEqualityComparer(Of BaseClass) = New BaseComparer
    ' Implicit conversion of IEqualityComparer(Of BaseClass) to
    ' IEqualityComparer(Of DerivedClass).
    Dim childComparer As IEqualityComparer(Of DerivedClass) = baseComparer
End Sub
```

Weitere Beispiele finden Sie unter [Verwenden von Varianz in Schnittstellen für generische Auflistungen (Visual Basic)](using-variance-in-interfaces-for-generic-collections.md).

Varianz in generischen Typparametern wird nur für Referenztypen unterstützt. Werttypen unterstützen keine Varianz. Beispielweise kann `IEnumerable(Of Integer)` nicht implizit in `IEnumerable(Of Object)` konvertiert werden, da Ganzzahlen durch Werttypen dargestellt werden.

```vb
Dim integers As IEnumerable(Of Integer) = New List(Of Integer)
' The following statement generates a compiler error
' with Option Strict On, because Integer is a value type.
' Dim objects As IEnumerable(Of Object) = integers
```

Es ist auch wichtig zu beachten, dass Klassen, die variante Schnittstellen implementieren, trotzdem noch invariant sind. Obwohl <xref:System.Collections.Generic.List%601> beispielsweise die kovariante Schnittstelle <xref:System.Collections.Generic.IEnumerable%601> implementiert, können Sie `List(Of Object)` implizit in `List(Of String)` konvertieren. Dies wird im folgenden Codebeispiel veranschaulicht.

```vb
' The following statement generates a compiler error
' because classes are invariant.
' Dim list As List(Of Object) = New List(Of String)

' You can use the interface object instead.
Dim listObjects As IEnumerable(Of Object) = New List(Of String)
```

## <a name="see-also"></a>Weitere Informationen

- [Using Variance in Interfaces for Generic Collections (Visual Basic) (Verwenden von Varianz in Schnittstellen für generische Auflistungen (Visual Basic))](using-variance-in-interfaces-for-generic-collections.md)
- [Creating Variant Generic Interfaces (Visual Basic) (Erstellen varianter generischer Schnittstellen (Visual Basic))](creating-variant-generic-interfaces.md)
- [Generische Schnittstellen](../../../../standard/generics/interfaces.md)
- [Variance in Delegates (Visual Basic) (Varianz in Delegaten (Visual Basic))](variance-in-delegates.md)
