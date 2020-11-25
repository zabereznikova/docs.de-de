---
title: Abhängigkeitseigenschaften
ms.date: 10/22/2008
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: ab30da59670c146874defe86b1d048f97eebf449
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734763"
---
# <a name="dependency-properties"></a>Abhängigkeitseigenschaften

Eine Abhängigkeits Eigenschaft (DP) ist eine reguläre Eigenschaft, die ihren Wert in einem Eigenschafts Speicher speichert, anstatt Sie in einer Typvariablen (Feld) zu speichern, z. b..

 Eine angefügte Abhängigkeits Eigenschaft ist eine Art von Abhängigkeits Eigenschaft, die als statische Get-und Set-Methoden modelliert ist, die "Properties" darstellen, die Beziehungen zwischen Objekten und ihren Containern beschreiben (z.b. die Position eines- `Button` Objekts in einem `Panel` Container).

 ✔️ die Abhängigkeits Eigenschaften bereitstellen, wenn Sie die Eigenschaften benötigen, um WPF-Funktionen wie formatieren, Trigger, Daten Bindungen, Animationen, dynamische Ressourcen und Vererbung zu unterstützen.

## <a name="dependency-property-design"></a>Design der Abhängigkeits Eigenschaft

 ✔️ <xref:System.Windows.DependencyObject> bei der Implementierung von Abhängigkeits Eigenschaften von oder einem seiner Untertypen erben. Der-Typ stellt eine sehr effiziente Implementierung eines Eigenschaften Stores bereit und unterstützt automatisch die WPF-Datenbindung.

 ✔️ stellen eine reguläre CLR-Eigenschaft und ein öffentliches statisches Schreib geschütztes Feld bereit, das eine Instanz von <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> für jede Abhängigkeits Eigenschaft speichert.

 ✔️ Implementieren Sie Abhängigkeits Eigenschaften durch Aufrufen von Instanzmethoden <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> und <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType> .

 ✔️ dem statischen Feld der Abhängigkeits Eigenschaft einen Namen, indem Sie den Namen der Eigenschaft mit "Property" versehen.

 ❌ Legen Sie Standardwerte von Abhängigkeits Eigenschaften nicht explizit im Code fest. Legen Sie Sie stattdessen in den Metadaten fest.

 Wenn Sie einen Standardwert für die Eigenschaft explizit festlegen, können Sie verhindern, dass diese Eigenschaft auf implizite Weise festgelegt wird, z. b. in Form einer Formatierung.

 ❌ Fügen Sie keinen Code in den Eigenschaftenaccessoren außer dem Standard Code ein, um auf das statische Feld zuzugreifen.

 Dieser Code wird nicht ausgeführt, wenn die Eigenschaft durch implizites Mittel (z. b. eine Formatierung) festgelegt wird, da die Formatierung das statische Feld direkt verwendet.

 ❌ Verwenden Sie keine Abhängigkeits Eigenschaften, um sichere Daten zu speichern. Auch private Abhängigkeits Eigenschaften können öffentlich aufgerufen werden.

## <a name="attached-dependency-property-design"></a>Design der angefügten Abhängigkeits Eigenschaften

 Abhängigkeits Eigenschaften, die im vorangehenden Abschnitt beschrieben werden, stellen intrinsische Eigenschaften des deklarierenden Typs dar. Beispielsweise ist die- `Text` Eigenschaft eine Eigenschaft von `TextButton` , die Sie deklariert. Eine besondere Art von Abhängigkeits Eigenschaft ist die angefügte Abhängigkeits Eigenschaft.

 Ein klassisches Beispiel für eine angefügte Eigenschaft ist die- <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> Eigenschaft. Die-Eigenschaft stellt die Spaltenposition der Schaltfläche (nicht des Rasters) dar, ist aber nur relevant, wenn die Schaltfläche in einem Raster enthalten ist, sodass Sie an Schaltflächen durch Raster angefügt wird.

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

 ❌ Fügen Sie die Validierungs Logik für die Abhängigkeits Eigenschaft nicht in die Accessoren der Eigenschaft ein. Übergeben Sie stattdessen einen Validierungs Rückruf an die- `DependencyProperty.Register` Methode.

## <a name="dependency-property-change-notifications"></a>Änderungs Benachrichtigungen für Abhängigkeits Eigenschaften

 ❌ Implementieren Sie keine Änderungs Benachrichtigungs Logik in Accessoren für Abhängigkeits Eigenschaften. Abhängigkeits Eigenschaften verfügen über eine integrierte Änderungs Benachrichtigungsfunktion, die verwendet werden muss, wenn ein Änderungs Benachrichtigungs Rückruf an den übergeben wird <xref:System.Windows.PropertyMetadata> .

## <a name="dependency-property-value-coercion"></a>Umwandlung von Abhängigkeits Eigenschafts Werten

 Die Eigenschafts Umwandlung erfolgt, wenn der Wert, der an einen Eigenschaften Setter übergeben wird, vom Setter geändert wird, bevor der Eigenschaften Speicher tatsächlich geändert wird.

 ❌ Implementieren Sie keine Umwandlungs Logik in Abhängigkeits Eigenschaften Accessoren.

 Abhängigkeits Eigenschaften verfügen über eine integrierte Umwandlungs Funktion und können verwendet werden, indem ein Umwandlungs Rückruf an den übergeben wird `PropertyMetadata` .

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Framework-Entwurfs Richtlinien](index.md)
- [Allgemeine Entwurfsmuster](common-design-patterns.md)
