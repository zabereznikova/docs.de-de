---
title: PresentationOptions:Freeze-Attribut
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cb305c69cec7c4e4766153ae64d37b19ab0bccea
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
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
