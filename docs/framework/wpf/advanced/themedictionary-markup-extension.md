---
title: ThemeDictionary-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- ThemeDictionaryExtension
- ThemeDictionary
helpviewer_keywords:
- ThemeDictionary markup extension [WPF]
- XAML [WPF], ThemeDictionary markup extension
ms.assetid: aa75e10b-13dd-4989-972d-51bab63a05e2
ms.openlocfilehash: f6ba0fe45aa11063c79d673b26794072968f4200
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646191"
---
# <a name="themedictionary-markup-extension"></a>ThemeDictionary-Markuperweiterung
Bietet Autoren von benutzerdefinierten Steuerelementen oder Anwendungen, die Steuerelemente von Drittanbietern integrieren, eine Möglichkeit, designspezifische Ressourcenverzeichnisse für das Formatieren der Steuerelemente zu verwenden.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xml  
<object property="{ThemeDictionary assemblyUri}" .../>  
```  
  
## <a name="xaml-object-element-usage"></a>Verwendung von XAML-Objektelementen  
  
```xml  
<object>  
  <object.property>  
    <ThemeDictionary AssemblyName="assemblyUri"/>  
  <object.property>  
<object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`assemblyUri`|Der URI (Uniform Resource Identifier) der Assembly, der Designinformationen enthält. In der Regel ist dies eine Paket-URI, die auf eine Assembly in dem größeren Paket verweist. Assemblyressourcen und Paket-URIs vereinfachen die Bereitstellung. Weitere Informationen finden Sie unter [Paket-URIs in WPF](../app-development/pack-uris-in-wpf.md).|  
  
## <a name="remarks"></a>Bemerkungen  
 Diese Erweiterung soll nur einen bestimmten Eigenschaftswert <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>ausfüllen: einen Wert für .  
  
 Mithilfe dieser Erweiterung können Sie eine einzelne Assembly nur für Ressourcen angeben, die einige Stile enthält, die nur verwendet werden sollen, wenn das Windows Aero-Design auf das System des Benutzers angewendet wird, andere Stile nur dann, wenn das Luna-Design aktiv ist usw. Durch die Verwendung dieser Erweiterung kann der Inhalt eines steuerelementspezifischen Ressourcenverzeichnisses automatisch ungültig gemacht und erneut geladen werden, sodass er bei Bedarf für ein anderes Design angegeben werden kann.  
  
 Die `assemblyUri` Zeichenfolge<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> (Eigenschaftswert) bildet die Grundlage einer Namenskonvention, die identifiziert, welches Wörterbuch für ein bestimmtes Design gilt. Die <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> Logik `ThemeDictionary` für den Abschluss der Konvention durch Generieren eines einheitlichen Ressourcenbezeichners (URI), der auf eine bestimmte Designwörterbuchvariante verweist, wie sie in einer vorkompilierten Ressourcenassembly enthalten ist. Diese Konvention und die Designinteraktionen mit allgemeinen Formatierungen von Steuerelementen und Formatierungen auf Seiten-/Anwendungsebene als Konzept werden hier nicht im Detail behandelt. Das grundlegende Szenario `ThemeDictionary` für die <xref:System.Windows.ResourceDictionary.Source%2A> Verwendung `ResourceDictionary` besteht darin, die Eigenschaft einer deklarierten auf Anwendungsebene anzugeben. Wenn Sie einen URI für `ThemeDictionary` die Assembly über eine Erweiterung und nicht als direkten URI bereitstellen, stellt die Erweiterungslogik eine Invalidierungslogik bereit, die immer dann gilt, wenn sich das Systemdesign ändert.  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `ThemeDictionary`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>-Wert der zugrunde liegenden <xref:System.Windows.ThemeDictionaryExtension>-Erweiterungsklasse zugeordnet.  
  
 `ThemeDictionary` kann auch in der Objektelementsyntax verwendet werden. In diesem Fall ist die <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A> Angabe des Werts der Eigenschaft erforderlich.  
  
 `ThemeDictionary` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.Markup.StaticExtension.Member%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `ThemeDictionary` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] der Prozessorimplementierung wird die Verarbeitung für diese <xref:System.Windows.ThemeDictionaryExtension> Markuperweiterung durch die Klasse definiert.  
  
 `ThemeDictionary` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [WPF-Anwendungsressource, Inhalts- und Datendateien](../app-development/wpf-application-resource-content-and-data-files.md)
