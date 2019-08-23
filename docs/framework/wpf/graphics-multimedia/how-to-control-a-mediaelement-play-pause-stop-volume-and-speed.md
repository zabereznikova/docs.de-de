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
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="f8d4f-102">Vorgehensweise: Steuern eines MediaElement-Objekts (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)</span><span class="sxs-lookup"><span data-stu-id="f8d4f-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="f8d4f-103">Im folgenden Beispiel wird gezeigt, wie die Wiedergabe von Medien <xref:System.Windows.Controls.MediaElement>mithilfe von gesteuert wird.</span><span class="sxs-lookup"><span data-stu-id="f8d4f-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="f8d4f-104">Im Beispiel wird ein einfacher Media Player erstellt, der es Ihnen ermöglicht, die Medien zu spielen, anzuhalten, zu stoppen und zu überspringen sowie das Volume und das Geschwindigkeits Verhältnis anzupassen.</span><span class="sxs-lookup"><span data-stu-id="f8d4f-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8d4f-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8d4f-105">Example</span></span>  
 <span data-ttu-id="f8d4f-106">Der folgende Code erstellt die Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="f8d4f-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8d4f-107">Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> -Eigenschaft <xref:System.Windows.Controls.MediaElement> von muss auf `Manual` festgelegt werden, damit die Medien interaktiv angehalten, angehalten und wiedergegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="f8d4f-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="f8d4f-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f8d4f-108">Example</span></span>  
 <span data-ttu-id="f8d4f-109">Der folgende Code implementiert die Funktionalität der Beispiel-UI-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="f8d4f-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="f8d4f-110">Die <xref:System.Windows.Controls.MediaElement.Play%2A>- <xref:System.Windows.Controls.MediaElement.Pause%2A>,- <xref:System.Windows.Controls.MediaElement.Stop%2A> und-Methoden werden verwendet, um die Medien zu spielen, anzuhalten und zu stoppen.</span><span class="sxs-lookup"><span data-stu-id="f8d4f-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="f8d4f-111">Wenn Sie <xref:System.Windows.Controls.MediaElement.Position%2A> die-Eigenschaft <xref:System.Windows.Controls.MediaElement> von ändern, können Sie in den Medien überspringen.</span><span class="sxs-lookup"><span data-stu-id="f8d4f-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="f8d4f-112">Schließlich werden <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> die -Eigenschaftunddie-Eigenschaftverwendet,umdasVolumeunddieWiedergabegeschwindigkeit<xref:System.Windows.Controls.MediaElement.Volume%2A> der Medien anzupassen.</span><span class="sxs-lookup"><span data-stu-id="f8d4f-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="f8d4f-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8d4f-113">See also</span></span>

- [<span data-ttu-id="f8d4f-114">Steuern eines MediaElement mit einem Storyboard</span><span class="sxs-lookup"><span data-stu-id="f8d4f-114">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
