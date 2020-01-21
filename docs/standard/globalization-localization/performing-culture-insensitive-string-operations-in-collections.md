---
title: Durchführen kulturunabhängiger Zeichenfolgenoperationen in Sammlungen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CaseInsensitiveComparer class, using
- CollectionsUtil.CreateCaseInsensitiveHashtable method
- culture-insensitive string operations, collections
- collections [.NET Framework], culture-insensitive string operations
- CaseInsensitiveHashCodeProvider class, using
- ArrayList.Sort method
- SortedList class, culture-insensitive string operations
- culture parameter
ms.assetid: 5cdc9396-a64b-4615-a1cd-b605db4c5983
ms.openlocfilehash: 13a9f4896a37be4297f2a1a11435b85ade381c66
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74353674"
---
# <a name="performing-culture-insensitive-string-operations-in-collections"></a>Durchführen kulturunabhängiger Zeichenfolgenoperationen in Sammlungen

Der <xref:System.Collections>-Namespace enthält Klassen und Member, die standardmäßig kulturabhängiges Verhalten bereitstellen. Die parameterlosen Konstruktoren für die <xref:System.Collections.CaseInsensitiveComparer>- und <xref:System.Collections.CaseInsensitiveHashCodeProvider>-Klasse initialisieren eine neue Instanz mit der <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>-Eigenschaft. Alle Überladungen der <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType>-Methode erstellen eine neue Instanz der <xref:System.Collections.Hashtable>-Klasse standardmäßig mit der `Thread.CurrentCulture`-Eigenschaft. Überladungen der <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>-Methode führen kulturabhängige Sortierungen standardmäßig mit der `Thread.CurrentCulture`-Eigenschaft aus. Wenn Zeichenfolgen als Schlüssel verwendet werden, kann sich <xref:System.Collections.SortedList> auf das Sortieren und Nachschlagen in einer `Thread.CurrentCulture`-Instanz auswirken. Befolgen Sie die Verwendungsempfehlungen in diesem Abschnitt, um aus diesen Klassen und Methoden im `Collections`-Namespace kulturunabhängige Ergebnisse abzurufen.

> [!NOTE]
> Wenn Sie <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> einer Vergleichsmethode übergeben, wird ein kulturunabhängiger Vergleich ausgeführt. Dies bewirkt jedoch keinen nicht linguistischen Vergleich, z. B. auf Dateipfade, Registrierungsschlüssel und Umgebungsvariablen. Und dadurch werden auch keine Sicherheitsentscheidungen anhand des Vergleichsergebnisses unterstützt. Für einen nicht linguistischen Vergleich oder Unterstützung für ergebnisbasierte Sicherheitsentscheidungen sollte die Anwendung eine Vergleichsmethode verwenden, die einen <xref:System.StringComparison>-Wert akzeptiert. Die Anwendung sollte dann <xref:System.StringComparison> übergeben.

## <a name="using-the-caseinsensitivecomparer-and-caseinsensitivehashcodeprovider-classes"></a>Verwenden der CaseInsensitiveComparer- und der CaseInsensitiveHashCodeProvider-Klasse

Die parameterlosen Konstruktoren für `CaseInsensitiveHashCodeProvider` und `CaseInsensitiveComparer` initialisieren eine neue Instanz der Klasse mit `Thread.CurrentCulture`, was zu kulturabhängigem Verhalten führt. Im folgenden Codebeispiel wird der Konstruktor für eine `Hashtable`-Instanz veranschaulicht, die kulturabhängig ist, weil für sie die parameterlosen Konstruktoren für `CaseInsensitiveHashCodeProvider` und `CaseInsensitiveComparer` verwendet werden.

```vb
internalHashtable = New Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default)
```

```csharp
internalHashtable = new Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default);
```

Wenn Sie eine kulturunabhängige `Hashtable`-Instanz über die Klassen `CaseInsensitiveComparer` und `CaseInsensitiveHashCodeProvider` erstellen möchten, initialisieren Sie neue Instanzen dieser Klassen mit den Konstruktoren, die einen `culture`-Parameter akzeptieren. Für den `culture`-Parameter geben Sie <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> an. Im folgenden Codebeispiel wird der Konstruktor für eine kulturunabhängige `Hashtable`-Instanz veranschaulicht.

```vb
internalHashtable = New Hashtable(New
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))
```

```csharp
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider
    (CultureInfo.InvariantCulture),
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));
```

## <a name="using-the-collectionsutilcreatecaseinsensitivehashtable-method"></a>Verwenden der CollectionsUtil.CreateCaseInsensitiveHashtable-Methode

Die `CollectionsUtil.CreateCaseInsensitiveHashTable`-Methode ist eine nützliche Abkürzung zum Erstellen einer neuen Instanz der `Hashtable`-Klasse, in der die Groß-/Kleinschreibung von Zeichenfolgen ignoriert wird. Alle Überladungen der `CollectionsUtil.CreateCaseInsensitiveHashTable`-Methode sind jedoch kulturabhängig, da in ihnen die `Thread.CurrentCulture`-Eigenschaft verwendet wird. Sie können mit dieser Methode keine kulturunabhängige `Hashtable`-Instanz erstellen. Um eine kulturunabhängige `Hashtable`-Instanz zu erstellen, verwenden Sie den `Hashtable`-Konstruktor, der einen `culture`-Parameter akzeptiert. Für den `culture`-Parameter geben Sie `CultureInfo.InvariantCulture` an. Im folgenden Codebeispiel wird der Konstruktor für eine kulturunabhängige `Hashtable`-Instanz veranschaulicht.

```vb
internalHashtable = New Hashtable(New
    CaseInsensitiveHashCodeProvider(CultureInfo.InvariantCulture),
    New CaseInsensitiveComparer(CultureInfo.InvariantCulture))
```

```csharp
internalHashtable = new Hashtable(new CaseInsensitiveHashCodeProvider
    (CultureInfo.InvariantCulture),
    new CaseInsensitiveComparer(CultureInfo.InvariantCulture));
```

<a name="cpconperformingculture-insensitivestringoperationsincollectionsanchor1"></a>

## <a name="using-the-sortedlist-class"></a>Verwenden der SortedList-Klasse

Eine `SortedList`-Instanz entspricht einer Auflistung von Schlüssel-Wert-Paaren, die nach Schlüsseln sortiert sind und auf die sowohl über Schlüssel als auch über Index zugegriffen werden kann. Wenn Sie eine `SortedList`-Instanz verwenden, in der Zeichenfolgen als Schlüssel verwendet werden, können Sortier- und Nachschlagevorgänge durch die `Thread.CurrentCulture`-Eigenschaft beeinflusst werden. Um für eine `SortedList`-Instanz kulturunabhängiges Verhalten zu erzielen, erstellen Sie die `SortedList`-Instanz mit einem Konstruktor, der einen `comparer`-Parameter akzeptiert. Der `comparer`-Parameter gibt die <xref:System.Collections.IComparer>-Implementierung an, die beim Vergleich von Schlüsseln zu verwenden ist. Geben Sie für den Parameter eine benutzerdefinierte Comparer-Klasse an, in der `CultureInfo.InvariantCulture` verwendet wird, um Schlüssel zu vergleichen. Das folgende Beispiel veranschaulicht eine benutzerdefinierte kulturunabhängige Comparer-Klasse, die Sie als `comparer`-Parameter für einen `SortedList`-Konstruktor angeben können.

```vb
Imports System.Collections
Imports System.Globalization

Friend Class InvariantComparer
    Implements IComparer
    Private m_compareInfo As CompareInfo
    Friend Shared [Default] As New InvariantComparer()

    Friend Sub New()
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo
    End Sub

    Public Function Compare(a As Object, b As Object) As Integer _
            Implements IComparer.Compare
        Dim sa As String = CType(a, String)
        Dim sb As String = CType(b, String)
        If Not (sa Is Nothing) And Not (sb Is Nothing) Then
            Return m_compareInfo.Compare(sa, sb)
        Else
            Return Comparer.Default.Compare(a, b)
        End If
    End Function
End Class
```

```csharp
using System;
using System.Collections;
using System.Globalization;

internal class InvariantComparer : IComparer
{
    private CompareInfo m_compareInfo;
    internal static readonly InvariantComparer Default = new
        InvariantComparer();

    internal InvariantComparer()
    {
        m_compareInfo = CultureInfo.InvariantCulture.CompareInfo;
    }

    public int Compare(Object a, Object b)
    {
        String sa = a as String;
        String sb = b as String;
        if (sa != null && sb != null)
            return m_compareInfo.Compare(sa, sb);
        else
            return Comparer.Default.Compare(a,b);
    }
}
```

Wenn Sie eine `SortedList`-Instanz für Zeichenfolgen verwenden, ohne eine benutzerdefinierte invariante Comparer-Klasse zu verwenden, gilt grundsätzlich, dass ein Ändern von `Thread.CurrentCulture`, nachdem die Liste aufgefüllt wurde, dazu führen kann, dass die Liste ungültig wird.

## <a name="using-the-arraylistsort-method"></a>Verwenden der ArrayList.Sort-Methode

Überladungen der `ArrayList.Sort`-Methode führen kulturabhängige Sortierungen standardmäßig mit der `Thread.CurrentCulture`-Eigenschaft aus. Die Ergebnisse können je nach Kultur aufgrund der unterschiedlichen Sortierreihenfolgen variieren. Um kulturabhängiges Verhalten zu vermeiden, verwenden Sie die Überladung dieser Methode, die eine `IComparer`-Implementierung akzeptieren. Geben Sie für den `comparer`-Parameter eine benutzerdefinierte invariante Comparer-Klasse an, in der `CultureInfo.InvariantCulture` verwendet wird. Ein Beispiel für eine benutzerdefinierte invariante Comparer-Klasse finden Sie im Thema [Verwenden der SortedList-Klasse](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1).

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.CaseInsensitiveComparer>
- <xref:System.Collections.CaseInsensitiveHashCodeProvider>
- <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>
- <xref:System.Collections.SortedList>
- <xref:System.Collections.Hashtable>
- <xref:System.Collections.IComparer>
- [Durchführen kulturunabhängiger Zeichenfolgenoperationen](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
- <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType>
