---
title: Übersicht über das Modell der attributierten Programmierung (MEF)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MEF, attributed programming model
- attributed programming model [MEF]
ms.assetid: 49b787ff-2741-4836-ad51-c3017dc592d4
ms.openlocfilehash: c6b1093d2e821a55cc5513b077a270748a780b71
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347628"
---
# <a name="attributed-programming-model-overview-mef"></a>Übersicht über das Modell der attributierten Programmierung (MEF)

Im Managed Extensibility Framework (MEF) ist ein *Programmiermodell* eine besondere Methode, den Satz der konzeptionellen Objekte zu definieren, mit denen MEF ausgeführt wird. Diese konzeptionellen Objekte umfassen Teile, Importe und Exporte. MEF verwendet diese Objekte, gibt jedoch nicht an, wie sie dargestellt werden sollen. Daher ist eine Vielzahl von Programmiermodellen möglich, einschließlich benutzerdefinierter Programmiermodelle.

Das in MEF verwendete Standardprogrammiermodell ist das *Modell der attributierten Programmierung*. Im Modell der attributierten Programmierung werden Teile, Importe, Exporte und andere Objekte mit Attributen definiert, die gewöhnliche .NET Framework-Klassen ergänzen. Dieses Thema erläutert, wie mit den Attributen, die vom Modell der attributierten Programmierung angeboten werden, eine MEF-Anwendung erstellt wird.

<a name="import_and_export_basics"></a>

## <a name="import-and-export-basics"></a>Importieren und Exportieren – Grundlagen

Ein *Export* ist ein Wert, den ein Teil anderen Teilen im Container zur Verfügung stellt, und ein *Import* ist eine Anforderung eines Teils an den Container, eine Auffüllung mit den verfügbaren Exporten vorzunehmen. Im Modell der attributierten Programmierung werden Importe und Exporte durch Ergänzen von Klassen oder Membern mit dem `Import` -Attribut und dem `Export` -Attribut deklariert. Das `Export` -Attribut kann eine Klasse, ein Feld, eine Eigenschaft oder eine Methode ergänzen, während das `Import` -Attribut ein Feld, eine Eigenschaft oder einen Konstruktorparameter ergänzen kann.

Damit ein Import mit einem Export verglichen werden kann, müssen Import und Export den gleichen *Vertrag*besitzen. Der Vertrag besteht aus einer Zeichenfolge, die als *Vertragsname*bezeichnet wird, und aus dem Typ des exportierten oder importierten Objekts, das als *Vertragstyp*bezeichnet wird. Nur, wenn sowohl der Vertragsname als auch der Vertragstyp übereinstimmen, erfüllt ein Export die Bedingungen für einen bestimmten Import.

Einer der oder beide Vertragsparameter können implizit oder explizit sein. Im folgenden Code wird eine Klasse gezeigt, die einen grundlegenden Import deklariert.

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

In diesem Import ist dem `Import` -Attribut weder ein Vertragstyp noch ein Vertragsnamensparameter zugeordnet. Daher werden beide in der ergänzten Eigenschaft abgeleitet. In diesem Fall ist der Vertragstyp `IMyAddin`, und der Vertragsname ist eine eindeutige aus dem Vertragstyp erstellte Zeichenfolge. (Anders ausgedrückt stimmt der Vertragsname nur mit Exporten überein, deren Namen ebenfalls vom Typ `IMyAddin`abgeleitet werden.)

Nachfolgend wird ein Export angezeigt, der dem vorherigen Import entspricht.

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

In diesem Export ist der Vertragstyp `IMyAddin` , da er als Parameter des `Export` -Attributs angegeben wird. Der exportierte Typ muss entweder mit dem Vertragstyp übereinstimmen, vom Vertragstyp abgeleitet werden oder den Vertragstyp implementieren, wenn es sich um eine Schnittstelle handelt. In diesem Export implementiert der tatsächliche `MyLogger` -Typ die `IMyAddin`-Schnittstelle. Der Vertragsname wird vom Vertragstyp abgeleitet, d. h., dass der Export dem vorherigen Import entspricht.

> [!NOTE]
> Exporte und Importe sollten normalerweise für öffentliche Klassen oder Member deklariert werden. Andere Deklarationen werden unterstützt, aber das Exportieren oder Importieren eines privaten, geschützten oder internen Members unterbricht das Isolationsmodell für den Teil und wird daher nicht empfohlen.

Der Vertragstyp muss für Export und Import genau zusammenpassen, damit er als Übereinstimmung betrachtet wird. Betrachten Sie den folgenden Export.

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

In diesem Export ist der Vertragstyp `MyLogger` anstatt `IMyAddin`. Obwohl `MyLogger``IMyAddin` implementiert und daher in ein `IMyAddin`-Objekt umgewandelt werden kann, entspricht dieser Export nicht dem vorherigen Import, da die Vertragstypen nicht identisch sind.

Im Allgemeinen ist es nicht notwendig, den Vertragsnamen anzugeben, und die meisten Verträge sollten im Hinblick auf den Vertragstyp und die Metadaten definiert werden. Unter bestimmten Umständen ist es jedoch wichtig, den Vertragsnamen direkt anzugeben. Der häufigste Fall ist, wenn eine Klasse mehrere Werte exportiert, die gemeinsam einen allgemeinen Typ verwenden, z. B. Primitive. Der Vertragsname kann als erster Parameter des `Import` -Attributs oder des `Export` -Attributs angegeben werden. Im folgenden Code werden ein Import und ein Export mit dem angegebenen Vertragsnamen `MajorRevision`gezeigt.

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

Wenn der Vertragstyp nicht angegeben wird, wird er immer noch vom Typ des Imports oder Exports abgeleitet. Auch wenn der Vertragsname explizit angegeben wird, muss der Vertragstyp auch genau für den Import übereinstimmen, um als Übereinstimmung betrachtet zu werden. Wenn das `MajorRevision` -Feld z. B. eine Zeichenfolge wäre, würden die abgeleiteten Vertragstypen nicht übereinstimmen, und der Export würde nicht mit dem Import übereinstimmen, obwohl er den gleichen Vertragsnamen besitzt.

### <a name="importing-and-exporting-a-method"></a>Importieren und Exportieren einer Methode

Das `Export` -Attribut kann eine Methode ebenso wie eine Klasse, Eigenschaft oder Funktion ergänzen. Für Methodenexporte muss ein Vertragstyp oder Vertragsname angegeben werden, da der Typ nicht abgeleitet werden kann. Der angegebene Typ kann entweder ein benutzerdefinierter Delegat oder ein generischer Typ sein, wie z. B. `Func`. Die folgende Klasse exportiert eine Methode mit dem Namen `DoSomething`.

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

In dieser Klasse erhält die `DoSomething` -Methode einen einzelnen `int` -Parameter und gibt `string`zurück. Damit eine Übereinstimmung mit dem Export vorliegt, muss der importbezogene Teil einen entsprechenden Member deklarieren. Die folgende Klasse importiert die `DoSomething` -Methode.

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

Weitere Informationen zur Verwendung des `Func<T, T>` -Objekts finden Sie unter <xref:System.Func%602>.

<a name="types_of_imports"></a>

## <a name="types-of-imports"></a>Importtypen

MEF unterstützt mehrere Importtypen, einschließlich "Dynamisch", "Verzögert", "Erforderlich" und "Optional".

### <a name="dynamic-imports"></a>Dynamische Importe

In einigen Fällen soll die importierende Klasse mit Exporten eines beliebigen Typs übereinstimmen, die einen bestimmten Vertragsnamen besitzen. In diesem Szenario kann die Klasse einen *dynamischen Import*deklarieren. Der folgende Import entspricht jeden Export mit dem Vertragsnamen "TheString".

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

Wenn der Vertragstyp vom `dynamic` -Schlüsselwort abgeleitet wird, stimmt er mit einem beliebigen Vertragstyp überein. In diesem Fall sollte für einen Import **immer** ein Vertragsname zur Prüfung von Übereinstimmungen mit Exporten angegeben werden. (Ohne Angabe eines Vertragsnamens wird angenommen, dass für den Import keine übereinstimmenden Export vorliegen.) Beide der folgenden Exporte entsprechen dem vorherigen Import.

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

Offensichtlich muss die importierende Klasse für den Umgang mit einem Objekt eines beliebigen Typs vorbereitet werden.

### <a name="lazy-imports"></a>Verzögerte Importe

In einigen Fällen erfordert die importierende Klasse möglicherweise einen indirekten Verweis auf das importierte Objekt, damit das Objekt nicht sofort instanziiert wird. In diesem Szenario kann die Klasse einen *verzögerten Import* mit dem Vertragstyp `Lazy<T>`deklarieren. Die folgende importierende Eigenschaft deklariert einen verzögerten Import.

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

Aus Sicht der Kompositions-Engine wird der Vertragstyp `Lazy<T>` als identisch mit dem Vertragstyp `T`eingestuft. Daher entspricht der vorherige Import dem folgenden Export.

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

Der Vertragsname und Vertragstyp kann im `Import` -Attribut für einen verzögerten Import angegeben werden (siehe Abschnitt "Grundlegende Importe und Exporte").

### <a name="prerequisite-imports"></a>Erforderliche Importe

Exportierte MEF-Teile werden in der Regel von der Kompositions-Engine erstellt, und zwar als Antwort auf eine direkte Anforderung oder die Notwendigkeit, einen übereinstimmenden Import aufzufüllen. Standardmäßig verwendet die Kompositions-Engine beim Erstellen eines Teils den parameterlosen Konstruktor. Damit die Engine einen anderen Konstruktor verwendet, können Sie sie mit dem `ImportingConstructor`-Attribut markieren.

Jeder Teil verfügt möglicherweise nur über einen Konstruktor für die Verwendung durch die Kompositions-Engine. Wenn kein parameterloser Konstruktor und kein Attribut vom Typ `ImportingConstructor` oder aber mehrere Attribute vom Typ `ImportingConstructor` angegeben werden, tritt ein Fehler auf.

Um die Parameter eines Konstruktors auszufüllen, der mit dem `ImportingConstructor` -Attribut markiert ist, werden alle diese Parameter automatisch als Importe deklariert. Dies ist eine einfache Möglichkeit zum Deklarieren von Importen, die während der Teileinitialisierung verwendet werden. Die folgende Klasse verwendet `ImportingConstructor` , um einen Import zu deklarieren.

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

Standardmäßig verwendet das `ImportingConstructor` -Attribut für alle Parameterimporte abgeleitete Vertragstypen und Vertragsnamen. Es ist möglich, dies durch das Ergänzen der Parameter mit `Import` -Attributen zu überschreiben, die anschließend explizit den Vertragstyp und den Vertragsnamen definieren können. Im folgenden Code wird ein Konstruktor gezeigt, der diese Syntax für das Importieren einer abgeleiteten Klasse anstelle einer übergeordneten Klasse verwendet.

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

Insbesondere sollten Sie bei Auflistungsparametern vorsichtig sein. Wenn Sie z. B. `ImportingConstructor` für einen Konstruktor mit einem Parameter des Typs `IEnumerable<int>`angeben, entspricht der Import einem einzelnen Export vom Typ `IEnumerable<int>`und nicht einer Gruppe von Exporten vom Typ `int`. Um eine Übereinstimmung mit einer Gruppe von Exporten vom Typ `int`zu erzielen, muss der Parameter mit dem `ImportMany` -Attribut ergänzt werden.

Parameter, die vom `ImportingConstructor` -Attribut als Importe deklariert wurden, werden ebenfalls als *erforderliche Importe*markiert. MEF gestattet normalerweise Exporte und Importe, um einen *Zyklus*zu bilden. Bei einem Zyklus importiert z. B. Objekt A das Objekt B, das wiederum Objekt A importiert. Unter normalen Umständen ist ein Zyklus kein Problem, und der Kompositionscontainer erstellt beide Objekte ordnungsgemäß.

Wenn ein importierter Wert vom Konstruktor eines Teils benötigt wird, kann dieses Objekt nicht an einem Zyklus teilnehmen. Wenn Objekt A erfordert, dass Objekt B erstellt wird, bevor es selbst erstellt werden kann, und wenn Objekt B Objekt A importiert, kann der Zyklus nicht aufgelöst werden, und ein Kompositionsfehler tritt auf. Für Konstruktorparameter deklarierte Importe sind daher erforderliche Importe, die alle ausgefüllt werden müssen, bevor die Exporte aus dem Objekt, das diese benötigt, verwendet werden können.

### <a name="optional-imports"></a>Optionale Importe

Das `Import` -Attribut gibt eine Anforderung an, damit der Teil funktionsfähig ist. Wenn ein Import nicht erfüllt werden kann, schlägt die Komposition dieses Teils fehl, und der Teil ist nicht verfügbar.

Sie können mit der *-Eigenschaft angeben, dass ein Import* optional `AllowDefault` ist. In diesem Fall ist die Komposition erfolgreich, auch wenn der Import mit keinen verfügbaren Exporten übereinstimmt, und die importierende Eigenschaft wird auf die Standardeinstellung für den Eigenschaftentyp festgelegt (`null` für Objekteigenschaften, `false` für boolesche Werte oder 0 (null) für numerische Eigenschaften). Die folgende Klasse verwendet einen optionalen Import.

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

### <a name="importing-multiple-objects"></a>Importieren von mehreren Objekten

Das `Import` -Attribut wird nur erstellt, wenn es mit genau einem Export übereinstimmt. In anderen Fällen treten Kompositionsfehler auf. Um mehr als einen Export zu importieren, der mit dem gleichen Vertrag übereinstimmt, verwenden Sie das `ImportMany` -Attribut. Mit diesem Attribut markierte Importe sind immer optional. Die Komposition schlägt nicht z. B. nicht fehl, wenn keine übereinstimmenden Exporte vorhanden sind. Die folgende Klasse importiert eine beliebige Anzahl von Exporten vom Typ `IMyAddin`.

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

Auf das importierte Array kann mit normaler `IEnumerable<T>` -Syntax und entsprechenden normalen Methoden zugegriffen werden. Es ist auch möglich, stattdessen ein normales Array (`IMyAddin[]`) zu verwenden.

Dieses Muster kann sehr wichtig sein, wenn Sie es in Verbindung mit der `Lazy<T>` -Syntax verwenden. Mit `ImportMany`, `IEnumerable<T>`und `Lazy<T>`können Sie z. B. indirekte Verweise auf eine beliebige Anzahl von Objekten importieren und nur die Objekte instanziieren, die notwendig werden. Die folgende Klasse zeigt dieses Muster.

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

## <a name="avoiding-discovery"></a>Verhindern der Erkennung von Teilen

In einigen Fällen möchten Sie unter Umständen verhindern, dass ein Teil als Teil eines Katalogs erkannt wird. Der Teil kann z. B. eine Basisklasse sein, von der geerbt werden soll, die aber nicht zu verwenden ist. Es gibt zwei Möglichkeiten, dies zu erreichen. Zuerst können Sie das `abstract` -Schlüsselwort für die Teilklasse verwenden. Abstrakte Klassen stellen nie Exporte bereit, obwohl sie geerbte Exporte für Klassen bereitstellen können, die von ihnen abgeleitet werden.

Wenn die Klasse nicht als abstrakt festgelegt werden kann, können Sie sie mit dem `PartNotDiscoverable` -Attribut ergänzen. Ein mit diesem Attribut ergänzter Teil wird in keine Kataloge eingeschlossen. Diese Muster werden im folgenden Beispiel dargestellt. `DataOne` wird vom Katalog gefunden. Da `DataTwo` abstrakt ist, wird es nicht gefunden. Da `DataThree` das `PartNotDiscoverable` -Attribut verwendete, wird es nicht gefunden.

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

## <a name="metadata-and-metadata-views"></a>Metadaten und Metadatenansichten

Exporte können zusätzliche Informationen über sich selbst bereitstellen, die als *Metadaten*bezeichnet wurden. Metadaten können verwendet werden, um Eigenschaften des exportierten Objekts an den importierenden Teil zu übermitteln. Der importierende Teil kann anhand dieser Daten entscheiden, welche Exporte verwendet werden sollen, oder um Informationen zu einem Export zu sammeln, ohne ihn erstellen zu müssen. Aus diesem Grund muss ein Import verzögert sein, um Metadaten verwenden zu können.

Um Metadaten zu verwenden, wird in der Regel eine Schnittstelle mit der Bezeichnung *Metadatenansicht*deklariert, durch die deklariert wird, welche Metadaten verfügbar sind. Die Metadaten-Ansichtsschnittstelle darf nur über Eigenschaften verfügen, und diese Eigenschaften müssen `get` -Accessoren besitzen. Die folgende Schnittstelle ist eine beispielhafte Metadatenansicht.

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

Es ist auch möglich, als Metadatenansicht eine generische Auflistung ( `IDictionary<string, object>`) zu verwenden, doch dadurch gehen die Vorteile der Typüberprüfung verloren, weshalb dies vermieden werden sollte.

Normalerweise sind alle in der Metadatenansicht genannten Eigenschaften erforderlich, und alle Exporte, die nicht darüber verfügen, werden nicht als Übereinstimmung betrachtet. Das `DefaultValue` -Attribut gibt an, dass eine Eigenschaft optional ist. Wenn die Eigenschaft nicht eingeschlossen ist, wird ihr der als Parameter von `DefaultValue`angegebene Standardwert zugewiesen. Die folgenden zwei Klassen sind verschiedene mit Metadaten ergänzte Klassen. Beide Klassen entsprechen der vorherigen Metadatenansicht.

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

Metadaten werden nach dem `Export` -Attribut mithilfe des `ExportMetadata` -Attributs ausgedrückt. Jedes Metadatenelement besteht aus einem Name-Wert-Paar. Der Namensteil der Metadaten muss mit dem Namen der entsprechenden Eigenschaft in der Metadatenansicht übereinstimmen, und der Wert wird der Eigenschaft zugewiesen.

Es handelt sich um den Importer, der die zu verwendende Metadatenansicht angibt (sofern zutreffend). Ein Import mit Metadaten wird als verzögerter Import deklariert, wobei die Metadatenschnittstelle der zweite Typparameter für `Lazy<T,T>`ist. Die folgende Klasse importiert den vorherigen Teil mit Metadaten.

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

In vielen Fällen sollen Metadaten mit dem `ImportMany` -Attribut kombiniert werden, um die verfügbaren Importe zu analysieren und nur einen davon auszuwählen und zu instanziieren, oder um eine Auflistung zu filtern, um eine bestimmte Bedingung zu erfüllen. Die folgende Klasse instanziiert nur `IPlugin` -Objekte, die über den `Name` -Wert "Logger" verfügen.

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

## <a name="import-and-export-inheritance"></a>Importieren und Exportieren von Vererbung

Wenn eine Klasse von einem Teil erbt, wird diese Klasse möglicherweise ebenfalls ein Teil. Importe werden immer von Unterklassen geerbt. Daher ist eine Unterklasse eines Teils immer ein Teil, und zwar mit den gleichen Importen wie die übergeordnete Klasse.

Mit dem `Export` -Attribut deklarierte Exporte werden nicht von Unterklassen geerbt. Ein Teil kann sich jedoch selbst mit dem `InheritedExport` -Attribut exportieren. Unterklassen des Teils erben den gleichen Export und stellen ihn bereit, einschließlich des Vertragsnamens und des Vertragstyps. Im Gegensatz zu einem `Export` -Attribut kann `InheritedExport` nur auf Klassen- und nicht auf Memberebene übernommen werden. Daher können Exporte auf Memberebene nie geerbt werden.

Die folgenden vier Klassen veranschaulichen die Prinzipien des Importierens und Exportierens von Vererbung. `NumTwo` erbt von `NumOne`, sodass `NumTwo``IMyData` importiert. Gewöhnliche Exporte werden nicht geerbt, sodass `NumTwo` keine Daten exportiert. `NumFour` erbt von `NumThree`. Da `NumThree``InheritedExport` verwendete, besitzt `NumFour` einen Export mit dem Vertragstyp `NumThree`. Exporte auf Memberebene werden nie geerbt, sodass `IMyData` nicht exportiert wird.

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

Wenn Metadaten einem `InheritedExport` -Attribut zugeordnet sind, werden diese Metadaten ebenfalls geerbt. (Weitere Informationen finden Sie im Abschnitt "Metadaten und Metadatenansichten".) Geerbte Metadaten können nicht von der Unterklasse geändert werden. Allerdings kann die Unterklasse durch erneutes Deklarieren des `InheritedExport` -Attributs mit dem gleichen Vertragsnamen und Vertragstyp (jedoch mit neuen Metadaten) die geerbten Metadaten durch neue Metadaten ersetzen. Die folgende Klasse verdeutlicht dieses Prinzip. Der `MegaLogger` -Teil erbt von `Logger` und schließt das `InheritedExport` -Attribut ein. Da `MegaLogger` neue Metadaten mit dem Namen "Status" erneut deklariert, erbt es nicht die Namens- und Versionsmetadaten von `Logger`.

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

Wenn Sie das `InheritedExport` -Attribut erneut deklarieren, um Metadaten zu überschreiben, stellen Sie sicher, dass die Vertragstypen identisch sind. (Im vorherigen Beispiel ist `IPlugin` der Vertragstyp.) Wenn sie sich unterscheiden und nicht überschrieben werden, erstellt das zweite Attribut einen zweiten, unabhängigen Export des Teils. Im Allgemeinen bedeutet dies, dass Sie den Vertragstyp explizit angeben müssen, wenn Sie ein `InheritedExport` -Attribut überschreiben (siehe vorheriges Beispiel).

Da Schnittstellen nicht direkt instanziiert werden können, können sie im Allgemeinen nicht mit `Export` -Attributen oder `Import` -Attribut ergänzt werden. Allerdings kann eine Schnittstelle mit einem `InheritedExport` -Attribut auf der Schnittstellenebene ergänzt werden. Dieser Export wird zusammen mit allen zugeordneten Metadaten von jeder beliebigen implementierenden Klasse geerbt. Die Schnittstelle selbst ist jedoch nicht als ein Teil verfügbar.

<a name="custom_export_attributes"></a>

## <a name="custom-export-attributes"></a>Benutzerdefinierte Exportattribute

Die grundlegenden Exportattribute, `Export` und `InheritedExport`, können so erweitert werden, dass sie Metadaten als Attributeigenschaften einschließen. Diese Methode ist für das Übernehmen ähnlicher Metadaten für viele Teile oder das Erstellen einer Vererbungsstruktur von Metadatenattributen hilfreich.

Ein benutzerdefiniertes Attribut kann den Vertragstyp, den Vertragsnamen oder beliebige andere Metadaten angeben. Um ein benutzerdefiniertes Attribut zu definieren, muss eine Klasse, die von `ExportAttribute` (oder `InheritedExportAttribute`) erbt, mit dem `MetadataAttribute` -Attribut ergänzt werden. Die folgende Klasse definiert ein benutzerdefiniertes Attribut.

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

Diese Klasse definiert ein benutzerdefiniertes Attribut namens `MyAttribute` mit dem Vertragstyp `IMyAddin` und einige Metadaten namens `MyMetadata`. Alle Eigenschaften in einer mit dem `MetadataAttribute` -Attribut markierten Klasse werden als Metadaten betrachtet, die im benutzerdefinierten Attribut definiert sind. Die folgenden zwei Deklarationen sind gleichwertig.

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

In der ersten Deklaration werden der Vertragstyp und die Metadaten explizit definiert. In der zweiten Deklaration sind der Vertragstyp und die Metadaten im benutzerdefinierten Attribut implizit. Insbesondere in Fällen, in denen eine große Menge an identischen Metadaten für viele Teile übernommen werden muss (z. B., Autor oder Urheberrechtsinformationen), können Sie durch Verwendung eines benutzerdefinierten Attributs viel Zeit sparen und Verdoppelungen vermeiden. Darüber hinaus können Vererbungsstrukturen benutzerdefinierter Attribute erstellt werden, um Variationen zu ermöglichen.

Sie können optionale Metadaten in einem benutzerdefinierten Attribut mithilfe des `DefaultValue` -Attributs erstellen. Wenn dieses Attribut in einer benutzerdefinierten Attributklasse für eine Eigenschaft übernommen wird, wird angegeben, dass die ergänzte Eigenschaft optional ist und nicht von einem Exporttool angegeben werden muss. Wenn kein Wert für die Eigenschaft bereitgestellt wird, wird ihm der Standardwert für den Eigenschaftentyp zugewiesen (normalerweise `null`, `false`oder 0.)

<a name="creation_policies"></a>

## <a name="creation-policies"></a>Erstellungsrichtlinien

Wenn ein Teil einen Import angibt und eine Komposition ausgeführt wird, versucht der Kompositionscontainer einen entsprechenden Export zu finden. Wenn der Import einem Export zugeordnet werden kann, wird der importierende Member auf eine Instanz des exportierten Objekts festgelegt. Der Ort, von dem die Instanz stammt, wird durch die *Erstellungsrichtlinie*des exportierenden Teils bestimmt.

Die zwei möglichen Erstellungsrichtlinien sind *freigegeben* und *nicht freigegeben*. Ein Teil mit der Erstellungsrichtlinie "Freigegeben" wird zwischen jedem Import im Container für einen Teil mit diesem Vertrag freigegeben. Wenn die Kompositions-Engine eine Übereinstimmung findet und eine importierende Eigenschaft festlegen muss, instanziiert sie nur dann eine neue Kopie des Teils, wenn noch keine vorhanden ist; andernfalls wird die vorhandene Kopie angegeben. Dies bedeutet, dass viele Objekte möglicherweise Verweise auf den gleichen Teil besitzen. Für solche Teile sollte nicht der interne Zustand verwendet werden, der an vielen Stellen geändert werden kann. Diese Richtlinie ist für statische Teile, Teile, die Dienste bereitstellen, und Teile, die viel Arbeitsspeicher oder andere Ressourcen belegen, geeignet.

Ein Teil mit der Erstellungsrichtlinie "Nicht freigegeben" wird bei jedem Auffinden eines übereinstimmenden Imports für einen der Exporte erstellt. Eine neue Kopie wird daher für jeden Import im Container instanziiert, der einem der exportierten Verträge des Teils entspricht. Der interne Zustand dieser Kopien wird nicht freigegeben. Diese Richtlinie ist geeignet für Teile, bei denen jeder Import einen eigenen internen Zustand benötigt.

Sowohl der Import als auch der Export können die Erstellungsrichtlinie eines Teils mit den Werten `Shared`, `NonShared`oder `Any`angeben. Die Standardeinstellung ist sowohl für Importe als auch Exporte `Any` . Ein Export, für den `Shared` oder `NonShared` angegeben wird, stimmt nur mit einem Import überein, für den die gleichen Werte oder `Any`angegeben werden. Entsprechend stimmt ein Import, für den `Shared` oder `NonShared` angegeben wird, nur mit einem Export überein, für den die gleichen Werte oder `Any`angegeben werden. Importe und Exporte mit nicht kompatiblen Erstellungsrichtlinien werden nicht als Übereinstimmung betrachtet, ebenso wie bei einem Import und Export, deren Vertragsnamen oder Vertragstypen nicht übereinstimmen. Wenn sowohl für Importe als auch Exporte `Any`angegeben wird, oder wenn keine Erstellungsrichtlinie angegeben wird und standardmäßig `Any`festgelegt wird, wird für die Erstellungsrichtlinie als Standardeinstellung "Freigegeben" festgelegt.

Das folgende Beispiel zeigt sowohl Importe als auch Exporte, die Erstellungsrichtlinien angeben. `PartOne` gibt keine Erstellungsrichtlinie an, weshalb der Standard `Any`ist. `PartTwo` gibt keine Erstellungsrichtlinie an, weshalb der Standard `Any`ist. Da sowohl Import als auch Export standardmäßig auf `Any`festgelegt werden, wird `PartOne` freigegeben. `PartThree` gibt eine `Shared` -Erstellungsrichtlinie an, weshalb `PartTwo` und `PartThree` gemeinsam die gleiche Kopie von `PartOne`nutzen. `PartFour` gibt eine `NonShared` -Erstellungsrichtlinie an, weshalb `PartFour` in `PartFive`nicht freigegeben wird. `PartSix` gibt eine `NonShared` -Erstellungsrichtlinie an. `PartFive` und `PartSix` erhalten jeweils separate Kopien von `PartFour`. `PartSeven` gibt eine `Shared` -Erstellungsrichtlinie an. Da es keinen exportierten `PartFour` mit der Erstellungsrichtlinie `Shared`gibt, gibt es für den `PartSeven` -Import keine Entsprechung, und er wird nicht ausgefüllt.

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

## <a name="life-cycle-and-disposing"></a>Lebenszyklus und Freigabe

Da Teile im Kompositionscontainer gehostet werden, kann ihr Lebenszyklus komplexer als gewöhnliche Objekte sein. Teile können zwei wichtige lebenszyklusbezogene Schnittstellen implementieren: `IDisposable` und `IPartImportsSatisfiedNotification`.

Teile, für die beim Herunterfahren bestimmte Schritte ausgeführt werden oder die Ressourcen freigeben müssen, sollten wie gewöhnlich für .NET Framework-Objekte `IDisposable`implementieren. Da jedoch der Container Verweise auf Teile erstellt und verwaltet, sollte nur der Container, der einen Teil besitzt, die `Dispose` -Methode dafür aufrufen. Der Container selbst implementiert `IDisposable`, und er ruft als Teil der Bereinigung in `Dispose` für alle Teile, die er besitzt, `Dispose` auf. Aus diesem Grund sollten Sie immer den Kompositionscontainer freigeben, wenn er und Teile, die er besitzt, nicht mehr benötigt werden.

Für langlebige Kompositionscontainer, kann der Speicherbedarf von Teilen mit der Erstellungsrichtlinie "Nicht freigegeben" ein Problem darstellen. Diese nicht freigegebenen Teile können mehrmals erstellt werden und werden erst freigegeben, wenn der Container selbst freigegeben wurde. Zu diesem Zweck verfügt der Container über die `ReleaseExport` -Methode. Durch Aufrufen dieser Methode für einen nicht freigegebenen Export wird der Export aus dem Kompositionscontainer entfernt und freigegeben. Teile, die nur vom entfernten Export usw. weiter unten in der Struktur verwendet werden, werden ebenfalls entfernt und freigegeben. Dadurch können Ressourcen ohne Freigabe des Kompositionscontainers selbst freigegeben werden.

`IPartImportsSatisfiedNotification` enthält eine Methode mit dem Namen `OnImportsSatisfied`. Diese Methode wird vom Kompositionscontainer für alle Teile aufgerufen, die die Schnittstelle implementieren, wenn die Komposition abgeschlossen wurde und die Importe des Teils verwendet werden können. Teile werden von der Kompositions-Engine erstellt, um die Importe anderer Teilen auszufüllen. Vor dem Festlegen der Importe eines Teils können Sie keine Initialisierung ausführen, die importierte Werte im Teilkonstruktor verwendet oder bearbeitet, sofern diese Werte nicht mithilfe des `ImportingConstructor` -Attributs als Voraussetzung angegeben wurden. Dies ist normalerweise die bevorzugte Methode, doch in einigen Fällen ist die Konstruktoreinfügung möglicherweise nicht verfügbar. In diesen Fällen kann die Initialisierung in `OnImportsSatisfied`ausgeführt werden, und der Teil sollte `IPartImportsSatisfiedNotification`implementieren.

## <a name="see-also"></a>Siehe auch

- [Channel 9-Video: Öffnen Ihrer Anwendungen mit dem Managed Extensibility Framework](https://channel9.msdn.com/events/TechEd/NorthAmerica/2009/DTL328)
- [Channel 9-Video: Managed Extensibility Framework (MEF) 2.0](https://channel9.msdn.com/posts/NET-45-Oleg-Lvovitch-and-Kevin-Ransom-Managed-Extensibility-Framework-MEF-20)
