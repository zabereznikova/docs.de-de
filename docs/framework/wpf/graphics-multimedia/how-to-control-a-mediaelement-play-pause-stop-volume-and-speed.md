---
title: "Gewusst wie: Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7362c57afa3d5615ffaa0616823a954a2d577cfe
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Gewusst wie: Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)
Im folgende Beispiel wird gezeigt, wie zum Steuern der Wiedergabe von Medien mit einem <xref:System.Windows.Controls.MediaElement>. Im Beispiel wird einen einfacher Media-Player, mit dem Sie wiedergeben, anhalten, beenden, und überspringen hin-und in den Medien sowie passen Sie das Volume und Geschwindigkeit Verhältnis erstellt.  
  
## <a name="example"></a>Beispiel  
 Im nachstehenden Code wird die Benutzeroberfläche.  
  
> [!NOTE]
>  Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Eigenschaft <xref:System.Windows.Controls.MediaElement> muss festgelegt werden, um `Manual` damit interaktiv zu beenden, Anhalten und Wiedergeben der Medien.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code implementiert die Funktionalität der Beispiel-UI-Steuerelemente. Die <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, und <xref:System.Windows.Controls.MediaElement.Stop%2A> Methoden bzw. wiedergeben, Anhalten und beenden die Medien verwendet werden. Ändern der <xref:System.Windows.Controls.MediaElement.Position%2A> Eigenschaft von der <xref:System.Windows.Controls.MediaElement> können Sie in den Medien zu überspringen, um. Schließlich die <xref:System.Windows.Controls.MediaElement.Volume%2A> und <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> Eigenschaften werden verwendet, um die Geschwindigkeit Volume und die Wiedergabe des Mediums anpassen.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch  
 [Steuern eines MediaElement mit einem Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)
