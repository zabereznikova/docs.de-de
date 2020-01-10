---
title: Abhängigkeitseigenschaften
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
ms.openlocfilehash: bd12d05dbba133503778e6df3cd0e6c3e5689d5b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709490"
---
# <a name="dependency-properties"></a>Abhängigkeitseigenschaften
Eine Abhängigkeits Eigenschaft (DP) ist eine reguläre Eigenschaft, die ihren Wert in einem Eigenschafts Speicher speichert, anstatt Sie in einer Typvariablen (Feld) zu speichern, z. b.  
  
 Eine angefügte Abhängigkeits Eigenschaft ist eine Art von Abhängigkeits Eigenschaft, die als statische Get-und Set-Methoden modelliert ist, die "Properties" darstellen, die Beziehungen zwischen Objekten und ihren Containern beschreiben (z. b. die Position eines `Button` Objekts in einem `Panel` Container).  
  
 **✓ DO** die Abhängigkeitseigenschaften bereitstellen, sollten Sie die Eigenschaften, WPF-Funktionen wie formatieren, Trigger, Datenbindung, Animationen, dynamische Ressourcen und Vererbung unterstützen.  
  
## <a name="dependency-property-design"></a>Design der Abhängigkeits Eigenschaft  
 **✓ DO** Vererben <xref:System.Windows.DependencyObject>, oder einem seiner Untertypen, bei der Implementierung von Abhängigkeitseigenschaften. Der-Typ stellt eine sehr effiziente Implementierung eines Eigenschaften Stores bereit und unterstützt automatisch die WPF-Datenbindung.  
  
 **✓ DO** Geben Sie einen regulären CLR-Eigenschaft und eine öffentliche statische schreibgeschützte Feld Speichern von einer Instanz von <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> für jede Abhängigkeitseigenschaft.  
  
 **✓ DO** Implementieren von Abhängigkeitseigenschaften durch Aufrufen von Instanzmethoden <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> und <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.  
  
 **✓ DO** benennen statische Abhängigkeit Eigenschaftenfeld Breitzeichenformat den Namen der Eigenschaft mit dem "Property".  
  
 **X DO NOT** Standardwerte von Abhängigkeitseigenschaften explizit im Code festlegen; stattdessen in den Metadaten festgelegte.  
  
 Wenn Sie einen Standardwert für die Eigenschaft explizit festlegen, können Sie verhindern, dass diese Eigenschaft auf implizite Weise festgelegt wird, z. b. in Form einer Formatierung.  
  
 **X DO NOT** fügen Sie Code in den Eigenschaftenaccessoren als standard Code auf das statische Feld zugreifen.  
  
 Dieser Code wird nicht ausgeführt, wenn die Eigenschaft durch implizites Mittel (z. b. eine Formatierung) festgelegt wird, da die Formatierung das statische Feld direkt verwendet.  
  
 **X DO NOT** Abhängigkeitseigenschaften verwenden, um sichere Daten zu speichern. Auch private Abhängigkeits Eigenschaften können öffentlich aufgerufen werden.  
  
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
  
 **X DO NOT** Abhängigkeit Eigenschaft Validierungslogik in den Eigenschaftenaccessoren abgelegt. Übergeben Sie stattdessen einen Validierungs Rückruf an `DependencyProperty.Register` Methode.  
  
## <a name="dependency-property-change-notifications"></a>Änderungs Benachrichtigungen für Abhängigkeits Eigenschaften  
 **X DO NOT** Change Notification Logik in den Eigenschaftenaccessoren Abhängigkeit implementieren. Abhängigkeits Eigenschaften verfügen über eine integrierte Änderungs Benachrichtigungsfunktion, die verwendet werden muss, indem ein Änderungs Benachrichtigungs Rückruf an den <xref:System.Windows.PropertyMetadata>bereitgestellt wird.  
  
## <a name="dependency-property-value-coercion"></a>Umwandlung von Abhängigkeits Eigenschafts Werten  
 Die Eigenschafts Umwandlung erfolgt, wenn der Wert, der an einen Eigenschaften Setter übergeben wird, vom Setter geändert wird, bevor der Eigenschaften Speicher tatsächlich geändert wird.  
  
 **X DO NOT** Umwandlung Logik in den Eigenschaftenaccessoren Abhängigkeit implementieren.  
  
 Abhängigkeits Eigenschaften verfügen über eine integrierte Umwandlungs Funktion und können verwendet werden, indem ein Umwandlungs Rückruf an den `PropertyMetadata`bereitgestellt wird.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Allgemeine Entwurfsmuster](../../../docs/standard/design-guidelines/common-design-patterns.md)
