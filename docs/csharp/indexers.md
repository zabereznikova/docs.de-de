---
title: Indexer
description: Erfahren Sie mehr über C#-Indexer und wie sie indizierte Eigenschaften, d.h. Eigenschaften, auf die mit mindestens einem Argument verwiesen wird, implementieren.
ms.date: 06/20/2016
ms.technology: csharp-fundamentals
ms.assetid: 0e9496da-e766-45a9-b92b-91820d4a350e
ms.openlocfilehash: 966483e80d8dd0421dce1b7fabdb0d443d73a0fc
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450881"
---
# <a name="indexers"></a>Indexer

*Indexer* sind ähnlich wie Eigenschaften. In vielen Aspekten bauen Indexer genauso wie [Eigenschaften](properties.md) auf den gleichen Sprachfunktionen auf. Indexer ermöglichen *indizierte* Eigenschaften: Eigenschaften, auf die von mindestens einem Argument verwiesen wird. Diese Argumente stellen einen Index in einer Auflistung von Werten bereit.

## <a name="indexer-syntax"></a>Indexersyntax

Sie können mithilfe eines Variablennamens und eckiger Klammern auf einen Indexer zugreifen. Geben Sie die Indexerargumente innerhalb der Klammern ein:

```csharp
var item = someObject["key"];
someObject["AnotherKey"] = item;
```

Sie können Indexer deklarieren, in dem sie das Schlüsselwort `this` als Eigenschaftenname verwenden und die Argumente in eckigen Klammern deklarieren. Diese Deklaration stimmt mit dem Gebrauch in oben stehendem Abschnitt überein:

```csharp
public int this[string key]
{
    get { return storage.Find(key); }
    set { storage.SetAt(key, value); }
}
```

Dieses erste Beispiel veranschaulicht die Beziehung zwischen der Syntax der Eigenschaften und der Indexer. Diese Analogie wirkt sich auf die meisten Syntaxregeln für Indexer auf. Indexer können beliebige gültige Zugriffsmodifizierer aufweisen (public, protected internal, protected, internal, private oder private protected). Sie können versiegelt, virtuell oder abstrakt sein. Bei Eigenschaften können Sie verschiedene Zugriffsmodifizierer für die Get- und Set-Accessoren eines Indexers angeben.
Außerdem können Sie schreibgeschützte Indexer (indem Sie die set-Zugriffsmethode auslassen) oder lesegeschützte Indexer (indem Sie die get-Zugriffsmethode auslassen) angeben.

Fast alles, was Sie von der Arbeit mit Eigenschaften kennen, können sie auch für Indexer anwenden. Die einzige Ausnahme von dieser Regel sind *automatisch implementierte Eigenschaften*. Der Compiler kann nicht immer angemessenen Speicher für einen Indexer generieren.

Indexer unterscheiden sich durch das Vorhandensein von Argumenten, die auf ein Element in einem Satz von Elementen verweisen, von Eigenschaften. Sie können mehrere Indexer in einem Typ definieren, solange die Argumentauflistung für jeden Indexer eindeutig ist. In den folgenden Szenarios erfahren Sie mehr über das Verwenden von einem oder mehreren Indexern in einer Klassendefinition. 

## <a name="scenarios"></a>Szenarien

Sie definieren *Indexer* in Ihrem Typ, wenn dessen API eine Auflistung modelliert, in der Sie die Argumente der Auflistung definieren. Ihre Indexer ordnen möglicherweise direkt zu Ihren Auflistungstypen zu, die Teil des .NET Core Frameworks sind. Ihr Typ hat möglicherweise andere Verpflichtungen als nur das Modellieren einer Auflistung.
Mit Indexern können Sie die API bereitstellen, die mit der Abstraktion Ihres Typs übereinstimmt, ohne die inneren Details offen zu legen, wie die Werte dieser Abstraktion gespeichert oder berechnet werden.

Die häufigsten Szenarios für das Verwenden von *Indexern*. Sie können auf den [Beispielordner für Indexer](https://github.com/dotnet/samples/tree/master/csharp/indexers) zugreifen. Anweisungen zum Herunterladen finden Sie unter [Beispiele und Lernprogramme](../samples-and-tutorials/index.md#viewing-and-downloading-samples).

### <a name="arrays-and-vectors"></a>Arrays und Vektoren

Eines der häufigsten Szenarios beim Erstellen von Indexern ist, wenn Ihr Typ ein Array oder einen Vektor modelliert. Sie können einen Indexer erstellen, um eine geordnete Datenliste zu modellieren. 

Der Vorteil beim Erstellen eines eigenen Indexers ist die Tatsache, dass Sie den Speicher für diese Auflistung an Ihre Bedürfnisse anpassen können. Stellen Sie sich ein Szenario vor, in dem Ihr Typ historische Daten modelliert, die zu groß sind, um sie auf einmal in den Speicher zu laden. Sie müssen Abschnitte der Auflistung nach Verbrauch laden und entladen. Das folgende Beispiel veranschaulicht dieses Verhalten. Es meldet, wie viele Datenpunkte vorhanden sind. Es erstellt Seiten, die auf Abruf Abschnitte der Daten anzeigen. Es entfernt Seiten aus dem Speicher, um Platz für Seiten zu schaffen, die für eine aktuelle Abfrage benötigt werden.

```csharp
public class DataSamples
{
    private class Page
    {
        private readonly List<Measurements> pageData = new List<Measurements>();
        private readonly int startingIndex;
        private readonly int length;
        private bool dirty;
        private DateTime lastAccess;

        public Page(int startingIndex, int length)
        {
            this.startingIndex = startingIndex;
            this.length = length;
            lastAccess = DateTime.Now;

            // This stays as random stuff:
            var generator = new Random();
            for(int i=0; i < length; i++)
            {
                var m = new Measurements
                {
                    HiTemp = generator.Next(50, 95),
                    LoTemp = generator.Next(12, 49),
                    AirPressure = 28.0 + generator.NextDouble() * 4
                };
                pageData.Add(m);
            }
        }
        public bool HasItem(int index) =>
            ((index >= startingIndex) &&
            (index < startingIndex + length));

        public Measurements this[int index]
        {
            get
            {
                lastAccess = DateTime.Now;
                return pageData[index - startingIndex];
            }
            set
            {
                pageData[index - startingIndex] = value;
                dirty = true;
                lastAccess = DateTime.Now;
            }
        }

        public bool Dirty => dirty;
        public DateTime LastAccess => lastAccess;
    }

    private readonly int totalSize;
    private readonly List<Page> pagesInMemory = new List<Page>();

    public DataSamples(int totalSize)
    {
        this.totalSize = totalSize;
    }

    public Measurements this[int index]
    {
        get
        {
            if (index < 0)
                throw new IndexOutOfRangeException("Cannot index less than 0");
            if (index >= totalSize)
                throw new IndexOutOfRangeException("Cannot index past the end of storage");

            var page = updateCachedPagesForAccess(index);
            return page[index];
        }
        set
        {
            if (index < 0)
                throw new IndexOutOfRangeException("Cannot index less than 0");
            if (index >= totalSize)
                throw new IndexOutOfRangeException("Cannot index past the end of storage");
            var page = updateCachedPagesForAccess(index);

            page[index] = value;
        }
    }

    private Page updateCachedPagesForAccess(int index)
    {
        foreach (var p in pagesInMemory)
        {
            if (p.HasItem(index))
            {
                return p;
            }
        }
        var startingIndex = (index / 1000) * 1000;
        var newPage = new Page(startingIndex, 1000);
        addPageToCache(newPage);
        return newPage;
    }

    private void addPageToCache(Page p)
    {
        if (pagesInMemory.Count > 4)
        {
            // remove oldest non-dirty page:
            var oldest = pagesInMemory
                .Where(page => !page.Dirty)
                .OrderBy(page => page.LastAccess)
                .FirstOrDefault();
            // Note that this may keep more than 5 pages in memory
            // if too much is dirty
            if (oldest != null)
                pagesInMemory.Remove(oldest);
        }
        pagesInMemory.Add(p);
    }
}
```

Sie können diesem Entwurfsausdruck folgen, um jede beliebige Auflistungsart dort zu modellieren, wo es gute Gründe gibt, nicht den gesamten Datensatz in eine Auflistung im Speicher zu laden. Beachten Sie, dass die Klasse `Page` eine private geschachtelte Klasse ist, die nicht Teil der öffentlichen Schnittstelle ist. Diese Informationen sind für jeden Benutzer der Klasse verborgen.

### <a name="dictionaries"></a>Wörterbücher

Ein weiteres häufiges Szenario ist, wenn Sie ein Wörterbuch oder eine Zuordnung modellieren möchten. In diesem Szenario speichert Ihr Typ Werte nach Schlüsseln, typischerweise Textschlüssel. In diesem Beispiel wird ein Wörterbuch erstellt, das Befehlszeilenargumente [Lambdaausdrücken](delegates-overview.md) zuordnet, die diese Optionen verwalten. In folgenden Beispiel werden zwei Klassen gezeigt: eine `ArgsActions`-Klasse, die eine Befehlszeilenoption einem `Action`-Delegaten zuordnet, und ein `ArgsProcessor`, um mit jeder `ArgsActions` eine `Action` auszuführen, wenn es auf diese Option trifft.

```csharp
public class ArgsProcessor
{
    private readonly ArgsActions actions;

    public ArgsProcessor(ArgsActions actions)
    {
        this.actions = actions;
    }

    public void Process(string[] args)
    {
        foreach(var arg in args)
        {
            actions[arg]?.Invoke();
        }
    }

}
public class ArgsActions
{
    readonly private Dictionary<string, Action> argsActions = new Dictionary<string, Action>();

    public Action this[string s]
    {
        get
        {
            Action action;
            Action defaultAction = () => {} ;
            return argsActions.TryGetValue(s, out action) ? action : defaultAction;
        }
    }

    public void SetOption(string s, Action a)
    {
        argsActions[s] = a;
    }
}
```

In diesem Beispiel ordnet die `ArgsAction`-Auflistung nah an der zugrundeliegenden Auflistung zu.
`get` legt fest, ob eine gegebene Option konfiguriert wurde. Falls dem so ist, gibt es die mit dieser Option verknüpfte `Action` zurück. Falls dem nicht so ist, gibt es eine `Action` zurück, die keine Auswirkungen hat. Die öffentliche Zugriffsmethode enthält keine `set`-Zugriffsmethode. Stattdessen enthält Sie den Entwurf, der eine öffentliche Methode für das Festlegen von Optionen verwendet.

### <a name="multi-dimensional-maps"></a>Mehrdimensionale Zuordnungen

Sie können Indexer erstellen, die mehrere Argumente verwenden. Zusätzlich sind müssen diese Argumente nicht denselben Typen aufweisen. Nachfolgend sehen Sie zwei Beispiele.   

Das erste Beispiel zeigt eine Klasse, die Werte einer Mandelbrot-Menge generiert. Weitere Informationen zur Mathematik der Menge finden Sie in [diesem Artikel](https://en.wikipedia.org/wiki/Mandelbrot_set). Der Indexer verwendet zwei double-Werte, um einen Punkt auf der X-Y-Ebene zu definieren.
Die get-Zugriffsmethode berechnet die Anzahl der Iterationen, bis ein Punkt festgelegt wird, der außerhalb der Menge liegt. Wenn die maximale Zahl an Iterationen erreicht ist, befindet sich der Punkt in der Menge, und der Wert „maxIterations“ der Klasse wird zurückgegeben. (Die vom Computer generierten Bilder, die durch die Mandelbrot-Menge bekannt wurden, definieren Farben für die Anzahl von Iterationen, die benötigt werden, um festzustellen, das sich ein Punkt außerhalb der Menge befindet.)

```csharp
public class Mandelbrot
{
    readonly private int maxIterations;

    public Mandelbrot(int maxIterations)
    {
        this.maxIterations = maxIterations;
    }

    public int this [double x, double y]
    {
        get
        {
            var iterations = 0;
            var x0 = x;
            var y0 = y;

            while ((x*x + y * y < 4) &&
                (iterations < maxIterations))
            {
                var newX = x * x - y * y + x0;
                y = 2 * x * y + y0;
                x = newX;
                iterations++;
            }
            return iterations;
        }
    }
}
```

Die Mandelbrot-Menge definiert Werte an jeder (x, y)-Koordinaten für reelle Zahlenwerte.
Dadurch wird ein Wörterbuch definiert, das eine unendliche Anzahl von Werten enthalten könnte. Deshalb liegt kein Speicher hinter der Menge. Stattdessen berechnet diese Klasse den Wert für jeden Punkt, wenn die `get`-Zugriffsmethode von Code aufgerufen wird. Es wird kein zugrundeliegender Speicher verwendet.

Hier ist ein letztes Beispiel für den Gebrauch von Indexern, in dem der Indexer mehrere Argumente mit unterschiedlichen Typen akzeptiert. Stellen Sie sich ein Programm vor, dass Daten zu historischen Temperaturen verwaltet. Dieser Indexer verwendet eine Stadt und ein Datum, um die höchste und niedrigste Temperatur für diesen Ort festzulegen oder abzurufen:

```csharp
using DateMeasurements = 
    System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements = 
    System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;

public class HistoricalWeatherData
{
    readonly CityDataMeasurements storage = new CityDataMeasurements();

    public Measurements this[string city, DateTime date]
    {
        get
        {
            var cityData = default(DateMeasurements);

            if (!storage.TryGetValue(city, out cityData))
                throw new ArgumentOutOfRangeException(nameof(city), "City not found");

            // strip out any time portion:
            var index = date.Date;
            var measure = default(Measurements);
            if (cityData.TryGetValue(index, out measure))
                return measure;
            throw new ArgumentOutOfRangeException(nameof(date), "Date not found");
        }
        set
        {
            var cityData = default(DateMeasurements);

            if (!storage.TryGetValue(city, out cityData))
            {
                cityData = new DateMeasurements();
                storage.Add(city, cityData);
            }

            // Strip out any time portion:
            var index = date.Date;
            cityData[index] = value;
        }
    }
}
```

In diesem Beispiel wird ein Indexer erstellt, der Wetterdaten zwei Argumenten zuordnet: eine Stadt (repräsentiert durch `string`) und ein Datum (repräsentiert durch `DateTime`). Der interne Speicher verwendet zwei `Dictionary`-Klassen, die das zweidimensionale Wörterbuch repräsentieren. Die öffentliche API repräsentiert nicht mehr den zugrundeliegenden Speicher. Stattdessen können Sie mit den Sprachfunktionen der Indexer eine öffentliche Schnittstelle erstellen, die Ihre Abstraktion repräsentiert, auch wenn der zugrundeliegende Speicher unterschiedliche Kernauflistungstypen verwenden muss.

Es gibt zwei Teile dieses Codes, die Entwicklern möglicherweise unbekannt sind. Diese zwei `using`-Anweisungen:

```csharp
using DateMeasurements = System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>;
using CityDataMeasurements = System.Collections.Generic.Dictionary<string, System.Collections.Generic.Dictionary<System.DateTime, IndexersSamples.Common.Measurements>>;
```

erstellen einen *Alias* für einen konstruierter generischen Typen. Durch diese Anweisungen kann ein Code später die deskriptiveren Namen `DateMeasurements` und `CityDateMeasurements` statt der generischen Konstruktion von `Dictionary<DateTime, Measurements>` und `Dictionary<string, Dictionary<DateTime, Measurements> >` verwenden. Diese Konstruktion erfordert den Gebrauch des vollqualifizierten Typnamens auf der rechten Seite des `=`-Zeichens.

In der zweiten Vorgehensweise entfernen Sie die Uhrzeitteile jedes `DateTime`-Objekts, das verwendet wird, um in die Auflistungen zu indizieren. .NET bietet keinen reinen Datumstyp.
Entwickler verwenden den `DateTime`-Typ, aber die `Date`-Eigenschaft, um sicherzustellen, das jedes `DateTime`-Objekt dieses Tages gleich ist.

## <a name="summing-up"></a>Schlussbemerkung

Sie sollten Indexer immer dann erstellen, wenn Sie ein Element, das einer Eigenschaft ähnelt, in Ihrer Klasse vorliegen haben, und wenn diese Eigenschaft nicht einen einzelnen Wert repräsentiert, sondern eine Auflistung von Werten, in der jedes einzelne Element durch einen Satz von Argumenten identifiziert wird. Diese Argumente können eindeutig identifizieren, auf welches Element in der Auflistung verwiesen werden sollte.
Indexer erweitern das Konzept der [Eigenschaften](properties.md), bei denen ein Member wie ein Datenelement außerhalb der Klasse behandelt wird, sondern wie eine Methode innerhalb der Klasse. Indexer ermöglichen es Argumenten, ein einzelnes Element in einer Eigenschaft zu finden, das einen Satz von Elementen repräsentiert.
