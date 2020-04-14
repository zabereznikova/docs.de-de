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
ms.openlocfilehash: 4cdba2a61be4e9686cd2120fd90a213534c222c8
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243361"
---
# <a name="componentresourcekey-markup-extension"></a>ComponentResourceKey-Markuperweiterung
Definiert und verweist auf Schlüssel für Ressourcen, die von externen Assemblys geladen werden. Dadurch kann eine Ressourcensuche einen Zieltyp in einer Assembly anstelle eines expliziten Ressourcenwörterbuchs in einer Assembly oder in einer Klasse angeben.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>XAML-Attributverwendung (Einstellungstaste, kompakt)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>XAML-Attributverwendung (Einstellungstaste, ausführlich)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>XAML-Attributverwendung (Anforderung von Ressource, kompakt)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>XAML-Attributverwendung (Anfordern von Ressource, ausführlich)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`targetTypeName`|Der Name des CLR-Typs (Common Common Language Runtime), der in der Ressourcenassembly definiert ist.|  
|`targetID`|Der Schlüssel für die Ressource. Wenn Ressourcen gesucht `targetID` werden, wird analog zur [x:Key-Richtlinie](../../../desktop-wpf/xaml-services/xkey-directive.md) der Ressource sein.|  
  
## <a name="remarks"></a>Bemerkungen  
 Wie in den obigen Verwendungen zu sehen, wird an zwei Stellen eine Verwendung von Markuperweiterungen`ComponentResourceKey`gefunden:  
  
- Die Definition eines Schlüssels in einem Designressourcenwörterbuch, wie von einem Steuerelementautor bereitgestellt.  
  
- Beim Zugriff auf eine Designressource aus der Assembly, wenn Sie das Steuerelement neu templieren, aber Eigenschaftswerte verwenden möchten, die aus Ressourcen stammen, die von den Designs des Steuerelements bereitgestellt werden.  
  
 Für den Verweis auf Komponentenressourcen, die aus Designs `{DynamicResource}` stammen, `{StaticResource}`wird im Allgemeinen empfohlen, anstelle von zu verwenden. Dies wird in den Verwendungen angezeigt. `{DynamicResource}`wird empfohlen, da das Design selbst vom Benutzer geändert werden kann. Wenn Sie möchten, dass die Komponentenressource, die am ehesten mit der Absicht des Steuerelementautors übereinstimmt, ein Design zu unterstützen, dynamisch sein soll.  
  
 Der <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifiziert einen Typ, der in der Zielassembly vorhanden ist, in der die Ressource tatsächlich definiert ist. A `ComponentResourceKey` kann definiert und verwendet werden, <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> unabhängig davon, genau zu wissen, wo die definiert ist, muss aber schließlich den Typ über Assemblys auflösen, auf die verwiesen wird.  
  
 Eine häufige <xref:System.Windows.ComponentResourceKey> Verwendung für besteht darin, Schlüssel zu definieren, die dann als Member einer Klasse verfügbar gemacht werden. Für diese Verwendung verwenden <xref:System.Windows.ComponentResourceKey> Sie den Klassenkonstruktor und nicht die Markuperweiterung. Weitere Informationen finden <xref:System.Windows.ComponentResourceKey>Sie unter , oder im Abschnitt "Definieren und Referenzieren von Schlüsseln für Themenressourcen" im Thema Übersicht zur Erstellung von [Steuerelementen](../controls/control-authoring-overview.md).  
  
 Sowohl für das Einrichten von Schlüsseln als auch für `ComponentResourceKey` das Verweisen auf schlüsselfertige Ressourcen wird die Attributsyntax häufig für die Markuperweiterung verwendet.  
  
 Die gezeigte kompakte <xref:System.Windows.ComponentResourceKey.%23ctor%2A> Syntax basiert auf der Konstruktorsignatur und der Verwendung eines Positionsparameters einer Markuperweiterung. Die Reihenfolge, `targetTypeName` in `targetID` der das und gegeben wird, ist wichtig. Die ausführliche Syntax basiert <xref:System.Windows.ComponentResourceKey.%23ctor%2A> auf dem parameterlosen Konstruktor <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> <xref:System.Windows.ComponentResourceKey.ResourceId%2A> und legt dann die und in einer Weise fest, die einer true Attributsyntax für ein Objektelement entspricht. In der ausführlichen Syntax ist die Reihenfolge, in der die Eigenschaften festgelegt sind, nicht wichtig. Die Beziehung und die Mechanismen dieser beiden Alternativen (kompakt und ausführlich) werden im Thema [Markup-Erweiterungen und WPF XAML](markup-extensions-and-wpf-xaml.md)ausführlicher beschrieben.  
  
 Technisch gesehen kann `targetID` der Wert für ein beliebiges Objekt sein, es muss keine Zeichenfolge sein. Die häufigste Verwendung in WPF besteht `targetID` jedoch darin, den Wert an Formularen auszurichten, die Zeichenfolgen sind und bei denen solche Zeichenfolgen in der [XamlName-Grammatik](../../../desktop-wpf/xaml-services/xamlname-grammar.md)gültig sind.  
  
 `ComponentResourceKey`kann in der Objektelementsyntax verwendet werden. In diesem Fall ist die Angabe <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> <xref:System.Windows.ComponentResourceKey.ResourceId%2A> des Werts der und der Eigenschaften erforderlich, um die Erweiterung ordnungsgemäß zu initialisieren.  
  
 In [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] der Reader-Implementierung wird die Verarbeitung für <xref:System.Windows.ComponentResourceKey> diese Markuperweiterung durch die Klasse definiert.  
  
 `ComponentResourceKey` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
- [Übersicht über XAML (WPF)](../../../desktop-wpf/fundamentals/xaml.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
