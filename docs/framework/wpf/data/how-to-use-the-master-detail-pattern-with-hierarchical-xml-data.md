---
title: 'Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: eb8dbdd8-5871-42bb-a16b-04e655fea677
ms.openlocfilehash: 0fe42d57fcaf4acee09340fdb3f5df73d7291566
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733415"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-xml-data"></a>Gewusst wie: Verwenden des Master/Detail-Musters mit hierarchischen XML-Daten
Dieses Beispiel zeigt, wie das Master/Detail-Szenario mit XML-Daten implementiert wird.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel ist die XML-Daten Version des Beispiels, das unter [Verwenden des Master/Detail-Musters mit hierarchischen Daten](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)erläutert wird. In diesem Beispiel werden die Daten aus der Datei `League.xml`. Beachten Sie, wie das dritte <xref:System.Windows.Controls.ListBox> Steuerelement die Auswahl Änderungen im zweiten <xref:System.Windows.Controls.ListBox> nachverfolgt, indem es an seine <xref:System.Windows.Controls.Primitives.Selector.SelectedValue%2A>-Eigenschaft gebunden wird.  
  
 [!code-xaml[MasterDetailXml#HowTo1](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto1)]  
[!code-xaml[MasterDetailXml#HowTo2](~/samples/snippets/csharp/VS_Snippets_Wpf/MasterDetailXml/CS/Window1.xaml#howto2)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.HierarchicalDataTemplate>
- [Themen zu Vorgehensweisen](data-binding-how-to-topics.md)
