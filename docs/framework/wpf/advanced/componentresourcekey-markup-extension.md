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
ms.openlocfilehash: f86b7000b97bbc1287347947a9244c24a7de74c2
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/24/2020
ms.locfileid: "82141138"
---
# <a name="componentresourcekey-markup-extension"></a>ComponentResourceKey-Markuperweiterung
Definiert und verweist Schlüssel für Ressourcen, die aus externen Assemblys geladen werden. Dadurch kann eine Ressourcen Suche einen Zieltyp in einer Assembly anstelle eines expliziten Ressourcen Wörterbuchs in einer Assembly oder in einer Klasse angeben.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>Verwendung von XAML-Attributen (Setting Key, Compact)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" ... />  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>Verwendung von XAML-Attributen (Setting Key, verbose)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" ... />  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>Verwendung von XAML-Attributen (Anfordern von Ressourcen, Compact)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" ... />  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>Verwendung von XAML-Attributen (Anfordern von Ressourcen, ausführlich)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" ... />  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`targetTypeName`|Der Name des in der Ressourcenassembly definierten öffentlichen common Language Runtime Typs (CLR).|  
|`targetID`|Der Schlüssel für die Ressource. Wenn Ressourcen gesucht werden, `targetID` entspricht der [x:Key-Direktive](../../../desktop-wpf/xaml-services/xkey-directive.md) der Ressource.|  
  
## <a name="remarks"></a>Bemerkungen  
 Wie in den obigen Verwendungen zu sehen ist,`ComponentResourceKey`wird eine {} Markup Erweiterungs Verwendung an zwei Stellen gefunden:  
  
- Die Definition eines Schlüssels innerhalb eines Design Ressourcen Wörterbuchs, wie von einem Steuerelement Autor bereitgestellt.  
  
- Zugreifen auf eine Design Ressource aus der Assembly, wenn Sie das Steuerelement neu erstellen, aber Eigenschaftswerte verwenden möchten, die aus Ressourcen stammen, die von den Designs des Steuer Elements bereitgestellt werden.  
  
 Zum Verweisen auf Komponenten Ressourcen, die von Designs stammen, empfiehlt es sich im Allgemeinen, `{DynamicResource}` anstelle von `{StaticResource}`zu verwenden. Dies wird in den Verwendungsmöglichkeiten angezeigt. `{DynamicResource}`wird empfohlen, da das Design selbst vom Benutzer geändert werden kann. Wenn Sie möchten, dass die Komponenten Ressource, die dem Steuerelement Autor am ehesten entspricht, um ein Design zu unterstützen, sollten Sie auch den Komponenten Ressourcen Verweis als dynamisch festlegen.  
  
 Der <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifiziert einen Typ, der in der Zielassembly vorhanden ist, in der die Ressource tatsächlich definiert ist. Ein `ComponentResourceKey` kann definiert und verwendet werden, unabhängig davon, wo definiert <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> ist, aber schließlich muss der Typ durch referenzierte Assemblys aufgelöst werden.  
  
 Eine häufige Verwendung für <xref:System.Windows.ComponentResourceKey> ist das Definieren von Schlüsseln, die dann als Member einer Klasse verfügbar gemacht werden. Für diese Verwendung verwenden Sie den <xref:System.Windows.ComponentResourceKey> -Klassenkonstruktor, nicht die Markup Erweiterung. Weitere Informationen finden <xref:System.Windows.ComponentResourceKey>Sie unter oder im Abschnitt "definieren und verweisen auf Schlüssel für Design Ressourcen" des Themas How [Control Authoring Overview](../controls/control-authoring-overview.md).  
  
 Sowohl beim Einrichten von Schlüsseln als auch beim Verweisen auf Schlüssel gebundene Ressourcen wird die Attribut Syntax häufig `ComponentResourceKey` für die Markup Erweiterung verwendet.  
  
 Die gezeigte Compact-Syntax basiert auf <xref:System.Windows.ComponentResourceKey.%23ctor%2A> der Konstruktorsignatur und der Positions Parameter Verwendung einer Markup Erweiterung. Die Reihenfolge, in `targetTypeName` der `targetID` die und angegeben werden, ist wichtig. Die ausführliche Syntax basiert auf dem <xref:System.Windows.ComponentResourceKey.%23ctor%2A> Parameter losen Konstruktor und legt dann <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> und <xref:System.Windows.ComponentResourceKey.ResourceId%2A> auf eine Weise fest, die einer echten Attribut Syntax für ein Objekt Element entspricht. In der ausführlichen Syntax ist die Reihenfolge, in der die Eigenschaften festgelegt werden, nicht wichtig. Die Beziehung und die Mechanismen dieser beiden Alternativen (Compact und verbose) werden im Thema [Markup Erweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)ausführlicher beschrieben.  
  
 Technisch gesehen kann der Wert `targetID` für ein beliebiges Objekt sein, es muss sich jedoch nicht um eine Zeichenfolge handeln. Die häufigste Verwendung in WPF besteht jedoch darin, den `targetID` Wert mit Formularen auszurichten, bei denen es sich um Zeichen folgen handelt, und in denen diese Zeichen folgen in der [XamlName-Grammatik](../../../desktop-wpf/xaml-services/xamlname-grammar.md)gültig sind.  
  
 `ComponentResourceKey`kann in der Objekt Element Syntax verwendet werden. In diesem Fall ist die Angabe des Werts der <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> -Eigenschaft <xref:System.Windows.ComponentResourceKey.ResourceId%2A> und der-Eigenschaft erforderlich, um die Erweiterung ordnungsgemäß zu initialisieren.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Reader-Implementierung wird die Handhabung dieser Markup Erweiterung durch die <xref:System.Windows.ComponentResourceKey> -Klasse definiert.  
  
 `ComponentResourceKey` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
