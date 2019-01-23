---
title: 'Vorgehensweise: Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
ms.openlocfilehash: e9939c2d3d740bfe9296c23e47ef8ea09d837e01
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54498920"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Vorgehensweise: Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)
Das folgende Beispiel zeigt, wie Sie steuern die Wiedergabe von Medien mit einer <xref:System.Windows.Controls.MediaElement>. Das Beispiel erstellt einen einfachen MediaPlayer, mit dem Sie wiedergeben, anhalten, beenden, und überspringen hin und her, auf dem Medium als auch das Verhältnis Lautstärke und Geschwindigkeit anpassen.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code erstellt die Benutzeroberfläche.  
  
> [!NOTE]
>  Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Eigenschaft <xref:System.Windows.Controls.MediaElement> muss festgelegt werden, um `Manual` um interaktiv zu beenden, Anhalten und Wiedergeben der Medien.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code implementiert die Funktionalität von der Beispiel-UI-Steuerelemente. Die <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, und <xref:System.Windows.Controls.MediaElement.Stop%2A> Methoden zum jeweils wiedergeben, Anhalten und beenden die Medien. Ändern der <xref:System.Windows.Controls.MediaElement.Position%2A> Eigenschaft der <xref:System.Windows.Controls.MediaElement> können Sie in den Medien zu überspringen, um. Zum Schluss die <xref:System.Windows.Controls.MediaElement.Volume%2A> und <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> Eigenschaften verwendet, um die Geschwindigkeit Volume und Wiedergabe des Mediums anzupassen.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch
- [Steuern eines MediaElement mit einem Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)
