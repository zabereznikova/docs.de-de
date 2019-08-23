---
title: 'Vorgehensweise: Steuern eines MediaElement-Objekts (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)'
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
ms.openlocfilehash: cde7c32b48dff3d6d054e700b2f95771ba3b3773
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930162"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Vorgehensweise: Steuern eines MediaElement-Objekts (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)
Im folgenden Beispiel wird gezeigt, wie die Wiedergabe von Medien <xref:System.Windows.Controls.MediaElement>mithilfe von gesteuert wird. Im Beispiel wird ein einfacher Media Player erstellt, der es Ihnen ermöglicht, die Medien zu spielen, anzuhalten, zu stoppen und zu überspringen sowie das Volume und das Geschwindigkeits Verhältnis anzupassen.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code erstellt die Benutzeroberfläche.  
  
> [!NOTE]
> Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> -Eigenschaft <xref:System.Windows.Controls.MediaElement> von muss auf `Manual` festgelegt werden, damit die Medien interaktiv angehalten, angehalten und wiedergegeben werden können.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code implementiert die Funktionalität der Beispiel-UI-Steuerelemente. Die <xref:System.Windows.Controls.MediaElement.Play%2A>- <xref:System.Windows.Controls.MediaElement.Pause%2A>,- <xref:System.Windows.Controls.MediaElement.Stop%2A> und-Methoden werden verwendet, um die Medien zu spielen, anzuhalten und zu stoppen. Wenn Sie <xref:System.Windows.Controls.MediaElement.Position%2A> die-Eigenschaft <xref:System.Windows.Controls.MediaElement> von ändern, können Sie in den Medien überspringen. Schließlich werden <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> die -Eigenschaftunddie-Eigenschaftverwendet,umdasVolumeunddieWiedergabegeschwindigkeit<xref:System.Windows.Controls.MediaElement.Volume%2A> der Medien anzupassen.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Steuern eines MediaElement mit einem Storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md)
