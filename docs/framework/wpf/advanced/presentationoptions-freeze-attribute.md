---
title: PresentationOptions:Freeze-Attribut
ms.date: 03/30/2017
helpviewer_keywords:
- Freeze attribute [WPF]
- Freezable elements [WPF]
- PresentationOptions prefix [WPF]
ms.assetid: 391032dd-2fba-4804-bb8a-3b071797a9f4
ms.openlocfilehash: e60c4a505db42936f188354f52edd7832fb9632b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59074656"
---
# <a name="presentationoptionsfreeze-attribute"></a>PresentationOptions:Freeze-Attribut
Legt die <xref:System.Windows.Freezable.IsFrozen%2A> Zustand `true` auf dem mit <xref:System.Windows.Freezable> Element. Standardverhalten für eine <xref:System.Windows.Freezable> ohne die `PresentationOptions:Freeze` Attribut angegeben ist, das <xref:System.Windows.Freezable.IsFrozen%2A> ist `false` am Serverantwortzeiten, Seitenladezeiten und abhängig davon, allgemeine <xref:System.Windows.Freezable> Verhalten zur Laufzeit.  
  
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
|`PresentationOptions`|Ein XML-Namespace-Präfix, das eine beliebige Zeichenfolge gültiges Präfix gemäß der XML 1.0-Spezifikation werden kann. Das Präfix `PresentationOptions` zu Identifikationszwecken in dieser Dokumentation verwendet wird.|  
|`freezableElement`|Ein Element aus, die instanziiert wird, eine abgeleitete Klasse von <xref:System.Windows.Freezable>.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Freeze` Attribut das einzige Attribut ist oder anderen Programmierelements definiert, der `http://schemas.microsoft.com/winfx/2006/xaml/presentation/options` XML-Namespace. Die `Freeze` Attribut in diesem speziellen Namespace vorhanden ist, insbesondere, damit es als ignorierbar bezeichnet werden kann [Mc: Ignorable-Attribut](mc-ignorable-attribute.md) als Teil der Stamm-Elementdeklarationen. Der Grund, `Freeze` muss in der Lage, ignoriert werden ist da nicht alle [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Implementierungen von ereignissprozessoren können so fixieren Sie einen <xref:System.Windows.Freezable> zur Ladezeit; diese Funktion ist nicht Teil der [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Spezifikation.  
  
 Die Möglichkeit zum Verarbeiten der `Freeze` Attribut ist insbesondere in integriert die [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor, der verarbeitet [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] für kompilierten Anwendungen. Das Attribut wird nicht unterstützt, von jeder Klasse, und die Attributsyntax ist nicht erweiterbar und können geändert werden kann. Wenn Sie Ihre eigenen implementieren [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor, Sie können auch das Einfrieren Verhalten der parallele, der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] Prozessor bei der Verarbeitung der `Freeze` -Attribut <xref:System.Windows.Freezable> Elemente zur Ladezeit.  
  
 Jeder Wert für die `Freeze` -Attribut ausschließlich `true` (ohne Beachtung von Groß-/Kleinschreibung), wird eine Ladezeitfehler generiert. (Angeben der `Freeze` als Attribut `false` ist kein Fehler, aber, der sich bereits die Standardeinstellung, also zum `false` führt keine Aktion).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Freezable>
- [Übersicht über Freezable-Objekte](freezable-objects-overview.md)
- [mc:Ignorable-Attribut](mc-ignorable-attribute.md)
