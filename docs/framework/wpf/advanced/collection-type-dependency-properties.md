---
title: "Abh&#228;ngigkeitseigenschaften vom Auflistungstyp | Microsoft Docs"
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
  - "Auflistungseigenschaften"
  - "Abhängigkeitseigenschaften"
  - "Eigenschaften, Auflistungstyp"
  - "Eigenschaften, Abhängigkeit"
ms.assetid: 99f96a42-3ab7-4f64-a16b-2e10d654e97c
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Abh&#228;ngigkeitseigenschaften vom Auflistungstyp
In diesem Thema finden Sie Unterstützung und Mustervorschläge für das Implementieren einer [Abhängigkeitseigenschaft](GTMT), wenn die Eigenschaft zum Auflistungstyp gehört.  
  
   
  
<a name="implementing"></a>   
## Implementieren einer Abhängigkeitseigenschaft vom Auflistungstyp  
 Für Abhängigkeitseigenschaften wird im Allgemeinen folgendes Implementierungsmuster verwendet: Sie definieren einen [!INCLUDE[TLA2#tla_clr](../../../../includes/tla2sharptla-clr-md.md)]\-Eigenschaftenwrapper, in dem diese Eigenschaft durch einen <xref:System.Windows.DependencyProperty>\-Bezeichner statt durch ein Feld oder ein anderes Konstrukt unterstützt wird.  Dieses Muster gilt auch, wenn Sie eine Eigenschaft vom Auflistungstyp implementieren.  Bei einer Eigenschaft vom Auflistungstyp wird dieses Muster jedoch komplexer, wenn der in der Auflistung enthaltene Typ selbst ein <xref:System.Windows.DependencyObject> oder eine von <xref:System.Windows.Freezable> abgeleitete Klasse ist.  
  
<a name="initializing"></a>   
## Initialisieren der Auflistung mit einem anderem Wert als dem Standardwert  
 Wenn Sie eine Abhängigkeitseigenschaft erstellen, geben Sie den Standardwert der Eigenschaft nicht als anfänglichen Feldwert an.  Stattdessen geben Sie den Standardwert über die Metadaten für die Abhängigkeitseigenschaft an.  Wenn die Eigenschaft ein Verweistyp ist, so ist der in den Metadaten für die Abhängigkeitseigenschaft angegebene Standardwert kein Standardwert pro Instanz, sondern ein Standardwert, der für alle Instanzen dieses Typs gilt.  Daher müssen Sie sorgfältig darauf achten, dass Sie nicht die durch die Metadaten für die Auflistungseigenschaft definierte einzelne statische Auflistung als funktionierenden Standardwert für neu erstellte Instanzen Ihres Typs verwenden.  Stattdessen müssen Sie sicherstellen, dass Sie den Auflistungswert bewusst auf eine eindeutige \(Instanz\-\) Auflistung im Rahmen der Klassenkonstruktorlogik festlegen.  Andernfalls haben Sie eine unbeabsichtigte Singletonklasse erstellt.  
  
 Betrachten Sie das folgende Beispiel.  Im nachstehenden Abschnitt des Beispiels wird die Definition für eine `Aquarium`\-Klasse veranschaulicht.  Die Klasse definiert die `AquariumObjects`\-Abhängigkeitseigenschaft vom Auflistungstyp, die den generischen <xref:System.Collections.Generic.List%601>\-Typ mit einer <xref:System.Windows.FrameworkElement>\-Typeinschränkung verwendet.  Im <xref:System.Windows.DependencyProperty.Register%28System.String%2CSystem.Type%2CSystem.Type%2CSystem.Windows.PropertyMetadata%29>\-Aufruf für die Abhängigkeitseigenschaft legen die Metadaten den Standardwert als neue generische <xref:System.Collections.Generic.List%601> fest.  
  
 <!-- TODO: review snippet reference [!code-csharp[PropertiesOvwSupport#CollectionProblemDefinition](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemdefinition)]  -->
 [!code-vb[PropertiesOvwSupport#CollectionProblemDefinition](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemdefinition)]  
[!code-csharp[PropertiesOvwSupport#CollectionProblemEndB](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemendb)]
[!code-vb[PropertiesOvwSupport#CollectionProblemEndB](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemendb)]  
  
 Wenn Sie jedoch den Code einfach so wie dargestellt lassen, wird der einzelne Listenstandardwert für alle Instanzen von `Aquarium` freigegeben.  Beim Ausführen des folgenden Testcodes, der zeigen soll, wie Sie zwei separate `Aquarium`\-Instanzen instanziieren und jeder einen einzelnen unterschiedlichen `Fish` hinzufügen würden, wäre das Ergebnis überraschend:  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemTestCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemtestcode)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemTestCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemtestcode)]  
  
 Statt über einen Eintrag in jeder Auflistung verfügt jede Auflistung über zwei Einträge\!  Dies liegt daran, dass jedes `Aquarium` seinen `Fish` der Standardwertauflistung hinzugefügt hat, die aus einem einzigen Konstruktoraufruf in den Metadaten resultiert und daher für alle Instanzen freigegeben ist.  Diese Situation ist in nahezu keinem Fall erwünscht.  
  
 Um dieses Problem zu beheben, müssen Sie für den Abhängigkeitseigenschaftswert der Auflistung eine eindeutige Instanz im Rahmen der Klassenkonstruktorlogik festlegen.  Da diese Eigenschaft eine schreibgeschützte Abhängigkeitseigenschaft ist, verwenden Sie zur Festlegung die <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyPropertyKey%2CSystem.Object%29>\-Methode, mit dem <xref:System.Windows.DependencyPropertyKey>, der nur innerhalb der Klasse verfügbar ist.  
  
 [!code-csharp[PropertiesOvwSupport#CollectionProblemCtor](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PropertiesOvwSupport/CSharp/page4.xaml.cs#collectionproblemctor)]
 [!code-vb[PropertiesOvwSupport#CollectionProblemCtor](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PropertiesOvwSupport/visualbasic/page4.xaml.vb#collectionproblemctor)]  
  
 Wenn Sie nun denselben Test erneut ausführen würden, entsprächen die Ergebnisse eher Ihren Erwartungen, da jedes `Aquarium` jetzt seine eigene eindeutige Auflistung unterstützt.  
  
 Dieses Muster sieht geringfügig anders aus, wenn Sie sich für eine nicht schreibgeschützte Auflistungseigenschaft entscheiden.  In diesem Fall rufen Sie den öffentlichen set\-Accessor vom Konstruktor aus auf, um die Initialisierung durchzuführen. Dadurch würde weiterhin die Nicht\-Schlüssel\-Signatur von <xref:System.Windows.DependencyObject.SetValue%28System.Windows.DependencyProperty%2CSystem.Object%29> innerhalb Ihres set\-Wrappers aufgerufen, mit einem öffentlichen <xref:System.Windows.DependencyProperty>\-Bezeichner.  
  
## Melden von Bindungswertänderungen durch Auflistungseigenschaften  
 Eine Auflistungseigenschaft, die selbst eine Abhängigkeitseigenschaft ist, meldet nicht automatisch Änderungen an ihren untergeordneten Eigenschaften.  Wenn Sie Bindungen in einer Auflistung erstellen, kann dies die Bindung daran hindern, Änderungen zu melden, sodass einige Datenbindungsszenarien ungültig gemacht werden.  Wenn Sie jedoch den <xref:System.Windows.FreezableCollection%601>\-Auflistungstyp als Ihren Auflistungstyp verwenden, werden Änderungen an untergeordneten Elementen in der Auflistung ordnungsgemäß gemeldet, und die Bindung funktioniert wie erwartet.  
  
 Um die Bindung von untergeordneten Eigenschaften in einem Abhängigkeitsobjekt zu aktivieren, erstellen Sie die Auflistungseigenschaft als <xref:System.Windows.FreezableCollection%601>\-Typ mit einer Typeinschränkung für diese Auflistung bezüglich jeder vom <xref:System.Windows.DependencyObject> abgeleiteten Klasse.  
  
## Siehe auch  
 <xref:System.Windows.FreezableCollection%601>   
 [XAML\- und benutzerdefinierte Klassen für WPF](../../../../docs/framework/wpf/advanced/xaml-and-custom-classes-for-wpf.md)   
 [Übersicht über Datenbindung](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md)   
 [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)