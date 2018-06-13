---
title: ComponentResourceKey-Markuperweiterung
ms.date: 03/30/2017
f1_keywords:
- ComponentResourceKey
- ComponentResourceKeyExtension
helpviewer_keywords:
- ComponentResourceKey markup extension [WPF]
- XAML [WPF], ComponentResourceKey markup extension
ms.assetid: d6bcdbe6-61b3-40a7-b381-4e02185b5a85
ms.openlocfilehash: d11c26add084165eaa9fd0b319a375c4b98c7fb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33540409"
---
# <a name="componentresourcekey-markup-extension"></a>ComponentResourceKey-Markuperweiterung
Definiert und verweist auf die Schlüssel für Ressourcen, die von externen Assemblys geladen werden. Dies ermöglicht eine Ressourcensuche einen Zieltyp in einer Assembly, anstatt explizit ein Ressourcenwörterbuch in einer Assembly oder einer Klasse angeben.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Verwendung von XAML-Attributen (Festlegen des Schlüssels, compact)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Verwendung von XAML-Attributen (Festlegen des Schlüssels, verbose)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Verwendung von XAML-Attributen (Anfordern der Ressource, compact)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Verwendung von XAML-Attributen (Anfordern der Ressource, verbose)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`targetTypeName`|Der Name der öffentlichen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Typ, der in der Ressourcenassembly definiert ist.|  
|`targetID`|Der Schlüssel für die Ressource. Wenn Ressourcen gesucht werden `targetID` werden analog zu den [X: Key-Anweisung](../../../../docs/framework/xaml-services/x-key-directive.md) der Ressource.|  
  
## <a name="remarks"></a>Hinweise  
 Wie in den oben genannten Verwendungen einer {`ComponentResourceKey`} Markuperweiterungsverwendung an zwei Stellen gefunden wird:  
  
-   Die Definition eines Schlüssels in einem Designressourcenwörterbuch, Autor eines Steuerelements bereitgestellt.  
  
-   Zugreifen auf eine Ressource Design aus der Assembly, wenn Sie Designressource das Steuerelement aber Eigenschaftswerte, die von Ressourcen, die das Steuerelement Designs gebotenen stammen, verwendet werden soll.  
  
 Zum Verweisen auf Ressourcen, die von Designs stammen, wird im Allgemeinen empfohlen, Sie verwenden `{DynamicResource}` statt `{StaticResource}`. Dies wird in den Verwendungen gezeigt. `{DynamicResource}` wird empfohlen, da das Design selbst vom Benutzer geändert werden kann. Wenn die Komponentenressource soll, die Absicht der Autor des Steuerelements für die Unterstützung eines Designs am ehesten entspricht, sollten Sie Ihre Komponentenressourcenverweis auch dynamisch zu sein aktivieren.  
  
 Die <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifiziert einen Typ, der in der Zielassembly vorhanden ist, in dem die Ressource tatsächlich definiert. Ein `ComponentResourceKey` definiert und unabhängig von genau zu wissen, verwendet werden können, in denen die <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> definiert ist, muss jedoch letztlich auflösen den Typ von Assemblys, auf die verwiesen wird.  
  
 Eine allgemeine Verwendung für <xref:System.Windows.ComponentResourceKey> besteht darin, Schlüssel, die anschließend zur Verfügung gestellt werden als Member einer Klasse definieren. Verwenden Sie für diese Verwendung der <xref:System.Windows.ComponentResourceKey> Klassenkonstruktor, nicht die Markuperweiterung. Weitere Informationen finden Sie unter <xref:System.Windows.ComponentResourceKey>, oder im Abschnitt "Definieren von und verweisen auf Schlüssel für Design-Ressourcen" dieses Themas [Steuerelement Dokumenterstellung (Übersicht)](../../../../docs/framework/wpf/controls/control-authoring-overview.md).  
  
 Sowohl beim Einrichten von Schlüsseln und verweisen auf Ressourcen mit Schlüsseln, die Attributsyntax ist häufig verwendet für die `ComponentResourceKey` Markuperweiterung.  
  
 Die kompakte Syntax basiert auf der <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> Konstruktorsignatur und Positionsparameterverwendung eine Markuperweiterung. In welcher Reihenfolge die `targetTypeName` und `targetID` sind wichtig ist. Die ausführliche Syntax basiert auf der <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> Standardkonstruktor und legt dann die <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> und <xref:System.Windows.ComponentResourceKey.ResourceId%2A> in einer Weise, die analog zu einem "true" Attributsyntax auf einer Object-Element ist. In der ausführliche Syntax ist die Reihenfolge, in der die Eigenschaften festgelegt werden, nicht wichtig. Die Beziehung und die Mechanismen der folgenden zwei alternativen (compact und verbose) wird in diesem Thema ausführlicher beschrieben [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
 Technisch gesehen ist der Wert für `targetID` kann jedes Objekt sein, er muss nicht in eine Zeichenfolge sein. Die häufigste Verwendung in WPF ist jedoch zum Ausrichten der `targetID` Wert mit Formularen, die Zeichenfolgen sind, und, in denen diese Zeichenfolgen sind gültig, in, der [XamlName-Grammatik](../../../../docs/framework/xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey` kann in der Syntax der Object-Element verwendet werden. In diesem Fall geben Sie den Wert sowohl die <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> und <xref:System.Windows.ComponentResourceKey.ResourceId%2A> Eigenschaften ist erforderlich, um die Erweiterung zu initialisieren.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] leserimplementierung, die Handhabung für diese Markuperweiterung wird definiert, indem die <xref:System.Windows.ComponentResourceKey> Klasse.  
  
 `ComponentResourceKey` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.ComponentResourceKey>  
 <xref:System.Windows.Controls.ControlTemplate>  
 [Übersicht über das Erstellen von Steuerelementen](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
 [Übersicht über XAML (WPF)](../../../../docs/framework/wpf/advanced/xaml-overview-wpf.md)  
 [Markuperweiterungen und WPF-XAML](../../../../docs/framework/wpf/advanced/markup-extensions-and-wpf-xaml.md)
