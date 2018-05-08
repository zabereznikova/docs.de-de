---
title: Abhängigkeitseigenschaften
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 039015f895a491d8709815d6aff52eb6139d779f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="dependency-properties"></a>Abhängigkeitseigenschaften
Eine Abhängigkeitseigenschaft (DP) ist eine reguläre Eigenschaft, die den Wert in einen Eigenschaftenspeicher, z. B. in einer Variablen des Typs (Feld), speichern, statt speichert.  
  
 Eine angehängte Abhängigkeitseigenschaft ist eine Art von Abhängigkeitseigenschaft modelliert als statische Get- und Set-Methoden, die "Eigenschaften" Beschreiben von Beziehungen zwischen Objekten und deren Container darstellen (z. B. die Position des eine `Button` -Objekt, auf eine `Panel` Container).  
  
 **Führen Sie ✓** die Abhängigkeitseigenschaften bereitstellen, sollten Sie die Eigenschaften, WPF-Funktionen wie formatieren, Trigger, Datenbindung, Animationen, dynamische Ressourcen und Vererbung unterstützen.  
  
## <a name="dependency-property-design"></a>Entwerfen der Abhängigkeit-Eigenschaft  
 **Führen Sie ✓** Vererben <xref:System.Windows.DependencyObject>, oder einem seiner Untertypen, bei der Implementierung von Abhängigkeitseigenschaften. Der Typ bietet eine äußerst effiziente Implementierung des einen Eigenschaftenspeicher und WPF-Datenbindung automatisch unterstützt.  
  
 **Führen Sie ✓** Geben Sie einen regulären CLR-Eigenschaft und eine öffentliche statische schreibgeschützte Feld Speichern von einer Instanz von <xref:System.Windows.DependencyProperty?displayProperty=nameWithType> für jede Abhängigkeitseigenschaft.  
  
 **Führen Sie ✓** Implementieren von Abhängigkeitseigenschaften durch Aufrufen von Instanzmethoden <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=nameWithType> und <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=nameWithType>.  
  
 **Führen Sie ✓** benennen statische Abhängigkeit Eigenschaftenfeld Breitzeichenformat den Namen der Eigenschaft mit dem "Property".  
  
 **X nicht** Standardwerte von Abhängigkeitseigenschaften explizit im Code festlegen; stattdessen in den Metadaten festgelegte.  
  
 Wenn Sie den Standardwert der Eigenschaft explizit festlegen, können Sie verhindern, dass diese Eigenschaft implizite Weise, wie z. B. eine Formatvorlage festgelegt wird.  
  
 **X nicht** fügen Sie Code in den Eigenschaftenaccessoren als standard Code auf das statische Feld zugreifen.  
  
 Code ausgeführt wird nicht, wenn implizite Wege, wie z. B. eine Formatvorlage, die Eigenschaft festgelegt ist, da Formatierung verwendet das statische Feld direkt.  
  
 **X nicht** Abhängigkeitseigenschaften verwenden, um sichere Daten zu speichern. Selbst bei privaten Abhängigkeitseigenschaften können öffentlich zugegriffen werden.  
  
## <a name="attached-dependency-property-design"></a>Abhängigkeit angefügte Eigenschaftenentwurf  
 Im vorherigen Abschnitt beschriebene Abhängigkeitseigenschaften darstellen systeminterne Eigenschaften des deklarierenden Typs; z. B. die `Text` Eigenschaft ist eine Eigenschaft des `TextButton`, die es deklariert wird. Eine spezielle Art von Abhängigkeitseigenschaft ist das angehängte Abhängigkeitseigenschaft.  
  
 Ein klassisches Beispiel einer angefügten Eigenschaft ist die <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=nameWithType> Eigenschaft. Die Eigenschaft darstellt, Spaltenposition Schaltfläche (nicht des Datenblatts), aber es ist nur relevant, wenn die Schaltfläche in einem Raster enthalten ist, weshalb es "Schaltflächen von Rastern angefügt ist".  
  
```  
<Grid>  
    <Grid.ColumnDefinitions>  
        <ColumnDefinition />  
        <ColumnDefinition />  
    </Grid.ColumnDefinitions>  
  
    <Button Grid.Column="0">Click</Button>  
    <Button Grid.Column="1">Clack</Button>  
</Grid>  
```  
  
 Die Definition einer angefügten Eigenschaft sieht größtenteils wie eine reguläre Abhängigkeit-Eigenschaft, mit dem Unterschied, dass die Accessoren durch statische Get- und Set-Methoden dargestellt werden:  
  
```  
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
 Eigenschaften implementieren häufig auf, was die Validierung aufgerufen wird. Validierungslogik ausgeführt wird, wenn versucht wird, den Wert einer Eigenschaft zu ändern.  
  
 Leider können keine Abhängigkeit Eigenschaftenaccessoren beliebige Validierungscode enthalten. Stattdessen muss die Abhängigkeit Eigenschaft Validierungslogik während der Registrierung angegeben werden.  
  
 **X nicht** Abhängigkeit Eigenschaft Validierungslogik in den Eigenschaftenaccessoren abgelegt. Stattdessen übergeben, um einen Validierungsrückruf `DependencyProperty.Register` Methode.  
  
## <a name="dependency-property-change-notifications"></a>Abhängigkeit Eigenschaft Änderungsbenachrichtigungen  
 **X nicht** Change Notification Logik in den Eigenschaftenaccessoren Abhängigkeit implementieren. Abhängigkeitseigenschaften verfügen über eine integrierte Änderung Benachrichtigungen-Funktion, die verwendet werden muss, durch Angabe eines Rückrufs zum Ändern der <xref:System.Windows.PropertyMetadata>.  
  
## <a name="dependency-property-value-coercion"></a>Abhängigkeit Eigenschaft-Wert-Umwandlung  
 Eigenschaft Umwandlung findet statt, wenn der angegebene Wert auf einen Eigenschaften-Setter von Setter-Methode geändert wird, bevor der Eigenschaftenspeicher tatsächlich geändert wird.  
  
 **X nicht** Umwandlung Logik in den Eigenschaftenaccessoren Abhängigkeit implementieren.  
  
 Abhängigkeitseigenschaften verfügen über eine integrierte Koersion-Funktion und kann verwendet werden, durch einen Rückruf Umwandlung zur Angabe der `PropertyMetadata`.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Allgemeine Entwurfsmuster](../../../docs/standard/design-guidelines/common-design-patterns.md)
