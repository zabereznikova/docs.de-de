---
title: Übersicht über das Modell der attributierten Programmierung (MEF)
description: In diesem Artikel erhalten Sie Informationen zu den ersten Schritten mit dem Modell der attributierten Programmierung für das Managed Extensibility Framework (MEF) in .NET.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MEF, attributed programming model
- attributed programming model [MEF]
ms.assetid: 49b787ff-2741-4836-ad51-c3017dc592d4
ms.openlocfilehash: aea3a19ffe6f177901e5c0839b618bb36f573beb
ms.sourcegitcommit: 97ce5363efa88179dd76e09de0103a500ca9b659
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2020
ms.locfileid: "86281367"
---
# <a name="attributed-programming-model-overview-mef"></a><span data-ttu-id="a9212-103">Übersicht über das Modell der attributierten Programmierung (MEF)</span><span class="sxs-lookup"><span data-stu-id="a9212-103">Attributed Programming Model Overview (MEF)</span></span>

<span data-ttu-id="a9212-104">Im Managed Extensibility Framework (MEF) ist ein *Programmiermodell* eine besondere Methode, den Satz der konzeptionellen Objekte zu definieren, mit denen MEF ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a9212-104">In the Managed Extensibility Framework (MEF), a *programming model* is a particular method of defining the set of conceptual objects on which MEF operates.</span></span> <span data-ttu-id="a9212-105">Diese konzeptionellen Objekte umfassen Teile, Importe und Exporte.</span><span class="sxs-lookup"><span data-stu-id="a9212-105">These conceptual objects include parts, imports, and exports.</span></span> <span data-ttu-id="a9212-106">MEF verwendet diese Objekte, gibt jedoch nicht an, wie sie dargestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="a9212-106">MEF uses these objects, but does not specify how they should be represented.</span></span> <span data-ttu-id="a9212-107">Daher ist eine Vielzahl von Programmiermodellen möglich, einschließlich benutzerdefinierter Programmiermodelle.</span><span class="sxs-lookup"><span data-stu-id="a9212-107">Therefore, a wide variety of programming models are possible, including customized programming models.</span></span>

<span data-ttu-id="a9212-108">Das in MEF verwendete Standardprogrammiermodell ist das *Modell der attributierten Programmierung*.</span><span class="sxs-lookup"><span data-stu-id="a9212-108">The default programming model used in MEF is the *attributed programming model*.</span></span> <span data-ttu-id="a9212-109">Im Modell der attributierten Programmierung werden Teile, Importe, Exporte und andere Objekte mit Attributen definiert, die gewöhnliche .NET Framework-Klassen ergänzen.</span><span class="sxs-lookup"><span data-stu-id="a9212-109">In the attributed programming model parts, imports, exports, and other objects are defined with attributes that decorate ordinary .NET Framework classes.</span></span> <span data-ttu-id="a9212-110">Dieses Thema erläutert, wie mit den Attributen, die vom Modell der attributierten Programmierung angeboten werden, eine MEF-Anwendung erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="a9212-110">This topic explains how to use the attributes provided by the attributed programming model to create a MEF application.</span></span>

<a name="import_and_export_basics"></a>

## <a name="import-and-export-basics"></a><span data-ttu-id="a9212-111">Importieren und Exportieren – Grundlagen</span><span class="sxs-lookup"><span data-stu-id="a9212-111">Import and Export Basics</span></span>

<span data-ttu-id="a9212-112">Ein *Export* ist ein Wert, den ein Teil anderen Teilen im Container zur Verfügung stellt, und ein *Import* ist eine Anforderung eines Teils an den Container, eine Auffüllung mit den verfügbaren Exporten vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="a9212-112">An *export* is a value that a part provides to other parts in the container, and an *import* is a requirement that a part expresses to the container, to be filled from the available exports.</span></span> <span data-ttu-id="a9212-113">Im Modell der attributierten Programmierung werden Importe und Exporte durch Ergänzen von Klassen oder Membern mit dem `Import` -Attribut und dem `Export` -Attribut deklariert.</span><span class="sxs-lookup"><span data-stu-id="a9212-113">In the attributed programming model, imports and exports are declared by decorating classes or members with the `Import` and `Export` attributes.</span></span> <span data-ttu-id="a9212-114">Das `Export` -Attribut kann eine Klasse, ein Feld, eine Eigenschaft oder eine Methode ergänzen, während das `Import` -Attribut ein Feld, eine Eigenschaft oder einen Konstruktorparameter ergänzen kann.</span><span class="sxs-lookup"><span data-stu-id="a9212-114">The `Export` attribute can decorate a class, field, property, or method, while the `Import` attribute can decorate a field, property, or constructor parameter.</span></span>

<span data-ttu-id="a9212-115">Damit ein Import mit einem Export verglichen werden kann, müssen Import und Export den gleichen *Vertrag*besitzen.</span><span class="sxs-lookup"><span data-stu-id="a9212-115">In order for an import to be matched with an export, the import and export must have the same *contract*.</span></span> <span data-ttu-id="a9212-116">Der Vertrag besteht aus einer Zeichenfolge, die als *Vertragsname*bezeichnet wird, und aus dem Typ des exportierten oder importierten Objekts, das als *Vertragstyp*bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="a9212-116">The contract consists of a string, called the *contract name*, and the type of the exported or imported object, called the *contract type*.</span></span> <span data-ttu-id="a9212-117">Nur, wenn sowohl der Vertragsname als auch der Vertragstyp übereinstimmen, erfüllt ein Export die Bedingungen für einen bestimmten Import.</span><span class="sxs-lookup"><span data-stu-id="a9212-117">Only if both the contract name and contract type match is an export considered to fulfill a particular import.</span></span>

<span data-ttu-id="a9212-118">Einer der oder beide Vertragsparameter können implizit oder explizit sein.</span><span class="sxs-lookup"><span data-stu-id="a9212-118">Either or both of the contract parameters can be implicit or explicit.</span></span> <span data-ttu-id="a9212-119">Im folgenden Code wird eine Klasse gezeigt, die einen grundlegenden Import deklariert.</span><span class="sxs-lookup"><span data-stu-id="a9212-119">The following code shows a class that declares a basic import.</span></span>

```vb
Public Class MyClass1
    <Import()>
    Public Property MyAddin As IMyAddin
End Class
```

```csharp
public class MyClass
{
    [Import]
    public IMyAddin MyAddin { get; set; }
}
```

<span data-ttu-id="a9212-120">In diesem Import ist dem `Import` -Attribut weder ein Vertragstyp noch ein Vertragsnamensparameter zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="a9212-120">In this import, the `Import` attribute has neither a contract type nor a contract name parameter attached.</span></span> <span data-ttu-id="a9212-121">Daher werden beide in der ergänzten Eigenschaft abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="a9212-121">Therefore, both will be inferred from the decorated property.</span></span> <span data-ttu-id="a9212-122">In diesem Fall ist der Vertragstyp `IMyAddin`, und der Vertragsname ist eine eindeutige aus dem Vertragstyp erstellte Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a9212-122">In this case, the contract type will be `IMyAddin`, and the contract name will be a unique string created from the contract type.</span></span> <span data-ttu-id="a9212-123">(Anders ausgedrückt stimmt der Vertragsname nur mit Exporten überein, deren Namen ebenfalls vom Typ `IMyAddin`abgeleitet werden.)</span><span class="sxs-lookup"><span data-stu-id="a9212-123">(In other words, the contract name will match only exports whose names are also inferred from the type `IMyAddin`.)</span></span>

<span data-ttu-id="a9212-124">Nachfolgend wird ein Export angezeigt, der dem vorherigen Import entspricht.</span><span class="sxs-lookup"><span data-stu-id="a9212-124">The following shows an export that matches the previous import.</span></span>

```vb
<Export(GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export(typeof(IMyAddin))]
public class MyLogger : IMyAddin { }
```

<span data-ttu-id="a9212-125">In diesem Export ist der Vertragstyp `IMyAddin` , da er als Parameter des `Export` -Attributs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a9212-125">In this export, the contract type is `IMyAddin` because it is specified as a parameter of the `Export` attribute.</span></span> <span data-ttu-id="a9212-126">Der exportierte Typ muss entweder mit dem Vertragstyp übereinstimmen, vom Vertragstyp abgeleitet werden oder den Vertragstyp implementieren, wenn es sich um eine Schnittstelle handelt.</span><span class="sxs-lookup"><span data-stu-id="a9212-126">The exported type must be either the same as the contract type, derive from the contract type, or implement the contract type if it is an interface.</span></span> <span data-ttu-id="a9212-127">In diesem Export implementiert der tatsächliche `MyLogger` -Typ die `IMyAddin`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="a9212-127">In this export, the actual type `MyLogger` implements the interface `IMyAddin`.</span></span> <span data-ttu-id="a9212-128">Der Vertragsname wird vom Vertragstyp abgeleitet, d. h., dass der Export dem vorherigen Import entspricht.</span><span class="sxs-lookup"><span data-stu-id="a9212-128">The contract name is inferred from the contract type, which means that this export will match the previous import.</span></span>

> [!NOTE]
> <span data-ttu-id="a9212-129">Exporte und Importe sollten normalerweise für öffentliche Klassen oder Member deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-129">Exports and imports should usually be declared on public classes or members.</span></span> <span data-ttu-id="a9212-130">Andere Deklarationen werden unterstützt, aber das Exportieren oder Importieren eines privaten, geschützten oder internen Members unterbricht das Isolationsmodell für den Teil und wird daher nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="a9212-130">Other declarations are supported, but exporting or importing a private, protected, or internal member breaks the isolation model for the part and is therefore not recommended.</span></span>

<span data-ttu-id="a9212-131">Der Vertragstyp muss für Export und Import genau zusammenpassen, damit er als Übereinstimmung betrachtet wird.</span><span class="sxs-lookup"><span data-stu-id="a9212-131">The contract type must match exactly for the export and import to be considered a match.</span></span> <span data-ttu-id="a9212-132">Betrachten Sie den folgenden Export.</span><span class="sxs-lookup"><span data-stu-id="a9212-132">Consider the following export.</span></span>

```vb
<Export()> 'WILL NOT match the previous import!
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export] //WILL NOT match the previous import!
public class MyLogger : IMyAddin { }
```

<span data-ttu-id="a9212-133">In diesem Export ist der Vertragstyp `MyLogger` anstatt `IMyAddin`.</span><span class="sxs-lookup"><span data-stu-id="a9212-133">In this export, the contract type is `MyLogger` instead of `IMyAddin`.</span></span> <span data-ttu-id="a9212-134">Obwohl `MyLogger``IMyAddin` implementiert und daher in ein `IMyAddin`-Objekt umgewandelt werden kann, entspricht dieser Export nicht dem vorherigen Import, da die Vertragstypen nicht identisch sind.</span><span class="sxs-lookup"><span data-stu-id="a9212-134">Even though `MyLogger` implements `IMyAddin`, and therefore could be cast to an `IMyAddin` object, this export will not match the previous import because the contract types are not the same.</span></span>

<span data-ttu-id="a9212-135">Im Allgemeinen ist es nicht notwendig, den Vertragsnamen anzugeben, und die meisten Verträge sollten im Hinblick auf den Vertragstyp und die Metadaten definiert werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-135">In general, it is not necessary to specify the contract name, and most contracts should be defined in terms of the contract type and metadata.</span></span> <span data-ttu-id="a9212-136">Unter bestimmten Umständen ist es jedoch wichtig, den Vertragsnamen direkt anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a9212-136">However, under certain circumstances, it is important to specify the contract name directly.</span></span> <span data-ttu-id="a9212-137">Der häufigste Fall ist, wenn eine Klasse mehrere Werte exportiert, die gemeinsam einen allgemeinen Typ verwenden, z. B. Primitive.</span><span class="sxs-lookup"><span data-stu-id="a9212-137">The most common case is when a class exports several values that share a common type, such as primitives.</span></span> <span data-ttu-id="a9212-138">Der Vertragsname kann als erster Parameter des `Import` -Attributs oder des `Export` -Attributs angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-138">The contract name can be specified as the first parameter of the `Import` or `Export` attribute.</span></span> <span data-ttu-id="a9212-139">Im folgenden Code werden ein Import und ein Export mit dem angegebenen Vertragsnamen `MajorRevision`gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a9212-139">The following code shows an import and an export with a specified contract name of `MajorRevision`.</span></span>

```vb
Public Class MyExportClass

    'This one will match
    <Export("MajorRevision")>
    Public ReadOnly Property MajorRevision As Integer
        Get
            Return 4
        End Get
    End Property

    <Export("MinorRevision")>
    Public ReadOnly Property MinorRevision As Integer
        Get
            Return 16
        End Get
    End Property
End Class
```

```csharp
public class MyClass
{
    [Import("MajorRevision")]
    public int MajorRevision { get; set; }
}

public class MyExportClass
{
    [Export("MajorRevision")] //This one will match.
    public int MajorRevision = 4;

    [Export("MinorRevision")]
    public int MinorRevision = 16;
}
```

<span data-ttu-id="a9212-140">Wenn der Vertragstyp nicht angegeben wird, wird er immer noch vom Typ des Imports oder Exports abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="a9212-140">If the contract type is not specified, it will still be inferred from the type of the import or export.</span></span> <span data-ttu-id="a9212-141">Auch wenn der Vertragsname explizit angegeben wird, muss der Vertragstyp auch genau für den Import übereinstimmen, um als Übereinstimmung betrachtet zu werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-141">However, even if the contract name is specified explicitly, the contract type must also match exactly for the import and export to be considered a match.</span></span> <span data-ttu-id="a9212-142">Wenn das `MajorRevision` -Feld z. B. eine Zeichenfolge wäre, würden die abgeleiteten Vertragstypen nicht übereinstimmen, und der Export würde nicht mit dem Import übereinstimmen, obwohl er den gleichen Vertragsnamen besitzt.</span><span class="sxs-lookup"><span data-stu-id="a9212-142">For example, if the `MajorRevision` field was a string, the inferred contract types would not match and the export would not match the import, despite having the same contract name.</span></span>

### <a name="importing-and-exporting-a-method"></a><span data-ttu-id="a9212-143">Importieren und Exportieren einer Methode</span><span class="sxs-lookup"><span data-stu-id="a9212-143">Importing and Exporting a Method</span></span>

<span data-ttu-id="a9212-144">Das `Export` -Attribut kann eine Methode ebenso wie eine Klasse, Eigenschaft oder Funktion ergänzen.</span><span class="sxs-lookup"><span data-stu-id="a9212-144">The `Export` attribute can also decorate a method, in the same way as a class, property, or function.</span></span> <span data-ttu-id="a9212-145">Für Methodenexporte muss ein Vertragstyp oder Vertragsname angegeben werden, da der Typ nicht abgeleitet werden kann.</span><span class="sxs-lookup"><span data-stu-id="a9212-145">Method exports must specify a contract type or contract name, as the type cannot be inferred.</span></span> <span data-ttu-id="a9212-146">Der angegebene Typ kann entweder ein benutzerdefinierter Delegat oder ein generischer Typ sein, wie z. B. `Func`.</span><span class="sxs-lookup"><span data-stu-id="a9212-146">The specified type can be either a custom delegate or a generic type, such as `Func`.</span></span> <span data-ttu-id="a9212-147">Die folgende Klasse exportiert eine Methode mit dem Namen `DoSomething`.</span><span class="sxs-lookup"><span data-stu-id="a9212-147">The following class exports a method named `DoSomething`.</span></span>

```vb
Public Class MyAddin

    'Explicitly specifying a generic type
    <Export(GetType(Func(Of Integer, String)))>
    Public Function DoSomething(ByVal TheParam As Integer) As String
        Return Nothing 'Function body goes here
    End Function

End Class
```

```csharp
public class MyAddin
{
    //Explicitly specifying a generic type.
    [Export(typeof(Func<int, string>))]
    public string DoSomething(int TheParam);
}
```

<span data-ttu-id="a9212-148">In dieser Klasse erhält die `DoSomething` -Methode einen einzelnen `int` -Parameter und gibt `string`zurück.</span><span class="sxs-lookup"><span data-stu-id="a9212-148">In this class, the `DoSomething` method takes a single `int` parameter and returns a `string`.</span></span> <span data-ttu-id="a9212-149">Damit eine Übereinstimmung mit dem Export vorliegt, muss der importbezogene Teil einen entsprechenden Member deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a9212-149">To match this export, the importing part must declare an appropriate member.</span></span> <span data-ttu-id="a9212-150">Die folgende Klasse importiert die `DoSomething` -Methode.</span><span class="sxs-lookup"><span data-stu-id="a9212-150">The following class imports the `DoSomething` method.</span></span>

```vb
Public Class MyClass1

    'Contract name must match!
    <Import()>
    Public Property MajorRevision As Func(Of Integer, String)
End Class
```

```csharp
public class MyClass
{
    [Import] //Contract name must match!
    public Func<int, string> DoSomething { get; set; }
}
```

<span data-ttu-id="a9212-151">Weitere Informationen zur Verwendung des `Func<T, T>` -Objekts finden Sie unter <xref:System.Func%602>.</span><span class="sxs-lookup"><span data-stu-id="a9212-151">For more information about how to use of the `Func<T, T>` object, see <xref:System.Func%602>.</span></span>

<a name="types_of_imports"></a>

## <a name="types-of-imports"></a><span data-ttu-id="a9212-152">Importtypen</span><span class="sxs-lookup"><span data-stu-id="a9212-152">Types of Imports</span></span>

<span data-ttu-id="a9212-153">MEF unterstützt mehrere Importtypen, einschließlich "Dynamisch", "Verzögert", "Erforderlich" und "Optional".</span><span class="sxs-lookup"><span data-stu-id="a9212-153">MEF support several import types, including dynamic, lazy, prerequisite, and optional.</span></span>

### <a name="dynamic-imports"></a><span data-ttu-id="a9212-154">Dynamische Importe</span><span class="sxs-lookup"><span data-stu-id="a9212-154">Dynamic Imports</span></span>

<span data-ttu-id="a9212-155">In einigen Fällen soll die importierende Klasse mit Exporten eines beliebigen Typs übereinstimmen, die einen bestimmten Vertragsnamen besitzen.</span><span class="sxs-lookup"><span data-stu-id="a9212-155">In some cases, the importing class may want to match exports of any type that have a particular contract name.</span></span> <span data-ttu-id="a9212-156">In diesem Szenario kann die Klasse einen *dynamischen Import*deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a9212-156">In this scenario, the class can declare a *dynamic import*.</span></span> <span data-ttu-id="a9212-157">Der folgende Import entspricht jeden Export mit dem Vertragsnamen "TheString".</span><span class="sxs-lookup"><span data-stu-id="a9212-157">The following import matches any export with contract name "TheString".</span></span>

```vb
Public Class MyClass1

    <Import("TheString")>
    Public Property MyAddin

End Class
```

```csharp
public class MyClass
{
    [Import("TheString")]
    public dynamic MyAddin { get; set; }
}
```

<span data-ttu-id="a9212-158">Wenn der Vertragstyp vom `dynamic` -Schlüsselwort abgeleitet wird, stimmt er mit einem beliebigen Vertragstyp überein.</span><span class="sxs-lookup"><span data-stu-id="a9212-158">When the contract type is inferred from the `dynamic` keyword, it will match any contract type.</span></span> <span data-ttu-id="a9212-159">In diesem Fall sollte für einen Import **immer** ein Vertragsname zur Prüfung von Übereinstimmungen mit Exporten angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-159">In this case, an import should **always** specify a contract name to match on.</span></span> <span data-ttu-id="a9212-160">(Ohne Angabe eines Vertragsnamens wird angenommen, dass für den Import keine übereinstimmenden Export vorliegen.) Beide der folgenden Exporte entsprechen dem vorherigen Import.</span><span class="sxs-lookup"><span data-stu-id="a9212-160">(If no contract name is specified, the import will be considered to match no exports.) Both of the following exports would match the previous import.</span></span>

```vb
<Export("TheString", GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class

<Export("TheString")>
Public Class MyToolbar

End Class
```

```csharp
[Export("TheString", typeof(IMyAddin))]
public class MyLogger : IMyAddin { }

[Export("TheString")]
public class MyToolbar { }
```

<span data-ttu-id="a9212-161">Offensichtlich muss die importierende Klasse für den Umgang mit einem Objekt eines beliebigen Typs vorbereitet werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-161">Obviously, the importing class must be prepared to deal with an object of arbitrary type.</span></span>

### <a name="lazy-imports"></a><span data-ttu-id="a9212-162">Verzögerte Importe</span><span class="sxs-lookup"><span data-stu-id="a9212-162">Lazy Imports</span></span>

<span data-ttu-id="a9212-163">In einigen Fällen erfordert die importierende Klasse möglicherweise einen indirekten Verweis auf das importierte Objekt, damit das Objekt nicht sofort instanziiert wird.</span><span class="sxs-lookup"><span data-stu-id="a9212-163">In some cases, the importing class may require an indirect reference to the imported object, so that the object is not instantiated immediately.</span></span> <span data-ttu-id="a9212-164">In diesem Szenario kann die Klasse einen *verzögerten Import* mit dem Vertragstyp `Lazy<T>`deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a9212-164">In this scenario, the class can declare a *lazy import* by using a contract type of `Lazy<T>`.</span></span> <span data-ttu-id="a9212-165">Die folgende importierende Eigenschaft deklariert einen verzögerten Import.</span><span class="sxs-lookup"><span data-stu-id="a9212-165">The following importing property declares a lazy import.</span></span>

```vb
Public Class MyClass1

    <Import()>
    Public Property MyAddin As Lazy(Of IMyAddin)

End Class
```

```csharp
public class MyClass
{
    [Import]
    public Lazy<IMyAddin> MyAddin { get; set; }
}
```

<span data-ttu-id="a9212-166">Aus Sicht der Kompositions-Engine wird der Vertragstyp `Lazy<T>` als identisch mit dem Vertragstyp `T`eingestuft.</span><span class="sxs-lookup"><span data-stu-id="a9212-166">From the point of view of the composition engine, a contract type of `Lazy<T>` is considered identical to contract type of `T`.</span></span> <span data-ttu-id="a9212-167">Daher entspricht der vorherige Import dem folgenden Export.</span><span class="sxs-lookup"><span data-stu-id="a9212-167">Therefore, the previous import would match the following export.</span></span>

```vb
<Export(GetType(IMyAddin))>
Public Class MyLogger
    Implements IMyAddin

End Class
```

```csharp
[Export(typeof(IMyAddin))]
public class MyLogger : IMyAddin { }
```

<span data-ttu-id="a9212-168">Der Vertragsname und Vertragstyp kann im `Import` -Attribut für einen verzögerten Import angegeben werden (siehe Abschnitt "Grundlegende Importe und Exporte").</span><span class="sxs-lookup"><span data-stu-id="a9212-168">The contract name and contract type can be specified in the `Import` attribute for a lazy import, as described earlier in the "Basic Imports and Exports" section.</span></span>

### <a name="prerequisite-imports"></a><span data-ttu-id="a9212-169">Erforderliche Importe</span><span class="sxs-lookup"><span data-stu-id="a9212-169">Prerequisite Imports</span></span>

<span data-ttu-id="a9212-170">Exportierte MEF-Teile werden in der Regel von der Kompositions-Engine erstellt, und zwar als Antwort auf eine direkte Anforderung oder die Notwendigkeit, einen übereinstimmenden Import aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="a9212-170">Exported MEF parts are typically created by the composition engine, in response to a direct request or the need to fill a matched import.</span></span> <span data-ttu-id="a9212-171">Standardmäßig verwendet die Kompositions-Engine beim Erstellen eines Teils den parameterlosen Konstruktor.</span><span class="sxs-lookup"><span data-stu-id="a9212-171">By default, when creating a part, the composition engine uses the parameter-less constructor.</span></span> <span data-ttu-id="a9212-172">Damit die Engine einen anderen Konstruktor verwendet, können Sie sie mit dem `ImportingConstructor`-Attribut markieren.</span><span class="sxs-lookup"><span data-stu-id="a9212-172">To make the engine use a different constructor, you can mark it with the `ImportingConstructor` attribute.</span></span>

<span data-ttu-id="a9212-173">Jeder Teil verfügt möglicherweise nur über einen Konstruktor für die Verwendung durch die Kompositions-Engine.</span><span class="sxs-lookup"><span data-stu-id="a9212-173">Each part may have only one constructor for use by the composition engine.</span></span> <span data-ttu-id="a9212-174">Wenn kein parameterloser Konstruktor und kein Attribut vom Typ `ImportingConstructor` oder aber mehrere Attribute vom Typ `ImportingConstructor` angegeben werden, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="a9212-174">Providing no parameterless constructor and no `ImportingConstructor` attribute, or providing more than one `ImportingConstructor` attribute, will produce an error.</span></span>

<span data-ttu-id="a9212-175">Um die Parameter eines Konstruktors auszufüllen, der mit dem `ImportingConstructor` -Attribut markiert ist, werden alle diese Parameter automatisch als Importe deklariert.</span><span class="sxs-lookup"><span data-stu-id="a9212-175">To fill the parameters of a constructor marked with the `ImportingConstructor` attribute, all of those parameters are automatically declared as imports.</span></span> <span data-ttu-id="a9212-176">Dies ist eine einfache Möglichkeit zum Deklarieren von Importen, die während der Teileinitialisierung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-176">This is a convenient way to declare imports that are used during part initialization.</span></span> <span data-ttu-id="a9212-177">Die folgende Klasse verwendet `ImportingConstructor` , um einen Import zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="a9212-177">The following class uses `ImportingConstructor` to declare an import.</span></span>

```vb
Public Class MyClass1

    Private _theAddin As IMyAddin

    'Parameterless constructor will NOT be used
    'because the ImportingConstructor
    'attribute is present.
    Public Sub New()

    End Sub

    'This constructor will be used.
    'An import with contract type IMyAddin
    'is declared automatically.
    <ImportingConstructor()>
    Public Sub New(ByVal MyAddin As IMyAddin)
        _theAddin = MyAddin
    End Sub

End Class
```

```csharp
public class MyClass
{
    private IMyAddin _theAddin;

    //Parameterless constructor will NOT be
    //used because the ImportingConstructor
    //attribute is present.
    public MyClass() { }

    //This constructor will be used.
    //An import with contract type IMyAddin is
    //declared automatically.
    [ImportingConstructor]
    public MyClass(IMyAddin MyAddin)
    {
        _theAddin = MyAddin;
    }
}
```

<span data-ttu-id="a9212-178">Standardmäßig verwendet das `ImportingConstructor` -Attribut für alle Parameterimporte abgeleitete Vertragstypen und Vertragsnamen.</span><span class="sxs-lookup"><span data-stu-id="a9212-178">By default, the `ImportingConstructor` attribute uses inferred contract types and contract names for all of the parameter imports.</span></span> <span data-ttu-id="a9212-179">Es ist möglich, dies durch das Ergänzen der Parameter mit `Import` -Attributen zu überschreiben, die anschließend explizit den Vertragstyp und den Vertragsnamen definieren können.</span><span class="sxs-lookup"><span data-stu-id="a9212-179">It is possible to override this by decorating the parameters with `Import` attributes, which can then define the contract type and contract name explicitly.</span></span> <span data-ttu-id="a9212-180">Im folgenden Code wird ein Konstruktor gezeigt, der diese Syntax für das Importieren einer abgeleiteten Klasse anstelle einer übergeordneten Klasse verwendet.</span><span class="sxs-lookup"><span data-stu-id="a9212-180">The following code demonstrates a constructor that uses this syntax to import a derived class instead of a parent class.</span></span>

```vb
<ImportingConstructor()>
Public Sub New(<Import(GetType(IMySubAddin))> ByVal MyAddin As IMyAddin)

End Sub
```

```csharp
[ImportingConstructor]
public MyClass([Import(typeof(IMySubAddin))]IMyAddin MyAddin)
{
    _theAddin = MyAddin;
}
```

<span data-ttu-id="a9212-181">Insbesondere sollten Sie bei Auflistungsparametern vorsichtig sein.</span><span class="sxs-lookup"><span data-stu-id="a9212-181">In particular, you should be careful with collection parameters.</span></span> <span data-ttu-id="a9212-182">Wenn Sie z. B. `ImportingConstructor` für einen Konstruktor mit einem Parameter des Typs `IEnumerable<int>`angeben, entspricht der Import einem einzelnen Export vom Typ `IEnumerable<int>`und nicht einer Gruppe von Exporten vom Typ `int`.</span><span class="sxs-lookup"><span data-stu-id="a9212-182">For example, if you specify `ImportingConstructor` on a constructor with a parameter of type `IEnumerable<int>`, the import will match a single export of type `IEnumerable<int>`, instead of a set of exports of type `int`.</span></span> <span data-ttu-id="a9212-183">Um eine Übereinstimmung mit einer Gruppe von Exporten vom Typ `int`zu erzielen, muss der Parameter mit dem `ImportMany` -Attribut ergänzt werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-183">To match a set of exports of type `int`, you have to decorate the parameter with the `ImportMany` attribute.</span></span>

<span data-ttu-id="a9212-184">Parameter, die vom `ImportingConstructor` -Attribut als Importe deklariert wurden, werden ebenfalls als *erforderliche Importe*markiert.</span><span class="sxs-lookup"><span data-stu-id="a9212-184">Parameters declared as imports by the `ImportingConstructor` attribute are also marked as *prerequisite imports*.</span></span> <span data-ttu-id="a9212-185">MEF gestattet normalerweise Exporte und Importe, um einen *Zyklus*zu bilden.</span><span class="sxs-lookup"><span data-stu-id="a9212-185">MEF normally allows exports and imports to form a *cycle*.</span></span> <span data-ttu-id="a9212-186">Bei einem Zyklus importiert z. B. Objekt A das Objekt B, das wiederum Objekt A importiert. Unter normalen Umständen ist ein Zyklus kein Problem, und der Kompositionscontainer erstellt beide Objekte ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="a9212-186">For example, a cycle is where object A imports object B, which in turn imports object A. Under ordinary circumstances, a cycle is not a problem, and the composition container constructs both objects normally.</span></span>

<span data-ttu-id="a9212-187">Wenn ein importierter Wert vom Konstruktor eines Teils benötigt wird, kann dieses Objekt nicht an einem Zyklus teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="a9212-187">When an imported value is required by the constructor of a part, that object cannot participate in a cycle.</span></span> <span data-ttu-id="a9212-188">Wenn Objekt A erfordert, dass Objekt B erstellt wird, bevor es selbst erstellt werden kann, und wenn Objekt B Objekt A importiert, kann der Zyklus nicht aufgelöst werden, und ein Kompositionsfehler tritt auf.</span><span class="sxs-lookup"><span data-stu-id="a9212-188">If object A requires that object B be constructed before it can be constructed itself, and object B imports object A, then the cycle will be unable to resolve and a composition error will occur.</span></span> <span data-ttu-id="a9212-189">Für Konstruktorparameter deklarierte Importe sind daher erforderliche Importe, die alle ausgefüllt werden müssen, bevor die Exporte aus dem Objekt, das diese benötigt, verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a9212-189">Imports declared on constructor parameters are therefore prerequisite imports, which must all be filled before any of the exports from the object that requires them can be used.</span></span>

### <a name="optional-imports"></a><span data-ttu-id="a9212-190">Optionale Importe</span><span class="sxs-lookup"><span data-stu-id="a9212-190">Optional Imports</span></span>

<span data-ttu-id="a9212-191">Das `Import` -Attribut gibt eine Anforderung an, damit der Teil funktionsfähig ist.</span><span class="sxs-lookup"><span data-stu-id="a9212-191">The `Import` attribute specifies a requirement for the part to function.</span></span> <span data-ttu-id="a9212-192">Wenn ein Import nicht erfüllt werden kann, schlägt die Komposition dieses Teils fehl, und der Teil ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a9212-192">If an import cannot be fulfilled, the composition of that part will fail and the part will not be available.</span></span>

<span data-ttu-id="a9212-193">Sie können mit der *-Eigenschaft angeben, dass ein Import* optional `AllowDefault` ist.</span><span class="sxs-lookup"><span data-stu-id="a9212-193">You can specify that an import is *optional* by using the `AllowDefault` property.</span></span> <span data-ttu-id="a9212-194">In diesem Fall ist die Komposition erfolgreich, auch wenn der Import mit keinen verfügbaren Exporten übereinstimmt, und die importierende Eigenschaft wird auf die Standardeinstellung für den Eigenschaftentyp festgelegt (`null` für Objekteigenschaften, `false` für boolesche Werte oder 0 (null) für numerische Eigenschaften). Die folgende Klasse verwendet einen optionalen Import.</span><span class="sxs-lookup"><span data-stu-id="a9212-194">In this case, the composition will succeed even if the import does not match any available exports, and the importing property will be set to the default for its property type (`null` for object properties, `false` for Booleans, or zero for numeric properties.) The following class uses an optional import.</span></span>

```vb
Public Class MyClass1

    <Import(AllowDefault:=True)>
    Public Property thePlugin As Plugin

    'If no matching export is available,
    'thePlugin will be set to null.
End Class
```

```csharp
public class MyClass
{
    [Import(AllowDefault = true)]
    public Plugin thePlugin { get; set; }

    //If no matching export is available,
    //thePlugin will be set to null.
}
```

### <a name="importing-multiple-objects"></a><span data-ttu-id="a9212-195">Importieren von mehreren Objekten</span><span class="sxs-lookup"><span data-stu-id="a9212-195">Importing Multiple Objects</span></span>

<span data-ttu-id="a9212-196">Das `Import` -Attribut wird nur erstellt, wenn es mit genau einem Export übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="a9212-196">The `Import` attribute will only be successfully composed when it matches one and only one export.</span></span> <span data-ttu-id="a9212-197">In anderen Fällen treten Kompositionsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="a9212-197">Other cases will produce a composition error.</span></span> <span data-ttu-id="a9212-198">Um mehr als einen Export zu importieren, der mit dem gleichen Vertrag übereinstimmt, verwenden Sie das `ImportMany` -Attribut.</span><span class="sxs-lookup"><span data-stu-id="a9212-198">To import more than one export that matches the same contract, use the `ImportMany` attribute.</span></span> <span data-ttu-id="a9212-199">Mit diesem Attribut markierte Importe sind immer optional.</span><span class="sxs-lookup"><span data-stu-id="a9212-199">Imports marked with this attribute are always optional.</span></span> <span data-ttu-id="a9212-200">Die Komposition schlägt nicht z. B. nicht fehl, wenn keine übereinstimmenden Exporte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="a9212-200">For example, composition will not fail if no matching exports are present.</span></span> <span data-ttu-id="a9212-201">Die folgende Klasse importiert eine beliebige Anzahl von Exporten vom Typ `IMyAddin`.</span><span class="sxs-lookup"><span data-stu-id="a9212-201">The following class imports any number of exports of type `IMyAddin`.</span></span>

```vb
Public Class MyClass1

    <ImportMany()>
    Public Property MyAddin As IEnumerable(Of IMyAddin)

End Class
```

```csharp
public class MyClass
{
    [ImportMany]
    public IEnumerable<IMyAddin> MyAddin { get; set; }
}
```

<span data-ttu-id="a9212-202">Auf das importierte Array kann mit normaler `IEnumerable<T>` -Syntax und entsprechenden normalen Methoden zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-202">The imported array can be accessed by using ordinary `IEnumerable<T>` syntax and methods.</span></span> <span data-ttu-id="a9212-203">Es ist auch möglich, stattdessen ein normales Array (`IMyAddin[]`) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9212-203">It is also possible to use an ordinary array (`IMyAddin[]`) instead.</span></span>

<span data-ttu-id="a9212-204">Dieses Muster kann sehr wichtig sein, wenn Sie es in Verbindung mit der `Lazy<T>` -Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9212-204">This pattern can be very important when you use it in combination with the `Lazy<T>` syntax.</span></span> <span data-ttu-id="a9212-205">Mit `ImportMany`, `IEnumerable<T>`und `Lazy<T>`können Sie z. B. indirekte Verweise auf eine beliebige Anzahl von Objekten importieren und nur die Objekte instanziieren, die notwendig werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-205">For example, by using `ImportMany`, `IEnumerable<T>`, and `Lazy<T>`, you can import indirect references to any number of objects and only instantiate the ones that become necessary.</span></span> <span data-ttu-id="a9212-206">Die folgende Klasse zeigt dieses Muster.</span><span class="sxs-lookup"><span data-stu-id="a9212-206">The following class shows this pattern.</span></span>

```vb
Public Class MyClass1

    <ImportMany()>
    Public Property MyAddin As IEnumerable(Of Lazy(Of IMyAddin))

End Class
```

```csharp
public class MyClass
{
    [ImportMany]
    public IEnumerable<Lazy<IMyAddin>> MyAddin { get; set; }
}
```

<a name="avoiding_discovery"></a>

## <a name="avoiding-discovery"></a><span data-ttu-id="a9212-207">Verhindern der Erkennung von Teilen</span><span class="sxs-lookup"><span data-stu-id="a9212-207">Avoiding Discovery</span></span>

<span data-ttu-id="a9212-208">In einigen Fällen möchten Sie unter Umständen verhindern, dass ein Teil als Teil eines Katalogs erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="a9212-208">In some cases, you may want to prevent a part from being discovered as part of a catalog.</span></span> <span data-ttu-id="a9212-209">Der Teil kann z. B. eine Basisklasse sein, von der geerbt werden soll, die aber nicht zu verwenden ist.</span><span class="sxs-lookup"><span data-stu-id="a9212-209">For example, the part may be a base class intended to be inherited from, but not used.</span></span> <span data-ttu-id="a9212-210">Es gibt zwei Möglichkeiten, dies zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="a9212-210">There are two ways to accomplish this.</span></span> <span data-ttu-id="a9212-211">Zuerst können Sie das `abstract` -Schlüsselwort für die Teilklasse verwenden.</span><span class="sxs-lookup"><span data-stu-id="a9212-211">First, you can use the `abstract` keyword on the part class.</span></span> <span data-ttu-id="a9212-212">Abstrakte Klassen stellen nie Exporte bereit, obwohl sie geerbte Exporte für Klassen bereitstellen können, die von ihnen abgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-212">Abstract classes never provide exports, although they can provide inherited exports to classes that derive from them.</span></span>

<span data-ttu-id="a9212-213">Wenn die Klasse nicht als abstrakt festgelegt werden kann, können Sie sie mit dem `PartNotDiscoverable` -Attribut ergänzen.</span><span class="sxs-lookup"><span data-stu-id="a9212-213">If the class cannot be made abstract, you can decorate it with the `PartNotDiscoverable` attribute.</span></span> <span data-ttu-id="a9212-214">Ein mit diesem Attribut ergänzter Teil wird in keine Kataloge eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a9212-214">A part decorated with this attribute will not be included in any catalogs.</span></span> <span data-ttu-id="a9212-215">Diese Muster werden im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="a9212-215">The following example demonstrates these patterns.</span></span> <span data-ttu-id="a9212-216">`DataOne` wird vom Katalog gefunden.</span><span class="sxs-lookup"><span data-stu-id="a9212-216">`DataOne` will be discovered by the catalog.</span></span> <span data-ttu-id="a9212-217">Da `DataTwo` abstrakt ist, wird es nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="a9212-217">Since `DataTwo` is abstract, it will not be discovered.</span></span> <span data-ttu-id="a9212-218">Da `DataThree` das `PartNotDiscoverable` -Attribut verwendete, wird es nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="a9212-218">Since `DataThree` used the `PartNotDiscoverable` attribute, it will not be discovered.</span></span>

```vb
<Export()>
Public Class DataOne
    'This part will be discovered
    'as normal by the catalog.
End Class

<Export()>
Public MustInherit Class DataTwo
    'This part will not be discovered
    'by the catalog.
End Class

<PartNotDiscoverable()>
<Export()>
Public Class DataThree
    'This part will also not be discovered
    'by the catalog.
End Class
```

```csharp
[Export]
public class DataOne
{
    //This part will be discovered
    //as normal by the catalog.
}

[Export]
public abstract class DataTwo
{
    //This part will not be discovered
    //by the catalog.
}

[PartNotDiscoverable]
[Export]
public class DataThree
{
    //This part will also not be discovered
    //by the catalog.
}
```

<a name="metadata_and_metadata_views"></a>

## <a name="metadata-and-metadata-views"></a><span data-ttu-id="a9212-219">Metadaten und Metadatenansichten</span><span class="sxs-lookup"><span data-stu-id="a9212-219">Metadata and Metadata Views</span></span>

<span data-ttu-id="a9212-220">Exporte können zusätzliche Informationen über sich selbst bereitstellen, die als *Metadaten*bezeichnet wurden.</span><span class="sxs-lookup"><span data-stu-id="a9212-220">Exports can provide additional information about themselves known as *metadata*.</span></span> <span data-ttu-id="a9212-221">Metadaten können verwendet werden, um Eigenschaften des exportierten Objekts an den importierenden Teil zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="a9212-221">Metadata can be used to convey properties of the exported object to the importing part.</span></span> <span data-ttu-id="a9212-222">Der importierende Teil kann anhand dieser Daten entscheiden, welche Exporte verwendet werden sollen, oder um Informationen zu einem Export zu sammeln, ohne ihn erstellen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="a9212-222">The importing part can use this data to decide which exports to use, or to gather information about an export without having to construct it.</span></span> <span data-ttu-id="a9212-223">Aus diesem Grund muss ein Import verzögert sein, um Metadaten verwenden zu können.</span><span class="sxs-lookup"><span data-stu-id="a9212-223">For this reason, an import must be lazy to use metadata.</span></span>

<span data-ttu-id="a9212-224">Um Metadaten zu verwenden, wird in der Regel eine Schnittstelle mit der Bezeichnung *Metadatenansicht*deklariert, durch die deklariert wird, welche Metadaten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a9212-224">To use metadata, you typically declare an interface known as a *metadata view*, which declares what metadata will be available.</span></span> <span data-ttu-id="a9212-225">Die Metadaten-Ansichtsschnittstelle darf nur über Eigenschaften verfügen, und diese Eigenschaften müssen `get` -Accessoren besitzen.</span><span class="sxs-lookup"><span data-stu-id="a9212-225">The metadata view interface must have only properties, and those properties must have `get` accessors.</span></span> <span data-ttu-id="a9212-226">Die folgende Schnittstelle ist eine beispielhafte Metadatenansicht.</span><span class="sxs-lookup"><span data-stu-id="a9212-226">The following interface is an example metadata view.</span></span>

```vb
Public Interface IPluginMetadata

    ReadOnly Property Name As String

    <DefaultValue(1)>
    ReadOnly Property Version As Integer

End Interface
```

```csharp
public interface IPluginMetadata
{
    string Name { get; }

    [DefaultValue(1)]
    int Version { get; }
}
```

<span data-ttu-id="a9212-227">Es ist auch möglich, als Metadatenansicht eine generische Auflistung ( `IDictionary<string, object>`) zu verwenden, doch dadurch gehen die Vorteile der Typüberprüfung verloren, weshalb dies vermieden werden sollte.</span><span class="sxs-lookup"><span data-stu-id="a9212-227">It is also possible to use a generic collection, `IDictionary<string, object>`, as a metadata view, but this forfeits the benefits of type checking and should be avoided.</span></span>

<span data-ttu-id="a9212-228">Normalerweise sind alle in der Metadatenansicht genannten Eigenschaften erforderlich, und alle Exporte, die nicht darüber verfügen, werden nicht als Übereinstimmung betrachtet.</span><span class="sxs-lookup"><span data-stu-id="a9212-228">Ordinarily, all of the properties named in the metadata view are required, and any exports that do not provide them will not be considered a match.</span></span> <span data-ttu-id="a9212-229">Das `DefaultValue` -Attribut gibt an, dass eine Eigenschaft optional ist.</span><span class="sxs-lookup"><span data-stu-id="a9212-229">The `DefaultValue` attribute specifies that a property is optional.</span></span> <span data-ttu-id="a9212-230">Wenn die Eigenschaft nicht eingeschlossen ist, wird ihr der als Parameter von `DefaultValue`angegebene Standardwert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a9212-230">If the property is not included, it will be assigned the default value specified as a parameter of `DefaultValue`.</span></span> <span data-ttu-id="a9212-231">Die folgenden zwei Klassen sind verschiedene mit Metadaten ergänzte Klassen.</span><span class="sxs-lookup"><span data-stu-id="a9212-231">The following are two different classes decorated with metadata.</span></span> <span data-ttu-id="a9212-232">Beide Klassen entsprechen der vorherigen Metadatenansicht.</span><span class="sxs-lookup"><span data-stu-id="a9212-232">Both of these classes would match the previous metadata view.</span></span>

```vb
<Export(GetType(IPlugin))>
<ExportMetadata("Name", "Logger")>
<ExportMetadata("Version", 4)>
Public Class MyLogger
    Implements IPlugin

End Class

'Version is not required because of the DefaultValue
<Export(GetType(IPlugin))>
<ExportMetadata("Name", "Disk Writer")>
Public Class DWriter
    Implements IPlugin

End Class
```

```csharp
[Export(typeof(IPlugin)),
    ExportMetadata("Name", "Logger"),
    ExportMetadata("Version", 4)]
public class Logger : IPlugin
{
}

[Export(typeof(IPlugin)),
    ExportMetadata("Name", "Disk Writer")]
    //Version is not required because of the DefaultValue
public class DWriter : IPlugin
{
}
```

<span data-ttu-id="a9212-233">Metadaten werden nach dem `Export` -Attribut mithilfe des `ExportMetadata` -Attributs ausgedrückt.</span><span class="sxs-lookup"><span data-stu-id="a9212-233">Metadata is expressed after the `Export` attribute by using the `ExportMetadata` attribute.</span></span> <span data-ttu-id="a9212-234">Jedes Metadatenelement besteht aus einem Name-Wert-Paar.</span><span class="sxs-lookup"><span data-stu-id="a9212-234">Each piece of metadata is composed of a name/value pair.</span></span> <span data-ttu-id="a9212-235">Der Namensteil der Metadaten muss mit dem Namen der entsprechenden Eigenschaft in der Metadatenansicht übereinstimmen, und der Wert wird der Eigenschaft zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="a9212-235">The name portion of the metadata must match the name of the appropriate property in the metadata view, and the value will be assigned to that property.</span></span>

<span data-ttu-id="a9212-236">Es handelt sich um den Importer, der die zu verwendende Metadatenansicht angibt (sofern zutreffend).</span><span class="sxs-lookup"><span data-stu-id="a9212-236">It is the importer that specifies what metadata view, if any, will be in use.</span></span> <span data-ttu-id="a9212-237">Ein Import mit Metadaten wird als verzögerter Import deklariert, wobei die Metadatenschnittstelle der zweite Typparameter für `Lazy<T,T>`ist.</span><span class="sxs-lookup"><span data-stu-id="a9212-237">An import with metadata is declared as a lazy import, with the metadata interface as the second type parameter to `Lazy<T,T>`.</span></span> <span data-ttu-id="a9212-238">Die folgende Klasse importiert den vorherigen Teil mit Metadaten.</span><span class="sxs-lookup"><span data-stu-id="a9212-238">The following class imports the previous part with metadata.</span></span>

```vb
Public Class Addin

    <Import()>
    Public Property plugin As Lazy(Of IPlugin, IPluginMetadata)
End Class
```

```csharp
public class Addin
{
    [Import]
    public Lazy<IPlugin, IPluginMetadata> plugin;
}
```

<span data-ttu-id="a9212-239">In vielen Fällen sollen Metadaten mit dem `ImportMany` -Attribut kombiniert werden, um die verfügbaren Importe zu analysieren und nur einen davon auszuwählen und zu instanziieren, oder um eine Auflistung zu filtern, um eine bestimmte Bedingung zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a9212-239">In many cases, you will want to combine metadata with the `ImportMany` attribute, in order to parse through the available imports and choose and instantiate only one, or filter a collection to match a certain condition.</span></span> <span data-ttu-id="a9212-240">Die folgende Klasse instanziiert nur `IPlugin` -Objekte, die über den `Name` -Wert "Logger" verfügen.</span><span class="sxs-lookup"><span data-stu-id="a9212-240">The following class instantiates only `IPlugin` objects that have the `Name` value "Logger".</span></span>

```vb
Public Class User

    <ImportMany()>
    Public Property plugins As IEnumerable(Of Lazy(Of IPlugin, IPluginMetadata))

    Public Function InstantiateLogger() As IPlugin

        Dim logger As IPlugin
        logger = Nothing

        For Each Plugin As Lazy(Of IPlugin, IPluginMetadata) In plugins
            If Plugin.Metadata.Name = "Logger" Then
                logger = Plugin.Value
            End If
        Next
        Return logger
    End Function

End Class
```

```csharp
public class User
{
    [ImportMany]
    public IEnumerable<Lazy<IPlugin, IPluginMetadata>> plugins;

    public IPlugin InstantiateLogger()
    {
        IPlugin logger = null;

        foreach (Lazy<IPlugin, IPluginMetadata> plugin in plugins)
        {
            if (plugin.Metadata.Name == "Logger")
                logger = plugin.Value;
        }
        return logger;
    }
}
```

<a name="import_and_export_inheritance"></a>

## <a name="import-and-export-inheritance"></a><span data-ttu-id="a9212-241">Importieren und Exportieren von Vererbung</span><span class="sxs-lookup"><span data-stu-id="a9212-241">Import and Export Inheritance</span></span>

<span data-ttu-id="a9212-242">Wenn eine Klasse von einem Teil erbt, wird diese Klasse möglicherweise ebenfalls ein Teil.</span><span class="sxs-lookup"><span data-stu-id="a9212-242">If a class inherits from a part, that class may also become a part.</span></span> <span data-ttu-id="a9212-243">Importe werden immer von Unterklassen geerbt.</span><span class="sxs-lookup"><span data-stu-id="a9212-243">Imports are always inherited by subclasses.</span></span> <span data-ttu-id="a9212-244">Daher ist eine Unterklasse eines Teils immer ein Teil, und zwar mit den gleichen Importen wie die übergeordnete Klasse.</span><span class="sxs-lookup"><span data-stu-id="a9212-244">Therefore, a subclass of a part will always be a part, with the same imports as its parent class.</span></span>

<span data-ttu-id="a9212-245">Mit dem `Export` -Attribut deklarierte Exporte werden nicht von Unterklassen geerbt.</span><span class="sxs-lookup"><span data-stu-id="a9212-245">Exports declared by using the `Export` attribute are not inherited by subclasses.</span></span> <span data-ttu-id="a9212-246">Ein Teil kann sich jedoch selbst mit dem `InheritedExport` -Attribut exportieren.</span><span class="sxs-lookup"><span data-stu-id="a9212-246">However, a part can export itself by using the `InheritedExport` attribute.</span></span> <span data-ttu-id="a9212-247">Unterklassen des Teils erben den gleichen Export und stellen ihn bereit, einschließlich des Vertragsnamens und des Vertragstyps.</span><span class="sxs-lookup"><span data-stu-id="a9212-247">Subclasses of the part will inherit and provide the same export, including contract name and contract type.</span></span> <span data-ttu-id="a9212-248">Im Gegensatz zu einem `Export` -Attribut kann `InheritedExport` nur auf Klassen- und nicht auf Memberebene übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-248">Unlike an `Export` attribute, `InheritedExport` can be applied only at the class level, and not at the member level.</span></span> <span data-ttu-id="a9212-249">Daher können Exporte auf Memberebene nie geerbt werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-249">Therefore, member-level exports can never be inherited.</span></span>

<span data-ttu-id="a9212-250">Die folgenden vier Klassen veranschaulichen die Prinzipien des Importierens und Exportierens von Vererbung.</span><span class="sxs-lookup"><span data-stu-id="a9212-250">The following four classes demonstrate the principles of import and export inheritance.</span></span> <span data-ttu-id="a9212-251">`NumTwo` erbt von `NumOne`, sodass `NumTwo``IMyData` importiert.</span><span class="sxs-lookup"><span data-stu-id="a9212-251">`NumTwo` inherits from `NumOne`, so `NumTwo` will import `IMyData`.</span></span> <span data-ttu-id="a9212-252">Gewöhnliche Exporte werden nicht geerbt, sodass `NumTwo` keine Daten exportiert.</span><span class="sxs-lookup"><span data-stu-id="a9212-252">Ordinary exports are not inherited, so `NumTwo` will not export anything.</span></span> <span data-ttu-id="a9212-253">`NumFour` erbt von `NumThree`.</span><span class="sxs-lookup"><span data-stu-id="a9212-253">`NumFour` inherits from `NumThree`.</span></span> <span data-ttu-id="a9212-254">Da `NumThree``InheritedExport` verwendete, besitzt `NumFour` einen Export mit dem Vertragstyp `NumThree`.</span><span class="sxs-lookup"><span data-stu-id="a9212-254">Because `NumThree` used `InheritedExport`, `NumFour` has one export with contract type `NumThree`.</span></span> <span data-ttu-id="a9212-255">Exporte auf Memberebene werden nie geerbt, sodass `IMyData` nicht exportiert wird.</span><span class="sxs-lookup"><span data-stu-id="a9212-255">Member-level exports are never inherited, so `IMyData` is not exported.</span></span>

```vb
<Export()>
Public Class NumOne
    <Import()>
    Public Property MyData As IMyData
End Class

Public Class NumTwo
    Inherits NumOne

    'Imports are always inherited, so NumTwo will
    'Import IMyData

    'Ordinary exports are not inherited, so
    'NumTwo will NOT export anything.  As a result it
    'will not be discovered by the catalog!

End Class

<InheritedExport()>
Public Class NumThree

    <Export()>
    Public Property MyData As IMyData

    'This part provides two exports, one of
    'contract type NumThree, and one of
    'contract type IMyData.

End Class

Public Class NumFour
    Inherits NumThree

    'Because NumThree used InheritedExport,
    'this part has one export with contract
    'type NumThree.

    'Member-level exports are never inherited,
    'so IMyData is not exported.

End Class
```

```csharp
[Export]
public class NumOne
{
    [Import]
    public IMyData MyData { get; set; }
}

public class NumTwo : NumOne
{
    //Imports are always inherited, so NumTwo will
    //import IMyData.

    //Ordinary exports are not inherited, so
    //NumTwo will NOT export anything. As a result it
    //will not be discovered by the catalog!
}

[InheritedExport]
public class NumThree
{
    [Export]
    Public IMyData MyData { get; set; }

    //This part provides two exports, one of
    //contract type NumThree, and one of
    //contract type IMyData.
}

public class NumFour : NumThree
{
    //Because NumThree used InheritedExport,
    //this part has one export with contract
    //type NumThree.

    //Member-level exports are never inherited,
    //so IMyData is not exported.
}
```

<span data-ttu-id="a9212-256">Wenn Metadaten einem `InheritedExport` -Attribut zugeordnet sind, werden diese Metadaten ebenfalls geerbt.</span><span class="sxs-lookup"><span data-stu-id="a9212-256">If there is metadata associated with an `InheritedExport` attribute, that metadata will also be inherited.</span></span> <span data-ttu-id="a9212-257">(Weitere Informationen finden Sie im Abschnitt "Metadaten und Metadatenansichten".) Geerbte Metadaten können nicht von der Unterklasse geändert werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-257">(For more information, see the earlier "Metadata and Metadata Views" section.) Inherited metadata cannot be modified by the subclass.</span></span> <span data-ttu-id="a9212-258">Allerdings kann die Unterklasse durch erneutes Deklarieren des `InheritedExport` -Attributs mit dem gleichen Vertragsnamen und Vertragstyp (jedoch mit neuen Metadaten) die geerbten Metadaten durch neue Metadaten ersetzen.</span><span class="sxs-lookup"><span data-stu-id="a9212-258">However, by re-declaring the `InheritedExport` attribute with the same contract name and contract type, but with new metadata, the subclass can replace the inherited metadata with new metadata.</span></span> <span data-ttu-id="a9212-259">Die folgende Klasse verdeutlicht dieses Prinzip.</span><span class="sxs-lookup"><span data-stu-id="a9212-259">The following class demonstrates this principle.</span></span> <span data-ttu-id="a9212-260">Der `MegaLogger` -Teil erbt von `Logger` und schließt das `InheritedExport` -Attribut ein.</span><span class="sxs-lookup"><span data-stu-id="a9212-260">The `MegaLogger` part inherits from `Logger` and includes the `InheritedExport` attribute.</span></span> <span data-ttu-id="a9212-261">Da `MegaLogger` neue Metadaten mit dem Namen "Status" erneut deklariert, erbt es nicht die Namens- und Versionsmetadaten von `Logger`.</span><span class="sxs-lookup"><span data-stu-id="a9212-261">Since `MegaLogger` re-declares new metadata named Status, it does not inherit the Name and Version metadata from `Logger`.</span></span>

```vb
<InheritedExport(GetType(IPlugin))>
<ExportMetadata("Name", "Logger")>
<ExportMetadata("Version", 4)>
Public Class Logger
    Implements IPlugin

    'Exports with contract type IPlugin
    'and metadata "Name" and "Version".
End Class

Public Class SuperLogger
    Inherits Logger

    'Exports with contract type IPlugin and
    'metadata "Name" and "Version", exactly the same
    'as the Logger class.

End Class

<InheritedExport(GetType(IPlugin))>
<ExportMetadata("Status", "Green")>
Public Class MegaLogger
    Inherits Logger

    'Exports with contract type IPlugin and
    'metadata "Status" only. Re-declaring
    'the attribute replaces all metadata.

End Class
```

```csharp
[InheritedExport(typeof(IPlugin)),
    ExportMetadata("Name", "Logger"),
    ExportMetadata("Version", 4)]
public class Logger : IPlugin
{
    //Exports with contract type IPlugin and
    //metadata "Name" and "Version".
}

public class SuperLogger : Logger
{
    //Exports with contract type IPlugin and
    //metadata "Name" and "Version", exactly the same
    //as the Logger class.
}

[InheritedExport(typeof(IPlugin)),
    ExportMetadata("Status", "Green")]
public class MegaLogger : Logger        {
    //Exports with contract type IPlugin and
    //metadata "Status" only. Re-declaring
    //the attribute replaces all metadata.
}
```

<span data-ttu-id="a9212-262">Wenn Sie das `InheritedExport` -Attribut erneut deklarieren, um Metadaten zu überschreiben, stellen Sie sicher, dass die Vertragstypen identisch sind.</span><span class="sxs-lookup"><span data-stu-id="a9212-262">When re-declaring the `InheritedExport` attribute to override metadata, make sure that the contract types are the same.</span></span> <span data-ttu-id="a9212-263">(Im vorherigen Beispiel ist `IPlugin` der Vertragstyp.) Wenn sie sich unterscheiden und nicht überschrieben werden, erstellt das zweite Attribut einen zweiten, unabhängigen Export des Teils.</span><span class="sxs-lookup"><span data-stu-id="a9212-263">(In the previous example, `IPlugin` is the contract type.) If they differ, instead of overriding, the second attribute will create a second, independent export from the part.</span></span> <span data-ttu-id="a9212-264">Im Allgemeinen bedeutet dies, dass Sie den Vertragstyp explizit angeben müssen, wenn Sie ein `InheritedExport` -Attribut überschreiben (siehe vorheriges Beispiel).</span><span class="sxs-lookup"><span data-stu-id="a9212-264">Generally, this means that you will have to explicitly specify the contract type when you override an `InheritedExport` attribute, as shown in the previous example.</span></span>

<span data-ttu-id="a9212-265">Da Schnittstellen nicht direkt instanziiert werden können, können sie im Allgemeinen nicht mit `Export` -Attributen oder `Import` -Attribut ergänzt werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-265">Since interfaces cannot be instantiated directly, they generally cannot be decorated with `Export` or `Import` attributes.</span></span> <span data-ttu-id="a9212-266">Allerdings kann eine Schnittstelle mit einem `InheritedExport` -Attribut auf der Schnittstellenebene ergänzt werden. Dieser Export wird zusammen mit allen zugeordneten Metadaten von jeder beliebigen implementierenden Klasse geerbt.</span><span class="sxs-lookup"><span data-stu-id="a9212-266">However, an interface can be decorated with an `InheritedExport` attribute at the interface level, and that export along with any associated metadata will be inherited by any implementing classes.</span></span> <span data-ttu-id="a9212-267">Die Schnittstelle selbst ist jedoch nicht als ein Teil verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a9212-267">The interface itself will not be available as a part, however.</span></span>

<a name="custom_export_attributes"></a>

## <a name="custom-export-attributes"></a><span data-ttu-id="a9212-268">Benutzerdefinierte Exportattribute</span><span class="sxs-lookup"><span data-stu-id="a9212-268">Custom Export Attributes</span></span>

<span data-ttu-id="a9212-269">Die grundlegenden Exportattribute, `Export` und `InheritedExport`, können so erweitert werden, dass sie Metadaten als Attributeigenschaften einschließen.</span><span class="sxs-lookup"><span data-stu-id="a9212-269">The basic export attributes, `Export` and `InheritedExport`, can be extended to include metadata as attribute properties.</span></span> <span data-ttu-id="a9212-270">Diese Methode ist für das Übernehmen ähnlicher Metadaten für viele Teile oder das Erstellen einer Vererbungsstruktur von Metadatenattributen hilfreich.</span><span class="sxs-lookup"><span data-stu-id="a9212-270">This technique is useful for applying similar metadata to many parts, or creating an inheritance tree of metadata attributes.</span></span>

<span data-ttu-id="a9212-271">Ein benutzerdefiniertes Attribut kann den Vertragstyp, den Vertragsnamen oder beliebige andere Metadaten angeben.</span><span class="sxs-lookup"><span data-stu-id="a9212-271">A custom attribute can specify the contract type, the contract name, or any other metadata.</span></span> <span data-ttu-id="a9212-272">Um ein benutzerdefiniertes Attribut zu definieren, muss eine Klasse, die von `ExportAttribute` (oder `InheritedExportAttribute`) erbt, mit dem `MetadataAttribute` -Attribut ergänzt werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-272">In order to define a custom attribute, a class inheriting from `ExportAttribute` (or `InheritedExportAttribute`) must be decorated with the `MetadataAttribute` attribute.</span></span> <span data-ttu-id="a9212-273">Die folgende Klasse definiert ein benutzerdefiniertes Attribut.</span><span class="sxs-lookup"><span data-stu-id="a9212-273">The following class defines a custom attribute.</span></span>

```vb
<MetadataAttribute()>
<AttributeUsage(AttributeTargets.Class, AllowMultiple:=false)>
Public Class MyAttribute
    Inherits ExportAttribute

    Public Property MyMetadata As String

    Public Sub New(ByVal myMetadata As String)
        MyBase.New(GetType(IMyAddin))

        myMetadata = myMetadata
    End Sub

End Class
```

```csharp
[MetadataAttribute]
[AttributeUsage(AttributeTargets.Class, AllowMultiple=false)]
public class MyAttribute : ExportAttribute
{
    public MyAttribute(string myMetadata)
        : base(typeof(IMyAddin))
    {
        MyMetadata = myMetadata;
    }

    public string MyMetadata { get; private set; }
}
```

<span data-ttu-id="a9212-274">Diese Klasse definiert ein benutzerdefiniertes Attribut namens `MyAttribute` mit dem Vertragstyp `IMyAddin` und einige Metadaten namens `MyMetadata`.</span><span class="sxs-lookup"><span data-stu-id="a9212-274">This class defines a custom attribute named `MyAttribute` with contract type `IMyAddin` and some metadata named `MyMetadata`.</span></span> <span data-ttu-id="a9212-275">Alle Eigenschaften in einer mit dem `MetadataAttribute` -Attribut markierten Klasse werden als Metadaten betrachtet, die im benutzerdefinierten Attribut definiert sind.</span><span class="sxs-lookup"><span data-stu-id="a9212-275">All properties in a class marked with the `MetadataAttribute` attribute are considered to be metadata defined in the custom attribute.</span></span> <span data-ttu-id="a9212-276">Die folgenden zwei Deklarationen sind gleichwertig.</span><span class="sxs-lookup"><span data-stu-id="a9212-276">The following two declarations are equivalent.</span></span>

```vb
<Export(GetType(IMyAddin))>
<ExportMetadata("MyMetadata", "theData")>
Public Property myAddin As MyAddin
```

```vb
<MyAttribute("theData")>
Public Property myAddin As MyAddin
```

```csharp
[Export(typeof(IMyAddin)),
    ExportMetadata("MyMetadata", "theData")]
public MyAddin myAddin { get; set; }
```

```csharp
[MyAttribute("theData")]
public MyAddin myAddin { get; set; }
```

<span data-ttu-id="a9212-277">In der ersten Deklaration werden der Vertragstyp und die Metadaten explizit definiert.</span><span class="sxs-lookup"><span data-stu-id="a9212-277">In the first declaration, the contract type and metadata are explicitly defined.</span></span> <span data-ttu-id="a9212-278">In der zweiten Deklaration sind der Vertragstyp und die Metadaten im benutzerdefinierten Attribut implizit.</span><span class="sxs-lookup"><span data-stu-id="a9212-278">In the second declaration, the contract type and metadata are implicit in the customized attribute.</span></span> <span data-ttu-id="a9212-279">Insbesondere in Fällen, in denen eine große Menge an identischen Metadaten für viele Teile übernommen werden muss (z. B., Autor oder Urheberrechtsinformationen), können Sie durch Verwendung eines benutzerdefinierten Attributs viel Zeit sparen und Verdoppelungen vermeiden.</span><span class="sxs-lookup"><span data-stu-id="a9212-279">Particularly in cases where a large amount of identical metadata must be applied to many parts (for example, author or copyright information), using a custom attribute can save a lot of time and duplication.</span></span> <span data-ttu-id="a9212-280">Darüber hinaus können Vererbungsstrukturen benutzerdefinierter Attribute erstellt werden, um Variationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a9212-280">Further, inheritance trees of custom attributes can be created to allow for variations.</span></span>

<span data-ttu-id="a9212-281">Sie können optionale Metadaten in einem benutzerdefinierten Attribut mithilfe des `DefaultValue` -Attributs erstellen.</span><span class="sxs-lookup"><span data-stu-id="a9212-281">To create optional metadata in a custom attribute, you can use the `DefaultValue` attribute.</span></span> <span data-ttu-id="a9212-282">Wenn dieses Attribut in einer benutzerdefinierten Attributklasse für eine Eigenschaft übernommen wird, wird angegeben, dass die ergänzte Eigenschaft optional ist und nicht von einem Exporttool angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="a9212-282">When this attribute is applied to a property in a custom attribute class, it specifies that the decorated property is optional and does not have to be supplied by an exporter.</span></span> <span data-ttu-id="a9212-283">Wenn kein Wert für die Eigenschaft bereitgestellt wird, wird ihm der Standardwert für den Eigenschaftentyp zugewiesen (normalerweise `null`, `false`oder 0.)</span><span class="sxs-lookup"><span data-stu-id="a9212-283">If a value for the property is not supplied, it will be assigned the default value for its property type (usually `null`, `false`, or 0.)</span></span>

<a name="creation_policies"></a>

## <a name="creation-policies"></a><span data-ttu-id="a9212-284">Erstellungsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="a9212-284">Creation Policies</span></span>

<span data-ttu-id="a9212-285">Wenn ein Teil einen Import angibt und eine Komposition ausgeführt wird, versucht der Kompositionscontainer einen entsprechenden Export zu finden.</span><span class="sxs-lookup"><span data-stu-id="a9212-285">When a part specifies an import and composition is performed, the composition container attempts to find a matching export.</span></span> <span data-ttu-id="a9212-286">Wenn der Import einem Export zugeordnet werden kann, wird der importierende Member auf eine Instanz des exportierten Objekts festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a9212-286">If it matches the import with an export successfully, the importing member is set to an instance of the exported object.</span></span> <span data-ttu-id="a9212-287">Der Ort, von dem die Instanz stammt, wird durch die *Erstellungsrichtlinie*des exportierenden Teils bestimmt.</span><span class="sxs-lookup"><span data-stu-id="a9212-287">Where this instance comes from is controlled by the exporting part's *creation policy*.</span></span>

<span data-ttu-id="a9212-288">Die zwei möglichen Erstellungsrichtlinien sind *freigegeben* und *nicht freigegeben*.</span><span class="sxs-lookup"><span data-stu-id="a9212-288">The two possible creation policies are *shared* and *non-shared*.</span></span> <span data-ttu-id="a9212-289">Ein Teil mit der Erstellungsrichtlinie "Freigegeben" wird zwischen jedem Import im Container für einen Teil mit diesem Vertrag freigegeben.</span><span class="sxs-lookup"><span data-stu-id="a9212-289">A part with a creation policy of shared will be shared between every import in the container for a part with that contract.</span></span> <span data-ttu-id="a9212-290">Wenn die Kompositions-Engine eine Übereinstimmung findet und eine importierende Eigenschaft festlegen muss, instanziiert sie nur dann eine neue Kopie des Teils, wenn noch keine vorhanden ist; andernfalls wird die vorhandene Kopie angegeben.</span><span class="sxs-lookup"><span data-stu-id="a9212-290">When the composition engine finds a match and has to set an importing property, it will instantiate a new copy of the part only if one does not already exist; otherwise, it will supply the existing copy.</span></span> <span data-ttu-id="a9212-291">Dies bedeutet, dass viele Objekte möglicherweise Verweise auf den gleichen Teil besitzen.</span><span class="sxs-lookup"><span data-stu-id="a9212-291">This means that many objects may have references to the same part.</span></span> <span data-ttu-id="a9212-292">Für solche Teile sollte nicht der interne Zustand verwendet werden, der an vielen Stellen geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="a9212-292">Such parts should not rely on internal state that might be changed from many places.</span></span> <span data-ttu-id="a9212-293">Diese Richtlinie ist für statische Teile, Teile, die Dienste bereitstellen, und Teile, die viel Arbeitsspeicher oder andere Ressourcen belegen, geeignet.</span><span class="sxs-lookup"><span data-stu-id="a9212-293">This policy is appropriate for static parts, parts that provide services, and parts that consume a lot of memory or other resources.</span></span>

<span data-ttu-id="a9212-294">Ein Teil mit der Erstellungsrichtlinie "Nicht freigegeben" wird bei jedem Auffinden eines übereinstimmenden Imports für einen der Exporte erstellt.</span><span class="sxs-lookup"><span data-stu-id="a9212-294">A part with the creation policy of non-shared will be created every time a matching import for one of its exports is found.</span></span> <span data-ttu-id="a9212-295">Eine neue Kopie wird daher für jeden Import im Container instanziiert, der einem der exportierten Verträge des Teils entspricht.</span><span class="sxs-lookup"><span data-stu-id="a9212-295">A new copy will therefore be instantiated for every import in the container that matches one of the part's exported contracts.</span></span> <span data-ttu-id="a9212-296">Der interne Zustand dieser Kopien wird nicht freigegeben.</span><span class="sxs-lookup"><span data-stu-id="a9212-296">The internal state of these copies will not be shared.</span></span> <span data-ttu-id="a9212-297">Diese Richtlinie ist geeignet für Teile, bei denen jeder Import einen eigenen internen Zustand benötigt.</span><span class="sxs-lookup"><span data-stu-id="a9212-297">This policy is appropriate for parts where each import requires its own internal state.</span></span>

<span data-ttu-id="a9212-298">Sowohl der Import als auch der Export können die Erstellungsrichtlinie eines Teils mit den Werten `Shared`, `NonShared`oder `Any`angeben.</span><span class="sxs-lookup"><span data-stu-id="a9212-298">Both the import and the export can specify the creation policy of a part, from among the values `Shared`, `NonShared`, or `Any`.</span></span> <span data-ttu-id="a9212-299">Die Standardeinstellung ist sowohl für Importe als auch Exporte `Any` .</span><span class="sxs-lookup"><span data-stu-id="a9212-299">The default is `Any` for both imports and exports.</span></span> <span data-ttu-id="a9212-300">Ein Export, für den `Shared` oder `NonShared` angegeben wird, stimmt nur mit einem Import überein, für den die gleichen Werte oder `Any`angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-300">An export that specifies `Shared` or `NonShared` will only match an import that specifies the same, or that specifies `Any`.</span></span> <span data-ttu-id="a9212-301">Entsprechend stimmt ein Import, für den `Shared` oder `NonShared` angegeben wird, nur mit einem Export überein, für den die gleichen Werte oder `Any`angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-301">Similarly, an import that specifies `Shared` or `NonShared` will only match an export that specifies the same, or that specifies `Any`.</span></span> <span data-ttu-id="a9212-302">Importe und Exporte mit nicht kompatiblen Erstellungsrichtlinien werden nicht als Übereinstimmung betrachtet, ebenso wie bei einem Import und Export, deren Vertragsnamen oder Vertragstypen nicht übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="a9212-302">Imports and exports with incompatible creation policies are not considered a match, in the same way as an import and export whose contract name or contract type are not a match.</span></span> <span data-ttu-id="a9212-303">Wenn sowohl für Importe als auch Exporte `Any`angegeben wird, oder wenn keine Erstellungsrichtlinie angegeben wird und standardmäßig `Any`festgelegt wird, wird für die Erstellungsrichtlinie als Standardeinstellung "Freigegeben" festgelegt.</span><span class="sxs-lookup"><span data-stu-id="a9212-303">If both import and export specify `Any`, or do not specify a creation policy and default to `Any`, the creation policy will default to shared.</span></span>

<span data-ttu-id="a9212-304">Das folgende Beispiel zeigt sowohl Importe als auch Exporte, die Erstellungsrichtlinien angeben.</span><span class="sxs-lookup"><span data-stu-id="a9212-304">The following example shows both imports and exports specifying creation policies.</span></span> <span data-ttu-id="a9212-305">`PartOne` gibt keine Erstellungsrichtlinie an, weshalb der Standard `Any`ist.</span><span class="sxs-lookup"><span data-stu-id="a9212-305">`PartOne` does not specify a creation policy, so the default is `Any`.</span></span> <span data-ttu-id="a9212-306">`PartTwo` gibt keine Erstellungsrichtlinie an, weshalb der Standard `Any`ist.</span><span class="sxs-lookup"><span data-stu-id="a9212-306">`PartTwo` does not specify a creation policy, so the default is `Any`.</span></span> <span data-ttu-id="a9212-307">Da sowohl Import als auch Export standardmäßig auf `Any`festgelegt werden, wird `PartOne` freigegeben.</span><span class="sxs-lookup"><span data-stu-id="a9212-307">Since both import and export default to `Any`, `PartOne` will be shared.</span></span> <span data-ttu-id="a9212-308">`PartThree` gibt eine `Shared` -Erstellungsrichtlinie an, weshalb `PartTwo` und `PartThree` gemeinsam die gleiche Kopie von `PartOne`nutzen.</span><span class="sxs-lookup"><span data-stu-id="a9212-308">`PartThree` specifies a `Shared` creation policy, so `PartTwo` and `PartThree` will share the same copy of `PartOne`.</span></span> <span data-ttu-id="a9212-309">`PartFour` gibt eine `NonShared` -Erstellungsrichtlinie an, weshalb `PartFour` in `PartFive`nicht freigegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a9212-309">`PartFour` specifies a `NonShared` creation policy, so `PartFour` will be non-shared in `PartFive`.</span></span> <span data-ttu-id="a9212-310">`PartSix` gibt eine `NonShared` -Erstellungsrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="a9212-310">`PartSix` specifies a `NonShared` creation policy.</span></span> <span data-ttu-id="a9212-311">`PartFive` und `PartSix` erhalten jeweils separate Kopien von `PartFour`.</span><span class="sxs-lookup"><span data-stu-id="a9212-311">`PartFive` and `PartSix` will each receive separate copies of `PartFour`.</span></span> <span data-ttu-id="a9212-312">`PartSeven` gibt eine `Shared` -Erstellungsrichtlinie an.</span><span class="sxs-lookup"><span data-stu-id="a9212-312">`PartSeven` specifies a `Shared` creation policy.</span></span> <span data-ttu-id="a9212-313">Da es keinen exportierten `PartFour` mit der Erstellungsrichtlinie `Shared`gibt, gibt es für den `PartSeven` -Import keine Entsprechung, und er wird nicht ausgefüllt.</span><span class="sxs-lookup"><span data-stu-id="a9212-313">Because there is no exported `PartFour` with a creation policy of `Shared`, the `PartSeven` import does not match anything and will not be filled.</span></span>

```vb
<Export()>
Public Class PartOne
    'The default creation policy for an export is Any.
End Class

Public Class PartTwo

    <Import()>
    Public Property partOne As PartOne

    'The default creation policy for an import is Any.
    'If both policies are Any, the part will be shared.

End Class

Public Class PartThree

    <Import(RequiredCreationPolicy:=CreationPolicy.Shared)>
    Public Property partOne As PartOne

    'The Shared creation policy is explicitly specified.
    'PartTwo and PartThree will receive references to the
    'SAME copy of PartOne.

End Class

<Export()>
<PartCreationPolicy(CreationPolicy.NonShared)>
Public Class PartFour
    'The NonShared creation policy is explicitly specified.
End Class

Public Class PartFive

    <Import()>
    Public Property partFour As PartFour

    'The default creation policy for an import is Any.
    'Since the export's creation policy was explicitly
    'defined, the creation policy for this property will
    'be non-shared.

End Class

Public Class PartSix

    <Import(RequiredCreationPolicy:=CreationPolicy.NonShared)>
    Public Property partFour As PartFour

    'Both import and export specify matching creation
    'policies.  PartFive and PartSix will each receive
    'SEPARATE copies of PartFour, each with its own
    'internal state.

End Class

Public Class PartSeven

    <Import(RequiredCreationPolicy:=CreationPolicy.Shared)>
    Public Property partFour As PartFour

    'A creation policy mismatch.  Because there is no
    'exported PartFour with a creation policy of Shared,
    'this import does not match anything and will not be
    'filled.

End Class
```

```csharp
[Export]
public class PartOne
{
    //The default creation policy for an export is Any.
}

public class PartTwo
{
    [Import]
    public PartOne partOne { get; set; }

    //The default creation policy for an import is Any.
    //If both policies are Any, the part will be shared.
}

public class PartThree
{
    [Import(RequiredCreationPolicy = CreationPolicy.Shared)]
    public PartOne partOne { get; set; }

    //The Shared creation policy is explicitly specified.
    //PartTwo and PartThree will receive references to the
    //SAME copy of PartOne.
}

[Export]
[PartCreationPolicy(CreationPolicy.NonShared)]
public class PartFour
{
    //The NonShared creation policy is explicitly specified.
}

public class PartFive
{
    [Import]
    public PartFour partFour { get; set; }

    //The default creation policy for an import is Any.
    //Since the export's creation policy was explicitly
    //defined, the creation policy for this property will
    //be non-shared.
}

public class PartSix
{
    [Import(RequiredCreationPolicy = CreationPolicy.NonShared)]
    public PartFour partFour { get; set; }

    //Both import and export specify matching creation
    //policies.  PartFive and PartSix will each receive
    //SEPARATE copies of PartFour, each with its own
    //internal state.
}

public class PartSeven
{
    [Import(RequiredCreationPolicy = CreationPolicy.Shared)]
    public PartFour partFour { get; set; }

    //A creation policy mismatch.  Because there is no
    //exported PartFour with a creation policy of Shared,
    //this import does not match anything and will not be
    //filled.
}
```

<a name="life_cycle_and_disposing"></a>

## <a name="life-cycle-and-disposing"></a><span data-ttu-id="a9212-314">Lebenszyklus und Freigabe</span><span class="sxs-lookup"><span data-stu-id="a9212-314">Life Cycle and Disposing</span></span>

<span data-ttu-id="a9212-315">Da Teile im Kompositionscontainer gehostet werden, kann ihr Lebenszyklus komplexer als gewöhnliche Objekte sein.</span><span class="sxs-lookup"><span data-stu-id="a9212-315">Because parts are hosted in the composition container, their life cycle can be more complex than ordinary objects.</span></span> <span data-ttu-id="a9212-316">Teile können zwei wichtige lebenszyklusbezogene Schnittstellen implementieren: `IDisposable` und `IPartImportsSatisfiedNotification`.</span><span class="sxs-lookup"><span data-stu-id="a9212-316">Parts can implement two important life cycle-related interfaces: `IDisposable` and `IPartImportsSatisfiedNotification`.</span></span>

<span data-ttu-id="a9212-317">Teile, für die beim Herunterfahren bestimmte Schritte ausgeführt werden oder die Ressourcen freigeben müssen, sollten wie gewöhnlich für .NET Framework-Objekte `IDisposable`implementieren.</span><span class="sxs-lookup"><span data-stu-id="a9212-317">Parts that require work to be performed at shut down or that need to release resources should implement `IDisposable`, as usual for .NET Framework objects.</span></span> <span data-ttu-id="a9212-318">Da jedoch der Container Verweise auf Teile erstellt und verwaltet, sollte nur der Container, der einen Teil besitzt, die `Dispose` -Methode dafür aufrufen.</span><span class="sxs-lookup"><span data-stu-id="a9212-318">However, since the container creates and maintains references to parts, only the container that owns a part should call the `Dispose` method on it.</span></span> <span data-ttu-id="a9212-319">Der Container selbst implementiert `IDisposable`, und er ruft als Teil der Bereinigung in `Dispose` für alle Teile, die er besitzt, `Dispose` auf.</span><span class="sxs-lookup"><span data-stu-id="a9212-319">The container itself implements `IDisposable`, and as portion of its cleanup in `Dispose` it will call `Dispose` on all the parts that it owns.</span></span> <span data-ttu-id="a9212-320">Aus diesem Grund sollten Sie immer den Kompositionscontainer freigeben, wenn er und Teile, die er besitzt, nicht mehr benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-320">For this reason, you should always dispose the composition container when it and any parts it owns are no longer needed.</span></span>

<span data-ttu-id="a9212-321">Für langlebige Kompositionscontainer, kann der Speicherbedarf von Teilen mit der Erstellungsrichtlinie "Nicht freigegeben" ein Problem darstellen.</span><span class="sxs-lookup"><span data-stu-id="a9212-321">For long-lived composition containers, memory consumption by parts with a creation policy of non-shared can become a problem.</span></span> <span data-ttu-id="a9212-322">Diese nicht freigegebenen Teile können mehrmals erstellt werden und werden erst freigegeben, wenn der Container selbst freigegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="a9212-322">These non-shared parts can be created multiple times and will not be disposed until the container itself is disposed.</span></span> <span data-ttu-id="a9212-323">Zu diesem Zweck verfügt der Container über die `ReleaseExport` -Methode.</span><span class="sxs-lookup"><span data-stu-id="a9212-323">To deal with this, the container provides the `ReleaseExport` method.</span></span> <span data-ttu-id="a9212-324">Durch Aufrufen dieser Methode für einen nicht freigegebenen Export wird der Export aus dem Kompositionscontainer entfernt und freigegeben.</span><span class="sxs-lookup"><span data-stu-id="a9212-324">Calling this method on a non-shared export removes that export from the composition container and disposes it.</span></span> <span data-ttu-id="a9212-325">Teile, die nur vom entfernten Export usw. weiter unten in der Struktur verwendet werden, werden ebenfalls entfernt und freigegeben.</span><span class="sxs-lookup"><span data-stu-id="a9212-325">Parts that are used only by the removed export, and so on down the tree, are also removed and disposed.</span></span> <span data-ttu-id="a9212-326">Dadurch können Ressourcen ohne Freigabe des Kompositionscontainers selbst freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="a9212-326">In this way, resources can be reclaimed without disposing the composition container itself.</span></span>

<span data-ttu-id="a9212-327">`IPartImportsSatisfiedNotification` enthält eine Methode mit dem Namen `OnImportsSatisfied`.</span><span class="sxs-lookup"><span data-stu-id="a9212-327">`IPartImportsSatisfiedNotification` contains one method named `OnImportsSatisfied`.</span></span> <span data-ttu-id="a9212-328">Diese Methode wird vom Kompositionscontainer für alle Teile aufgerufen, die die Schnittstelle implementieren, wenn die Komposition abgeschlossen wurde und die Importe des Teils verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a9212-328">This method is called by the composition container on any parts that implement the interface when composition has been completed and the part's imports are ready for use.</span></span> <span data-ttu-id="a9212-329">Teile werden von der Kompositions-Engine erstellt, um die Importe anderer Teilen auszufüllen.</span><span class="sxs-lookup"><span data-stu-id="a9212-329">Parts are created by the composition engine to fill the imports of other parts.</span></span> <span data-ttu-id="a9212-330">Vor dem Festlegen der Importe eines Teils können Sie keine Initialisierung ausführen, die importierte Werte im Teilkonstruktor verwendet oder bearbeitet, sofern diese Werte nicht mithilfe des `ImportingConstructor` -Attributs als Voraussetzung angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="a9212-330">Before the imports of a part have been set, you cannot perform any initialization that relies on or manipulates imported values in the part constructor unless those values have been specified as prerequisites by using the `ImportingConstructor` attribute.</span></span> <span data-ttu-id="a9212-331">Dies ist normalerweise die bevorzugte Methode, doch in einigen Fällen ist die Konstruktoreinfügung möglicherweise nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a9212-331">This is normally the preferred method, but in some cases, constructor injection may not be available.</span></span> <span data-ttu-id="a9212-332">In diesen Fällen kann die Initialisierung in `OnImportsSatisfied`ausgeführt werden, und der Teil sollte `IPartImportsSatisfiedNotification`implementieren.</span><span class="sxs-lookup"><span data-stu-id="a9212-332">In those cases, initialization can be performed in `OnImportsSatisfied`, and the part should implement `IPartImportsSatisfiedNotification`.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9212-333">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a9212-333">See also</span></span>

- [<span data-ttu-id="a9212-334">Channel 9-Video: Öffnen Ihrer Anwendungen mit dem Managed Extensibility Framework</span><span class="sxs-lookup"><span data-stu-id="a9212-334">Channel 9 Video: Open Up Your Applications with the Managed Extensibility Framework</span></span>](https://channel9.msdn.com/events/TechEd/NorthAmerica/2009/DTL328)
- [<span data-ttu-id="a9212-335">Channel 9-Video: Managed Extensibility Framework (MEF) 2.0</span><span class="sxs-lookup"><span data-stu-id="a9212-335">Channel 9 Video: Managed Extensibility Framework (MEF) 2.0</span></span>](https://channel9.msdn.com/posts/NET-45-Oleg-Lvovitch-and-Kevin-Ransom-Managed-Extensibility-Framework-MEF-20)
