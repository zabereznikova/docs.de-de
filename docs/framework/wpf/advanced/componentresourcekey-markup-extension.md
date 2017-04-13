---
title: "ComponentResourceKey-Markuperweiterung | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ComponentResourceKey"
  - "ComponentResourceKeyExtension"
helpviewer_keywords: 
  - "ComponentResourceKey-Markuperweiterung"
  - "XAML, ComponentResourceKey-Markuperweiterung"
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# ComponentResourceKey-Markuperweiterung
Definiert und verweist auf Schlüssel für Ressourcen, die aus externen Assemblys geladen werden.  Dadurch kann in einem Ressourcenlookup ein Zieltyp in einer Assembly angegebenen werden, und es muss nicht explizit ein Ressourcenwörterbuch in einer Assembly oder einer Klasse angegeben werden.  
  
## Verwendung von XAML\-Attributen \(Festlegen des Schlüssels, kompakt\)  
  
```  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## Verwendung von XAML\-Attributen \(Festlegen des Schlüssels, ausführlich\)  
  
```  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## Verwendung von XAML\-Attributen \(Anfordern der Ressource, kompakt\)  
  
```  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## Verwendung von XAML\-Attributen \(Anfordern der Ressource, ausführlich\)  
  
```  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`targetTypeName`|Der Name des öffentlichen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)]\-Typs, der in der Ressourcenassembly definiert ist.|  
|`targetID`|Der Schlüssel für die Ressource.  Wenn Ressourcen gesucht werden, ist `targetID` analog zum [x:Key\-Direktive](../../../../docs/framework/xaml-services/x-key-directive.md) der Ressource.|  
  
## Hinweise  
 Wie oben in den Verwendungen zu sehen war, kann eine {`ComponentResourceKey` } Markuperweiterungsverwendung an zwei Stellen gefunden werden:  
  
-   Die Definition eines Schlüssels in einem Designressourcenwörterbuch, wie von einem Steuerelementautor bereitgestellt.  
  
-   Beim Zugreifen auf eine Designressource von der Assembly, wenn Sie eine neue Vorlage für das Steuerelement verwenden, aber die Eigenschaftswerte nutzen möchten, die von Ressourcen kommen,die von den Designs des Steuerelements bereitgestellt werden.  
  
 Zum Verweisen auf Komponentenressourcen, die aus Designs kommen, wird im Allgemeinen empfohlen, dass Sie `{DynamicResource}` statt `{StaticResource}` verwenden.  Dies wird in den Verwendungen angezeigt.  `{DynamicResource}` wird empfohlen, da das Design selbst vom Benutzer geändert werden kann.  Wenn Sie die Komponentenressource möchten, die am besten der Absicht des Steuerelementautors zur Unterstützung eines Designs entspricht, sollten Sie der Komponentenressourcenverweis ermöglichen, auch dynamisch zu sein.  
  
 Mit <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> wird ein Typ bestimmt, der als Typ in der Zielassembly vorhanden ist, in der die Ressource eigentlich definiert wird.  Ein `ComponentResourceKey` kann auch ohne genaue Kenntnisse darüber, wo <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> definiert ist, definiert und verwendet werden, muss den Typ jedoch letztlich über Assemblys auflösen, auf die verwiesen wird.  
  
 Eine häufige Verwendung für <xref:System.Windows.ComponentResourceKey> ist die Definition von Schlüsseln, die dann als Member einer Klasse verfügbar gemacht werden.  Für diese Verwendung müssen Sie den <xref:System.Windows.ComponentResourceKey>\-Klassenkonstruktor einsetzen, nicht die Markuperweiterung.  Weitere Informationen finden Sie unter <xref:System.Windows.ComponentResourceKey> oder im Abschnitt "Definieren und Angeben von Schlüsseln für Designressourcen" des Themas [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Sowohl beim Einrichten von Schlüsseln sowie Verweisen auf Ressourcen mit Schlüsseln wird die Attributsyntax häufig für die `ComponentResourceKey`\-Markuperweiterung verwendet.  
  
 Die dargestellte kompakte Syntax stützt sich auf die <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=fullName>\-Konstruktorsignatur und die positionelle Parameternutzung einer Markuperweiterung.  Die Reihenfolge, in der `targetTypeName` und `targetID` angegeben werden, ist wichtig.  Die ausführliche Syntax stützt sich auf den <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=fullName>\-Standardkonstruktor. Dann werden <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> und <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in analoger Weise zur tatsächlichen Attributsyntax für ein Objektelement festgelegt.  In der ausführlichen Syntax ist die Reihenfolge, in der die Eigenschaften festgelegt werden, nicht wichtig.  Die Beziehung und die Mechanismen dieser Alternativen \(kompakt und ausführlich\) werden detaillierter im Thema [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md) beschrieben.  
  
 Technisch kann der Wert für `targetID` jedes Objekt sein, es muss keine Zeichenfolge sein.  Die gängigste Verwendung in WPF ist jedoch, den `targetID`\-Wert an Formularen auszurichten, die Zeichenfolgen sind, und wo solche Zeichenfolgen im [XamlName\-Grammatik](../../../../docs/framework/xaml-services/xamlname-grammar.md) gültig sind.  
  
 `ComponentResourceKey` kann in der Objektelementsyntax verwendet werden.  In diesem Fall ist die Angabe des Werts der Eigenschaften <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> und <xref:System.Windows.ComponentResourceKey.ResourceId%2A> erforderlich, um die Erweiterung ordnungsgemäß zu initialisieren.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Readerimplementierung wird die Verarbeitung dieser Markuperweiterung von der <xref:System.Windows.ComponentResourceKey>\-Klasse definiert.  
  
 `ComponentResourceKey` ist eine Markuperweiterung.  Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.  Alle Markuperweiterungen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwenden die Zeichen { und } in der Attributsyntax. Dies ist die Konvention, anhand der ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss.  Weitere Informationen finden Sie unter [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Siehe auch  
 <xref:System.Windows.ComponentResourceKey>   
 <xref:System.Windows.Controls.ControlTemplate>   
 [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)