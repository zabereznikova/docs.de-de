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
ms.openlocfilehash: ab38c2c885e230183852fff895e0a8a8f1d7a666
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459491"
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
|`assemblyUri`|Der URI (Uniform Resource Identifier) der Assembly, die Design Informationen enthält. In der Regel ist dies eine Paket-URI, die auf eine Assembly in dem größeren Paket verweist. Assemblyressourcen und Paket-URIs vereinfachen die Bereitstellung. Weitere Informationen finden Sie unter [Paket-URIs in WPF](../app-development/pack-uris-in-wpf.md).|  
  
## <a name="remarks"></a>Hinweise  
 Diese Erweiterung soll nur einen bestimmten Eigenschafts Wert ausfüllen: einen Wert für <xref:System.Windows.ResourceDictionary.Source%2A?displayProperty=nameWithType>.  
  
 Mit dieser Erweiterung können Sie eine einzelne nur-Ressource-Assembly angeben, die einige Formate enthält, die nur verwendet werden, wenn das Windows Aero-Design auf das System des Benutzers angewendet wird, andere Stile nur, wenn das Luna-Design aktiv ist usw. Durch die Verwendung dieser Erweiterung kann der Inhalt eines steuerelementspezifischen Ressourcenverzeichnisses automatisch ungültig gemacht und erneut geladen werden, sodass er bei Bedarf für ein anderes Design angegeben werden kann.  
  
 Die `assemblyUri` Zeichenfolge (<xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>-Eigenschafts Wert) bildet die Grundlage einer Benennungs Konvention, die identifiziert, welches Wörterbuch für ein bestimmtes Design gilt. Die <xref:System.Windows.Markup.MarkupExtension.ProvideValue%2A> Logik für `ThemeDictionary` schließt die Konvention ab, indem ein URI (Uniform Resource Identifier) erstellt wird, der auf eine bestimmte Design Dictionary-Variante verweist, die in einer vorkompilierten Ressourcenassembly enthalten ist. Diese Konvention und die Designinteraktionen mit allgemeinen Formatierungen von Steuerelementen und Formatierungen auf Seiten-/Anwendungsebene als Konzept werden hier nicht im Detail behandelt. Das grundlegende Szenario für die Verwendung von `ThemeDictionary` besteht darin, die <xref:System.Windows.ResourceDictionary.Source%2A>-Eigenschaft einer `ResourceDictionary` anzugeben, die auf der Anwendungsebene deklariert ist. Wenn Sie einen URI für die Assembly über eine `ThemeDictionary` Erweiterung anstelle eines direkten URIs bereitstellen, stellt die Erweiterungs Logik eine invalidierungslogik bereit, die immer dann angewendet wird, wenn das Systemdesign geändert wird.  
  
 Die Attributsyntax ist die mit dieser Markuperweiterung am häufigsten verwendete Syntax. Das Zeichenfolgentoken, das auf die `ThemeDictionary`-Bezeichnerzeichenfolge folgt, wird als <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>-Wert der zugrunde liegenden <xref:System.Windows.ThemeDictionaryExtension>-Erweiterungsklasse zugeordnet.  
  
 `ThemeDictionary` kann auch in der Objektelementsyntax verwendet werden. In diesem Fall muss der Wert der <xref:System.Windows.ThemeDictionaryExtension.AssemblyName%2A>-Eigenschaft angegeben werden.  
  
 `ThemeDictionary` kann zudem in einer ausführlichen Attributverwendung verwendet werden, die die <xref:System.Windows.Markup.StaticExtension.Member%2A>-Eigenschaft als Eigenschaft=Wert-Paar angibt:  
  
```xml  
<object property="{ThemeDictionary AssemblyName=assemblyUri}" .../>  
```  
  
 Die ausführliche Verwendung ist häufig hilfreich, wenn für eine Erweiterung mehr als eine Eigenschaft festgelegt werden kann oder wenn bestimmte Eigenschaften optional sind. Da für `ThemeDictionary` nur eine (erforderliche) Eigenschaft festgelegt werden kann, ist diese ausführliche Verwendung unüblich.  
  
 In der Implementierung des [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessors wird die Behandlung dieser Markup Erweiterung durch die <xref:System.Windows.ThemeDictionaryExtension>-Klasse definiert.  
  
 `ThemeDictionary` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
- [WPF-Anwendungsressource, Inhalts- und Datendateien](../app-development/wpf-application-resource-content-and-data-files.md)
