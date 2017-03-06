---
title: "Ausführliche Informationen zum allgemeinen Typsystem"
description: "Ausführliche Informationen zum allgemeinen Typsystem"
keywords: .NET, .NET Core
author: stevehoag
ms.author: shoag
ms.date: 07/20/2016
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: b5482a1d-7bdc-40fe-aa45-10df930ceb5b
translationtype: Human Translation
ms.sourcegitcommit: 90fe68f7f3c4b46502b5d3770b1a2d57c6af748a
ms.openlocfilehash: 6be672acc84a76106e25b82574acad16beb4a8ac
ms.lasthandoff: 03/02/2017

---

# <a name="common-type-system-in-depth"></a>Ausführliche Informationen zum allgemeinen Typsystem

Dieses Thema enthält die folgenden Abschnitte, die das allgemeine Typsystem ausführlich behandeln:

* [Typen in .NET](#types-in-net)

* [Typdefinitionen](#type-definitions)

* [Typmember](#type-members)

* [Eigenschaften von Typmembern](#characteristics-of-type-members)


## <a name="types-in-net"></a>Typen in .NET

Alle Typen in .NET sind entweder Werttypen oder Verweistypen. 

Werttypen sind Datentypen, deren Objekte durch den tatsächlichen Wert des Objekts dargestellt werden. Wenn einer Variablen eine Instanz eines Werttyps zugewiesen wird, wird dieser Variablen eine neue Kopie des Werts übergeben.

Referenztypen sind Datentypen, deren Objekte durch einen Verweis (ähnlich einem Zeiger) auf den tatsächlichen Wert des Objekts dargestellt werden. Wenn ein Verweistyp einer Variablen zugeordnet wird, verweist (oder zeigt) diese Variable auf den ursprünglichen Wert. Es wird keine Kopie erstellt. 

Das allgemeine Typsystem in .NET unterstützt die folgenden fünf Typkategorien:

* [Klassen](#classes)

* [Strukturen](#structures)

* [Enumerationen](#enumerations)

* [Schnittstellen](#interfaces)

* [Delegaten](#delegates)

### <a name="classes"></a>Klassen

Eine Klasse ist ein Referenztyp, der direkt von einer anderen Klasse abgeleitet werden kann und der implizit von [System.Object](xref:System.Object) abgeleitet ist. Die Klasse definiert die Vorgänge, die ein Objekt (d. h. eine Instanz der Klasse) ausführen kann (Methoden, Ereignisse oder Eigenschaften), sowie die Daten, die das Objekt enthält (Felder). Obwohl eine Klasse im Allgemeinen sowohl Definition als auch Implementierung enthält (im Gegensatz zu Schnittstellen, die z. B. nur eine Definition ohne Implementierung enthalten), kann sie über einen oder mehrere Member ohne Implementierung verfügen.

In der folgenden Tabelle werden einige Eigenschaften beschrieben, über die eine Klasse verfügen kann. Jede für Laufzeitunterstützung ausgelegte Sprache bietet eine Möglichkeit, eines oder mehrere Merkmale für eine Klasse oder einen Klassenmember festzulegen. In einzelnen Programmiersprachen, die .NET als Ziel haben, sind jedoch möglicherweise nicht alle dieser Eigenschaften verfügbar.

Merkmal | Beschreibung
-------------- | -----------
sealed | Legt fest, dass von diesem Typ keine andere Klasse abgeleitet werden kann.
implements | Gibt an, dass die Klasse eine oder mehrere Schnittstellen verwendet; es werden Implementierungen von Schnittstellenmembern bereitgestellt.
abstract | Gibt an, dass die Klasse nicht instanziiert werden kann. Um die Klasse verwenden zu können, müssen Sie eine andere Klasse davon ableiten.
inherits | Legt fest, dass an jeder Stelle, an der die Basisklasse angegeben ist, Instanzen der Klasse verwendet werden können. Eine abgeleitete Klasse, die von einer Basisklasse erbt, kann die Implementierung jedes öffentlichen Members verwenden, der von der Basisklasse bereitgestellt wird, oder die abgeleitete Klasse kann die Implementierung der öffentlichen Member mit einer eigenen Implementierung überschreiben.
exported oder not exported | Gibt an, ob eine Klasse außerhalb der Assembly, in der sie definiert wurde, sichtbar ist. Dieses Merkmal gilt nur für Klassen der obersten Ebene und nicht für geschachtelte Klassen.

> [!NOTE]
> Eine Klasse kann auch in einer übergeordneten Klasse oder Struktur geschachtelt werden. Auch geschachtelte Klassen verfügen über Membermerkmale. Weitere Informationen finden Sie unter [Geschachtelte Typen](#nested-types).

Klassenmember, die keine Implementierung haben, sind abstrakte Member. Eine Klasse mit einem oder mehreren abstrakten Membern ist selbst abstrakt, und von dieser Klasse können keine Instanzen erstellt werden. Bei einigen Sprachen, die für die Laufzeit konzipiert sind, können Klassen selbst dann als abstrakt gekennzeichnet werden, wenn sie keine abstrakten Member haben. Sie können eine abstrakte Klasse verwenden, um eine gewisse Basisfunktionalität einzuschließen, die von abgeleiteten Klassen ggf. geerbt bzw. überschrieben werden kann. Nicht abstrakte Klassen werden als konkrete Klassen bezeichnet.

Eine Klasse kann eine beliebige Anzahl von Schnittstellen implementieren, sie kann jedoch nur von einer Basisklasse neben [System.Object](xref:System.Object) erben. Hiervon erben alle Klassen implizit. Alle Klassen müssen über mindestens einen Konstruktor verfügen, durch den neue Instanzen der Klasse initialisiert werden. Wenn Sie nicht explizit einen Konstruktor definieren, stellen die meisten Compiler automatisch einen Standardkonstruktor (ohne Parameter) bereit.

### <a name="structures"></a>Strukturen

Eine Struktur ist ein Werttyp, der implizit von [System.ValueType](xref:System.ValueType) abgeleitet ist. Dies ist wiederum von [System.Object](xref:System.Object) abgeleitet. Eine Struktur ist hilfreich beim Darstellen von Werten mit geringen Arbeitsspeicheranforderungen und beim Übergeben von Werten über Parameter als Wert an Methoden mit stark typisierten Parametern. In .NET sind alle primitiven Datentypen ([Boolean](xref:System.Boolean), [Byte](xref:System.Byte), [Char](xref:System.Char), [DateTime](xref:System.DateTime), [Decimal](xref:System.Decimal), [Double](xref:System.Double), [Int16](xref:System.Int16), [Int32](xref:System.Int32), [Int64](xref:System.Int64), [SByte](xref:System.SByte), [Single](xref:System.Single), [UInt16](xref:System.UInt16), [UInt32](xref:System.UInt32) und [UInt64](xref:System.UInt64)) als Strukturen definiert.

Wie Klassen definieren Strukturen sowohl Daten (die Felder der Struktur) als auch die Vorgänge, die für diese Daten (die Methoden der Struktur) ausgeführt werden können. Dies bedeutet, dass Sie Methoden für Strukturen aufrufen können, einschließlich der für die [System.Object](xref:System.Object)-Klasse und die [System.ValueType](xref:System.ValueType)-Klasse definierten virtuellen Methoden sowie aller Methoden, die für den Werttyp selbst definiert wurden. Anders ausgedrückt können Strukturen Felder, Eigenschaften und Ereignisse sowie statische und nicht statische Methoden aufweisen. Sie können Instanzen von Strukturen erstellen, diese als Parameter übergeben, als lokale Variablen speichern oder im Feld eines anderen Werttyps oder Verweistyps speichern. Strukturen können auch Schnittstellen implementieren.

Werttypen unterscheiden sich in mehreren Punkten auch von Klassen. Zunächst können sie nicht direkt von einem Typ erben, obwohl sie implizit von [System.ValueType](xref:System.ValueType) erben. Ebenso sind alle Werttypen versiegelt, was bedeutet, dass kein anderer Typ von ihnen abgeleitet werden kann. Außerdem benötigen sie keine Konstruktoren.

Die Common Language Runtime stellt für jeden Werttyp einen entsprechenden geschachtelten Werttyp bereit, der eine Klasse darstellt, die denselben Zustand und dasselbe Verhalten wie der Werttyp aufweist. Eine Instanz eines Werttyps wird beim Übergeben an eine Methode geschachtelt, die einen Parameter vom Typ [System.Object](xref:System.Object) annimmt. Sie wird mittels Unboxing konvertiert (d. h. aus einer Instanz einer Klasse zurück in die Instanz eines Werttyps konvertiert), wenn ein Steuerelement aus einem Methodenaufruf zurückgegeben wird, in dem ein Werttyp als Parameter als Verweis angenommen wird. In einigen Sprachen muss eine spezielle Syntax verwendet werden, wenn ein mittels Boxing gepackter Typ erforderlich ist; in anderen Sprachen wird der mittels Boxing gepackte Typ bei Bedarf automatisch verwendet. Die Definition eines Werttyps schließt sowohl den mittels Boxing gepackten als auch den mittels Unboxing entpackten Typ ein.

### <a name="enumerations"></a>Enumerationen

Eine Enumeration ist ein Werttyp, der direkt von [System.Enum](xref:System.Enum) erbt und alternative Namen für die Werte eines zugrunde liegenden primitiven Typs bereitstellt. Ein Enumerationstyp verfügt über einen Namen, einen zugrunde liegenden Typ, bei dem es sich um einen der integrierten Ganzzahltypen mit oder ohne Vorzeichen handeln muss (z.B. [Byte](xref:System.Byte), [Int32](xref:System.Int32) oder [UInt64](xref:System.UInt64)), und einen Satz von Feldern. Die Felder sind statische Literalfelder, von denen jedes eine Konstante darstellt. Derselbe Wert kann auch mehreren Feldern zugewiesen werden. In dieser Situation muss einer der Werte als primärer Enumerationswert für die Reflektion und Zeichenfolgenkonvertierung gekennzeichnet werden.

Sie können einer Enumeration einen Wert des zugrunde liegenden Typs zuweisen und umgekehrt (für die Laufzeit ist keine Typumwandlung erforderlich). Sie können eine Instanz einer Enumeration erstellen und die Methoden von [System.Enum](xref:System.Enum) sowie alle für den zugrunde liegenden Enumerationstyp definierten Methoden aufrufen. In einigen Sprachen ist es jedoch möglicherweise nicht zulässig, dass eine Enumeration als Parameter übergeben wird, wenn eine Instanz des zugrunde liegenden Typs erforderlich ist (oder umgekehrt).

Für Enumerationen gelten die folgenden zusätzlichen Beschränkungen: 

* Sie können keine eigenen Methoden definieren.

* Sie können keine Schnittstellen implementieren.

* Sie können keine Eigenschaften oder Ereignisse definieren.

* Sie können nicht generisch sein, es sei denn, sie sind nur deshalb generisch, weil sie in einem generischen Typ geschachtelt sind. Das bedeutet, dass eine Enumeration nicht über eigene Typparameter verfügen kann. 

> [!NOTE]
> Geschachtelte Typen (z.B. Enumerationen), die mit C# erstellt wurden, enthalten die Typparameter aller einschließenden generischen Typen und sind daher generisch, auch wenn sie über keine eigenen Typparameter verfügen. Weitere Informationen finden Sie im Referenzthema [Type.MakeGenericType](xref:System.Type.MakeGenericType(System.Type[])). 

Durch das [FlagsAttribute](xref:System.FlagsAttribute)-Attribut wird eine spezielle Art von Enumeration, das so genannte Bitfeld, ausgewiesen. Von der Laufzeit selbst wird nicht zwischen herkömmlichen Enumerationen und Bitfeldern unterschieden, in Ihrer Programmiersprache könnte dies jedoch der Fall sein. Wird diese Unterscheidung getroffen, können zum Generieren nicht benannter Werte zwar bitweise Operatoren für Bitfelder, jedoch nicht für Enumerationen verwendet werden. Enumerationen werden im Allgemeinen für Listen eindeutiger Elemente verwendet, z. B. für Wochentage bzw. Namen für Regionen oder Länder usw. Bitfelder werden in der Regel für Listen verwendet, in denen Qualitätsmerkmale oder Mengen definiert sind, die kombiniert auftreten können, z. B. `Red And Big And Fast`.

Das folgende Beispiel zeigt, wie Bitfelder und herkömmliche Enumerationen in Kombination verwendet werden können.

```csharp
using System;
using System.Collections.Generic;

// A traditional enumeration of some root vegetables.
public enum SomeRootVegetables
{
    HorseRadish,
    Radish,
    Turnip
}

// A bit field or flag enumeration of harvesting seasons.
[Flags]
public enum Seasons
{
    None = 0,
    Summer = 1,
    Autumn = 2,
    Winter = 4,
    Spring = 8,
    All = Summer | Autumn | Winter | Spring
}

public class Example
{
   public static void Main()
   {
       // Hash table of when vegetables are available.
       Dictionary<SomeRootVegetables, Seasons> AvailableIn = new Dictionary<SomeRootVegetables, Seasons>();

       AvailableIn[SomeRootVegetables.HorseRadish] = Seasons.All;
       AvailableIn[SomeRootVegetables.Radish] = Seasons.Spring;
       AvailableIn[SomeRootVegetables.Turnip] = Seasons.Spring | 
            Seasons.Autumn;

       // Array of the seasons, using the enumeration.
       Seasons[] theSeasons = new Seasons[] { Seasons.Summer, Seasons.Autumn, 
            Seasons.Winter, Seasons.Spring };

       // Print information of what vegetables are available each season.
       foreach (Seasons season in theSeasons)
       {
          Console.Write(String.Format(
              "The following root vegetables are harvested in {0}:\n", 
              season.ToString("G")));
          foreach (KeyValuePair<SomeRootVegetables, Seasons> item in AvailableIn)
          {
             // A bitwise comparison.
             if (((Seasons)item.Value & season) > 0)
                 Console.Write(String.Format("  {0:G}\n", 
                      (SomeRootVegetables)item.Key));
          }
       }
   }
}
// The example displays the following output:
//    The following root vegetables are harvested in Summer:
//      HorseRadish
//    The following root vegetables are harvested in Autumn:
//      Turnip
//      HorseRadish
//    The following root vegetables are harvested in Winter:
//      HorseRadish
//    The following root vegetables are harvested in Spring:
//      Turnip
//      Radish
//      HorseRadish
```

```vb
Imports System.Collections.Generic

' A traditional enumeration of some root vegetables.
Public Enum SomeRootVegetables
   HorseRadish
   Radish
   Turnip
End Enum 

' A bit field or flag enumeration of harvesting seasons.
<Flags()> Public Enum Seasons
   None = 0
   Summer = 1
   Autumn = 2
   Winter = 4
   Spring = 8
   All = Summer Or Autumn Or Winter Or Spring
End Enum 

' Entry point.
Public Class Example
   Public Shared Sub Main()
      ' Hash table of when vegetables are available.
      Dim AvailableIn As New Dictionary(Of SomeRootVegetables, Seasons)()

      AvailableIn(SomeRootVegetables.HorseRadish) = Seasons.All
      AvailableIn(SomeRootVegetables.Radish) = Seasons.Spring
      AvailableIn(SomeRootVegetables.Turnip) = Seasons.Spring Or _
                                               Seasons.Autumn

      ' Array of the seasons, using the enumeration.
      Dim theSeasons() As Seasons = {Seasons.Summer, Seasons.Autumn, _
                                     Seasons.Winter, Seasons.Spring}

      ' Print information of what vegetables are available each season.
      For Each season As Seasons In theSeasons
         Console.WriteLine(String.Format( _
              "The following root vegetables are harvested in {0}:", _
              season.ToString("G")))
         For Each item As KeyValuePair(Of SomeRootVegetables, Seasons) In AvailableIn
            ' A bitwise comparison.
            If(CType(item.Value, Seasons) And season) > 0 Then
               Console.WriteLine("  " + _
                     CType(item.Key, SomeRootVegetables).ToString("G"))
            End If
         Next
      Next
   End Sub 
End Class 
' The example displays the following output:
'    The following root vegetables are harvested in Summer:
'      HorseRadish
'    The following root vegetables are harvested in Autumn:
'      Turnip
'      HorseRadish
'    The following root vegetables are harvested in Winter:
'      HorseRadish
'    The following root vegetables are harvested in Spring:
'      Turnip
'      Radish
'      HorseRadish
```

### <a name="interfaces"></a>Schnittstellen

Eine Schnittstelle definiert einen Vertrag, der eine Kann-Beziehung oder eine Hat-ein-Beziehung angibt. Schnittstellen werden häufig zur Implementierung einer Funktionalität verwendet, z.B. Vergleichen und Sortieren (die [IComparable](xref:System.IComparable)- und [IComparable&lt;T&gt;](xref:System.IComparable%601)-Schnittstellen), Testen auf Gleichheit (die [IEquatable&lt;T&gt;](xref:System.IEquatable%601)-Schnittstelle) oder Aufzählung von Elementen in einer Sammlung (die [IEnumerable](xref:System.Collections.IEnumerable)- und [IEnumerable&lt;T&gt;](xref:System.Collections.Generic.IEnumerable%601)-Schnittstellen). Schnittstellen können Eigenschaften, Methoden und Ereignisse aufweisen, die alle abstrakte Member sind. Während die Schnittstelle die Member und deren Signaturen definiert, definiert der die Schnittstelle implementierende Typ die Funktionalität der Schnittstellenmember. Dies bedeutet, dass jede Klasse oder Struktur, die eine Schnittstelle implementiert, Definitionen für die in der Schnittstelle deklarierten abstrakten Member bereitstellen muss. Für eine Schnittstelle kann es erforderlich sein, dass eine beliebige implementierende Klasse oder Struktur auch mindestens eine andere Schnittstelle implementiert.

Für Schnittstellen gelten die folgenden Beschränkungen: 

* Eine Schnittstelle kann mit beliebigem Zugriff deklariert werden, die Schnittstellenmember müssen jedoch alle über die Zugriffsart public verfügen.

* Schnittstellen können keine Konstruktoren definieren.

* Schnittstellen können keine Felder definieren.

* Schnittstellen können nur Instanzmember definieren. Sie können keine statischen Member definieren.

Jede Sprache muss Regeln zur Verfügung stellen, mit deren Hilfe eine Implementierung der Schnittstelle zugeordnet werden kann, die den Member benötigt. Der Grund ist, dass in mehreren Schnittstellen Member mit identischen Signaturen deklariert werden können, die jedoch möglicherweise über separate Implementierungen verfügen.

### <a name="delegates"></a>Delegaten

Delegaten sind Verweistypen, die einen ähnlichen Zweck erfüllen wie Funktionszeiger in C++. Sie werden für Ereignishandler und Rückruffunktionen in .NET verwendet. Im Gegensatz zu Funktionszeigern sind Delegaten sicher, überprüfbar und typsicher. Ein Delegattyp kann jede Instanzmethode oder statische Methode darstellen, die über eine kompatible Signatur verfügt. 

Ein Parameter eines Delegaten ist mit dem entsprechenden Parameter einer Methode kompatibel, wenn der Typ des Delegatenparameters restriktiver ist als der Methodenparameter, da so gewährleistet ist, dass ein an den Delegaten übergebenes Argument problemlos an die Methode weitergeleitet werden kann.

Ebenso ist der Rückgabetyp eines Delegaten kompatibel mit dem Rückgabetyp einer Methode, wenn der Rückgabetyp der Methode restriktiver ist als der Rückgabetyp des Delegaten, da so gewährleistet ist, dass der Rückgabewert der Methode problemlos in den Rückgabetyp des Delegaten umgewandelt werden kann.

Beispielsweise kann ein Delegat mit einem Parameter des Typs [IEnumerable](xref:System.Collections.IEnumerable) und dem Rückgabetyp [Object](xref:System.Object) eine Methode mit einem Parameter des Typs [Object](xref:System.Object) und einem Rückgabewert des Typs [IEnumerable](xref:System.Collections.IEnumerable) darstellen. 

 Ein Delegat wird als gebunden an die Methode bezeichnet, die er darstellt. Ein Delegat kann nicht nur an die Methode, sondern auch an ein Objekt gebunden sein. Das Objekt stellt den ersten Parameter der Methode dar und wird jedes Mal an die Methode übergeben, wenn der Delegat aufgerufen wird. Wenn es sich bei der Methode um eine Instanzmethode handelt, wird das gebundene Objekt als impliziter `this`-Parameter (`Me` in Visual Basic) übergeben. Wenn die Methode statisch ist, wird das Objekt als erster formaler Parameter der Methode übergeben, und die Delegatsignatur muss den verbleibenden Parametern entsprechen. 
 
 Alle Delegaten erben von [System.MulticastDelegate](xref:System.MulticastDelegate), und der erbt wiederum von [System.Delegate](xref:System.Delegate). In den Programmiersprachen C# und Visual Basic ist die Vererbung von diesen Typen nicht zulässig. Stattdessen werden Schlüsselwörter zum Deklarieren von Delegaten bereitgestellt.
 
 Da Delegaten von [MulticastDelegate](xref:System.MulticastDelegate) erben, verfügt ein Delegat über eine Aufrufliste. Dabei handelt es sich um eine Liste der Methoden, die dieser Delegat darstellt und die beim Aufrufen des Delegaten ausgeführt werden. Alle Methoden in der Liste empfangen die beim Aufrufen des Delegaten angegebenen Argumente.

> [!NOTE]
> Der Rückgabewert von Delegaten mit mehr als einer Methode in der Aufrufliste ist nicht definiert, selbst wenn diese über einen Rückgabetyp verfügen.

In vielen Fällen (z. B. bei Rückrufmethoden) stellt ein Delegat nur eine Methode dar. Sie müssen den Delegaten lediglich erstellen und aufrufen. 

Für Delegaten, die mehrere Methoden darstellen, enthält .NET Methoden der [Delegate](xref:System.Delegate)-Delegatklasse und [MulticastDelegate](xref:System.MulticastDelegate)-Delegatklasse, um verschiedene Vorgänge zu unterstützen. Dazu gehören das Hinzufügen einer Methode zur Aufrufliste eines Delegaten (die [Delegate.Combine](xref:System.Delegate.Combine(System.Delegate,System.Delegate))-Methode), das Entfernen einer Methode (die [Delegate.Remove](xref:System.Delegate.Remove(System.Delegate,System.Delegate))-Methode) und das Abrufen der Aufrufliste (die [Delegate.GetInvocationList](xref:System.Delegate.GetInvocationList)-Methode).

> [!NOTE]
> Es ist in C# oder Visual Basic nicht erforderlich, diese Methoden für Ereignishandlerdelegaten einzusetzen, da in diesen Programmiersprachen Syntax zum Hinzufügen und Entfernen von Ereignishandlern bereitsteht.

## <a name="type-definitions"></a>Typdefinitionen

Eine Typdefinition enthält Folgendes: 

* Alle für den Typ definierten Attribute.

* Den Zugriff des Typs (Sichtbarkeit).

* Den Typnamen.

* Den Basistyp des Typs.

* Alle durch den Typ implementierten Schnittstellen.

* Definitionen für jeden Member des Typs.

### <a name="attributes"></a>Attribute

Durch Attribute werden zusätzliche benutzerdefinierte Metadaten bereitgestellt. Sie werden in dem meisten Fällen verwendet, um zusätzliche Informationen zu einem Typ in seiner Assembly zu speichern oder um das Verhalten eines Typmembers zur Entwurfszeit oder in der Laufzeitumgebung zu ändern. 

Attribute sind selbst Klassen, die von [System.Attribute](xref:System.Attribute) erben. Sprachen, die die Verwendung von Attributen unterstützen, verfügen über eine eigene Syntax zum Anwenden von Attributen auf ein Sprachelement. Attribute können auf fast alle Sprachelemente angewendet werden. Die einzelnen Elemente, auf die ein Attribut angewendet werden kann, werden vom auf die Attributklasse angewendeten [AttributeUsageAttribute](xref:System.AttributeUsageAttribute) definiert.

### <a name="type-accessibility"></a>Typzugriff

Alle Typen verfügen über einen Modifizierer, der regelt, welche anderen Typen auf diesen Typ zugreifen können. In der folgenden Tabelle werden die von der Laufzeit unterstützten Zugriffsarten auf Typen beschrieben.

Barrierefreiheit | Beschreibung
------------- | -----------
public | Auf diesen Typ kann von allen Assemblys zugegriffen werden.
Assembly | Auf diesen Typ kann nur innerhalb seiner Assembly zugegriffen werden.

Der Zugriff auf einen geschachtelten Typ hängt von seiner Zugriffsdomäne ab, die sowohl durch den deklarierten Zugriffstyp des Members als auch durch die Zugriffsdomäne des direkt enthaltenden Typs bestimmt wird. Die Zugriffsdomäne eines geschachtelten Typs kann jedoch nicht über die des enthaltenden Typs hinausgehen.

Die Zugriffsdomäne eines geschachtelten Members `M`, der in einem Typ `T` innerhalb eines Programms `P` deklariert ist, wird wie folgt definiert (wobei `M` selbst ein Typ sein kann): 

* Wenn die deklarierte Zugriffsart von `M` den Wert `public` hat, entspricht die Zugriffsdomäne von `M` der von `T`.

* Wenn die deklarierte Zugriffsart von `M` den Wert `protected internal` hat, entspricht die Zugriffsdomäne von `M` der Schnittmenge zwischen der Zugriffsdomäne von `T`, dem Programmtext von `P` und dem Programmtext jedes Typs, der von `T` abgeleitet und außerhalb von `P` deklariert wurde.

* Wenn die deklarierte Zugriffsart von `M` den Wert `protected` hat, entspricht die Zugriffsdomäne von `M` der Schnittmenge zwischen der Zugriffsdomäne von `T`, dem Programmtext von `T` und jedem von `T` abgeleiteten Typ.

* Wenn die deklarierte Zugriffsart von `M` den Wert `internal` hat, entspricht die Zugriffsdomäne von `M` der Schnittmenge zwischen der Zugriffsdomäne von `T` und dem Programmtext von `P`.

* Wenn die deklarierte Zugriffsart von `M` den Wert `private` hat, entspricht die Zugriffsdomäne von `M` dem Programmtext von `T`.

### <a name="type-names"></a>Typnamen

Das allgemeine Typsystem sieht lediglich zwei Namenseinschränkungen vor: 

* Alle Namen werden als Unicode-Zeichenfolgen (16-Bit-Zeichen) codiert.

* Ein eingebetteter Wert von 0x0000 (16 Bits) ist für Namen nicht zulässig.

In den meisten Sprachen gelten jedoch möglicherweise zusätzliche Beschränkungen für Typnamen. Alle Vergleiche erfolgen byteweise, sie berücksichtigen daher die Groß-/Kleinschreibung und sind unabhängig vom Gebietsschema.

Obwohl ein Typ auf Typen aus anderen Modulen und Assemblys verweisen kann, muss er vollständig innerhalb eines .NET-Moduls definiert werden. (Abhängig von der Compilerunterstützung kann er jedoch auf mehrere Quellcodedateien aufgeteilt werden.) Typnamen müssen nur innerhalb eines Namespace eindeutig sein. Um einen Typ vollständig zu identifizieren, muss der Typname durch den Namespace gekennzeichnet werden, die die Typimplementierung enthält.

### <a name="base-types-and-interfaces"></a>Basistypen und Schnittstellen

Ein Typ kann Werte und Verhaltensdefinitionen von anderen Typen erben. Gemäß dem allgemeinen Typsystem können Typen nicht von mehr als einem Basistyp erben.

Ein Typ kann eine beliebige Anzahl von Schnittstellen implementieren. Zur Implementierung einer Schnittstelle muss ein Typ alle virtuellen Member der betreffenden Schnittstelle implementieren. Eine virtuelle Methode kann durch einen abgeleiteten Typ implementiert und entweder statisch oder dynamisch aufgerufen werden.

## <a name="type-members"></a>Typmember

Die Laufzeit ermöglicht es Ihnen, Member des Typs zu definieren. Hierbei werden das Verhalten und der Zustand eines Typs angegeben. Typmember umfassen Folgendes:

* [Felder](#fields)

* [Eigenschaften](#properties)

* [Methoden](#methods)

* [Konstruktoren](#constructors)

* [Ereignisse](#events)

* [Geschachtelte Typen](#nested-types)

### <a name="fields"></a>Felder

Ein Feld beschreibt und enthält Teile des Typzustands. Felder können jedem von der Laufzeit unterstützten Typ entsprechen. In den meisten Fällen sind Felder `private` oder `protected`, damit auf sie nur innerhalb der Klasse oder aus einer abgeleiteten Klasse zugegriffen werden kann. Wenn der Wert eines Felds außerhalb seines Typs geändert werden kann, wird normalerweise ein Eigenschaftensatzaccessor verwendet. Öffentlich verfügbar gemachte Felder sind normalerweise schreibgeschützt und können zwei Typen aufweisen: 

* Konstanten, deren Wert zur Entwurfszeit zugewiesen wird. Diese sind statische Member einer Klasse, obwohl sie nicht mit dem `static`-Schlüsselwort (`Shared` in Visual Basic) definiert werden.

* Schreibgeschützte Variablen, deren Werte im Klassenkonstruktor zugewiesen werden können.

Im folgenden Beispiel werden diese zwei Verwendungen für schreibgeschützte Felder veranschaulicht.

```csharp
using System;

public class Constants
{
   public const double Pi = 3.1416;
   public readonly DateTime BirthDate;

   public Constants(DateTime birthDate)
   {
      this.BirthDate = birthDate;
   }
}

public class Example
{
   public static void Main()
   {
      Constants con = new Constants(new DateTime(1974, 8, 18));
      Console.Write(Constants.Pi + "\n");
      Console.Write(con.BirthDate.ToString("d") + "\n");
   }
}
// The example displays the following output if run on a system whose current
// culture is en-US:
//    3.1417
//    8/18/1974
```

```vb
Public Class Constants
   Public Const Pi As Double = 3.1416
   Public ReadOnly BirthDate As Date

   Public Sub New(birthDate As Date)
      Me.BirthDate = birthDate
   End Sub
End Class

Public Module Example
   Public Sub Main()
      Dim con As New Constants(#8/18/1974#)
      Console.WriteLine(Constants.Pi.ToString())
      Console.WriteLine(con.BirthDate.ToString("d"))
   End Sub
End Module
' The example displays the following output if run on a system whose current
' culture is en-US:
'    3.1417
'    8/18/1974
```

### <a name="properties"></a>Eigenschaften

Eine Eigenschaft benennt einen Wert oder Zustand des Typs und definiert Methoden zum Abrufen oder Festlegen des Eigenschaftswerts. Eigenschaften können primitive Typen, Auflistungen primitiver Typen, benutzerdefinierte Typen oder Auflistungen benutzerdefinierter Typen sein. Eigenschaften werden häufig verwendet, um die Unabhängigkeit der öffentlichen Schnittstelle eines Typs von seiner tatsächlichen Darstellung zu gewährleisten. So können Eigenschaften Werte reflektieren, die nicht direkt in der Klasse gespeichert sind (z. B., wenn eine Eigenschaft einen berechneten Wert zurückgibt), oder eine Validierung ausführen, bevor privaten Feldern Werte zugewiesen werden. Im folgenden Codebeispiel wird das zweite Schema veranschaulicht.

```csharp
using System;

public class Person
{
   private int m_Age;

   public int Age
   { 
      get { return m_Age; }
      set {
         if (value < 0 || value > 125)
         {
            throw new ArgumentOutOfRangeException("The value of the Age property must be between 0 and 125.");
         }
         else
         {
            m_Age = value;
         }         
      }
   }
}
```

```vb
Public Class Person
   Private m_Age As Integer

   Public Property Age As Integer
      Get
         Return m_Age
      End Get
      Set
         If value < 0 Or value > 125 Then
            Throw New ArgumentOutOfRangeException("The value of the Age property must be between 0 and 125.")
         Else
            m_Age = value
         End If
      End Set
   End Property
End Class
```

Die Microsoft Intermediate Language (MSIL) schließt nicht nur die Eigenschaft ein, sondern für einen Typ mit einer lesbaren Eigenschaft darüber hinaus eine `get`*_propertyname*-Methode und für einen Typ mit einer beschreibbaren Eigenschaft eine `set`*_propertyname*-Methode.

### <a name="methods"></a>Methoden

Eine Methode beschreibt Vorgänge, die für den Typ verfügbar sind. Eine Methodensignatur gibt die zulässigen Typen aller Parameter sowie des Rückgabewerts der Methode an.

Obwohl die meisten Methoden die erforderliche Anzahl von Parametern für Methodenaufrufe genau definieren, unterstützen einige Methoden eine variable Anzahl von Parametern. Der letzte deklarierte Parameter dieser Methoden wird mit dem [ParamArrayAttribute](xref:System.ParamArrayAttribute)-Attribut markiert. Sprachcompiler stellen in der Regel ein Schlüsselwort bereit, z.B. `params` in C# und `ParamArray` in Visual Basic, das die explizite Verwendung von [ParamArrayAttribute](xref:System.ParamArrayAttribute) unnötig macht.

### <a name="constructors"></a>Konstruktoren

Ein Konstruktor ist eine spezielle Methodenform, durch die neue Instanzen einer Klasse oder Struktur erstellt werden. Wie jede andere Methode kann ein Konstruktor Parameter einschließen. Konstruktoren verfügen jedoch nicht über einen Rückgabewert (d. h., sie geben `void` zurück). 

Wenn der Quellcode für eine Klasse nicht explizit einen Konstruktor definiert, schließt der Compiler einen Standardkonstruktor (ohne Parameter) ein. Wenn der Quellcode für eine Klasse jedoch nur parametrisierte Konstruktoren definiert, generiert der C#-Compiler keinen parameterlosen Konstruktor.

Wenn der Quellcode für eine Struktur Konstruktoren definiert, müssen diese parametrisiert werden. Eine Struktur kann keinen Standardkonstruktor (parameterlos) definieren, und Compiler generieren keine parameterlosen Konstruktoren für Strukturen oder andere Werttypen. Alle Werttypen verfügen über einen impliziten Standardkonstruktor. Dieser Konstruktor wird von der Common Language Runtime implementiert und initialisiert alle Felder der Struktur mit ihren Standardwerten. 

### <a name="events"></a>Ereignisse

Ein Ereignis definiert ein Ereignis, auf das reagiert werden kann, und definiert Methoden, mit denen das Ereignis ausgelöst und abonniert bzw. sein Abonnement aufgehoben werden kann. Häufig werden mithilfe von Ereignissen andere Typen über Zustandsänderungen informiert.

### <a name="nested-types"></a>Geschachtelte Typen

Ein geschachtelter Typ ist ein Typ, der ein Member eines anderen Typs ist. Geschachtelte Typen müssen eng mit dem zugehörigen enthaltenden Typ verknüpft sein und dürfen nicht für allgemeine Zwecke verwendbar sein. Geschachtelte Typen sind sinnvoll, wenn der deklarierende Typ Instanzen des geschachtelten Typs verwendet und erstellt und die Verwendung des geschachtelten Typs nicht in öffentlichen Membern verfügbar gemacht wird.

Für einige Entwickler sind geschachtelte Typen verwirrend, und sie sollten nur öffentlich sichtbar sein, wenn ein zwingender Grund dafür vorliegt. In einer gut entworfenen Bibliothek sollten Entwickler nur selten geschachtelte Typen zum Instanziieren von Objekten oder Deklarieren von Variablen verwenden müssen.

## <a name="characteristics-of-type-members"></a>Eigenschaften von Typmembern

Das allgemeine Typsystem unterstützt Typmember, die eine Vielzahl unterschiedlicher Merkmale haben können. Zur Unterstützung all dieser Merkmale sind jedoch keine speziellen Sprachen erforderlich. In der folgenden Tabelle sind diese Membermerkmale beschrieben.

Merkmal | Anwendbar auf | Beschreibung
-------------- | ------------ | -----------
abstract | Methoden, Eigenschaften und Ereignisse | Der Typ stellt keine Methodenimplementierung bereit. Typen, die abstrakte Methoden erben oder implementieren, müssen eine Implementierung für die Methode bereitstellen. Die einzige Ausnahme liegt vor, wenn der abgeleitete Typ selbst vom Typ abstract ist. Alle Methoden vom Typ abstract sind auch virtual.
private | Alle | Zugriff ist nur innerhalb desselben Typs wie dem des Members oder innerhalb eines geschachtelten Typs möglich.
family | Alle | Zugriff innerhalb desselben Typs wie dem des Members und von abgeleiteten Typen möglich, die davon erben.
assembly | Alle | Zugriff nur in der Assembly möglich, in der der Typ definiert ist.
family und assembly | Alle | Zugriff nur von Typen möglich, die sowohl über den Zugriffstyp family als auch assembly verfügen.
family oder assembly | Alle | Zugriff nur von Typen möglich, die über den Zugriffstyp "family" oder "assembly" verfügen.
public | Alle | Zugriff von jedem Typ möglich.
final | Methoden, Eigenschaften und Ereignisse | Die virtuelle Methode kann in einem abgeleiteten Typ nicht überschrieben werden.
initialize-only | Felder | Der Wert kann lediglich initialisiert werden. Nach der Initialisierung ist kein Schreibzugriff möglich.
instance | Felder, Methoden, Eigenschaften und Ereignisse | Wenn ein Member nicht als `static` (C#), `Shared` (Visual Basic), `virtual` (C#) oder `Overridable` (Visual Basic) gekennzeichnet ist, handelt es sich um einen Instanzmember (es ist kein instance-Schlüsselwort vorhanden). Im Arbeitsspeicher befinden sich so viele Kopien dieser Member wie Objekte, von denen sie verwendet werden.
literal | Felder | Der dem Feld zugewiesene Wert ist ein fester, zur Kompilierungszeit bekannter Wert eines integrierten Werttyps. Literalfelder werden zeitweise auch als Konstanten bezeichnet.
newslot oder override | Alle | Definiert, wie der Member mit geerbten Membern mit identischer Signatur interagiert: `newslot` blendet Member mit identischer Signatur aus; `override` ersetzt die Definition einer geerbten virtuellen Methode. Der Standardwert ist newslot.
static | Felder, Methoden, Eigenschaften und Ereignisse | Der Member gehört dem Typ an, mit dem er definiert wurde, und keiner bestimmten Instanz des Typs. Der Member existiert selbst dann, wenn keine Instanz des Typs erstellt wird, und wird von allen Instanzen des Typs gemeinsam genutzt.
virtual | Methoden, Eigenschaften und Ereignisse | Die Methode kann durch einen abgeleiteten Typ implementiert und entweder statisch oder dynamisch aufgerufen werden. Beim dynamischen Aufruf bestimmt der Typ der Instanz, durch die der Aufruf zur Laufzeit ausgeführt wird (und nicht der zur Kompilierungszeit bekannte Typ), welche Implementierung der Methode aufgerufen wird. Um eine Methode vom Typ virtual statisch aufzurufen, muss die Variable u. U. in einen Typ umgewandelt werden, der die gewünschte Methodenversion verwendet.

### <a name="overloading"></a>Überladen

Jeder Typmember verfügt über eine eindeutige Signatur. Methodensignaturen bestehen aus dem Methodennamen und einer Parameterliste (die Reihenfolge und Typen der Argumente der Methode). Solange die Signaturen unterschiedlich sind, können innerhalb eines Typs mehrere Methoden mit demselben Namen definiert werden. Wenn zwei oder mehrere Methoden mit demselben Namen definiert sind, wird von einer "überladenen" Methode gesprochen. In [System.Char](xref:System.Char) wird z.B. die `IsDigit`-Methode überladen. Eine Methode nimmt einen [Char](xref:System.Char) an. Die andere Methode nimmt einen [String](xref:System.String) und einen [Int32](xref:System.Int32) an. 

> [!NOTE]
> Der Rückgabetyp wird nicht als Teil der Signatur einer Methode betrachtet. Dies bedeutet, dass Methoden nicht überladen werden können, wenn sich nur ihr Rückgabetyp unterscheidet.

### <a name="inheriting-overriding-and-hiding-members"></a>Vererben, Überschreiben und Verdecken von Membern

Ein abgeleiteter Typ erbt alle Member seines Basistyps. Dies bedeutet, dass diese Member für den abgeleiteten Typ definiert und verfügbar sind. Das Verhalten oder die Merkmale geerbter Member können auf zwei Weisen geändert werden: 

* Ein abgeleiteter Typ kann einen geerbten Member verdecken, indem er einen neuen Member mit derselben Signatur definiert. Dies kann z. B. geschehen, um einen Member, der zuvor als public deklariert war, als private zu definieren, oder um ein neues Verhalten für eine geerbte Methode zu definieren, die mit `final` gekennzeichnet ist.

* Ein abgeleiteter Typ kann eine geerbte virtuelle Methode überschreiben. Die überschreibende Methode stellt eine neue Definition für die Methode bereit, die basierend auf dem Werttyp zur Laufzeit aufgerufen wird und nicht basierend auf dem zur Kompilierungszeit bekannten Variablentyp. Eine virtuelle Methode kann nur von einer Methode überschrieben werden, wenn die virtuelle Methode nicht als `final` gekennzeichnet ist und die neue Methode mindestens dieselben Zugriffstypen unterstützt wie die virtuelle Methode.

## <a name="see-also"></a>Siehe auch

[Typkonvertierung in .NET Framework](type-conversion.md)
