---
title: 'Gewusst wie: Definieren einer Ressource und Verweisen auf eine Ressource'
ms.date: 03/30/2017
helpviewer_keywords:
- resources [WPF], defining
- defining resources [WPF]
- resources [WPF], referencing
- referencing resources [WPF]
ms.assetid: b86b876b-0a10-489b-9a5d-581ea9b32406
ms.openlocfilehash: 89471c45aabd9f3415c45a2e8af41d1a52900324
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460175"
---
# <a name="how-to-define-and-reference-a-resource"></a>Gewusst wie: Definieren einer Ressource und Verweisen auf eine Ressource

In diesem Beispiel wird gezeigt, wie Sie eine Ressource definieren und mithilfe eines Attributs in [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]referenzieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei Arten von Ressourcen definiert: eine <xref:System.Windows.Media.SolidColorBrush> Ressource und mehrere <xref:System.Windows.Style> Ressourcen. Der <xref:System.Windows.Media.SolidColorBrush>-Ressourcen `MyBrush` wird verwendet, um den Wert mehrerer Eigenschaften bereitzustellen, die jeweils einen <xref:System.Windows.Media.Brush> Type-Wert annehmen. Die <xref:System.Windows.Style> Ressourcen `PageBackground`, `TitleText` und `Label` jeweils einen bestimmten Steuerelement Typen als Ziel haben. Die Stile legen eine Vielzahl von unterschiedlichen Eigenschaften für die Ziel Steuerelemente fest, wenn auf diese Stil Ressource durch den Ressourcen Schlüssel verwiesen wird. Sie wird verwendet, um die <xref:System.Windows.FrameworkElement.Style%2A>-Eigenschaft mehrerer spezifischer Steuerelemente festzulegen, die in [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]definiert sind.

Beachten Sie, dass eine der Eigenschaften innerhalb der Setter des `Label` Stils auch auf die zuvor definierte `MyBrush` Ressource verweist. Dies ist ein gängiges Verfahren, aber es ist wichtig zu beachten, dass Ressourcen analysiert und in ein Ressourcen Wörterbuch eingegeben werden, in der Sie angegeben sind. Ressourcen werden auch von der im Wörterbuch gefundenen Reihenfolge angefordert, wenn Sie die [StaticResource-Markup Erweiterung](staticresource-markup-extension.md) verwenden, um auf diese innerhalb einer anderen Ressource zu verweisen. Stellen Sie sicher, dass alle Ressourcen, auf die Sie verweisen, zuvor in der Ressourcensammlung definiert sind, als wenn diese Ressource dann angefordert wird. Wenn erforderlich, können Sie die strikte Erstellungs Reihenfolge von Ressourcen verweisen umgehen, indem Sie stattdessen eine [dynamikresource-Markup Erweiterung](dynamicresource-markup-extension.md) verwenden, um zur Laufzeit auf die Ressource zu verweisen. Sie sollten jedoch beachten, dass diese dynamikresource-Technik Leistung aufweist. Konsequenzen. Weitere Informationen finden Sie unter [XAML-Ressourcen](xaml-resources.md).

[!code-xaml[FEResource#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEResource/CS/default.xaml#xaml)]

## <a name="see-also"></a>Siehe auch

- [XAML-Ressourcen](xaml-resources.md)
- [Erstellen von Formaten und Vorlagen](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
