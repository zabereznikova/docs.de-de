---
title: 'Gewusst wie: Definieren einer Ressource und Verweisen auf eine Ressource'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: e33c86b03d8b18113f3a15b3ab251753958ff5b2
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646511"
---
# <a name="how-to-define-and-reference-a-resource"></a>Gewusst wie: Definieren einer Ressource und Verweisen auf eine Ressource

In diesem Beispiel wird gezeigt, wie Sie eine [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]Ressource definieren und mithilfe eines Attributs in darauf verweisen.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Arten <xref:System.Windows.Media.SolidColorBrush> von Ressourcen <xref:System.Windows.Style> definiert: eine Ressource und mehrere Ressourcen. Die <xref:System.Windows.Media.SolidColorBrush> `MyBrush` Ressource wird verwendet, um den Wert <xref:System.Windows.Media.Brush> mehrerer Eigenschaften bereitzustellen, die jeweils einen Typwert annehmen. Die <xref:System.Windows.Style> `PageBackground`Ressourcen `TitleText` `Label` und jedes Ziel für einen bestimmten Steuerelementtyp. Die Stile legen eine Vielzahl unterschiedlicher Eigenschaften für die Zielsteuerelemente fest, wenn auf <xref:System.Windows.FrameworkElement.Style%2A> diese Stilressource durch [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]den Ressourcenschlüssel verwiesen wird und zum Festlegen der Eigenschaft mehrerer spezifischer Steuerelementelemente, die in definiert sind.

Beachten Sie, dass eine der Eigenschaften `Label` innerhalb der `MyBrush` Setter des Stils auch auf die zuvor definierte Ressource verweist. Dies ist eine gängige Technik, aber es ist wichtig, sich daran zu erinnern, dass Ressourcen analysiert und in ein Ressourcenwörterbuch in der Reihenfolge eingegeben werden, in der sie angegeben werden. Ressourcen werden auch von der Reihenfolge im Wörterbuch angefordert, wenn Sie die [StaticResource Markup-Erweiterung](staticresource-markup-extension.md) verwenden, um sie aus einer anderen Ressource zu referenzieren. Stellen Sie sicher, dass jede Ressource, auf die Sie verweisen, früher in der Ressourcenauflistung definiert ist, als dort, wo diese Ressource dann angefordert wird. Bei Bedarf können Sie die strikte Erstellungsreihenfolge von Ressourcenverweisen umgehen, indem Sie stattdessen eine [DynamicResource Markup Extension](dynamicresource-markup-extension.md) verwenden, um auf die Ressource zur Laufzeit zu verweisen. Weitere Informationen finden Sie unter [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md).

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](../../../desktop-wpf/fundamentals/xaml-resources-define.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
