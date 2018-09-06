---
title: 'Gewusst wie: Verwenden eines ThicknessConverter-Objekts'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- border thickness [WPF]
- ThicknessConverter objects [WPF]
ms.assetid: 52682194-d7fd-499c-8005-73fcc84e7b2c
ms.openlocfilehash: 6c8f9e83468a7b189b96efca2e175c0f3fe0dfff
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43856663"
---
# <a name="how-to-use-a-thicknessconverter-object"></a>Gewusst wie: Verwenden eines ThicknessConverter-Objekts
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird gezeigt, wie zum Erstellen einer Instanz von <xref:System.Windows.ThicknessConverter> und um die Breite eines Rahmens zu ändern.  
  
 Das Beispiel definiert eine benutzerdefinierte Methode namens `changeThickness`; diese Methode zuerst konvertiert den Inhalt der ein <xref:System.Windows.Controls.ListBoxItem>, wie definiert in einer separaten [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] -Datei, um eine Instanz von <xref:System.Windows.Thickness>, und konvertiert Sie den Inhalt in einem späteren Zeitpunkt eine <xref:System.String>. Diese Methode übergibt der <xref:System.Windows.Controls.ListBoxItem> auf eine <xref:System.Windows.ThicknessConverter> -Objekt, das konvertiert die <xref:System.Windows.Controls.ContentControl.Content%2A> von einer <xref:System.Windows.Controls.ListBoxItem> mit einer Instanz von <xref:System.Windows.Thickness>. Dieser Wert übergeben wird dann wieder als Wert für die <xref:System.Windows.Controls.Border.BorderThickness%2A> Eigenschaft der <xref:System.Windows.Controls.Border>.  
  
 Dieses Beispiel wird nicht ausgeführt.  
  
 [!code-csharp[ThicknessConverter#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ThicknessConverter/CSharp/Window1.xaml.cs#1)]
 [!code-vb[ThicknessConverter#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ThicknessConverter/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Thickness>  
 <xref:System.Windows.ThicknessConverter>  
 <xref:System.Windows.Controls.Border>  
 [Vorgehensweise: Ändern Sie die Margin-Eigenschaft](https://msdn.microsoft.com/library/8a313efd-5f99-4097-b4c1-8fa49d8379a2)  
 [Gewusst wie: Konvertieren ein ListBoxItem in einen neuen Typ von Daten](https://msdn.microsoft.com/library/7a080b88-184e-4b27-bb61-d42bafba9727)  
 [Übersicht über Panel-Elemente](../../../../docs/framework/wpf/controls/panels-overview.md)
