---
title: "Laden von XAML und Abh&#228;ngigkeitseigenschaften | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Benutzerdefinierte Abhängigkeitseigenschaften"
  - "Abhängigkeitseigenschaften, XAML-Laden und"
  - "Laden von XML-Daten"
ms.assetid: 6eea9f4e-45ce-413b-a266-f08238737bf2
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# Laden von XAML und Abh&#228;ngigkeitseigenschaften
Die aktuelle [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessors berücksichtigt Abhängigkeitseigenschaften.  Der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor verwendet beim Laden binärer [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Daten und beim Verarbeiten von Attributen, bei denen es sich um Abhängigkeitseigenschaften handelt, Methoden des Eigenschaftensystems für Abhängigkeitseigenschaften.  Hierdurch werden die Eigenschaftenwrapper erfolgreich umgangen.  Wenn Sie benutzerdefinierte Abhängigkeitseigenschaften implementieren, müssen Sie dieses Verhalten berücksichtigen. Fügen Sie keinen anderen Code in den Eigenschaftenwrapper ein als die Methoden <xref:System.Windows.DependencyObject.GetValue%2A> und <xref:System.Windows.DependencyObject.SetValue%2A> des Eigenschaftensystems.  
  
 [!INCLUDE[autoOutline](../Token/autoOutline_md.md)]  
  
<a name="prerequisites"></a>   
## Vorbereitungsmaßnahmen  
 In diesem Thema wird vorausgesetzt, dass Sie sich mit Abhängigkeitseigenschaften aus Sicht eines Consumers und eines Autors vertraut gemacht sowie [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md) und [Benutzerdefinierte Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/custom-dependency-properties.md) gelesen haben.  Sie sollten außerdem [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md) und [Ausführliche Erläuterung der XAML\-Syntax](../../../../docs/framework/wpf/advanced/xaml-syntax-in-detail.md) gelesen haben.  
  
<a name="implementation"></a>   
## Implementierung und Leistung des WPF\-XAML\-Ladeprogramms  
 Für Implementierungen ist es einfacher, eine Eigenschaft als Abhängigkeitseigenschaft zu erkennen und diese mit der <xref:System.Windows.DependencyObject.SetValue%2A>\-Methode des Eigenschaftensystems festzulegen, als den Eigenschaftenwrapper und den zugehörigen Setter zu verwenden.  Der Grund hierfür ist, dass der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor das gesamte Objektmodell des zugrunde liegenden Codes herleiten muss, jedoch lediglich die von der Markupstruktur vorgegebenen Typ\- und Memberbeziehungen und verschiedene Zeichenfolgen bekannt sind.  
  
 Der Typ wird durch eine Kombination von xmlns\- und Assembly\-Attributen ermittelt, die Identifizierung der Member, die Ermittlung, welcher Member als Attribut festgelegt werden kann und welche Typen die Eigenschaftswerte unterstützen würde jedoch andernfalls eine komplexe Reflektion unter Verwendung von <xref:System.Reflection.PropertyInfo> erfordern.  Da die Abhängigkeitseigenschaften für einen bestimmten Typ über das Eigenschaftensystem als Speichertabelle zugänglich sind, verwendet die [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessors diese Tabelle und leitet her, dass eine gegebene Eigenschaft *ABC* effizienter festgelegt werden kann, indem <xref:System.Windows.DependencyObject.SetValue%2A> für den enthaltenen abgeleiteten Typ <xref:System.Windows.DependencyObject> aufgerufen wird, unter Verwendung des Abhängigkeitseigenschaft\-Bezeichners *ABCProperty*.  
  
<a name="implications"></a>   
## Auswirkungen auf benutzerdefinierte Abhängigkeitseigenschaften  
 Da mit der aktuellen [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-Implementierung des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessorverhaltens für das Festlegen von Eigenschaften die Wrapper vollständig umgangen werden, dürfen Sie keine weitere Logik in die Definitionen des Wrappers für die benutzerdefinierte Abhängigkeitseigenschaft einfügen.  Diese Logik wird nicht ausgeführt, wenn die Eigenschaft in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] statt in Code festgelegt wird.  
  
 Andere Aspekte des [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessors, die Eigenschaftswerte aus der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Verarbeitung abrufen, verwenden ebenfalls <xref:System.Windows.DependencyObject.GetValue%2A> statt den Wrapper.  Vermeiden Sie aus diesem Grund alle zusätzlichen Implementierungen in der `get`\-Definition, die über den <xref:System.Windows.DependencyObject.GetValue%2A>\-Aufruf hinausgehen.  
  
 Das folgende Beispiel zeigt eine empfohlene Abhängigkeitseigenschaft\-Definition mit Wrappern, wobei der Eigenschaftenbezeichner als `public` `static` `readonly`\-Feld gespeichert wird und die `get`\-Definition und die `set`\-Definition außer den erforderlichen Methoden des Eigenschaftensystems, die den zugrunde liegenden Code der Abhängigkeitseigenschaft definieren, keinen weiteren Code enthalten.  
  
 [!code-csharp[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WPFAquariumSln/CSharp/WPFAquariumObjects/Class1.cs#agwithwrapper)]
 [!code-vb[WPFAquariumSln#AGWithWrapper](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WPFAquariumSln/visualbasic/wpfaquariumobjects/class1.vb#agwithwrapper)]  
  
## Siehe auch  
 [Übersicht über Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-properties-overview.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Metadaten für Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-metadata.md)   
 [Abhängigkeitseigenschaften vom Auflistungstyp](../../../../docs/framework/wpf/advanced/collection-type-dependency-properties.md)   
 [Sicherheit von Abhängigkeitseigenschaften](../../../../docs/framework/wpf/advanced/dependency-property-security.md)   
 [Sichere Konstruktormuster für DependencyObjects](../../../../docs/framework/wpf/advanced/safe-constructor-patterns-for-dependencyobjects.md)