---
title: "ThemeDictionary-Markuperweiterung | Microsoft Docs"
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
  - "ThemeDictionaryExtension"
  - "ThemeDictionary"
helpviewer_keywords: 
  - "ThemeDictionary-Markuperweiterung"
  - "XAML, ThemeDictionary-Markuperweiterung"
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# ThemeDictionary-Markuperweiterung
Bietet Autoren von benutzerdefinierten Steuerelementen oder Anwendungen, die Steuerelemente von Drittanbietern integrieren, eine Möglichkeit, Design\-spezifische Ressourcenwörterbücher für das Formatieren der Steuerelemente zu verwenden.  
  
## Verwendung von XAML\-Attributen  
  
```  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## Verwendung von XAML\-Objektelementen  
  
```  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## XAML\-Werte  
  
|||  
|-|-|  
|`assemblyUri`|Die [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] der Assembly, die Designinformationen enthält.  In der Regel ist dies ein Paket\-URI, der auf eine Assembly in dem größeren Paket verweist.  Assemblyressourcen und Paket\-URIs vereinfachen die Bereitstellung.  Weitere Informationen finden Sie unter [Paket\-URI in WPF](../../../../docs/framework/wpf/app-development/pack-uris-in-wpf.md).|  
  
## Hinweise  
 Diese Erweiterung ist dazu gedacht, nur einen bestimmten Eigenschaftswert zu füllen: einen Wert für <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=fullName>.  
  
 Indem Sie diese Erweiterung verwenden, können Sie eine einzelne Assembly angeben, die nur aus Ressourcen besteht und einige Stile enthält, die nur verwendet werden können, wenn das [!INCLUDE[TLA#tla_aero](../../../../includes/tlasharptla-aero-md.md)]\-Design auf das System des Benutzers angewendet wird, sowie andere Stile, die nur verwendet werden können, wenn Luna aktiv ist, usw.  Durch die Verwendung dieser Erweiterung können die Inhalte eines steuerelementspezifischen Ressourcenwörterbuchs automatisch ungültig gemacht und neu geladen werden, sodass sie bei Bedarf für ein anderes Design angegeben werden können.  
  
 Die `assemblyUri`\-Zeichenfolge \(<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>\-Eigenschaftswert\) bildet die Grundlage einer Benennungskonvention, die angibt, welches Wörterbuch für ein bestimmtes Design gültig ist.  Die <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A>\-Logik für `ThemeDictionary` entspricht der Konvention, da ein [!INCLUDE[TLA#tla_uri](../../../../includes/tlasharptla-uri-md.md)] generiert wird, der auf eine bestimmte in einer vorkompilierten Ressourcenassembly enthaltene Variante eines Designwörterbuchs verweist.  Diese Konvention und die Designinteraktionen mit allgemeinen Formatierungen von Steuerelementen und Formatierungen auf Seiten\-\/Anwendungsebene als Konzept werden hier nicht im Detail behandelt.  Das grundlegende Szenario für die Verwendung von `ThemeDictionary` ist das Angeben der <xref:System.Windows.ResourceDictionary.Source%2A>\-Eigenschaft eines `ResourceDictionary`, das auf der Anwendungsebene deklariert ist.  Wenn Sie einen [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] für die Assembly über eine `ThemeDictionary`\-Erweiterung statt direkt als [!INCLUDE[TLA2#tla_uri](../../../../includes/tla2sharptla-uri-md.md)] bereitstellen, stellt die Erweiterungslogik eine Ungültigkeitslogik bereit, die bei Änderungen des Systemdesigns gültig wird.  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax.  Das Zeichenfolgentoken, das auf die `ThemeDictionary`\-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>\-Wert der zugrunde liegenden <xref:System.Windows.ThemeDictionaryExtension>\-Erweiterungsklasse zugeordnet.  
  
 `ThemeDictionary` wird möglicherweise auch in der Objektelementsyntax verwendet.  In diesem Fall muss der Wert für die <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>\-Eigenschaft angegeben werden.  
  
 `ThemeDictionary` kann zudem in einer ausführlichen Attributverwendung genutzt werden, die die <xref:System.Windows.Markup.StaticExtension.Member%2A>\-Eigenschaft als Eigenschaft\-Wert\-Paar angibt:  
  
```  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind.  Da für `ThemeDictionary` nur eine Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]\-[!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessorimplementierung wird die Handhabung dieser Markuperweiterung durch die <xref:System.Windows.ThemeDictionaryExtension>\-Klasse definiert.  
  
 `ThemeDictionary` ist eine Markuperweiterung.  Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll.  Alle Markuperweiterungen in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] verwenden die Zeichen { und } in der Attributsyntax. Dies ist die Konvention, anhand der ein [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]\-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss.  Weitere Informationen finden Sie unter [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## Siehe auch  
 [Erstellen von Formaten und Vorlagen](../../../../docs/framework/wpf/controls/styling-and-templating.md)   
 [Übersicht über XAML \(WPF\)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)   
 [Markuperweiterungen und WPF\-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)   
 [WPF\-Anwendungsressource, Inhalts\- und Datendateien](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md)