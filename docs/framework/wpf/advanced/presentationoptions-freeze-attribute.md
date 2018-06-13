---
title: PresentationOptions:Freeze-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: 896f7b24599b68f178d2a006e5ddc07278564bde
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33546070"
---
# <a name="presentationoptionsfreeze-attribute"></a>PresentationOptions:Freeze-Attribut
Legt die <xref:System.Windows.Freezable.IsFrozen%2A> Zustand `true` für das enthaltende <xref:System.Windows.Freezable> Element. Standardverhalten für eine <xref:System.Windows.Freezable> ohne die `PresentationOptions:Freeze` Attribut angegeben ist, <xref:System.Windows.Freezable.IsFrozen%2A> ist `false` zur Ladezeit und in Abhängigkeit davon Allgemein <xref:System.Windows.Freezable> Verhalten zur Laufzeit.  
  
## <a name="xaml-attribute-usage"></a>Verwendung von XAML-Attributen  
  
```  
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
|`PresentationOptions`|Ein XML-Namespace-Präfix, der eine beliebige gültige Präfixzeichenfolge gemäß der XML 1.0-Spezifikation sein kann. Das Präfix `PresentationOptions` für Identifikationszwecke in dieser Dokumentation verwendet wird.|  
|`freezableElement`|Ein Element, das alle instanziiert abgeleitete Klasse der <xref:System.Windows.Freezable>.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Freeze` Attribut das einzige Attribut ist oder in anderen Programmierelements definiert die `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML-Namespace. Die `Freeze` Attribut in diesem speziellen Namespace vorhanden ist, insbesondere, damit es als ignorierbares mit festgelegt werden kann [Mc: Ignorierbares Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md) als Teil der Stamm-Elementdeklarationen. Der Grund, `Freeze` muss in der Lage, ignorierbares werden ist da nicht alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Implementierungen von ereignissprozessoren können so fixieren Sie eine <xref:System.Windows.Freezable> zur Ladezeit; diese Funktion ist nicht Teil der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Spezifikation.  
  
 Die Möglichkeit zum Verarbeiten der `Freeze` Attribut ist insbesondere in integriert die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor, der verarbeitet [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für kompilierte Anwendungen. Das Attribut wird nicht durch alle Klassen unterstützt, und die Attributsyntax ist nicht erweiterbar oder geändert werden kann. Wenn Sie eine eigene Implementierung von [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor, Sie können das Fixieren Verhalten des parallel auf, der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor bei der Verarbeitung der `Freeze` -Attribut <xref:System.Windows.Freezable> Elemente zur Ladezeit des.  
  
 Jeder Wert für die `Freeze` außer-Attribut `true` (ohne Beachtung von Groß-/Kleinschreibung), wird ein Ladezeitfehler generiert. (Angeben der `Freeze` Attribut `false` ist kein Fehler, aber, der sich bereits die Standardeinstellung, also zu `false` wird keine Aktion ausgeführt).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Freezable>  
 [Übersicht über Freezable-Objekte](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)  
 [mc:Ignorable-Attribut](../../../../docs/framework/wpf/advanced/mc-ignorable-attribute.md)
