---
title: "Abh&#228;ngigkeitseigenschaften | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 212cfb1e-cec4-4047-94a6-47209b387f6f
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Abh&#228;ngigkeitseigenschaften
Eine Abhängigkeitseigenschaft \(DP\) ist eine reguläre Eigenschaft, die in einem Eigenschaftenspeicher nicht speichern, es in einer Variablen des Typs \(Feld\), z. B. der Wert gespeichert wird.  
  
 Eine angefügte Abhängigkeitseigenschaft ist eine Abhängigkeitseigenschaft, die als statischer Get\- und Set\-Methoden, die "Eigenschaften" Beschreiben von Beziehungen zwischen Objekten und deren Container darstellen \(z. B. die Position des ein `Button` \-Objekt, auf eine `Panel` Container\).  
  
 **✓ führen** die Abhängigkeitseigenschaften bereitstellen, sollten Sie die Eigenschaften, WPF\-Funktionen wie formatieren, Trigger, Datenbindung, Animationen, dynamische Ressourcen und Vererbung unterstützen.  
  
## Entwurf der Abhängigkeit\-Eigenschaft  
 **✓ führen** erben von <xref:System.Windows.DependencyObject>, oder einem seiner Untertypen, die bei der Implementierung von Abhängigkeitseigenschaften. Der Typ stellt eine äußerst effiziente Implementierung von einem Eigenschaftenspeicher und WPF\-Datenbindung automatisch unterstützt.  
  
 **✓ führen** Geben Sie einen regulären CLR\-Eigenschaft und die öffentliche statische schreibgeschützte Feld Speichern von einer Instanz von <xref:System.Windows.DependencyProperty?displayProperty=fullName> für jede Abhängigkeitseigenschaft.  
  
 **✓ führen** Implementieren von Abhängigkeitseigenschaften durch Aufrufen von Instanzmethoden <xref:System.Windows.DependencyObject.GetValue%2A?displayProperty=fullName> und <xref:System.Windows.DependencyObject.SetValue%2A?displayProperty=fullName>.  
  
 **✓ führen** nennen Sie die statische\-abhängigkeitseigenschaftenfeld Breitzeichenformat den Namen der Eigenschaft mit dem "Property".  
  
 **X nicht** Standardwerte von Abhängigkeitseigenschaften explizit im Code festlegen; stattdessen in den Metadaten festgelegte.  
  
 Wenn Sie den Standardwert der Eigenschaft explizit festlegen, können Sie verhindern, dass diese Eigenschaft implizite Weise, wie z. B. einen Stil festgelegt wird.  
  
 **X nicht** fügen Sie Code in die Eigenschaftenaccessoren als den standardmäßigen Code Zugriff auf das statische Feld.  
  
 Verwendet das statische Feld direkt, dass Code ausgeführt wird nicht da formatieren, wenn die Eigenschaft implizite Art und Weise, wie z. B. einen Stil festgelegt ist.  
  
 **X nicht** Verwenden von Abhängigkeitseigenschaften zum Speichern von Daten zu sicher. Auch private Abhängigkeitseigenschaften können öffentlich zugegriffen werden.  
  
## Angefügte Abhängigkeitseigenschaft Property Design  
 Abhängigkeitseigenschaften, die im vorherigen Abschnitt beschriebenen stellen systeminterne Eigenschaften des deklarierenden Typs dar. zum Beispiel die `Text` \-Eigenschaft ist eine Eigenschaft des `TextButton`, die es deklariert wird. Eine besondere Art von Abhängigkeitseigenschaft ist das angehängte Abhängigkeitseigenschaft.  
  
 Ein klassisches Beispiel für eine angefügte Eigenschaft ist die <xref:System.Windows.Controls.Grid.Column%2A?displayProperty=fullName> Eigenschaft. Die Eigenschaft Spaltenposition Schaltfläche \(nicht des Datenblatts\) darstellt, aber dies ist nur relevant, wenn die Schaltfläche in einem Raster enthalten ist, weshalb es "Schaltflächen von Rastern angefügt ist".  
  
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
  
 Die Definition einer angefügten Eigenschaft sieht größtenteils, der eine reguläre Abhängigkeit\-Eigenschaft, mit der Ausnahme, dass die Accessoren durch statische Get\- und Set\-Methoden dargestellt werden:  
  
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
  
## Abhängigkeitsüberprüfung\-Eigenschaft  
 Eigenschaften implementieren häufig, was die Validierung aufgerufen wird. Validierungslogik ausgeführt wird, wenn versucht wird, den Wert einer Eigenschaft ändern.  
  
 Leider können keine Abhängigkeit Eigenschaftenaccessoren beliebige Validierungscode enthalten. Stattdessen muss die Abhängigkeit Eigenschaft Validierungslogik während der Registrierung angegeben werden.  
  
 **X nicht** Abhängigkeit Eigenschaft Validierungslogik in den Eigenschaftenaccessoren abgelegt. Übergeben Sie stattdessen einen Validierungsrückruf zu `DependencyProperty.Register` Methode.  
  
## Abhängigkeit Benachrichtigungen für Eigenschaftenänderung  
 **X nicht** Change Notification Logik in Abhängigkeit von Eigenschaftenaccessoren implementieren. Abhängigkeitseigenschaften verfügen über eine integrierte Änderung Benachrichtigungen\-Funktion, die verwendet werden muss, durch Angabe eines Rückrufs zum Ändern der <xref:System.Windows.PropertyMetadata>.  
  
## Koersion des Eigenschaftswerts Abhängigkeit  
 Eigenschaft Umwandlung findet statt, wenn der angegebene Wert auf einen Eigenschaften\-Setter von Setter\-Methode geändert wird, bevor der Eigenschaftenspeicher tatsächlich geändert wird.  
  
 **X nicht** erzwingungslogik in Abhängigkeit von Eigenschaftenaccessoren implementieren.  
  
 Abhängigkeitseigenschaften verfügen über eine integrierte Koersion\-Funktion und es kann verwendet werden, durch einen Rückruf Umwandlung zur Angabe der `PropertyMetadata`.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Allgemeine Entwurfsmuster](../../../docs/standard/design-guidelines/common-design-patterns.md)