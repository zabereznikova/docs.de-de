---
title: Vererbung in C#
description: Lernen Sie die Verwendung der Vererbung in C#-Bibliotheken und -Anwendungen.
keywords: Vererbung (C#), Basisklassen abgeleitete Klassen, abstrakte Basisklassen
author: rpetrusha
manager: wpickett
ms.author: ronpet
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: aeb68c74-0ea0-406f-9fbe-2ce02d47ef31
ms.translationtype: HT
ms.sourcegitcommit: 7912d46736fd9f9d9d2ee41c416d3dfc157cfe12
ms.openlocfilehash: 44e77b099b15b5ddccfd6b3826d0225de1b0a74f
ms.contentlocale: de-de
ms.lasthandoff: 08/09/2017

---
# <a name="inheritance-in-c-and-net"></a>Vererbung in C# und .NET

Dieses Tutorial macht Sie mit der Vererbung in C# vertraut. Vererbung ist eine Funktion der objektorientierten Programmiersprachen, die Ihnen ermöglicht, eine Basisklasse zu definieren, die eine bestimmte Funktionalität bietet (Daten und Verhalten), und abgeleitete Klassen zu definieren, die diese Funktionalität entweder übernehmen oder außer Kraft setzen.

## <a name="prerequisites"></a>Erforderliche Komponenten

In diesem Tutorial wird vorausgesetzt, dass Sie .NET Core installiert haben. Installationsanweisungen finden Sie im [.NET Core-Installationshandbuch](https://www.microsoft.com/net/core). Sie benötigen auch einen Code-Editor. In diesem Tutorial wird [Visual Studio Code](https://code.visualstudio.com) verwendet, obwohl Sie einen Code-Editor Ihrer Wahl verwenden können.

## <a name="running-the-examples"></a>Ausführen der Beispiele

Verwenden Sie zum Erstellen und Ausführen der Beispiele in diesem Tutorial das Befehlszeilenhilfsprogramm [dotnet](../../core/tools/dotnet.md). Gehen Sie für jedes Beispiel wie folgt vor:

1. Erstellen Sie ein Verzeichnis zum Speichern des Beispiels.
1. Geben Sie den Befehl [dotnet new console](../../core/tools/dotnet-new.md) in einer Befehlszeile ein, um ein neues .NET Core-Projekt zu erstellen.
1. Kopieren Sie den Code aus dem Beispiel, und fügen Sie ihn in den Code-Editor ein.
1. Geben Sie den Befehl [dotnet restore](../../core/tools/dotnet-restore.md) in der Befehlszeile ein, um die Abhängigkeiten des Projekts zu laden oder wiederherzustellen.
1. Geben Sie den Befehl [dotnet run](../../core/tools/dotnet-run.md) zum Kompilieren und Ausführen des Beispiels ein.

## <a name="background-what-is-inheritance"></a>Hintergrund: Was ist Vererbung?

*Vererbung* ist eines der wichtigsten Attribute bei der objektorientierten Programmierung. Sie können damit eine untergeordnete Klasse definieren, die das Verhalten einer übergeordneten Klasse wiederverwendet (erbt), erweitert oder ändert. Die Klasse, deren Member geerbt werden, ist die *Basisklasse*. Die Klasse, die die Member der Basisklasse erbt, ist die *abgeleitete Klasse*.

C# und .NET unterstützen nur die *einzelne Vererbung*. D.h., eine Klasse kann nur von einer einzelnen Klasse erben. Allerdings ist Vererbung transitiv, sodass Sie eine Vererbungshierarchie für einen Satz von Typen definieren können. Mit anderen Worten: Typ `D` kann von Typ `C` erben, der von Typ `B` erbt, der vom Basisklassentyp `A` erbt. Da Vererbung transitiv ist, stehen die Member des Typs `A` Typ `D` zur Verfügung.

Nicht alle Member einer Basisklasse werden von abgeleiteten Klassen geerbt. Die folgenden Member werden nicht geerbt:

- [Statische Konstruktoren](../programming-guide/classes-and-structs/static-constructors.md), die die statischen Daten einer Klasse initialisieren.

- [Instanzkonstruktoren](../programming-guide/classes-and-structs/constructors.md), die Sie aufrufen, um eine neue Instanz der Klasse zu erstellen. Jede Klasse muss ihre eigenen Konstruktoren definieren.

- [Finalizer](../programming-guide/classes-and-structs/destructors.md), die vom Garbage Collector der Laufzeit aufgerufen werden, um Instanzen einer Klasse zu zerstören.

Während alle anderen Member einer Basisklasse von abgeleiteten Klassen geerbt werden, hängt ihre Sichtbarkeit davon ab, ob auf sie zugegriffen werden kann. Ob auf einen Member zugegriffen werden kann, beeinflusst dessen Sichtbarkeit für abgeleitete Klassen wie folgt:

- [Private](../language-reference/keywords/private.md) Member sind nur in abgeleiteten Klassen sichtbar, die in ihrer Basisklasse geschachtelt sind. Andernfalls sind sie in abgeleiteten Klassen nicht sichtbar. Im folgenden Beispiel ist `A.B` eine geschachtelte Klasse, die sich von `A` ableitet, und `C` leitet sich von `A` ab. Das private Feld `A.value` ist in A.B sichtbar. Wenn Sie jedoch die Kommentare aus der `C.GetValue`-Methode entfernen und versuchen, das Beispiel zu kompilieren, verursacht dies Compilerfehler CS0122: „Der Zugriff auf "A.value" ist aufgrund des Schutzgrads nicht möglich.“

  [!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/private.cs#1)]

- [Geschützte](../language-reference/keywords/protected.md) Member sind nur in abgeleiteten Klassen sichtbar.

- [Interne](../language-reference/keywords/protected.md) Member sind nur in abgeleiteten Klassen sichtbar, die sich in der gleichen Assembly wie die Basisklasse befinden. Sie sind nicht in abgeleiteten Klassen sichtbar, die sich in einer anderen Assembly als die Basisklasse befinden.

- [Öffentliche] (../language-reference/keywords/protected.md) Member sind in abgeleiteten Klassen sichtbar und Teil der öffentlichen Schnittstelle der abgeleiteten Klasse. Öffentlich geerbte Member können so aufgerufen werden, als ob sie in der abgeleiteten Klasse definiert wurden. Im folgenden Beispiel definiert Klasse `A` eine Methode namens `Method1`, und Klasse `B` erbt von Klasse `A`. Das Beispiel ruft dann `Method1` auf, als wäre sie eine Instanzmethode von `B`.

[!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/basics.cs#1)]

Abgeleitete Klassen können auch geerbte Member *überschreiben*, indem sie eine alternative Implementierung bereitstellen. Um einen Member überschreiben zu können, muss der Member in der Basisklasse mit dem Schlüsselwort [virtual](../language-reference/keywords/virtual.md) markiert sein. Standardmäßig sind Member der Basisklasse nicht als `virtual` markiert und können nicht überschrieben werden. Der Versuch, wie im folgenden Beispiel einen nicht virtuellen Member zu überschreiben, verursacht den Compilerfehler CS0506: „"<member>" : Der geerbte Member "<member>" kann nicht überschrieben werden, da er nicht als "virtual", "abstract" oder "override" markiert ist.“

```csharp
public class A
{
    public void Method1()
    {
        // Do something.
    }
}

public class B : A
{
    public override void Method1() // Generates CS0506.
    {
        // Do something else.
    }
}
```

In einigen Fällen *muss* eine abgeleitete Klasse die Basisklassenimplementierung überschreiben. Basisklassenmember, die mit dem Schlüsselwort [abstract](../language-reference/keywords/abstract.md) markiert sind, erfordern, dass abgeleitete Klassen sie überschreiben. Der Versuch, das folgende Beispiel zu kompilieren, verursacht den Compilerfehler CS0534: „<class> implementiert den geerbten abstrakten Member <member> nicht.“, da Klasse `B` keine Implementierung für `A.Method1` bietet.

```csharp
public abstract class A
{
    public abstract void Method1();
}

public class B : A // Generates CS0534.
{
    public void Method3()
    {
        // Do something.
    }
}
```

Vererbung gilt nur für Klassen und Schnittstellen. Andere Typkategorien (Strukturen, Delegate und Enumerationen) unterstützen keine Vererbung. Aus diesem Grund verursacht der Versuch, Code wie den folgenden zu kompilieren, den Compilerfehler CS0527: „Der Typ "ValueType" in der Schnittstellenliste ist keine Schnittstelle.“ Die Fehlermeldung gibt an, dass die Vererbung nicht unterstützt wird, obwohl Sie die Schnittstellen definieren können, die eine Struktur implementiert.

```csharp
using System;

public struct ValueStructure : ValueType // Generates CS0527.
{
}
```

## <a name="implicit-inheritance"></a>Implizite Vererbung

Neben Typen, die sie vielleicht über die einzelne Vererbung erben, erben alle Typen im Typensystem von .NET implizit von <xref:System.Object> oder einem davon abgeleiteten Typ. Dadurch wird sichergestellt, dass die allgemeine Funktionalität für einen beliebigen Typ verfügbar ist.

Um zu sehen, was implizite Vererbung bedeutet, definieren wir eine neue Klasse `SimpleClass`, die einfach eine leere Klassendefinition ist:

[!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/simpleclass.cs#1)]

Wir können dann die Reflektion (die uns ermöglicht, die Metadaten eines Typs zu überprüfen, um Informationen zu diesem Typ zu erhalten) verwenden, um eine Liste der Member abzurufen, die zum `SimpleClass`-Typ gehören. Obwohl wir keine Member in unserer `SimpleClass`-Klasse definiert haben, gibt die Ausgabe des Beispiels an, dass sie tatsächlich neun Member hat. Einer davon ist ein parameterloser (oder standardmäßiger) Konstruktor, der automatisch vom C#-Compiler für den `SimpleClass`-Typ angegeben wird. Die verbleibenden acht sind Member von <xref:System.Object>, dem Typ, von dem alle Klassen und Schnittstellen im .NET-Typsystem letztlich implizit erben.

[!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/simpleclass.cs#2)]

Implizite Vererbung von der <xref:System.Object> -Klasse macht diese Methoden der `SimpleClass`-Klasse verfügbar:

- Die öffentliche `ToString`-Methode, die ein `SimpleClass`-Objekt in seine Zeichenfolgendarstellung konvertiert, gibt den vollqualifizierten Typnamen zurück. In diesem Fall gibt die `ToString`-Methode die Zeichenfolge „SimpleClass“ zurück.

- Drei Methoden, die zwei Objekte auf Gleichheit testen: die öffentliche `Equals(Object)`-Instanzmethode, die öffentliche statische `Equals(Object, Object)`-Methode und die öffentliche statische `ReferenceEquals(Object, Object)`-Methode. Standardmäßig testen diese Methoden auf Verweisgleichheit; d.h., um gleich zu sein, müssen zwei Objektvariablen auf das gleiche Objekt verweisen.

- Die öffentliche `GetHashCode`-Methode, die einen Wert, berechnet, der die Verwendung einer Instanz des Typs in Hashauflistungen ermöglicht.

- Die öffentliche `GetType` -Methode, die ein <xref:System.Type> -Objekt zurückgibt, das den `SimpleClass` -Typ darstellt.

- Die geschützte <xref:System.Object.Finalize%2A> -Methode, die nicht verwaltete Ressourcen freigeben soll, bevor der Speicher eines Objekts durch den Garbage Collector freigegeben wird.

- Die geschützte <xref:System.Object.MemberwiseClone%2A> -Methode, die einen flachen Klon des aktuellen Objekts erstellt.

Aufgrund der impliziten Vererbung können wir alle geerbten Member aus einem `SimpleClass`-Objekt einfach aufrufen, als wären sie tatsächlich in der `SimpleClass`-Klasse definierte Member. Im folgenden Beispiel wird die `SimpleClass.ToString`-Methode aufgerufen, die `SimpleClass` von <xref:System.Object> erbt.

[!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/simpleclass2.cs#1)]

Die folgende Tabelle enthält die Kategorien von Typen, die Sie in C# erstellen können, und die Typen, von denen sie implizit erben. Jeder Basistyp macht implizit abgeleiteten Typen über Vererbung einen anderen Satz von Membern verfügbar.

| Typkategorie | Erbt implizit von                                                      |
| ------------- | ----------------------------------------------------------------------------- |
| Klasse         | <xref:System.Object>                                                          |
| struct        | <xref:System.ValueType>, <xref:System.Object>                                 |
| enum          | <xref:System.Enum>, <xref:System.ValueType>, <xref:System.Object>             |
| delegate      | <xref:System.MulticastDelegate>, <xref:System.Delegate>, <xref:System.Object> |

## <a name="inheritance-and-an-is-a-relationship"></a>Vererbung und eine „ist ein“-Beziehung

Mit Vererbung wird normalerweise eine „ist ein“-Beziehung zwischen einer Basisklasse und einer oder mehreren abgeleiteten Klassen ausgedrückt, wobei die abgeleiteten Klassen spezialisierte Versionen der Basisklasse sind; die abgeleitete Klasse ist ein Typ der Basisklasse. Die `Publication`-Klasse stellt z.B. eine Publikation beliebiger Art dar, und die `Book`- und `Magazine`-Klasse stellen bestimmte Typen von Publikationen dar.

> [!NOTE]
> Eine Klasse oder Struktur kann eine oder mehrere Schnittstellen implementieren. Die Schnittstellenimplementierung wird zwar oft als Problemumgehung für einzelne Vererbung oder Möglichkeit der Verwendung von Vererbung mit Strukturen dargestellt, doch sie soll eine andere Beziehung (eine „tun können“-Beziehung) zwischen einer Schnittstelle und ihrem implementierenden Typ ausdrücken als Vererbung. Eine Schnittstelle definiert eine Teilmenge der Funktionalität (z.B. die Möglichkeit zum Testen auf Gleichheit, zum Vergleichen oder Sortieren von Objekten oder zum Unterstützen kulturspezifischer Analyse und Formatierung), die die Schnittstelle den implementierenden Typen zur Verfügung stellt.

Beachten Sie, dass „ist ein“ auch die Beziehung zwischen einem Typ und einer bestimmten Instanziierung des betreffenden Typs ausdrückt. Im folgenden Beispiel ist `Automobile` eine Klasse mit drei eindeutigen schreibgeschützten Eigenschaften: `Make`, der Autohersteller; `Model`, den Autotyp, und `Year`, das Herstellungsjahr. Unsere `Automobile` -Klasse verfügt auch über einen Konstruktor, dessen Argumente den Eigenschaftswerten zugewiesen werden, und er überschreibt die <xref:System.Object.ToString%2A?displayProperty=fullName> -Methode, um eine Zeichenfolge zu erzeugen, die eindeutig die `Automobile` -Instanz anstelle der `Automobile` -Klasse identifiziert.

[!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/is-a.cs#1)]

In diesem Fall sollten wir uns nicht auf die Vererbung verlassen, um bestimmte Automarken und Modelle darzustellen. Wir müssen z.B. keinen `Packard`-Typ definieren, um Autos darzustellen, die von der Packard Motor Car Company hergestellt werden. Stattdessen können wir sie durch Erstellen eines `Automobile`-Objekts darstellen, wobei die entsprechenden Werten an dessen Klassenkonstruktor übergeben werden, wie es im folgenden Beispiel geschieht.

[!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/is-a.cs#2)]

Eine auf Vererbung basierende „ist ein“-Beziehung wird am besten auf eine Basisklasse und abgeleitete Klassen angewendet, die der Basisklasse weitere Member hinzufügen oder zusätzliche Funktionalität erfordern, die in der Basisklasse nicht vorhanden ist.

## <a name="designing-the-base-class-and-derived-classes"></a>Entwerfen der Basisklasse und abgeleiteter Klassen

Wir betrachten das Entwerfen einer Basisklasse und ihrer abgeleiteten Klassen. In diesem Abschnitt definieren wir eine Basisklasse `Publication`, die eine Publikation jeder Art darstellt, z.B. ein Buch, eine Zeitschrift, eine Zeitung, ein Journal, einen Artikel usw. Wir definieren auch eine `Book`-Klasse, die von `Publication` abgeleitet ist. Wir könnten das Beispiel einfach erweitern, um andere abgeleitete Klassen wie `Magazine`, `Journal`, `Newspaper` und `Article` zu definieren.

### <a name="the-base-publication-class"></a>Die Basisklasse „Publication“

Beim Entwurf unserer `Publication`-Klasse müssen wir einige Entwurfsentscheidungen treffen:

- Welche Member sollen in unsere Basis-`Publication`-Klasse einbezogen werden? Sollen die `Publication`-Member Methodenimplementierungen bereitstellen, oder ist `Publication` eine abstrakte Basisklasse, die als Vorlage für ihre abgeleiteten Klassen dient?

  In diesem Fall stellt die `Publication`-Klasse Methodenimplementierungen bereit. Der Abschnitt [Entwerfen abstrakter Basisklassen und ihrer abgeleiteten Klassen](#abstract) enthält ein Beispiel, in dem eine abstrakte Basisklasse verwendet wird, um die Methoden zu definieren, die abgeleitete Klassen überschreiben müssen. Abgeleitete Klassen können beliebige Implementierungen bereitstellen, die für den abgeleiteten Typ geeignet sind.

  Die Möglichkeit zur Wiederverwendung von Code (d.h., mehrere abgeleitete Klassen nutzen gemeinsam die Deklaration und Implementierung von Basisklassenmethoden und müssen sie nicht überschreiben) ist ein Vorteil der nicht abstrakten Basisklassen. Daher sollten wir Member zu `Publication` hinzufügen, wenn ihr Code vermutlich von einigen oder den meisten spezialisierten `Publication`-Typen gemeinsam genutzt wird. Wenn wir dies nicht effizient durchführen, müssen wir letztendlich weitgehend identische Implementierungen von Membern in abgeleiteten Klassen bereitstellen, statt einer einzelnen Implementierung in der Basisklasse. Die Notwendigkeit, duplizierten Code an mehreren Standorten zu verwalten, ist eine potenzielle Fehlerquelle.

  Um sowohl die Wiederverwendung von Code zu maximieren als auch eine logische und intuitive Vererbungshierarchie zu erstellen, möchten wir sicher sein, dass wir in die `Publication`-Klasse nur die Daten und Funktionen einbeziehen, die alle bzw. die meisten Publikationen gemeinsam haben. Abgeleitete Klassen implementieren dann Member, die für die jeweiligen Publikationsarten, die sie darstellen, eindeutig sind.

- Wie weit sollen wir unsere Klassenhierarchie ausdehnen? Möchten wir statt nur einer Basisklasse und einer oder mehreren abgeleiteten Klassen eine Hierarchie von drei oder mehr Klassen entwickeln? Beispielsweise könnte `Publication` eine Basisklasse von `Periodical` sein, was wiederum eine Basisklasse von `Magazine`, `Journal` und `Newspaper` ist.

  Für unser Beispiel verwenden wir die einfache Hierarchie einer `Publication`-Klasse und einer einzelnen abgeleiteten Klasse, `Book`. Wir könnten das Beispiel mühelos erweitern, um eine Reihe von zusätzlichen Klassen zu erstellen, die von `Publication` abgeleitet sind, wie z.B. `Magazine` und `Article`.

- Ist es sinnvoll, die Basisklasse zu instanziieren? Wenn dies nicht der Fall ist, sollten wir das Schlüsselwort [abstract](../language-reference/keywords/abstract.md) auf die Klasse anwenden. Wenn versucht wird, eine mit dem `abstract`-Schlüsselwort markierte Klasse durch einen direkten Aufruf ihres Klassenkonstruktors zu instanziieren, generiert der C#-Compiler den Fehler CS0144: „Es konnte keine Instanz der abstrakten Klasse oder Schnittstelle erstellt werden.“ Wenn versucht wird, die Klasse mithilfe der Reflektion zu instanziieren, löst die Reflektionsmethode eine <xref:System.MemberAccessException> aus. Andernfalls kann unsere `Publication`-Klasse durch Aufruf ihres Klassenkonstruktors instanziiert werden.

  Standardmäßig kann eine Basisklasse durch Aufruf ihres Klassenkonstruktors instanziiert werden. Beachten Sie, dass wir nicht explizit einen Klassenkonstruktor definieren müssen. Wenn im Quellcode der Basisklasse keiner vorhanden ist, stellt der C#-Compiler automatisch einen (parameterlosen) Standardkonstruktor bereit.

  In unserem Beispiel markieren wir die `Publication`-Klasse als [abstract](../language-reference/keywords/abstract.md), sodass sie nicht instanziiert werden kann.

- Müssen abgeleitete Klassen die Implementierung der Basisklasse eines bestimmten Members erben, oder können sie optional die Implementierung der Basisklasse überschreiben? Um abgeleiteten Klassen zu erlauben, eine Basisklassenmethode zu überschreiben, müssen wir das [virtual](../language-reference/keywords/virtual.md)-Schlüsselwort verwenden. Standardmäßig können in der Basisklasse definierte Methoden *nicht* überschrieben werden.

- Stellt eine abgeleitete Klasse die endgültige Klasse in der Vererbungshierarchie dar und kann nicht selbst als Basisklasse für weitere abgeleitete Klassen verwendet werden? Standardmäßig kann jede Klasse als Basisklasse dienen. Wir können das [sealed](../language-reference/keywords/sealed.md)-Schlüsselwort anwenden, um anzugeben, dass eine Klasse nicht als Basisklasse für zusätzliche Klassen dienen kann. Beim Versuch der Ableitung von einer versiegelten Klasse wird der Compilerfehler CS0509 generiert: „Vom versiegelten Typ <typeName> kann nicht abgeleitet werden“.

  In unserem Beispiel markieren wir unsere abgeleitete Klasse als `sealed`.

Das folgende Beispiel zeigt sowohl den Quellcode für die `Publication`-Klasse als auch eine `PublicationType`-Enumeration, die von der Eigenschaft `Publication.PublicationType` zurückgegeben wird. Zusätzlich zu den Membern, die sie von <xref:System.Object> erbt, definiert die `Publication`-Klasse die folgenden eindeutigen Member und Memberüberschreibungen:

[!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/base-and-derived.cs#1)]

- Ein Konstruktor

  Da die `Publication`-Klasse `abstract` ist, kann sie nicht direkt von Code wie dem folgenden aus instanziiert werden:

  ```csharp
  var publication = new Publication("Tiddlywinks for Experts", "Fun and Games",
                                    PublicationType.Book);
  ```

  Ihr Instanzkonstruktor kann jedoch direkt von abgeleiteten Klassenkonstruktoren aufgerufen werden, wie der Quellcode für die `Book`-Klasse veranschaulicht.

- Zwei publikationsbezogene Eigenschaften

  `Title` ist eine schreibgeschützte Eigenschaft <xref:System.String>, deren Wert durch Aufrufen des `Publication`-Konstruktors abgerufen wird, der den Wert in einem privaten Feld namens `pubTitle` speichert.

  `Pages` ist eine schreibgeschützte Eigenschaft <xref:System.Int32>, die angibt, wie viele Seiten die Publikation insgesamt hat. Der Wert wird in einem privaten Feld namens `totalPages` gespeichert. Er muss eine positive Zahl sein; andernfalls wird eine <xref:System.ArgumentOutOfRangeException> ausgelöst.

- Herausgeberbezogene Elemente

  Zwei schreibgeschützte Eigenschaften, `Publisher` und `Type`, geben den Wert der privaten Felder `pubName` und `pubType` zurück. Die Werte werden ursprünglich durch den Aufruf des `Publication`-Klassenkonstruktors abgerufen.

- Veröffentlichungsbezogene Elemente

  Zwei Methoden, `Publish` und `GetPublicationDate`, legen das Veröffentlichungsdatum fest und geben es zurück. Die `Publish`-Methode setzt ein privates `published`-Flag auf `true`, wenn sie aufgerufen wird, und weist das ihr übergebene Datum als Argument dem privaten Feld `datePublished` zu. Die `GetPublicationDate`-Methode gibt die Zeichenfolge „NYP“ zurück, wenn das `published`-Flag `false` ist, und den Wert des Felds `datePublished`, wenn es `true` ist.

- Copyrightbezogene Elemente

  Die `Copyright`-Methode übernimmt den Namen des Urheberrechtsinhabers und das Jahr des Copyrights als Argumente und weist sie den privaten Feldern `copyrName` und `copyrDate` zu. Die Werte können aus den Eigenschaften `CopyrightName` und `CopyrightDate` abgerufen werden.

- Eine Überschreibung der `ToString`-Methode

  Wenn ein Typ die <xref:System.Object.ToString%2A?displayProperty=fullName> -Methode nicht überschreibt, gibt sie den vollqualifizierten Namen des Typs zurück, was zur Unterscheidung einer Instanz von einer anderen von geringem Nutzen ist. Die `Publication`-Klasse überschreibt <xref:System.Object.ToString%2A?displayProperty=fullName>, um den Wert der Eigenschaft `Title` zurückzugeben.

Die folgende Abbildung veranschaulicht die Beziehung zwischen unserer Basis-`Publication` -Klasse und der implizit geerbten <xref:System.Object> -Klasse.

![Die Klassen „Object“ und „Publication“](media/publication-class.jpg)

### <a name="the-book-class"></a>Die `Book`-Klasse

Die `Book`-Klasse stellt ein Buch als einen speziellen Typ der Publikation dar. Das folgende Beispiel zeigt den Quellcode für die `Book`-Klasse.

[!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/base-and-derived.cs#2)]

Zusätzlich zu den Membern, die sie von `Publication` erbt, definiert die `Book`-Klasse die folgenden eindeutigen Member und Memberüberschreibungen:

- Zwei Konstruktoren

  Die beiden `Book`-Konstruktoren nutzen gemeinsam drei allgemeine Parameter. Zwei, *title* und *publisher*, entsprechen den Parametern des `Publication`-Konstruktors. Der dritte ist *author*, der in einem privaten Feld `authorName` gespeichert ist. Ein Konstruktor enthält einen *isbn*-Parameter, der in dem privaten Feld `id` gespeichert ist.

  Der erste Konstruktor verwendet das [this](../language-reference/keywords/this.md)-Schlüsselwort, um den anderen Konstruktor aufzurufen. Dies ist ein allgemeines Muster der Konstruktordefinition. Konstruktoren mit weniger Parametern stellen beim Aufrufen des Konstruktors mit der größten Anzahl von Parametern Standardwerte zur Verfügung.

  Der zweite Konstruktor verwendet das [base](../language-reference/keywords/base.md)-Schlüsselwort, um Titel und Herausgebername an den Basisklassenkonstruktor zu übergeben. Wenn Ihr Quellcode keinen expliziten Aufruf eines Basisklassenkonstruktors enthält, stellt der C#-Compiler automatisch einen Aufruf des standardmäßigen oder parameterlosen Konstruktors der Basisklasse bereit.

- Eine schreibgeschützte Eigenschaft `ISBN`, die die ISBN des `Book`-Objekts zurückgibt, eine eindeutige 10- oder 13-stellige Nummer. Die ISBN wird als Argument einem der `Book`-Konstruktoren übergeben und im privaten Feld `id` gespeichert.

- Eine schreibgeschützte Eigenschaft `Author`. Der Autorenname wird als Argument beiden `Book`-Konstruktoren übergeben und im privaten Feld `authorName` gespeichert.

- Zwei schreibgeschützte preisbezogene Eigenschaften, `Price` und `Currency`. Ihre Werte werden in einem Aufruf der `SetPrice`-Methode als Argumente bereitgestellt. Der Preis wird in einem privaten Feld namens `bookPrice` gespeichert. Die Eigenschaft `Currency` ist das dreistellige ISO-Währungssymbol (z.B. USD für den US-Dollar) und befindet sich im privaten Feld `ISOCurrencySymbol`. ISO-Währungssymbole können aus der Eigenschaft <xref:System.Globalization.RegionInfo.ISOCurrencySymbol%2A> abgerufen werden.

- Eine `SetPrice`-Methode, die die Werte der Felder `bookPrice` und `ISOCurrencySymbol` festlegt. Dies sind die Rückgabewerte der Eigenschaften `Price` und `Currency`.

- Überschreibt die `ToString`-Methode (geerbt von `Publication`) und die Methoden <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> und <xref:System.Object.GetHashCode%2A> (geerbt von <xref:System.Object>).

  Sofern sie nicht überschrieben wird, führt die Methode <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> Tests hinsichtlich der Verweisgleichheit durch. D.h., zwei Objektvariablen werden als gleich betrachtet, wenn sie auf das gleiche Objekt verweisen. Andererseits sollten im Fall der `Book`-Klasse zwei `Book`-Objekte gleich sein, wenn sie die gleiche ISBN haben.

  Wenn Sie die <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName>-Methode überschreiben, müssen Sie auch die <xref:System.Object.GetHashCode%2A>-Methode überschreiben. Diese gibt einen Wert zurück, den die Laufzeit zum Speichern von Elementen in Hashauflistungen für einen effizienten Abruf verwendet. Der Hashcode sollte einen Wert zurückgeben, der mit dem Test auf Gleichheit konsistent ist. Da wir <xref:System.Object.Equals%28System.Object%29?displayProperty=fullName> überschrieben haben, sodass `true` zurückgegeben wird, wenn die ISBN-Eigenschaften von zwei `Book`-Objekten gleich sind, geben wir den Hashcode zurück, der durch Aufrufen der <xref:System.String.GetHashCode%2A>-Methode der von der Eigenschaft `ISBN` zurückgegebenen Zeichenfolge berechnet wurde.

Die folgende Abbildung veranschaulicht die Beziehung zwischen der `Book`-Klasse und `Publication`, ihrer Basisklasse.

![Die Klassen „Publication“ und „Book“](media/book-class.jpg)

Wir können jetzt ein `Book`-Objekt instanziieren, sowohl dessen eindeutige als auch geerbte Member aufrufen und es als Argument an eine Methode übergeben, die einen Parameter des Typs `Publication` oder `Book` erwartet, wie im folgenden Beispiel gezeigt.

[!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/use-publication.cs#1)]

## <a name="designing-abstract-base-classes-and-their-derived-classes"></a>Entwerfen abstrakter Basisklassen und der von ihnen abgeleiteten Klassen
<a name="abstract"></a>

Im vorherigen Beispiel definierten wir eine Basisklasse, die eine Implementierung für eine Reihe von Methoden bereitstellte, um abgeleiteten Klassen die gemeinsame Nutzung von Code zu erlauben. In vielen Fällen wird jedoch nicht erwartet, dass die Basisklasse eine Implementierung bereitstellt. Stattdessen ist die Basisklasse eine *abstrakte Klasse*; sie dient als Vorlage, die die Member definiert, die jede abgeleitete Klasse implementieren muss. Im Fall einer abstrakten Basisklasse ist die Implementierung jedes abgeleiteten Typs in der Regel für diesen Typ eindeutig.

Jede geschlossene zweidimensionale geometrische Form besitzt beispielsweise zwei Eigenschaften: den Flächeninhalt, die innere Ausdehnung der Form; und den Umfang, d.h. die Länge der Kanten der Form. Wie diese Eigenschaften berechnet werden, hängt jedoch vollständig von der jeweiligen Form ab. Die Formel zum Berechnen des Umfangs eines Kreises unterscheidet sich z.B. grundlegend von der zum Berechnen des Umfangs eines Dreiecks.

Das folgende Beispiel definiert eine abstrakte Basisklasse mit dem Namen `Shape`, die zwei Eigenschaften definiert: `Area` und `Perimeter`. Beachten Sie, dass zusätzlich zum Markieren der Klasse mit dem [abstract](../language-reference/keywords/abstract.md)-Schlüsselwort auch jeder Instanzmember mit dem [abstract](../language-reference/keywords/abstract.md)-Schlüsselwort markiert wird. In diesem Fall überschreibt `Shape` auch die <xref:System.Object.ToString%2A?displayProperty=fullName> -Methode, um den Namen des Typs anstelle dessen vollqualifizierten Namens zurückzugeben. Außerdem definiert sie zwei statische Member, `GetArea` und `GetPerimeter`, die Aufrufern ermöglichen, mühelos Fläche und Umfang einer Instanz einer beliebigen abgeleiteten Klasse abzurufen. Wenn wir eine Instanz einer abgeleiteten Klasse an eine der beiden Methoden übergeben, ruft die Laufzeit die Methodenüberschreibung der abgeleiteten Klasse auf.

[!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/shape.cs#1)]

Dann können wir einige Klassen von `Shape` ableiten, die bestimmte Formen darstellen. Das folgende Beispiel definiert drei Klassen, `Triangle`, `Rectangle` und `Circle`. Jede verwendet eine Formel, die für die Berechnung von Fläche und Umfang der betreffenden Form eindeutig ist. Einige der abgeleiteten Klassen definieren auch Eigenschaften, z.B. `Rectangle.Diagonal` und `Circle.Diameter`, die für die Form, die sie darstellen, eindeutig sind.

[!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/shape.cs#2)]

Im folgenden Beispiel werden von `Shape` abgeleitete Objekte verwendet. Es instanziiert ein Array von Objekten, die von `Shape` abgeleitet sind, und ruft die statischen Methoden der `Shape`-Klasse auf, deren Umschließungen `Shape`-Eigenschaftswerte zurückgeben. Beachten Sie, dass die Laufzeit Werte aus den überschriebenen Eigenschaften der abgeleiteten Typen abruft. Das Beispiel wandelt auch jedes `Shape` -Objekt im Array in seinen abgeleiteten Typ um, und wenn die Umwandlung erfolgreich ist, ruft es Eigenschaften dieser bestimmten Unterklasse von `Shape` auf. 

[!code-csharp[Vererbung](../../../samples/snippets/csharp/tutorials/inheritance/shape.cs#3)]

## <a name="see-also"></a>Siehe auch

[Klassen und Objekte](../tour-of-csharp/classes-and-objects.md)   
[Vererbung (C#-Programmierhandbuch)](../programming-guide/classes-and-structs/inheritance.md)

