---
title: "Vererbung von Eigenschaftswerten | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Vererbung, Eigenschaftswerte"
  - "Eigenschaften, Wertevererbung"
  - "Wertevererbung"
ms.assetid: d7c338f9-f2bf-48ed-832c-7be58ac390e4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Vererbung von Eigenschaftswerten
Das Vererben von Eigenschaftswerten ist ein Feature des [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]\-Eigenschaftensystems.  Die Vererbung von Eigenschaftswerten ermöglicht untergeordneten Elementen in einer Elementstruktur, den Wert einer bestimmten Eigenschaft von übergeordneten Elementen so zu übernehmen, wie er im nächsten übergeordneten Element festgelegt wurde.  Das übergeordnete Element hat seinen Wert möglicherweise ebenfalls über die Vererbung des Eigenschaftswerts erhalten, sodass das System bis auf den Seitenstamm zurückgeführt werden kann.  Die Vererbung von Eigenschaftswerten stellt nicht das standardmäßige Verhalten des Eigenschaftensystems dar; eine Eigenschaft muss mit einer bestimmten Metadateneinstellung erstellt worden sein, damit dieses Element die Vererbung von Eigenschaftswerten für untergeordnete Elemente veranlassen kann.  
  
   
  
<a name="Property_Value_Inheritance_is_Containment_Inheritance"></a>   
## Vererbung von Eigenschaftswerten ist Kapselungsvererbung  
 Der Begriff "Vererbung" in diesem Zusammenhang ist nicht identisch mit dem Konzept der Vererbung im Zusammenhang mit Typen und der allgemeinen objektorientierten Programmierung, bei der abgeleitete Klassen Memberdefinitionen von ihren Basisklassen erben.  Diese Bedeutung von Vererbung findet auch in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Anwendung: In verschiedenen Basisklassen definierte Eigenschaften werden als Attribute für abgeleitete [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Klassen verfügbar gemacht, wenn sie als Elemente verwendet werden, und dem Code als Member bereitgestellt.  Bei der Vererbung von Eigenschaftswerten geht es insbesondere darum, wie Eigenschaftswerte von einem Element an ein anderes vererbt werden können, und zwar basierend auf den untergeordneten\/übergeordneten Beziehungen in einer Elementstruktur.  Diese Elementstruktur ist bei der Schachtelung von Elementen in anderen Elementen direkt sichtbar, während Sie Anwendungen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Markup definieren.  Objektstrukturen können auch programmgesteuert erstellt werden, indem Objekte designierten Auflistungen anderer Objekte hinzugefügt werden. Die Vererbung von Eigenschaftswerten funktioniert in der fertigen Struktur zur Laufzeit auf die gleiche Weise.  
  
<a name="Practical_Applications_of_Property_Value_Inheritance"></a>   
## Vererbung von Eigenschaftswerten in der Praxis  
 Die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)][!INCLUDE[TLA#tla_api#plural](../../../../includes/tlasharptla-apisharpplural-md.md)] umfassen mehrere Eigenschaften, für die die Vererbung von Eigenschaftswerten aktiviert ist.  In der Regel sieht das Szenario für diese Eigenschaften so aus, dass sie eine Eigenschaft umfassen, die auch nur einmal pro Seite festgelegt werden kann, wobei diese Eigenschaft auch ein Member einer der Basiselementklassen ist und daher auch für die meisten der untergeordneten Elemente vorhanden ist.  So steuert die <xref:System.Windows.FrameworkElement.FlowDirection%2A>\-Eigenschaft zum Beispiel, in welcher Richtung fließender Inhalt dargestellt und auf der Seite angeordnet werden soll.  Normalerweise soll das Textflusskonzept für alle untergeordneten Elemente konsistent gehandhabt werden.  Falls die Flussrichtung aus irgendeinem Grund auf einer Ebene der Elementstruktur durch eine Benutzer\- oder Umgebungsaktion zurückgesetzt wird, sollte sie normalerweise strukturübergreifend zurückgesetzt werden.  Wenn die <xref:System.Windows.FrameworkElement.FlowDirection%2A>\-Eigenschaft für die Vererbung aktiviert wurde, muss der Wert auf der Ebene in der Elementstruktur, die die Präsentationsanforderungen der einzelnen Seiten in der Anwendung umfasst, nur einmal festgelegt bzw. zurückgesetzt werden.  Sogar der ursprüngliche Standardwert erbt auf diese Art und Weise.  Das Modell der Eigenschaftswertvererbung ermöglicht einzelnen Elementen jedoch weiterhin, den Wert in den seltenen Fällen zurückzusetzen, in denen eine Kombination von Flussrichtungen beabsichtigt ist.  
  
<a name="Making_a_Custom_Property_Inheritable"></a>   
## Aktivieren der Vererbung einer benutzerdefinierten Eigenschaft  
 Indem Sie die Metadaten einer benutzerdefinierten Eigenschaft ändern, können Sie ihre eigenen benutzerdefinierten Eigenschaften für die Vererbung aktivieren.  Beachten Sie jedoch, dass sich das Festlegen einer Eigenschaft als vererbbar auf die Leistung auswirkt.  In dem Fall, in dem diese Eigenschaft nicht über einen festgelegten lokalen Wert verfügt bzw. über einen Wert, der über Stile, Vorlagen oder Datenbindung übernommen wird, stellt eine vererbbare Eigenschaft ihre zugewiesenen Werte allen untergeordneten Elementen in der logischen Struktur zur Verfügung.  
  
 Um eine Eigenschaft für die Wertevererbung zu aktivieren, erstellen Sie wie unter [Registrieren einer angefügten Eigenschaft](../../../../docs/framework/wpf/advanced/how-to-register-an-attached-property.md) beschrieben eine benutzerdefinierte angefügte Eigenschaft.  Registrieren Sie die Eigenschaft mit Metadaten \(<xref:System.Windows.FrameworkPropertyMetadata>\), und geben Sie die "Inherits"\-Option in den Optionseinstellungen für die Metadaten an.  Stellen Sie außerdem sicher, dass die Eigenschaft über einen festgelegten Standardwert verfügt, da dieser Wert nun erbt.  Obwohl Sie die Eigenschaft als angehängt registriert haben, können Sie ggf. einen Eigenschaften\-"Wrapper" für den get\/set\-Zugriff auf den Besitzertyp erstellen, so wie dies bei einer "nicht angefügten" [Abhängigkeitseigenschaft](GTMT) der Fall ist.  Anschließend kann die vererbbare Eigenschaft entweder festgelegt werden, indem der direkte Eigenschaftenwrapper für den Besitzertyp oder abgeleitete Typen verwendet wird, oder sie kann mit der Syntax für angehängte Eigenschaften für ein <xref:System.Windows.DependencyObject> festgelegt werden.  
  
 Das Konzept angehängter Eigenschaften ist demjenigen globaler Eigenschaften ähnlich; Sie können ein beliebiges <xref:System.Windows.DependencyObject> auf den Wert überprüfen und ein gültiges Ergebnis erhalten.  Ein typisches Szenario für angehängt Elemente ist, dass Eigenschaftswerte für untergeordnete Elemente festgelegt werden. Das Szenario ist noch effektiver, wenn die betreffende Eigenschaft eine angehängte Eigenschaft ist, die stets implizit als angehängte Eigenschaft für jedes Element \(<xref:System.Windows.DependencyObject>\) in der Struktur vorhanden ist.  
  
> [!NOTE]
>  Obwohl das Vererben von Eigenschaftswerten bei nicht angefügten Abhängigkeitseigenschaften anscheinend funktioniert, ist das Vererbungsverhalten bei einer nicht angefügten Eigenschaft über bestimmte Elementgrenzen in der Laufzeitstruktur nicht definiert.  Verwenden Sie immer <xref:System.Windows.DependencyProperty.RegisterAttached%2A> zum Registrieren von Eigenschaften, wenn Sie <xref:System.Windows.FrameworkPropertyMetadata.Inherits%2A> in den Metadaten angeben.  
  
<a name="InheritanceContext"></a>   
## Vererben von Eigenschaftswerten über Strukturgrenzen hinweg  
 Das Vererben von Eigenschaften erfolgt durch das Durchlaufen einer Elementstruktur.  Diese Struktur ist häufig parallel zur logischen Struktur.  Wenn Sie jedoch ein [WPF\-Kernebenen](GTMT)\-Objekt in das Markup einbeziehen, das eine Elementstruktur definiert, wie z. B. einen <xref:System.Windows.Media.Brush>, erstellen Sie eine nicht aufeinanderfolgende logische Struktur.  Eine echte logische Struktur erstreckt sich konzeptionell nicht über den <xref:System.Windows.Media.Brush>, da die logische Struktur ein Konzept auf [WPF\-Frameworkebene](GTMT) darstellt.  Dies spiegelt sich auch in den Ergebnissen wider, wenn Sie die Methoden von <xref:System.Windows.LogicalTreeHelper> verwenden.  Die Eigenschaftswertvererbung kann diese Lücke in der logischen Struktur jedoch überbrücken und vererbte Werte trotzdem weiter übergeben, solange die vererbbare Eigenschaft als angehängte Eigenschaft registriert wurde und keine Begrenzung angetroffen wird, die die Vererbung absichtlich blockiert \(wie z. B. <xref:System.Windows.Controls.Frame>\).  
  
## Siehe auch  
 [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [Übersicht über angefügte Eigenschaften](../../../../docs/framework/wpf/advanced/attached-properties-overview.md)   
 [Priorität von Abhängigkeitseigenschaftswerten](../../../../docs/framework/wpf/advanced/dependency-property-value-precedence.md)