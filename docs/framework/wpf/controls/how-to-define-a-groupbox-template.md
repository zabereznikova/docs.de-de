---
title: 'Vorgehensweise: Definieren einer GroupBox-Vorlage'
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], GroupBox
- GroupBox control [WPF], creating templates
ms.assetid: 85a4d1a7-4753-4f4a-b26d-14fa10c1ddb5
ms.openlocfilehash: 0e1b0487629bba3550a8b6b4a31c163a7ade6a87
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54743721"
---
# <a name="how-to-define-a-groupbox-template"></a>Vorgehensweise: Definieren einer GroupBox-Vorlage
Dieses Beispiel zeigt, wie Sie eine Vorlage zum Erstellen einer <xref:System.Windows.Controls.GroupBox> Steuerelement.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel definiert eine <xref:System.Windows.Controls.GroupBox> Steuerelementvorlage mit einem <xref:System.Windows.Controls.Grid> Steuerelement für das Layout. Die Vorlage verwendet eine <xref:System.Windows.Controls.BorderGapMaskConverter> definieren den Rahmen der <xref:System.Windows.Controls.GroupBox> , damit die Rahmen nicht verdeckt die <xref:System.Windows.Controls.HeaderedContentControl.Header%2A> Inhalt.  
  
 [!code-xaml[GroupBoxSnippet#GroupBoxTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GroupBoxSnippet/CS/Window1.xaml#groupboxtemplate)]  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Controls.GroupBox>
- [GroupBox Gewusst-wie-Themen](https://msdn.microsoft.com/library/7692e155-a4c6-428c-b7e0-64b3740daca7)
