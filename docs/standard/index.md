---
title: "Einführung in .NET"
description: "Einführung in .NET"
keywords: .NET, .NET Core
author: richlander
manager: wpickett
ms.date: 10/05/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bbfe6465-329d-4982-869d-472e7ef85d93
translationtype: Human Translation
ms.sourcegitcommit: be774ae1291def36baafffbf2f717cf98565cd60
ms.openlocfilehash: fba870a93784b579da1065a07d82974951ac7e28

---

# <a name="net-primer"></a>Einführung in .NET

> In den Tutorials unter [„Erste Schritte mit .NET Core“](../core/getting-started.md) finden Sie Informationen zum Erstellen einer einfachen .NET Core-Anwendung. Es dauert nur wenige Minuten, bis Ihre erste App funktioniert und ausgeführt wird.

.NET ist eine Entwicklungsplattform für allgemeine Zwecke. .NET kann für alle Arten von Apps oder Arbeitsauslastungen verwendet werden, bei denen Lösungen für allgemeine Zwecke zum Einsatz kommen. Es bietet verschiedene wichtige und für viele Entwickler attraktive Features, wie z.B. automatische Speicherverwaltung und moderne Programmiersprachen, die das effiziente Erstellen hochwertiger Anwendungen erleichtern. .NET ermöglicht eine allgemeine Programmierumgebung mit vielen praktischen Features und stellt gleichzeitig einen detaillierten Zugriff auf native Arbeitsspeicher und APIs bereit.

Es sind viele Implementierungen von .NET verfügbar, basierend auf offenen [.NET-Standards](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md), die die Grundlagen der Plattform spezifizieren. Die Implementierungen sind für verschiedene Anwendungstypen (z.B. Desktop, mobil, Spiele, Cloud) separat optimiert und unterstützen eine Vielzahl von Chips (z.B. x86/x64, ARM) und Betriebssysteme (z.B. Windows, Linux, iOS, Android, macOS). Open Source ist auch ein wichtiger Bestandteil des .NET-Ökosystems: Es stehen viele .NET-Implementierungen und Bibliotheken mit von der OSI genehmigten Lizenzen zur Verfügung.

Informationen zu den verschiedenen .NET-Editionen von Microsoft und anderen Anbietern finden Sie unter [Übersicht über .NET-Implementierungen](../about/products.md).

In dieser Einführung werden einige der wichtigsten Konzepte der .NET-Plattform vorgestellt, und Sie erhalten Links zu weiterführenden Ressourcen zu jedem Thema. Nach dieser Einführung sind Sie mit den wichtigsten Begriffen und Konzepten der .NET-Plattform vertraut und kennen die Quellen, mit denen Sie Ihre Kenntnisse vertiefen können. 

## <a name="a-stroll-through-net"></a>Eine kleine Tour durch .NET

Wie jedes ausgereifte und moderne Framework für die Anwendungsentwicklung verfügt .NET über zahlreiche leistungsstarke Features, die Entwicklern die Arbeit erleichtern und ihnen ermöglichen, leistungsfähigeren Code zu schreiben. In diesem Abschnitt werden die Grundlagen der wichtigsten Features vorgestellt, und Sie erhalten Hinweise auf Artikel oder Dokumente mit detaillierteren Erläuterungen, sofern notwendig. Nach dieser Tour verfügen Sie über genügend Informationen, sodass Sie die Beispiele in unseren GitHub-Repositorys sowie anderen Code lesen und verstehen können, was passiert.

*   [Programmiersprachen](#programming-languages)
*   [Automatic Memory Management](#automatic-memory-management)
*   [Typsicherheit](#type-safety)
*   [Delegaten und Lambdas](#delegates-and-lambdas)
*   [Generische Typen (Generika)](#generic-types-generics)
*   [Language-Integrated Query (LINQ)](#language-integrated-query-linq)
*   [Asynchrone Programmierung](#async-programming)
*   [Native Interoperabilität](#native-interoperability)
*   [Unsicherer Code](#unsafe-code)

### <a name="programming-languages"></a>Programmiersprachen

Als Entwickler können Sie Anwendungen in jeder beliebigen Programmiersprache erstellen, die .NET unterstützt. Da .NET Sprachenunabhängigkeit und Sprachinteroperabilität bietet, ist eine Interaktion mit allen anderen .NET-Anwendungen und -Komponenten möglich, unabhängig davon, in welcher Sprache sie entwickelt wurden.

Programmiersprachen, die Ihnen ermöglichen, Anwendungen für die .NET-Plattform zu entwickeln, erfüllen die [CLI-Spezifikation (Common Language Infrastructure)](https://www.visualstudio.com/en-us/mt639507).

Zu den von .NET unterstützten Microsoft-Sprachen gehören C#, F# und Visual Basic. 

* C# ist einfach, leistungsstark, typsicher und objektorientiert, behält aber gleichzeitig die Ausdruckskraft und Eleganz der C-Sprachen bei. Wer sich mit C und ähnlichen Sprachen auskennt, wird wenig Probleme bei der Verwendung von C# haben.

* F# ist eine plattformübergreifende, funktionsorientierte Programmiersprache, die auch die herkömmliche und imperative Programmierung unterstützt.

* Visual Basic ist eine einfach zu erlernende Sprache, mit der Sie eine Vielzahl von Anwendungen erstellen können, die in .NET ausgeführt werden.

> [!NOTE]
> In der aktuellen Version von .NET Core wird nur C# vollständig über alle Microsoft-Tools hinweg unterstützt.  F# wird im .NET Core SDK unterstützt, kann aber noch nicht mit den Visual Studio-Tools verwendet werden.  Die Visual Basic-Unterstützung für das SDK und die Visual Studio-Tools sind geplant.

### <a name="automatic-memory-management"></a>Automatische Speicherverwaltung

Die Garbage Collection ist das bekannteste Feature von .NET. Entwickler müssen den Arbeitsspeicher nicht aktiv verwalten, es gibt aber Mechanismen, um dem Garbage Collector (GC) weitere Informationen zur Verfügung zu stellen. C# enthält das `new`-Schlüsselwort, um Arbeitsspeicher anhand eines bestimmten Typs zuzuweisen, und das `using`-Schlüsselwort, um den Bereich für die Verwendung des Objekts bereitzustellen. Der Garbage Collector arbeitet bei der Speicherverwaltung mit dem Prinzip der Verzögerung und gibt dem Anwendungsdurchsatz den Vorzug vor dem sofortigen Erfassen von Arbeitsspeicher.

Die beiden folgenden Zeilen weisen Speicher zu:

```cs
var title = ".NET Primer";
var list = new List<string>;

```

Es gibt kein entsprechendes Schlüsselwort zum Aufheben der Speicherzuweisung, da diese automatisch erfolgt, wenn der Garbage Collector während seiner geplanten Ausführung Arbeitsspeicher freigibt.

Methodenvariablen verlieren normalerweise ihre Gültigkeit, sobald eine Methode beendet ist. An diesem Punkt können sie gesammelt werden. Mit der `using`-Anweisung können Sie den Garbage Collector darüber informieren, dass ein bestimmtes Objekt noch vor Beendigung der Methode seine Gültigkeit verliert.

```cs
using(FileStream stream = GetFileStream(context))
{
    //operations on the stream
}

```

Sobald der `using`-Block beendet ist, weiß der Garbage Collector, dass das `stream`-Objekt im obigen Beispiel gesammelt und der verwendete Speicherplatz freigegeben werden kann.

Eines der weniger offensichtlichen, doch ziemlich weitreichenden Features, die durch den Garbage Collector ermöglicht werden, ist die Speichersicherheit. Das unveränderliche Merkmal der Speichersicherheit ist sehr einfach: Ein Programm ist speichersicher, wenn es nur auf Arbeitsspeicher zugreift, der zugewiesen (nicht freigegeben) wurde. Verbleibende Zeiger sind immer Fehler, und es ist häufig schwierig, sie zu finden.

Die .NET-Runtime bietet zusätzliche Dienste, um die Speichersicherheit zu gewährleisten, die von einem Garbage Collector nicht geboten wird. Sie stellt sicher, dass Programme keine Indizierung über das Ende eines Arrays hinaus durchführen und nicht auf Phantomfelder hinter dem Ende eines Objekts zugreifen.

Das folgende Beispiel löst aufgrund der Speichersicherheit eine Ausnahme aus.

```cs
int[] numbers = new int[42];
int number = numbers[42]; // will throw (indexes are 0-based)

```

### <a name="type-safety"></a>Typsicherheit

Objekte werden in Form von Typen zugeordnet. Die einzigen Vorgänge, die für ein bestimmtes Objekt zulässig sind, und der Arbeitsspeicher, den dieses Objekt belegt, gehören zum Typ des Objekts. Ein `Dog`-Typ kann `Jump`- und `WagTail`-Methoden besitzen, wahrscheinlich aber keine `SumTotal`-Methode. Ein Programm kann nur die deklarierten Methoden eines bestimmten Typs aufrufen. Alle anderen Aufrufe führen entweder zu einem Fehler während der Kompilierung oder zu einer Laufzeitausnahme (bei Verwendung von dynamischen Features oder `object`).

.NET-Sprachen sind objektorientiert und arbeiten mit Hierarchien aus Basisklassen und abgeleiteten Klassen. Die .NET-Runtime lässt nur Objektumwandlungen und -aufrufe zu, die der Objekthierarchie entsprechen. Denken Sie daran, dass jeder in einer .NET-Sprache definierte Typ vom `object`-Basistyp abgeleitet ist.

```cs
Dog dog = Dog.AdoptDog(); // Returns a Dog type
Pet pet = (Pet)dog; // Dog derives from Pet
pet.ActCute();
Car car = (Car)dog; // will throw - no relationship between Car and Dog
object temp = (object)dog; // legal - a Dog is an object
car = (Car)temp; // will throw - the runtime isn't fooled
car.Accelerate() // the dog won't like this, nor will the program get this far

```

Mithilfe der Typsicherheit lässt sich auch eine Kapselung erzwingen, indem die Genauigkeit der Accessorschlüsselwörter garantiert wird. Accessorschlüsselwörter sind Artefakte, die den Zugriff auf Member eines bestimmten Typs durch anderen Code steuern. Diese werden üblicherweise für verschiedene Arten von Daten innerhalb eines Typs verwendet, mit denen das Verhalten des Typs verwaltet wird.

```cs
Dog dog = Dog._nextDogToBeAdopted; // will throw - this is a private field

```

Einige .NET-Sprachen unterstützen den **Typrückschluss**. Typrückschluss bedeutet, dass der Compiler den Typ eines Ausdrucks auf der linken Seite aus dem Ausdruck auf der rechten Seite ableitet. Dies bedeutet nicht, dass die Typsicherheit verletzt oder außer Kraft gesetzt wird. Der resultierende Typ **besitzt** einen starken Typ mit allem, was dies impliziert. Wir schreiben die ersten beiden Zeilen des vorherigen Beispiels neu, um einen Typrückschluss einzuführen. Der Rest des Beispiels bleibt vollständig gleich.

```cs
  var dog = Dog.AdoptDog();
  var pet = (Pet)dog;
  pet.ActCute();
  Car car = (Car)dog; // will throw - no relationship between Car and Dog
  object temp = (object)dog; // legal - a Dog is an object
  car = (Car)temp; // will throw - the runtime isn't fooled
  car.Accelerate() // the dog won't like this, nor will the program get this far

```

### <a name="delegates-and-lambdas"></a>Delegaten und Lambdas

Delegaten ähneln C++-Funktionszeigern, mit dem großen Unterschied, dass sie typsicher sind. Sie stellen eine Art separater Methode innerhalb des CLR-Typsystems dar. Reguläre Methoden werden an eine Klasse angefügt und können nur über statische oder instanzaufrufende Konventionen direkt aufgerufen werden.

Delegaten werden in verschiedenen APIs und an anderen Stellen in der .NET-Welt verwendet, insbesondere über Lambdaausdrücke, die ein Kernstück von LINQ sind.

Weitere Informationen hierzu finden Sie im Dokument [Delegaten und Lambdas](delegates-lambdas.md).

### <a name="generic-types-generics"></a>Generische Typen (Generika)

Generische Typen – häufig auch „Generika“ genannt – wurden in .NET Framework 2.0 eingeführt. Kurz gesagt: Generika ermöglichen dem Programmierer, beim Entwerfen der Klassen einen „Typparameter“ einzuführen, über den der Clientcode (die Benutzer des Typs) den genauen Typ angeben kann, der anstelle des Typparameters verwendet werden soll.

Generika wurden eingeführt, um Programmierer beim Implementieren generischer Datenstrukturen zu unterstützen. Vor der Einführung von Generika mussten Programmierer mit Elementen vom Typ _object_ arbeiten, um z.B. den Typ _List_ generisch zu machen. Das führte zu verschiedenen Probleme hinsichtlich der Leistung und der Semantik, von möglichen Laufzeitfehlern ganz zu schweigen. Die bekannteste Variante solcher Fehler tritt auf, wenn eine Datenstruktur z.B. sowohl ganze Zahlen als auch Zeichenfolgen enthält und beim Arbeiten mit den Members der Liste eine _InvalidCastException_ ausgelöst wird.

Das unten stehende Beispiel zeigt ein einfaches Programm, das unter Verwendung einer Instanz von @System.Collections.Generic.List%601-Typen ausgeführt wird.

```cs
using System;
using System.Collections.Generic;

namespace GenericsSampleShort {
    public static void Main(string[] args){
        // List<string> is the client way of specifying the actual type for the type parameter T
        List<string> listOfStrings = new List<string> { "First", "Second", "Third" };

        // listOfStrings can accept only strings, both on read and write.
        listOfStrings.Add("Fourth");

        // Below will throw a compile-time error, since the type parameter
        // specifies this list as containing only strings.
        listOfStrings.Add(1);

    }
}

```

Weitere Informationen finden Sie im Artikel [Generische Typen (Generika) – Übersicht](generics.md).

### <a name="async-programming"></a>Asynchrone Programmierung

Die asynchrone Programmierung ist ein erstklassiges Konzept in .NET und bietet Unterstützung für asynchrone Vorgänge während der Laufzeit, in den Frameworkbibliotheken und in den .NET-Sprachkonstrukten. Intern basiert sie auf Objekten (z.B. `Task`), die davon profitieren, dass das Betriebssystem E/A-gebundene Jobs so effizient wie möglich ausführt.

Erste Informationen über die asynchrone Programmierung in .NET finden Sie unter [Async (Übersicht)](async.md).

### <a name="language-integrated-query-linq"></a>Sprachintegrierte Abfrage (Language-Integrated Query, LINQ)

LINQ ist ein Satz leistungsstarker Features für C# und VB, mit denen Sie einfachen, deklarativen Code für Datenvorgänge schreiben können. Die Daten können in vielfältiger Form vorliegen (als In-Memory-Objekte, in einer SQL-Datenbank oder in einem XML-Dokument), aber der LINQ-Code unterscheidet sich in der Regel für die verschiedenen Datenquellen nicht.

Weitere Informationen sowie einige Beispiele finden Sie unter [LINQ (Language Integrated Query)](using-linq.md).

### <a name="native-interoperability"></a>Native Interoperabilität

Jedes heute verwendete Betriebssystem stellt Plattformunterstützung für verschiedene Aufgaben der Programmierung bereit. .NET bietet verschiedene Möglichkeiten, diese APIs zu nutzen. Diese Unterstützung wird als „native Interoperabilität“ bezeichnet, und in diesem Abschnitt geht es darum, wie mit verwaltetem .NET-Code auf native APIs zugegriffen werden kann.

Die wichtigste Methode, um native Interoperabilität zu erreichen, erfolgt über einen Plattformaufruf: „P/Invoke“. Die Unterstützung in .NET Core steht für Linux- und Windows-Plattformen zur Verfügung. Eine andere, nur unter Windows verfügbare Methode zum Erreichen nativer Interoperabilität wird als „COM interop“ bezeichnet und zur Arbeit mit [COM-Komponenten](https://msdn.microsoft.com/library/bwa2bx93.aspx) in verwaltetem Code verwendet. Die Methode setzt auf der P/Invoke-Infrastruktur auf, funktioniert jedoch etwas anders.

Der Großteil der Interoperabilitätsunterstützung von Mono (und damit auch von Xamarin) für Java und Objective-C ist gleich aufgebaut, verwendet also die gleichen Prinzipien.

Weitere Informationen dazu finden Sie im Dokument [Native Interoperabilität](native-interop.md).

### <a name="unsafe-code"></a>Unsicherer Code

Die CLR ermöglicht die Fähigkeit, über `unsafe`-Code auf nativen Arbeitsspeicher zuzugreifen und Zeigerarithmetik durchzuführen. Diese Vorgänge werden für bestimmte Algorithmen sowie für die Systeminteroperabilität benötigt. Unsicherer Code ist zwar leistungsstark, aber von seiner Verwendung wird abgeraten, sofern er nicht für die Interoperabilität mit System-APIs oder zur Implementierung des effizientesten Algorithmus erforderlich ist. Unsicherer Code wird in verschiedenen Umgebungen möglicherweise unterschiedlich ausgeführt und bietet auch nicht die Vorteile von Garbage Collector und Typsicherheit. Es wird empfohlen, die Verwendung von unsicherem Code so weit wie möglich eingrenzen und den Code sehr gründlich zu testen.

Die `ToString()`-Methode der [StringBuilder](https://github.com/dotnet/coreclr/blob/master/src/mscorlib/src/System/Text/StringBuilder.cs#L327)-Klasse veranschaulicht, wie sich durch Verwendung von `unsafe`-Code effizient einen Algorithmus implementieren lässt, indem Arbeitsspeichersegmente direkt verschoben werden:

```cs
public override String ToString() {
          Contract.Ensures(Contract.Result<String>() != null);

          VerifyClassInvariant();

          if (Length == 0)
              return String.Empty;

          string ret = string.FastAllocateString(Length);
          StringBuilder chunk = this;
          unsafe {
              fixed (char* destinationPtr = ret)
              {
                  do
                  {
                      if (chunk.m_ChunkLength > 0)
                      {
                          // Copy these into local variables so that they are stable even in the presence of ----s (hackers might do this)
                          char[] sourceArray = chunk.m_ChunkChars;
                          int chunkOffset = chunk.m_ChunkOffset;
                          int chunkLength = chunk.m_ChunkLength;

                          // Check that we will not overrun our boundaries.
                          if ((uint)(chunkLength + chunkOffset) <= ret.Length && (uint)chunkLength <= (uint)sourceArray.Length)
                          {
                              fixed (char* sourcePtr = sourceArray)
                                  string.wstrcpy(destinationPtr + chunkOffset, sourcePtr, chunkLength);
                          }
                          else
                          {
                              throw new ArgumentOutOfRangeException("chunkLength", Environment.GetResourceString("ArgumentOutOfRange_Index"));
                          }
                      }
                      chunk = chunk.m_ChunkPrevious;
                  } while (chunk != null);
              }
          }
          return ret;
      }

```

## <a name="notes"></a>Notizen

Der Begriff „.NET-Runtime“ wird in diesem Dokument verwendet, um die verschiedenen Implementierungen von .NET abzudecken, wie z.B. CLR, Mono, IL2CPP und viele weitere. Die spezifischeren Namen werden nur bei Bedarf genannt.

Dieses Dokument bietet keine Informationen zu früherer Funktionalität, sondern beschreibt die .NET-Plattform im heutigen Zustand. Für dieses Dokument spielt es keine Rolle, ob ein .NET-Feature schon länger verfügbar war oder erst kürzlich eingeführt wurde. Es kommt nur darauf an, ob ein Feature so wichtig ist, dass es hier aufgeführt und beschrieben werden sollte.



<!--HONumber=Nov16_HO1-->


