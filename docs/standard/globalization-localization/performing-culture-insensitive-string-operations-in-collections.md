---
title: Durchführen kulturunabhängiger Zeichenfolgenoperationen in Auflistungen
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CaseInsensitiveComparer class, using
- CollectionsUtil.CreateCaseInsensitiveHashtable method
- culture-insensitive string operations, collections
- collections [.NET], culture-insensitive string operations
- CaseInsensitiveHashCodeProvider class, using
- ArrayList.Sort method
- SortedList class, culture-insensitive string operations
- culture parameter
ms.assetid: 5cdc9396-a64b-4615-a1cd-b605db4c5983
ms.openlocfilehash: 0a55a41b7cd2a2d245d0fb7722dddee794777422
ms.sourcegitcommit: b1442669f1982d3a1cb18ea35b5acfb0fc7d93e4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93063962"
---
# <a name="performing-culture-insensitive-string-operations-in-collections"></a><span data-ttu-id="79a71-102">Durchführen kulturunabhängiger Zeichenfolgenoperationen in Auflistungen</span><span class="sxs-lookup"><span data-stu-id="79a71-102">Performing Culture-Insensitive String Operations in Collections</span></span>

<span data-ttu-id="79a71-103">Der <xref:System.Collections>-Namespace enthält Klassen und Member, die standardmäßig kulturabhängiges Verhalten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="79a71-103">There are classes and members in the <xref:System.Collections> namespace that provide culture-sensitive behavior by default.</span></span> <span data-ttu-id="79a71-104">Die parameterlosen Konstruktoren für die <xref:System.Collections.CaseInsensitiveComparer>- und <xref:System.Collections.CaseInsensitiveHashCodeProvider>-Klasse initialisieren eine neue Instanz mit der <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="79a71-104">The parameterless constructors for the <xref:System.Collections.CaseInsensitiveComparer> and <xref:System.Collections.CaseInsensitiveHashCodeProvider> classes initialize a new instance using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="79a71-105">Alle Überladungen der <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType>-Methode erstellen eine neue Instanz der <xref:System.Collections.Hashtable>-Klasse standardmäßig mit der `Thread.CurrentCulture`-Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="79a71-105">All overloads of the <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> method create a new instance of the <xref:System.Collections.Hashtable> class using the `Thread.CurrentCulture` property by default.</span></span> <span data-ttu-id="79a71-106">Überladungen der <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>-Methode führen kulturabhängige Sortierungen standardmäßig mit der `Thread.CurrentCulture`-Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="79a71-106">Overloads of the <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> method perform culture-sensitive sorts by default using `Thread.CurrentCulture`.</span></span> <span data-ttu-id="79a71-107">Wenn Zeichenfolgen als Schlüssel verwendet werden, kann sich <xref:System.Collections.SortedList> auf das Sortieren und Nachschlagen in einer `Thread.CurrentCulture`-Instanz auswirken.</span><span class="sxs-lookup"><span data-stu-id="79a71-107">Sorting and lookup in a <xref:System.Collections.SortedList> can be affected by `Thread.CurrentCulture` when strings are used as the keys.</span></span> <span data-ttu-id="79a71-108">Befolgen Sie die Verwendungsempfehlungen in diesem Abschnitt, um aus diesen Klassen und Methoden im `Collections`-Namespace kulturunabhängige Ergebnisse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="79a71-108">Follow the usage recommendations provided in this section to obtain culture-insensitive results from these classes and methods in the `Collections` namespace.</span></span>

> [!NOTE]
> <span data-ttu-id="79a71-109">Wenn Sie <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> einer Vergleichsmethode übergeben, wird ein kulturunabhängiger Vergleich ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="79a71-109">Passing <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="79a71-110">Dies bewirkt jedoch keinen nicht linguistischen Vergleich, z. B. auf Dateipfade, Registrierungsschlüssel und Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="79a71-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="79a71-111">Und dadurch werden auch keine Sicherheitsentscheidungen anhand des Vergleichsergebnisses unterstützt.</span><span class="sxs-lookup"><span data-stu-id="79a71-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="79a71-112">Für einen nicht linguistischen Vergleich oder Unterstützung für ergebnisbasierte Sicherheitsentscheidungen sollte die Anwendung eine Vergleichsmethode verwenden, die einen <xref:System.StringComparison>-Wert akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="79a71-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="79a71-113">Die Anwendung sollte dann <xref:System.StringComparison> übergeben.</span><span class="sxs-lookup"><span data-stu-id="79a71-113">The application should then pass <xref:System.StringComparison>.</span></span>

## <a name="using-the-caseinsensitivecomparer-and-caseinsensitivehashcodeprovider-classes"></a><span data-ttu-id="79a71-114">Verwenden der CaseInsensitiveComparer- und der CaseInsensitiveHashCodeProvider-Klasse</span><span class="sxs-lookup"><span data-stu-id="79a71-114">Using the CaseInsensitiveComparer and CaseInsensitiveHashCodeProvider Classes</span></span>

<span data-ttu-id="79a71-115">Die parameterlosen Konstruktoren für `CaseInsensitiveHashCodeProvider` und `CaseInsensitiveComparer` initialisieren eine neue Instanz der Klasse mit `Thread.CurrentCulture`, was zu kulturabhängigem Verhalten führt.</span><span class="sxs-lookup"><span data-stu-id="79a71-115">The parameterless constructors for `CaseInsensitiveHashCodeProvider` and `CaseInsensitiveComparer` initialize a new instance of the class using the `Thread.CurrentCulture`, resulting in culture-sensitive behavior.</span></span> <span data-ttu-id="79a71-116">Im folgenden Codebeispiel wird der Konstruktor für eine `Hashtable`-Instanz veranschaulicht, die kulturabhängig ist, weil für sie die parameterlosen Konstruktoren für `CaseInsensitiveHashCodeProvider` und `CaseInsensitiveComparer` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79a71-116">The following code example demonstrates the constructor for a `Hashtable` that is culture-sensitive because it uses the parameterless constructors for `CaseInsensitiveHashCodeProvider` and `CaseInsensitiveComparer`.</span></span>

```vb
internalHashtable = New Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default)
```

```csharp
internalHashtable = new Hashtable(CaseInsensitiveHashCodeProvider.Default, CaseInsensitiveComparer.Default);
```

<span data-ttu-id="79a71-117">Wenn Sie eine kulturunabhängige `Hashtable`-Instanz über die Klassen `CaseInsensitiveComparer` und `CaseInsensitiveHashCodeProvider` erstellen möchten, initialisieren Sie neue Instanzen dieser Klassen mit den Konstruktoren, die einen `culture`-Parameter akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="79a71-117">If you want to create a culture-insensitive `Hashtable` using the `CaseInsensitiveComparer` and `CaseInsensitiveHashCodeProvider` classes, initialize new instances of these classes using the constructors that accept a `culture` parameter.</span></span> <span data-ttu-id="79a71-118">Für den `culture`-Parameter geben Sie <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> an.</span><span class="sxs-lookup"><span data-stu-id="79a71-118">For the `culture` parameter, specify <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="79a71-119">Im folgenden Codebeispiel wird der Konstruktor für eine kulturunabhängige `Hashtable`-Instanz veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="79a71-119">The following code example demonstrates the constructor for a culture-insensitive `Hashtable`.</span></span>

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

## <a name="using-the-collectionsutilcreatecaseinsensitivehashtable-method"></a><span data-ttu-id="79a71-120">Verwenden der CollectionsUtil.CreateCaseInsensitiveHashtable-Methode</span><span class="sxs-lookup"><span data-stu-id="79a71-120">Using the CollectionsUtil.CreateCaseInsensitiveHashTable Method</span></span>

<span data-ttu-id="79a71-121">Die `CollectionsUtil.CreateCaseInsensitiveHashTable`-Methode ist eine nützliche Abkürzung zum Erstellen einer neuen Instanz der `Hashtable`-Klasse, in der die Groß-/Kleinschreibung von Zeichenfolgen ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="79a71-121">The `CollectionsUtil.CreateCaseInsensitiveHashTable` method is a useful shortcut for creating a new instance of the `Hashtable` class that ignores the case of strings.</span></span> <span data-ttu-id="79a71-122">Alle Überladungen der `CollectionsUtil.CreateCaseInsensitiveHashTable`-Methode sind jedoch kulturabhängig, da in ihnen die `Thread.CurrentCulture`-Eigenschaft verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="79a71-122">However, all overloads of the `CollectionsUtil.CreateCaseInsensitiveHashTable` method are culture-sensitive because they use the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="79a71-123">Sie können mit dieser Methode keine kulturunabhängige `Hashtable`-Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="79a71-123">You cannot create a culture-insensitive `Hashtable` using this method.</span></span> <span data-ttu-id="79a71-124">Um eine kulturunabhängige `Hashtable`-Instanz zu erstellen, verwenden Sie den `Hashtable`-Konstruktor, der einen `culture`-Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="79a71-124">To create a culture-insensitive `Hashtable`, use the `Hashtable` constructor that accepts a `culture` parameter.</span></span> <span data-ttu-id="79a71-125">Für den `culture`-Parameter geben Sie `CultureInfo.InvariantCulture` an.</span><span class="sxs-lookup"><span data-stu-id="79a71-125">For the `culture` parameter, specify `CultureInfo.InvariantCulture`.</span></span> <span data-ttu-id="79a71-126">Im folgenden Codebeispiel wird der Konstruktor für eine kulturunabhängige `Hashtable`-Instanz veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="79a71-126">The following code example demonstrates the constructor for a culture-insensitive `Hashtable`.</span></span>

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

## <a name="using-the-sortedlist-class"></a><span data-ttu-id="79a71-127">Verwenden der SortedList-Klasse</span><span class="sxs-lookup"><span data-stu-id="79a71-127">Using the SortedList Class</span></span>

<span data-ttu-id="79a71-128">Eine `SortedList`-Instanz entspricht einer Auflistung von Schlüssel-Wert-Paaren, die nach Schlüsseln sortiert sind und auf die sowohl über Schlüssel als auch über Index zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="79a71-128">A `SortedList` represents a collection of key-and-value pairs that are sorted by the keys and are accessible by key and by index.</span></span> <span data-ttu-id="79a71-129">Wenn Sie eine `SortedList`-Instanz verwenden, in der Zeichenfolgen als Schlüssel verwendet werden, können Sortier- und Nachschlagevorgänge durch die `Thread.CurrentCulture`-Eigenschaft beeinflusst werden.</span><span class="sxs-lookup"><span data-stu-id="79a71-129">When you use a `SortedList` where strings are the keys, the sorting and lookup can be affected by the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="79a71-130">Um für eine `SortedList`-Instanz kulturunabhängiges Verhalten zu erzielen, erstellen Sie die `SortedList`-Instanz mit einem Konstruktor, der einen `comparer`-Parameter akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="79a71-130">To obtain culture-insensitive behavior from a `SortedList`, create a `SortedList` using one of the constructors that accepts a `comparer` parameter.</span></span> <span data-ttu-id="79a71-131">Der `comparer`-Parameter gibt die <xref:System.Collections.IComparer>-Implementierung an, die beim Vergleich von Schlüsseln zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="79a71-131">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing keys.</span></span> <span data-ttu-id="79a71-132">Geben Sie für den Parameter eine benutzerdefinierte Comparer-Klasse an, in der `CultureInfo.InvariantCulture` verwendet wird, um Schlüssel zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="79a71-132">For the parameter, specify a custom comparer class that uses `CultureInfo.InvariantCulture` to compare keys.</span></span> <span data-ttu-id="79a71-133">Das folgende Beispiel veranschaulicht eine benutzerdefinierte kulturunabhängige Comparer-Klasse, die Sie als `comparer`-Parameter für einen `SortedList`-Konstruktor angeben können.</span><span class="sxs-lookup"><span data-stu-id="79a71-133">The following example illustrates a custom culture-insensitive comparer class that you can specify as the `comparer` parameter to a `SortedList` constructor.</span></span>

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

<span data-ttu-id="79a71-134">Wenn Sie eine `SortedList`-Instanz für Zeichenfolgen verwenden, ohne eine benutzerdefinierte invariante Comparer-Klasse zu verwenden, gilt grundsätzlich, dass ein Ändern von `Thread.CurrentCulture`, nachdem die Liste aufgefüllt wurde, dazu führen kann, dass die Liste ungültig wird.</span><span class="sxs-lookup"><span data-stu-id="79a71-134">In general, if you use a `SortedList` on strings without specifying a custom invariant comparer, a change to `Thread.CurrentCulture` after the list has been populated can invalidate the list.</span></span>

## <a name="using-the-arraylistsort-method"></a><span data-ttu-id="79a71-135">Verwenden der ArrayList.Sort-Methode</span><span class="sxs-lookup"><span data-stu-id="79a71-135">Using the ArrayList.Sort Method</span></span>

<span data-ttu-id="79a71-136">Überladungen der `ArrayList.Sort`-Methode führen kulturabhängige Sortierungen standardmäßig mit der `Thread.CurrentCulture`-Eigenschaft aus.</span><span class="sxs-lookup"><span data-stu-id="79a71-136">Overloads of the `ArrayList.Sort` method perform culture-sensitive sorts by default using the `Thread.CurrentCulture` property.</span></span> <span data-ttu-id="79a71-137">Die Ergebnisse können je nach Kultur aufgrund der unterschiedlichen Sortierreihenfolgen variieren.</span><span class="sxs-lookup"><span data-stu-id="79a71-137">Results can vary by culture due to different sort orders.</span></span> <span data-ttu-id="79a71-138">Um kulturabhängiges Verhalten zu vermeiden, verwenden Sie die Überladung dieser Methode, die eine `IComparer`-Implementierung akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="79a71-138">To eliminate culture-sensitive behavior, use the overloads of this method that accept an `IComparer` implementation.</span></span> <span data-ttu-id="79a71-139">Geben Sie für den `comparer`-Parameter eine benutzerdefinierte invariante Comparer-Klasse an, in der `CultureInfo.InvariantCulture` verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="79a71-139">For the `comparer` parameter, specify a custom invariant comparer class that uses `CultureInfo.InvariantCulture`.</span></span> <span data-ttu-id="79a71-140">Ein Beispiel für eine benutzerdefinierte invariante Comparer-Klasse finden Sie im Thema [Verwenden der SortedList-Klasse](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1).</span><span class="sxs-lookup"><span data-stu-id="79a71-140">An example of a custom invariant comparer class is provided in the [Using the SortedList Class](#cpconperformingculture-insensitivestringoperationsincollectionsanchor1) topic.</span></span>

## <a name="see-also"></a><span data-ttu-id="79a71-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79a71-141">See also</span></span>

- <xref:System.Collections.CaseInsensitiveComparer>
- <xref:System.Collections.CaseInsensitiveHashCodeProvider>
- <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>
- <xref:System.Collections.SortedList>
- <xref:System.Collections.Hashtable>
- <xref:System.Collections.IComparer>
- [<span data-ttu-id="79a71-142">Durchführen kulturunabhängiger Zeichenfolgenoperationen</span><span class="sxs-lookup"><span data-stu-id="79a71-142">Performing Culture-Insensitive String Operations</span></span>](performing-culture-insensitive-string-operations.md)
- <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType>
