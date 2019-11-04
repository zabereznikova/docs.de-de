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
ms.openlocfilehash: 85e6862d59284df1b51bf5ea7fbba786fe0492d7
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458967"
---
# <a name="componentresourcekey-markup-extension"></a>ComponentResourceKey-Markuperweiterung
Definiert und verweist Schlüssel für Ressourcen, die aus externen Assemblys geladen werden. Dadurch kann eine Ressourcen Suche einen Zieltyp in einer Assembly anstelle eines expliziten Ressourcen Wörterbuchs in einer Assembly oder in einer Klasse angeben.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Verwendung von XAML-Attributen (Setting Key, Compact)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Verwendung von XAML-Attributen (Setting Key, verbose)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Verwendung von XAML-Attributen (Anfordern von Ressourcen, Compact)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Verwendung von XAML-Attributen (Anfordern von Ressourcen, ausführlich)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`targetTypeName`|Der Name des in der Ressourcenassembly definierten öffentlichen common Language Runtime Typs (CLR).|  
|`targetID`|Der Schlüssel für die Ressource. Wenn Ressourcen gesucht werden, werden `targetID` analog zur [x:Key-Direktive](../../xaml-services/x-key-directive.md) der Ressource.|  
  
## <a name="remarks"></a>Hinweise  
 Wie in den obigen Verwendungsmöglichkeiten zu sehen ist, wird eine {`ComponentResourceKey`}-Markup Erweiterungs Verwendung an zwei Stellen gefunden:  
  
- Die Definition eines Schlüssels innerhalb eines Design Ressourcen Wörterbuchs, wie von einem Steuerelement Autor bereitgestellt.  
  
- Zugreifen auf eine Design Ressource aus der Assembly, wenn Sie das Steuerelement neu erstellen, aber Eigenschaftswerte verwenden möchten, die aus Ressourcen stammen, die von den Designs des Steuer Elements bereitgestellt werden.  
  
 Zum Verweisen auf Komponenten Ressourcen, die von Designs stammen, empfiehlt es sich im Allgemeinen, anstelle von `{StaticResource}``{DynamicResource}` zu verwenden. Dies wird in den Verwendungsmöglichkeiten angezeigt. `{DynamicResource}` wird empfohlen, da das Design selbst vom Benutzer geändert werden kann. Wenn Sie möchten, dass die Komponenten Ressource, die dem Steuerelement Autor am ehesten entspricht, um ein Design zu unterstützen, sollten Sie auch den Komponenten Ressourcen Verweis als dynamisch festlegen.  
  
 Der-<xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifiziert einen Typ, der in der Zielassembly vorhanden ist, in der die Ressource tatsächlich definiert ist. Eine `ComponentResourceKey` kann definiert und verwendet werden, unabhängig davon, wo die <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> definiert ist, aber schließlich muss der Typ durch referenzierte Assemblys aufgelöst werden.  
  
 Eine häufige Verwendung für <xref:System.Windows.ComponentResourceKey> besteht darin, Schlüssel zu definieren, die dann als Member einer Klasse verfügbar gemacht werden. Für diese Verwendung verwenden Sie den <xref:System.Windows.ComponentResourceKey>-Klassenkonstruktor, nicht die Markup Erweiterung. Weitere Informationen finden Sie unter <xref:System.Windows.ComponentResourceKey>oder im Abschnitt "definieren und verweisen auf Schlüssel für Design Ressourcen" in der [Übersicht über das Erstellen](../controls/control-authoring-overview.md)von Themen zur Dokument Steuerung.  
  
 Sowohl beim Einrichten von Schlüsseln als auch beim Verweisen auf Schlüssel gebundene Ressourcen wird die Attribut Syntax häufig für die `ComponentResourceKey` Markup Erweiterung verwendet.  
  
 Die gezeigte Compact-Syntax basiert auf der <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType>-Konstruktorsignatur und der Positions Parameter Verwendung einer Markup Erweiterung. Die Reihenfolge, in der die `targetTypeName` und `targetID` angegeben sind, ist wichtig. Die ausführliche Syntax basiert auf dem <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> Parameter losen Konstruktor und legt dann die <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> und <xref:System.Windows.ComponentResourceKey.ResourceId%2A> auf eine Weise fest, die einer echten Attribut Syntax für ein Objekt Element entspricht. In der ausführlichen Syntax ist die Reihenfolge, in der die Eigenschaften festgelegt werden, nicht wichtig. Die Beziehung und die Mechanismen dieser beiden Alternativen (Compact und verbose) werden im Thema [Markup Erweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)ausführlicher beschrieben.  
  
 Technisch gesehen kann der Wert für `targetID` ein beliebiges Objekt sein, es muss sich jedoch nicht um eine Zeichenfolge handeln. Die häufigste Verwendung in WPF besteht jedoch darin, den `targetID` Wert mit Formularen auszurichten, bei denen es sich um Zeichen folgen handelt und diese Zeichen folgen in der [XamlName-Grammatik](../../xaml-services/xamlname-grammar.md)gültig sind.  
  
 `ComponentResourceKey` können in der Objekt Element Syntax verwendet werden. In diesem Fall ist es erforderlich, den Wert der Eigenschaften <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> und <xref:System.Windows.ComponentResourceKey.ResourceId%2A> anzugeben, um die Erweiterung ordnungsgemäß zu initialisieren.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Reader-Implementierung wird die Handhabung dieser Markup Erweiterung durch die <xref:System.Windows.ComponentResourceKey>-Klasse definiert.  
  
 `ComponentResourceKey` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
