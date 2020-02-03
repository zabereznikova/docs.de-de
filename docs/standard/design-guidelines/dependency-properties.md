---
title: Abhängigkeitseigenschaften
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: e1372b75cb6501f8bc3fec913364e9d80157ad83
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741725"
---
# <a name="dependency-properties"></a>Abhängigkeitseigenschaften
Eine Abhängigkeits Eigenschaft (DP) ist eine reguläre Eigenschaft, die ihren Wert in einem Eigenschafts Speicher speichert, anstatt Sie in einer Typvariablen (Feld) zu speichern, z. b.

 Eine angefügte Abhängigkeits Eigenschaft ist eine Art von Abhängigkeits Eigenschaft, die als statische Get-und Set-Methoden modelliert ist, die "Properties" darstellen, die Beziehungen zwischen Objekten und ihren Containern beschreiben (z. b. die Position eines `Button` Objekts in einem `Panel` Container).

 ✔️ die Abhängigkeits Eigenschaften bereitstellen, wenn Sie die Eigenschaften benötigen, um WPF-Funktionen wie formatieren, Trigger, Daten Bindungen, Animationen, dynamische Ressourcen und Vererbung zu unterstützen.

## <a name="dependency-property-design"></a>Design der Abhängigkeits Eigenschaft
 beim Implementieren von Abhängigkeits Eigenschaften können ✔️ von <xref:System.Windows.DependencyObject>oder einem seiner Untertypen erben. Der-Typ stellt eine sehr effiziente Implementierung eines Eigenschaften Stores bereit und unterstützt automatisch die WPF-Datenbindung.

 ✔️ stellen eine reguläre CLR-Eigenschaft und ein öffentliches statisches Schreib geschütztes Feld bereit, das eine Instanz von <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> für jede Abhängigkeits Eigenschaft speichert.

 ✔️ Implementieren Sie Abhängigkeits Eigenschaften durch Aufrufen von Instanzmethoden <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> und <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.

 ✔️ dem statischen Feld der Abhängigkeits Eigenschaft einen Namen, indem Sie den Namen der Eigenschaft mit "Property" versehen.

 ❌ Standardwerte von Abhängigkeits Eigenschaften nicht explizit im Code festlegen. Legen Sie Sie stattdessen in den Metadaten fest.

 Wenn Sie einen Standardwert für die Eigenschaft explizit festlegen, können Sie verhindern, dass diese Eigenschaft auf implizite Weise festgelegt wird, z. b. in Form einer Formatierung.

 ❌ keinen Code in den Eigenschaftenaccessoren als den Standard Code für den Zugriff auf das statische Feld einfügen.

 Dieser Code wird nicht ausgeführt, wenn die Eigenschaft durch implizites Mittel (z. b. eine Formatierung) festgelegt wird, da die Formatierung das statische Feld direkt verwendet.

 ❌ keine Abhängigkeits Eigenschaften verwenden, um sichere Daten zu speichern. Auch private Abhängigkeits Eigenschaften können öffentlich aufgerufen werden.

## <a name="attached-dependency-property-design"></a>Design der angefügten Abhängigkeits Eigenschaften
 Abhängigkeits Eigenschaften, die im vorangehenden Abschnitt beschrieben werden, stellen intrinsische Eigenschaften des deklarierenden Typs dar. die `Text`-Eigenschaft ist z. b. eine Eigenschaft von `TextButton`, die Sie deklariert. Eine besondere Art von Abhängigkeits Eigenschaft ist die angefügte Abhängigkeits Eigenschaft.

 Ein klassisches Beispiel für eine angefügte Eigenschaft ist die <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType>-Eigenschaft. Die-Eigenschaft stellt die Spaltenposition der Schaltfläche (nicht des Rasters) dar, ist aber nur relevant, wenn die Schaltfläche in einem Raster enthalten ist, sodass Sie an Schaltflächen durch Raster angefügt wird.

```xaml
<Grid>
    <Grid.ColumnDefinitions>
        <ColumnDefinition />
        <ColumnDefinition />
    </Grid.ColumnDefinitions>

    <Button Grid.Column="0">Click</Button>
    <Button Grid.Column="1">Clack</Button>
</Grid>
```

 Die Definition einer angefügten Eigenschaft sieht in der Regel wie eine reguläre Abhängigkeits Eigenschaft aus, mit dem Unterschied, dass die Accessoren durch statische Get-und Set-Methoden dargestellt werden:

```csharp
public class Grid {

    public static int GetColumn(DependencyObject obj) {
        return (int)obj.GetValue(ColumnProperty);
    }

    public static void SetColumn(DependencyObject obj, int value) {
        obj.SetValue(ColumnProperty,value);
    }

    public static readonly DependencyProperty ColumnProperty =
        DependencyProperty.RegisterAttached(
            "Column",
            typeof(int),
            typeof(Grid)
    );
}
```

## <a name="dependency-property-validation"></a>Validierung der Abhängigkeits Eigenschaft
 Eigenschaften implementieren häufig, was als Validierung bezeichnet wird. Die Validierungs Logik wird ausgeführt, wenn versucht wird, den Wert einer Eigenschaft zu ändern.

 Leider können Abhängigkeits Eigenschaftenaccessoren keinen beliebigen Validierungscode enthalten. Stattdessen muss bei der Eigenschaften Registrierung eine Validierungs Logik für die Abhängigkeits Eigenschaft angegeben werden.

 ❌ die Validierungs Logik für die Abhängigkeits Eigenschaft in den Accessoren der Eigenschaft nicht ablegen. Übergeben Sie stattdessen einen Validierungs Rückruf an `DependencyProperty.Register` Methode.

## <a name="dependency-property-change-notifications"></a>Änderungs Benachrichtigungen für Abhängigkeits Eigenschaften
 in ❌ wird keine Änderungs Benachrichtigungs Logik in Accessoren für Abhängigkeits Eigenschaften implementiert. Abhängigkeits Eigenschaften verfügen über eine integrierte Änderungs Benachrichtigungsfunktion, die verwendet werden muss, indem ein Änderungs Benachrichtigungs Rückruf an den <xref:System.Windows.PropertyMetadata>bereitgestellt wird.

## <a name="dependency-property-value-coercion"></a>Umwandlung von Abhängigkeits Eigenschafts Werten
 Die Eigenschafts Umwandlung erfolgt, wenn der Wert, der an einen Eigenschaften Setter übergeben wird, vom Setter geändert wird, bevor der Eigenschaften Speicher tatsächlich geändert wird.

 ❌ implementieren keine Umwandlungs Logik in Accessoren für Abhängigkeits Eigenschaften.

 Abhängigkeits Eigenschaften verfügen über eine integrierte Umwandlungs Funktion und können verwendet werden, indem ein Umwandlungs Rückruf an den `PropertyMetadata`bereitgestellt wird.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Allgemeine Entwurfsmuster](../../../docs/standard/design-guidelines/common-design-patterns.md)
