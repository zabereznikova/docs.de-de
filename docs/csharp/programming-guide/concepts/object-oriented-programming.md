---
title: Objektorientiertes Programmieren (C#)
ms.date: 02/08/2020
ms.assetid: 89574786-65ef-4335-88bc-fbacd094f183
ms.openlocfilehash: 01d6f55bf0752f902f351675c4596abbb8ac85c2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "77627889"
---
# <a name="object-oriented-programming-c"></a>Objektorientiertes Programmieren (C#)

C# bietet vollständige Unterstützung für objektorientierte Programmierung, einschließlich Kapselung, Vererbung und Polymorphie.

- *Kapselung* bedeutet, dass eine Gruppe verwandter Eigenschaften, Methoden sowie anderer Member als eine Einheit bzw. ein Objekt behandelt wird.
- *Vererbung* beschreibt die Fähigkeit, neue Klassen basierend auf einer vorhandenen Klasse zu erstellen.
- *Polymorphismus* bedeutet, dass Sie mehrere Klassen untereinander austauschen können, obwohl jede Klasse dieselben Eigenschaften oder Methoden auf unterschiedliche Art und Weise implementiert.

## <a name="classes-and-objects"></a>Klassen und Objekte

Die Begriffe *Klasse* und *Objekt* beschreiben jeweils den *Typ* von Objekten und die *Instanzen* von Klassen. Das Erstellen eines Objekts wird daher als *Instanziierung* bezeichnet. Um auf den Vergleich mit Bauplänen zurückzukommen: Eine Klasse ist ein Bauplan, und ein Objekt ist ein anhand dieses Bauplans errichtetes Gebäude.

So definieren Sie eine Klasse

```csharp
class SampleClass
{
}
```

C# stellt auch Typen namens *Strukturen* bereit, die nützlich sind, wenn Sie keine Unterstützung für Vererbungen oder Polymorphie benötigen.

So definieren Sie eine Struktur

```csharp
struct SampleStruct
{
}
```

Weitere Informationen finden Sie in den Artikeln zu den Schlüsselwörtern [Klasse](../../language-reference/keywords/class.md) und [Struktur](../../language-reference/builtin-types/struct.md).

### <a name="class-members"></a>Klassenmember

Jede Klasse kann über andere *Klassenmember* verfügen. Diese enthalten Eigenschaften, die Klassendaten beschreiben, Methoden, die Klassenverhalten definieren sowie Ereignisse, die die Kommunikation zwischen verschiedenen Klassen und Objekten bereitstellen.

#### <a name="properties-and-fields"></a>Eigenschaften und Felder

Felder und Eigenschaften stellen die in einem Objekt enthaltenen Informationen dar. Felder sind wie Variablen, sie können direkt gelesen oder festgelegt werden und unterliegen anwendbaren Zugriffsmodifizierern.

So definieren Sie ein Feld, auf das innerhalb von Instanzen der Klasse zugegriffen werden kann:

```csharp
public class SampleClass
{
    string sampleField;
}
```

Eigenschaften verfügen über `get`- und `set`-Zugriffsmethoden, die eine bessere Kontrolle über das Festlegen oder Abrufen von Werten ermöglichen.

Mit C# können Sie ein privates Feld erstellen, um den Eigenschaftswert zu speichern, oder Sie können automatisch implementierte Eigenschaften verwenden, die dieses Feld automatisch im Hintergrund erstellen und die grundlegende Logik für die Eigenschaftenprozeduren bereitstellen.

So definieren Sie eine automatisch implementierte Eigenschaft

```csharp
class SampleClass
{
    public int SampleProperty { get; set; }
}
```

Verwenden Sie den folgenden Code, wenn Sie zusätzliche Lese- und Schreibvorgänge für den Eigenschaftswert ausführen müssen, um ein Feld zum Speichern des Eigenschaftswerts zu definieren und die grundlegende Logik zum Speichern und Abrufen bereitzustellen:

```csharp
class SampleClass
{
    private int _sample;
    public int Sample
    {
        // Return the value stored in a field.
        get => _sample;
        // Store the value in the field.
        set =>  _sample = value;
    }
}
```

Die meisten Eigenschaften verfügen über Methoden oder Prozeduren zum Festlegen und Abrufen des Eigenschaftswerts. Sie können jedoch schreib- oder lesegeschützte Eigenschaften erstellen, um zu verhindern, dass die Eigenschaften gelesen oder geändert werden. In C# muss die `get`-Eigenschaftenmethode oder die `set`-Eigenschaftenmethode nicht angegeben werden. Automatisch implementierte Eigenschaften können jedoch nicht lesegeschützt sein. Schreibgeschützte automatisch implementierte Eigenschaften können in Konstruktoren der enthaltenden Klasse festgelegt werden.

Weitere Informationen finden Sie unter:

- [get](../../language-reference/keywords/get.md)

- [set](../../language-reference/keywords/set.md)

#### <a name="methods"></a>Methoden

Eine *Methode* ist eine Aktion, die von einem Objekt ausgeführt werden kann.

So definieren Sie eine Methode einer Klasse:

```csharp
class SampleClass
{
    public int sampleMethod(string sampleParam)
    {
        // Insert code here
    }
}
```

Eine Klasse kann über mehrere Implementierungen oder *Überladungen* der gleichen Methode verfügen, die sich in der Anzahl der Parameter oder Parametertypen unterscheiden.

So überladen Sie eine Methode

```csharp
public int sampleMethod(string sampleParam) {}
public int sampleMethod(int sampleParam) {}
```

In den meisten Fällen deklarieren Sie eine Methode innerhalb einer Klassendefinition. Auch C# unterstützt jedoch *Erweiterungsmethoden*, mit denen Sie einer vorhandenen Klasse außerhalb der eigentlichen Klassendefinition Methoden hinzuzufügen können.

Weitere Informationen finden Sie unter:

- [Methoden](../classes-and-structs/methods.md)
- [Erweiterungsmethoden](../classes-and-structs/extension-methods.md)

#### <a name="constructors"></a>Konstruktoren

Konstruktoren sind Klassenmethoden, die automatisch ausgeführt werden, wenn ein Objekt eines bestimmten Typs erstellt wird. Konstruktoren initialisieren normalerweise die Datenmember des neuen Objekts. Konstruktoren können nur einmal während der Erstellung der Klasse ausgeführt werden. Weiterhin wird der Code im Konstruktor immer vor jedem anderen Code in einer Klasse ausgeführt. Sie können jedoch mehrere Konstruktorüberladungen auf die gleiche Weise wie für jede andere Methode erstellen.

So definieren Sie einen Konstruktor für eine Klasse:

```csharp
public class SampleClass
{
    public SampleClass()
    {
        // Add code here
    }
}
```

Weitere Informationen finden Sie unter [Konstruktoren](../classes-and-structs/constructors.md).

#### <a name="finalizers"></a>Finalizer

Finalizer werden zur Zerstörung von Klasseninstanzen verwendet. In .NET Framework verwaltet die Garbage Collection die Speicherbelegung automatisch und gibt Arbeitsspeicher für die verwalteten Objekte in der Anwendung frei. Möglicherweise sind jedoch noch Finalizer erforderlich, um alle nicht verwalteten Ressourcen zu bereinigen, die von der Anwendung erstellt werden. Es kann nur einen Finalizer für eine Klasse geben.

Weitere Informationen zu Finalizern und der Garbage Collection in .NET Framework finden Sie unter [Garbage Collection](../../../standard/garbage-collection/index.md).

#### <a name="events"></a>Ereignisse

Ereignisse aktivieren eine Klasse oder ein Objekt, um Informationen über Aktionen von Interesse an andere Klassen oder Objekte zu übermitteln. Die Klasse, die das Ereignis sendet (oder auslöst), wird als *Herausgeber* bezeichnet, und die Klassen, die das Ereignis empfangen (oder verarbeiten), werden als *Abonnenten* bezeichnet. Weitere Informationen zu Ereignissen sowie zu ihrer Auslösung und Behandlung finden Sie unter [Ereignisse](../../../standard/events/index.md).

- Verwenden Sie das Schlüsselwort [event](../../language-reference/keywords/event.md), um ein Ereignis in einer Klasse zu deklarieren.

- Um ein Ereignis auszulösen, rufen Sie den Ereignisdelegaten auf.

- Verwenden Sie den `+=`-Operator, um ein Ereignis zu abonnieren, und verwenden Sie den `-=`-Operator, um das Abonnement eines Ereignisses zu kündigen.

#### <a name="nested-classes"></a>Geschachtelte Klassen

Eine Klasse, die in einer anderen Klasse definiert wird, wird als *geschachtelt* bezeichnet. Standardmäßig ist die geschachtelte Klasse privat.

```csharp
class Container
{
    class Nested
    {
        // Add code here.
    }
}
```

Um eine Instanz der geschachtelten Klasse zu erstellen, verwenden Sie den Namen der Containerklasse und geben einen Punkt sowie anschließend den Namen der geschachtelten Klasse ein:

```csharp
Container.Nested nestedInstance = new Container.Nested()
```

### <a name="access-modifiers-and-access-levels"></a>Zugriffsmodifizierer und Zugriffsebenen

Alle Klassen und Klassenmember können mit *Zugriffsmodifizierern* angeben, welche Zugriffsebene sie für andere Klassen bereitstellen.

Die folgenden Zugriffsmodifizierer sind verfügbar:

|C#-Modifizierer|Definition|
|------------------|----------------|
|[public](../../language-reference/keywords/public.md)|Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder einer anderen Assembly, die darauf verweist, zugegriffen werden.|
|[private](../../language-reference/keywords/private.md)|Auf den Typ oder Member kann nur von Code in der gleichen Klasse zugegriffen werden.|
|[protected](../../language-reference/keywords/protected.md)|Auf den Typ oder Member kann nur von Code in der gleichen Klasse oder in einer abgeleiteten Klasse zugegriffen werden.|
|[internal](../../language-reference/keywords/internal.md)|Auf den Typ oder Member kann von jedem Code in der gleichen Assembly zugegriffen werden, jedoch nicht von Code in einer anderen Assembly.|
|[protected internal](../../language-reference/keywords/protected-internal.md)|Auf den Typ oder Member kann von jedem Code in der gleichen Assembly oder von jeder abgeleiteten Klasse in einer anderen Assembly zugegriffen werden.|
|[private protected](../../language-reference/keywords/private-protected.md)|Auf den Typ oder Member kann nur über Code in der gleichen Klasse, in einer abgeleiteten Klasse oder innerhalb der Basisklassenassembly zugegriffen werden.|

Weitere Informationen finden Sie unter [Zugriffsmodifizierer](../classes-and-structs/access-modifiers.md).

### <a name="instantiating-classes"></a>Instanziieren von Klassen

Um ein Objekt zu erstellen, müssen Sie eine Klasse instanziieren oder eine Klasseninstanz erstellen.

```csharp
SampleClass sampleObject = new SampleClass();
```

Nachdem Sie eine Klasse instanziiert haben, können Sie den Eigenschaften und Feldern der Instanz Werte zuweisen und Klassenmethoden aufrufen.

```csharp
// Set a property value.
sampleObject.sampleProperty = "Sample String";
// Call a method.
sampleObject.sampleMethod();
```

Verwenden Sie Objektinitialisierer, um Eigenschaften im Rahmen des Klasseninstanziierungsprozesses Werte zuzuweisen:

```csharp
// Set a property value.
SampleClass sampleObject = new SampleClass
    { FirstProperty = "A", SecondProperty = "B" };
```

Weitere Informationen finden Sie unter:

- [new-Operator](../../language-reference/operators/new-operator.md)
- [Objekt- und Auflistungsinitialisierer](../classes-and-structs/object-and-collection-initializers.md)

### <a name="static-classes-and-members"></a>Statische Klassen und Member

Ein statischer Member der Klasse ist eine Eigenschaft, eine Prozedur oder ein Feld, die von allen Instanzen einer Klasse gemeinsam verwendet werden.

So definieren Sie einen statischen Member:

```csharp
static class SampleClass
{
    public static string SampleString = "Sample String";
}
```

Verwenden Sie den Namen der Klasse, ohne ein Objekt dieser Klasse zu erstellen, um auf den statischen Member zuzugreifen:

```csharp
Console.WriteLine(SampleClass.SampleString);
```

Statische Klassen in C# haben nur statische Member und können nicht instanziiert werden. Statische Member können auch nicht auf nicht statische Eigenschaften, Felder oder Methoden zugreifen.

Weitere Informationen finden Sie unter [static](../../language-reference/keywords/static.md).

### <a name="anonymous-types"></a>Anonyme Typen

Mit anonymen Typen können Objekte erstellt werden, ohne eine Klassendefinition für den Datentyp zu schreiben. Stattdessen erzeugt der Compiler eine Klasse. Die Klasse hat keinen verwendbaren Namen und enthält die von Ihnen in der Deklaration des Objekts angegebenen Eigenschaften.

So erstellen Sie eine Instanz eines anonymen Typs

```csharp
// sampleObject is an instance of a simple anonymous type.
var sampleObject =
    new { FirstProperty = "A", SecondProperty = "B" };
```

Weitere Informationen finden Sie unter: [Anonyme Typen](../classes-and-structs/anonymous-types.md).

## <a name="inheritance"></a>Vererbung

Vererbung ermöglicht die Erstellung neuer Klassen, die in anderen Klassen definiertes Verhalten wieder verwenden, erweitern und ändern. Die Klasse, deren Member vererbt werden, wird *Basisklasse* genannt, und die Klasse, die diese Member erbt, wird *abgeleitete Klasse* genannt. Alle Klassen in C# erben jedoch implizit von der Klasse <xref:System.Object>, die die .NET-Klassenhierarchie unterstützt und einfache Dienste für alle Klassen bereitstellt.

> [!NOTE]
> C# unterstützt keine mehrfache Vererbung. Sie können also nur eine Basisklasse für eine abgeleitete Klasse angeben.

So erben Sie von einer Basisklasse

```csharp
class DerivedClass:BaseClass {}
```

Standardmäßig können alle Klassen geerbt werden. Sie können jedoch angeben, dass eine Klasse nicht als Basisklasse verwendet werden darf, oder eine Klasse erstellen, die nur als Basisklasse verwendet werden kann.

So geben Sie an, dass eine Klasse nicht als Basisklasse verwendet werden kann

```csharp
public sealed class A { }
```

So geben Sie an, dass eine Klasse nur als Basisklasse verwendet und nicht instanziiert werden kann:

```csharp
public abstract class B { }
```

Weitere Informationen finden Sie unter:

- [sealed](../../language-reference/keywords/sealed.md)

- [abstract](../../language-reference/keywords/abstract.md)

### <a name="overriding-members"></a>Überschreiben von Membern

Standardmäßig erbt eine abgeleitete Klasse alle Member von ihrer Basisklasse. Wenn Sie das Verhalten des geerbten Members ändern möchten, müssen Sie diesen überschreiben. Das heißt, Sie können eine neue Implementierung der Methode, der Eigenschaft oder des Ereignisses in der abgeleiteten Klasse definieren.

Mit folgenden Modifizierern steuern Sie das Überschreiben von Eigenschaften und Methoden:

|C#-Modifizierer|Definition|
|------------------|----------------|
|[virtual](../../language-reference/keywords/virtual.md)|Ermöglicht das Überschreiben eines Klassenmembers in einer abgeleiteten Klasse.|
|[override](../../language-reference/keywords/override.md)|Überschreibt einen virtuellen (überschreibbaren) Member, der in der Basisklasse definiert wurde.|
|[abstract](../../language-reference/keywords/abstract.md)|Erfordert das Überschreiben eines Klassenmembers in der abgeleiteten Klasse.|
|[new-Modifizierer](../../language-reference/keywords/new-modifier.md)|Blendet einen von einer Basisklasse geerbten Member aus.|

## <a name="interfaces"></a>Schnittstellen

Schnittstellen definieren (wie Klassen) einen Satz von Eigenschaften, Methoden und Ereignissen. Im Gegensatz zu Klassen jedoch bieten Schnittstellen keine Implementierung. Sie werden durch Klassen implementiert und als von Klassen unabhängige Entitäten definiert. Eine Schnittstelle stellt insofern einen Vertrag dar, dass eine Klasse, die eine Schnittstelle implementiert, jeden Aspekt dieser Schnittstelle gemäß seiner Definition implementieren muss.

So definieren Sie eine Schnittstelle

```csharp
interface ISampleInterface
{
    void doSomething();
}
```

So implementieren Sie eine Schnittstelle in einer Klasse

```csharp
class SampleClass : ISampleInterface
{
    void ISampleInterface.doSomething()
    {
        // Method implementation.
    }
}
```

Weitere Informationen finden Sie im Programmierleitfaden zu [Schnittstellen](../interfaces/index.md) und der Sprachreferenz zum Schlüsselwort [Schnittstelle](../../language-reference/keywords/interface.md).

## <a name="generics"></a>Generics

Klassen, Strukturen, Schnittstellen und Methoden in .NET Framework können *Typparameter* enthalten, die Objekttypen definieren, die sie speichern oder verwenden können. Das einfachste Beispiel für Generics ist eine Auflistung, in der Sie den Typ von Objekten angeben können, die in einer Auflistung gespeichert werden sollen.

So definieren Sie eine generische Klasse

```csharp
public class SampleGeneric<T>
{
    public T Field;
}
```

So erstellen Sie eine Instanz einer generischen Klasse

```csharp
SampleGeneric<string> sampleObject = new SampleGeneric<string>();
sampleObject.Field = "Sample string";
```

Weitere Informationen finden Sie unter:

- [Generics](../../../standard/generics/index.md)

- [Generics](../generics/index.md)

## <a name="delegates"></a>Delegaten

Ein *Delegat* ist ein Typ, der eine Methodensignatur definiert. Er kann einen Verweis auf jede Methode bereitstellen, die über eine kompatible Signatur verfügt. Sie können die Methode über den Delegaten aufrufen. Delegaten werden verwendet, um Methoden als Argumente an anderen Methoden zu übergeben.

> [!NOTE]
> Ereignishandler sind nichts weiter als Methoden, die durch Delegaten aufgerufen werden. Weitere Informationen zur Ereignisbehandlung mit Delegaten finden Sie unter [Ereignisse](../../../standard/events/index.md).

So erstellen Sie einen Delegaten

```csharp
public delegate void SampleDelegate(string str);
```

So erstellen Sie einen Verweis auf eine Methode, die der vom Delegaten angegebenen Signatur entspricht:

```csharp
class SampleClass
{
    // Method that matches the SampleDelegate signature.
    public static void sampleMethod(string message)
    {
        // Add code here.
    }
    // Method that instantiates the delegate.
    void SampleDelegate()
    {
        SampleDelegate sd = sampleMethod;
        sd("Sample string");
    }
}
```

Weitere Informationen finden Sie im Programmierleitfaden zu [Delegaten](../delegates/index.md) und der Sprachreferenz zum Schlüsselwort [Delegat](../../language-reference/builtin-types/reference-types.md).

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
