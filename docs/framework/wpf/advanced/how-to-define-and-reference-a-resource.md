---
title: 'Vorgehensweise: Definieren einer Ressource und Verweisen auf eine Ressource'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: 80be1460906100072e6263c967c213df7968c705
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776505"
---
# <a name="how-to-define-and-reference-a-resource"></a>Vorgehensweise: Definieren einer Ressource und Verweisen auf eine Ressource

Dieses Beispiel zeigt, wie Sie eine Ressource definieren und darauf verweisen, indem Sie mithilfe eines Attributs in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].

## <a name="example"></a>Beispiel

Das folgende Beispiel definiert zwei Typen von Ressourcen: ein <xref:System.Windows.Media.SolidColorBrush> Ressource und mehrere <xref:System.Windows.Style> Ressourcen. Die <xref:System.Windows.Media.SolidColorBrush> Ressource `MyBrush` wird verwendet, um dem Wert verschiedener Eigenschaften angeben, dass jeweils ein <xref:System.Windows.Media.Brush> Typwert. Die <xref:System.Windows.Style> Ressourcen `PageBackground`, `TitleText` und `Label` jeweils einen bestimmten Steuerelementtyp abzielen. Die Stile auf die entsprechenden Steuerelemente, eine Vielzahl von unterschiedliche Eigenschaften festlegen, wenn diese Ressource "Style" verweist auf Ressourcenschlüssel (ResourceKey) und zum Festlegen dient der <xref:System.Windows.FrameworkElement.Style%2A> Eigenschaft für mehrere bestimmte Steuerelemente in definierten [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].

Beachten Sie, dass eine der Eigenschaften in die Setter der `Label` Stil verweist, auch die `MyBrush` Ressource, die zuvor definiert haben. Dies ist eine gängige Methode, aber es ist wichtig zu beachten, dass Ressourcen analysiert und in einem Ressourcenverzeichnis in der Reihenfolge, die ihnen zugewiesen sind eingegeben werden. Ressourcen werden auch angefordert, durch die Reihenfolge, die im Wörterbuch gefunden wird, wenn Sie verwenden die [StaticResource-Markuperweiterung](staticresource-markup-extension.md) aus einer anderen Ressource verweisen. Stellen Sie sicher, dass alle Ressourcen, die Sie verweisen, bereits definiert ist, in der ressourcenauflistung als die, in dem die Ressource dann angefordert wird. Wenn erforderlich, die strengen Erstellung-Reihenfolge der Ressourcenverweise mithilfe von Sie umgehen Problem können einer [DynamicResource-Markuperweiterung](dynamicresource-markup-extension.md) stattdessen auf die Ressource zur Laufzeit, aber Sie sollten sich bewusst sein, die diese DynamicResource Technik wurde die Leistung beeinträchtigen. Weitere Informationen finden Sie unter [XAML-Ressourcen](xaml-resources.md).

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](xaml-resources.md)
- [Erstellen von Formaten und Vorlagen](../controls/styling-and-templating.md)
