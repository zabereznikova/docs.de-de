---
title: PresentationOptions:Freeze-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: d3e0cee293a9585b972b0145da953976ed94b74c
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991429"
---
# <a name="presentationoptionsfreeze-attribute"></a>PresentationOptions:Freeze-Attribut
Legt den <xref:System.Windows.Freezable.IsFrozen%2A> Zustand für `true` das enthaltende <xref:System.Windows.Freezable> Element auf fest. Das Standardverhalten für <xref:System.Windows.Freezable> eine ohne `PresentationOptions:Freeze` das angegebene- `false` Attribut <xref:System.Windows.Freezable.IsFrozen%2A> ist zur Ladezeit und abhängig vom allgemeinen <xref:System.Windows.Freezable> Verhalten zur Laufzeit.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```xaml  
<object  
  xmlns:PresentationOptions="http://schemas.microsoft.com/winfx/2006/xaml/presentation/options"  
  xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"  
  mc:Ignorable="PresentationOptions">  
    <freezableElement PresentationOptions:Freeze="true"/>  
</object>  
```  
  
## <a name="xaml-values"></a>XAML-Werte  
  
|||  
|-|-|  
|`PresentationOptions`|Ein XML-Namespace Präfix, bei dem es sich um eine beliebige gültige Präfix Zeichenfolge handeln kann, gemäß XML 1,0 Dieses Präfix `PresentationOptions` wird zu Identifikationszwecken in dieser Dokumentation verwendet.|  
|`freezableElement`|Ein Element, das jede abgeleitete Klasse von <xref:System.Windows.Freezable>instanziiert.|  
  
## <a name="remarks"></a>Hinweise  
 Das `Freeze` -Attribut ist das einzige Attribut oder ein anderes Programmier Element, `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` das im XML-Namespace definiert ist. Das `Freeze` -Attribut ist in diesem speziellen Namespace speziell vorhanden, sodass es als Ignorable festgelegt werden kann, wobei das [MC: Ignorable-Attribut](mc-ignorable-attribute.md) als Teil der Stamm Element Deklarationen verwendet wird. Der Grund, `Freeze` Warum ignoriert werden muss, besteht darin, dass nicht alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor Implementierungen zur Ladezeit ein <xref:System.Windows.Freezable> Einfrieren können. diese Funktion ist nicht Teil [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] der Spezifikation.  
  
 Die Möglichkeit, das `Freeze` -Attribut zu verarbeiten, ist speziell in den [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor integriert [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] , der für kompilierte Anwendungen verarbeitet. Das Attribut wird von keiner Klasse unterstützt, und die Attribut Syntax ist nicht erweiterbar oder änderbar. Wenn Sie einen eigenen [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor implementieren, können Sie auswählen, ob das Einfrieren [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] des Prozessors beim Verarbeiten des `Freeze` Attributs für <xref:System.Windows.Freezable> Elemente zur Ladezeit parallel durchlaufen werden soll.  
  
 Jeder Wert für das `Freeze` -Attribut `true` , der keine Groß-/Kleinschreibung beachtet, generiert einen Lade Zeitfehler. (Die Angabe `Freeze` des- `false` Attributs als ist kein Fehler, aber dies ist bereits der Standardwert, `false` sodass das Festlegen von auf nichts bewirkt.)  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Freezable>
- [Übersicht über Freezable-Objekte](freezable-objects-overview.md)
- [mc:Ignorable-Attribut](mc-ignorable-attribute.md)
