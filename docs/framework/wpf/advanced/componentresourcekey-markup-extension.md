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
ms.openlocfilehash: 5f72d6c3273cfda4276383cfe72f90196e5d4340
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169753"
---
# <a name="componentresourcekey-markup-extension"></a>ComponentResourceKey-Markuperweiterung
Definiert und verweist auf die Schlüssel für Ressourcen, die aus externen Assemblys geladen werden. Dies ermöglicht eine Ressourcensuche einen Zieltyp in einer Assembly, anstatt explizit ein Ressourcenwörterbuch in eine Assembly oder auf eine Klasse angeben.  
  
## <a name="xaml-attribute-usage-setting-key-compact"></a>XAML-Attributverwendung (Festlegen des Schlüssels, compact)  
  
```xml  
<object x:Key="{ComponentResourceKey {x:Type targetTypeName}, targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-setting-key-verbose"></a>XAML-Attributverwendung (Festlegen des Schlüssels, verbose)  
  
```xml  
<object x:Key="{ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-compact"></a>XAML-Attributverwendung (anfordernden Ressource, compact)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey {x:Type targetTypeName}, targetID}}" .../>  
```  
  
## <a name="xaml-attribute-usage-requesting-resource-verbose"></a>XAML-Attributverwendung (anfordernden Ressource, verbose)  
  
```xml  
<object property="{DynamicResource {ComponentResourceKey TypeInTargetAssembly={x:Type targetTypeName}, ResourceID=targetID}}" .../>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`targetTypeName`|Der Name der öffentlichen [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] Typ, in der Resource-Assembly definiert ist.|  
|`targetID`|Der Schlüssel für die Ressource. Wenn Ressourcen gesucht werden `targetID` werden analog zu den [X: Key Directive](../../xaml-services/x-key-directive.md) der Ressource.|  
  
## <a name="remarks"></a>Hinweise  
 Wie in den oben genannten Verwendungen ein {`ComponentResourceKey`} Markuperweiterungsverwendung befindet sich an zwei Stellen:  
  
-   Die Definition eines Schlüssels in einem Ressourcenverzeichnis des Designs, wie vom Autor eines Steuerelements bereitgestellt.  
  
-   Zugriff auf eine Design-Ressource aus der Assembly, wenn Sie anpassungszenarios das Steuerelement aber Eigenschaftswerte verwenden, die von Ressourcen, die von den Designs des Steuerelements bereitgestellt werden soll.  
  
 Zum Verweisen auf Komponentenressourcen, die von Designs stammen, wird allgemein empfohlen, dass Sie verwenden `{DynamicResource}` statt `{StaticResource}`. Dies wird in den Verwendungen gezeigt. `{DynamicResource}` wird empfohlen, da des Designs, die vom Benutzer geändert werden kann. Wenn die Komponentenressource werden, die am ehesten der Autor des Steuerelements die Absicht sollen für die Unterstützung von Design entspricht, sollten Sie Ihre Komponentenressourcenverweis auch dynamisch sein aktivieren.  
  
 Die <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> identifiziert einen Typ, der in der Zielassembly vorhanden ist, in dem die Ressource ist definiert. Ein `ComponentResourceKey` definiert und unabhängig von genau zu wissen, verwendet werden können, in denen die <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> ist definiert, aber letztendlich muss den Typ von referenzierten Assemblys aufgelöst werden.  
  
 Eine häufige Verwendung für <xref:System.Windows.ComponentResourceKey> besteht darin, Schlüssel, die anschließend bereitgestellt werden als Member einer Klasse definieren. Für diese Verwendung ist, verwenden Sie die <xref:System.Windows.ComponentResourceKey> Klassenkonstruktor, nicht die Markuperweiterung. Weitere Informationen finden Sie unter <xref:System.Windows.ComponentResourceKey>, oder im Abschnitt "Definieren und Angeben von Schlüsseln für Designressourcen" des Themas [Übersicht über das Erstellen](../controls/control-authoring-overview.md).  
  
 Für sowohl beim Einrichten von Schlüsseln und verweisen auf Ressourcen mit Schlüsseln Attributsyntax häufig wird für die `ComponentResourceKey` Markuperweiterung.  
  
 Die kompakte Syntax basiert auf der <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> Konstruktorsignatur und Nutzung der Positionsparameter einer Markuperweiterung. Die Reihenfolge, in der `targetTypeName` und `targetID` erhalten ist wichtig. Die ausführliche Syntax basiert auf der <xref:System.Windows.ComponentResourceKey.%23ctor%2A?displayProperty=nameWithType> Standardkonstruktor und legt dann die <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> und <xref:System.Windows.ComponentResourceKey.ResourceId%2A> auf eine Weise, die analog zu einem "true" Attributsyntax für ein Objektelement ist. Ausführliche Syntax ist die Reihenfolge, in der die Eigenschaften festgelegt sind, nicht wichtig. Die Beziehung und die Mechanismen dieser Alternativen ("kompakt" und "ausführlich") wird ausführlich im Thema [Markuperweiterungen und WPF XAML](markup-extensions-and-wpf-xaml.md).  
  
 Technisch gesehen ist der Wert für `targetID` kann jedes Objekt sein, es muss nicht auf eine Zeichenfolge sein. Die häufigste Verwendung in WPF ist jedoch der Anpassung an die `targetID` Wert mit Formularen, die Zeichenfolgen sind, und, in denen diese Zeichenfolgen in gültig sind, die [XamlName-Grammatik](../../xaml-services/xamlname-grammar.md).  
  
 `ComponentResourceKey` kann in Objektelementsyntax verwendet werden. In diesem Fall geben Sie den Wert sowohl die <xref:System.Windows.ComponentResourceKey.TypeInTargetAssembly%2A> und <xref:System.Windows.ComponentResourceKey.ResourceId%2A> Eigenschaften ist erforderlich, um die Erweiterung ordnungsgemäß initialisiert.  
  
 In der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] -readerimplementierung, wird die Handhabung dieser Markuperweiterung durch definiert die <xref:System.Windows.ComponentResourceKey> Klasse.  
  
 `ComponentResourceKey` ist eine Markuperweiterung. Markuperweiterungen werden in der Regel implementiert, wenn Attributwerte mit Escapezeichen versehen werden müssen, damit diese nicht als literale Werte oder als Handlernamen betrachtet werden, und diese Anforderung eher global und nicht nur durch den Einsatz von Typkonvertern für bestimmte Typen oder Eigenschaften erfüllt werden soll. Alle Markuperweiterungen in XAML verwenden die Zeichen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] und [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] in der Attributsyntax. Dies ist die Konvention, anhand der ein XAML-Prozessor erkennt, dass das Attribut von einer Markuperweiterung verarbeitet werden muss. Weitere Informationen finden Sie unter [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.ComponentResourceKey>
- <xref:System.Windows.Controls.ControlTemplate>
- [Übersicht über das Erstellen von Steuerelementen](../controls/control-authoring-overview.md)
- [Übersicht über XAML (WPF)](xaml-overview-wpf.md)
- [Markuperweiterungen und WPF-XAML](markup-extensions-and-wpf-xaml.md)
