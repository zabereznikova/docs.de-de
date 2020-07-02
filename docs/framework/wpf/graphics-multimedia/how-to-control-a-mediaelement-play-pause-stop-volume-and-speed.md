---
title: 'Gewusst wie: Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)'
description: Steuern der Wiedergabe von Medien in Windows Presentation Foundation (WPF). Starten, anhalten, anhalten, überspringen und Ändern von Volume und Geschwindigkeit.
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
ms.openlocfilehash: da846299eaa1e36b6e5caab08bc1f861e9f9c46d
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853603"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Gewusst wie: Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)
Im folgenden Beispiel wird gezeigt, wie die Wiedergabe von Medien mithilfe von gesteuert wird <xref:System.Windows.Controls.MediaElement> . Im Beispiel wird ein einfacher Media Player erstellt, der es Ihnen ermöglicht, die Medien zu spielen, anzuhalten, zu stoppen und zu überspringen sowie das Volume und das Geschwindigkeits Verhältnis anzupassen.  
  
## <a name="example"></a>Beispiel  
 Der folgende Code erstellt die Benutzeroberfläche.  
  
> [!NOTE]
> Die- <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Eigenschaft von <xref:System.Windows.Controls.MediaElement> muss auf festgelegt werden, `Manual` damit die Medien interaktiv angehalten, angehalten und wiedergegeben werden können.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Beispiel  
 Der folgende Code implementiert die Funktionalität der Beispiel-UI-Steuerelemente. Die <xref:System.Windows.Controls.MediaElement.Play%2A> <xref:System.Windows.Controls.MediaElement.Pause%2A> -,-und- <xref:System.Windows.Controls.MediaElement.Stop%2A> Methoden werden verwendet, um die Medien zu spielen, anzuhalten und zu stoppen. <xref:System.Windows.Controls.MediaElement.Position%2A>Wenn Sie die-Eigenschaft von ändern <xref:System.Windows.Controls.MediaElement> , können Sie in den Medien überspringen. Schließlich werden die <xref:System.Windows.Controls.MediaElement.Volume%2A> -Eigenschaft und die-Eigenschaft <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> verwendet, um das Volume und die Wiedergabegeschwindigkeit der Medien anzupassen.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- [Steuern eines MediaElement-Objekts mit einem Storyboard](how-to-control-a-mediaelement-by-using-a-storyboard.md)
