---
title: Abhängigkeitseigenschaften
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: KrzysztofCwalina
ms.openlocfilehash: b577f42c98cb56fb367cb57a550cb094a8ef105e
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53145240"
---
# <a name="dependency-properties"></a>Abhängigkeitseigenschaften
Eine Abhängigkeitseigenschaft (DP) handelt es sich um eine reguläre Eigenschaft, die den Wert in einen Eigenschaftenspeicher, z. B. in einer Variablen vom Typ (Feld), speichern, statt speichert.  
  
 Eine angefügte Abhängigkeitseigenschaft ist eine Art von Abhängigkeitseigenschaft modelliert, die als statische Get- und Set-Methoden, die "Eigenschaften" Beschreiben von Beziehungen zwischen Objekten und ihren Containern darstellt (z. B. die Position des ein `Button` -Objekt ein `Panel` Container).  
  
 **✓ DO** die Abhängigkeitseigenschaften bereitstellen, sollten Sie die Eigenschaften, WPF-Funktionen wie formatieren, Trigger, Datenbindung, Animationen, dynamische Ressourcen und Vererbung unterstützen.  
  
## <a name="dependency-property-design"></a>Eigenschaftenentwurf Abhängigkeit  
 **✓ DO** Vererben <xref:System.Windows.DependencyObject>, oder einem seiner Untertypen, bei der Implementierung von Abhängigkeitseigenschaften. Der Typ stellt eine sehr effiziente Implementierung der einen Eigenschaftenspeicher und WPF-Datenbindung automatisch unterstützt.  
  
 **✓ DO** Geben Sie einen regulären CLR-Eigenschaft und eine öffentliche statische schreibgeschützte Feld Speichern von einer Instanz von <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> für jede Abhängigkeitseigenschaft.  
  
 **✓ DO** Implementieren von Abhängigkeitseigenschaften durch Aufrufen von Instanzmethoden <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> und <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.  
  
 **✓ DO** benennen statische Abhängigkeit Eigenschaftenfeld Breitzeichenformat den Namen der Eigenschaft mit dem "Property".  
  
 **X DO NOT** Standardwerte von Abhängigkeitseigenschaften explizit im Code festlegen; stattdessen in den Metadaten festgelegte.  
  
 Wenn Sie den Standardwert der Eigenschaft explizit festlegen, können Sie verhindern, dass die Eigenschaft einige implizite Art und Weise, wie z. B. ein Stil festgelegt wird.  
  
 **X DO NOT** fügen Sie Code in den Eigenschaftenaccessoren als standard Code auf das statische Feld zugreifen.  
  
 Dass Code ausgeführt wird nicht, wenn impliziter Art und Weise, wie z. B. eine Formatierung, die die Eigenschaft festgelegt ist, da Stile wird das statische Feld direkt verwendet.  
  
 **X DO NOT** Abhängigkeitseigenschaften verwenden, um sichere Daten zu speichern. Auch private Abhängigkeitseigenschaften können öffentlich zugegriffen werden.  
  
## <a name="attached-dependency-property-design"></a>Angefügte Abhängigkeitseigenschaft Eigenschaftenentwurf  
 Abhängigkeitseigenschaften, die im vorherigen Abschnitt beschriebenen stellen die systeminterne Eigenschaften des deklarierenden Typs dar. z. B. die `Text` Eigenschaft ist eine Eigenschaft des `TextButton`, die es deklariert wird. Eine besondere Art von Abhängigkeitseigenschaft ist das angefügte Abhängigkeitseigenschaft.  
  
 Ein klassisches Beispiel für eine angefügte Eigenschaft ist die <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> Eigenschaft. Die Eigenschaft darstellt, der Schaltfläche (nicht des Rasters) Spaltenposition, aber dies ist nur relevant, wenn die Schaltfläche in einem Raster enthalten ist, weshalb er "Schaltflächen von Rastern angefügt ist".  
  
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
  
 Die Definition einer angefügten Eigenschaft sieht sich größtenteils wie eine reguläre Abhängigkeit-Eigenschaft, mit dem Unterschied, dass die Accessoren durch statische Get- und Set-Methoden dargestellt werden:  
  
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
  
## <a name="dependency-property-validation"></a>Abhängigkeitsüberprüfung-Eigenschaft  
 Eigenschaften implementieren häufig, welche die Validierung aufgerufen wird. Validierungslogik ausgeführt wird, wenn versucht wird, den Wert einer Eigenschaft ändern.  
  
 Leider können keine Abhängigkeit von Eigenschaftenaccessoren beliebige Validierungscode enthalten. Stattdessen muss Logik zur Überprüfung von Dependency-Eigenschaft während der Registrierung angegeben werden.  
  
 **X DO NOT** Abhängigkeit Eigenschaft Validierungslogik in den Eigenschaftenaccessoren abgelegt. Übergeben Sie stattdessen einen Validierungsrückruf zu `DependencyProperty.Register` Methode.  
  
## <a name="dependency-property-change-notifications"></a>Benachrichtigungen über Eigenschaftsänderungen Abhängigkeit  
 **X DO NOT** Change Notification Logik in den Eigenschaftenaccessoren Abhängigkeit implementieren. Abhängigkeitseigenschaften verfügen über eine integrierte Change Benachrichtigungen-Funktion, die verwendet werden muss, durch Angabe der Rückruf einer änderungsbenachrichtigung auf dem <xref:System.Windows.PropertyMetadata>.  
  
## <a name="dependency-property-value-coercion"></a>Koersion des Eigenschaftswerts Abhängigkeit  
 Eigenschaft Koersion findet statt, wenn der angegebene Wert auf einen Eigenschaften-Setter vom Setter geändert wird, bevor der Eigenschaftenspeicher tatsächlich geändert wird.  
  
 **X DO NOT** Umwandlung Logik in den Eigenschaftenaccessoren Abhängigkeit implementieren.  
  
 Abhängigkeitseigenschaften verfügen über eine integrierte Koersion-Funktion und kann verwendet werden, durch Angabe eines Umwandlung-Rückrufs, der die `PropertyMetadata`.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Allgemeine Entwurfsmuster](../../../docs/standard/design-guidelines/common-design-patterns.md)
