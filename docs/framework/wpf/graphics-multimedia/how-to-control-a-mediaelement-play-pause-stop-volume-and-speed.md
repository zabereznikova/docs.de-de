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
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="919d4-104">Gewusst wie: Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)</span><span class="sxs-lookup"><span data-stu-id="919d4-104">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="919d4-105">Im folgenden Beispiel wird gezeigt, wie die Wiedergabe von Medien mithilfe von gesteuert wird <xref:System.Windows.Controls.MediaElement> .</span><span class="sxs-lookup"><span data-stu-id="919d4-105">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="919d4-106">Im Beispiel wird ein einfacher Media Player erstellt, der es Ihnen ermöglicht, die Medien zu spielen, anzuhalten, zu stoppen und zu überspringen sowie das Volume und das Geschwindigkeits Verhältnis anzupassen.</span><span class="sxs-lookup"><span data-stu-id="919d4-106">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="919d4-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="919d4-107">Example</span></span>  
 <span data-ttu-id="919d4-108">Der folgende Code erstellt die Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="919d4-108">The code below creates the UI.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="919d4-109">Die- <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Eigenschaft von <xref:System.Windows.Controls.MediaElement> muss auf festgelegt werden, `Manual` damit die Medien interaktiv angehalten, angehalten und wiedergegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="919d4-109">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="919d4-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="919d4-110">Example</span></span>  
 <span data-ttu-id="919d4-111">Der folgende Code implementiert die Funktionalität der Beispiel-UI-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="919d4-111">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="919d4-112">Die <xref:System.Windows.Controls.MediaElement.Play%2A> <xref:System.Windows.Controls.MediaElement.Pause%2A> -,-und- <xref:System.Windows.Controls.MediaElement.Stop%2A> Methoden werden verwendet, um die Medien zu spielen, anzuhalten und zu stoppen.</span><span class="sxs-lookup"><span data-stu-id="919d4-112">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="919d4-113"><xref:System.Windows.Controls.MediaElement.Position%2A>Wenn Sie die-Eigenschaft von ändern <xref:System.Windows.Controls.MediaElement> , können Sie in den Medien überspringen.</span><span class="sxs-lookup"><span data-stu-id="919d4-113">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="919d4-114">Schließlich werden die <xref:System.Windows.Controls.MediaElement.Volume%2A> -Eigenschaft und die-Eigenschaft <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> verwendet, um das Volume und die Wiedergabegeschwindigkeit der Medien anzupassen.</span><span class="sxs-lookup"><span data-stu-id="919d4-114">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="919d4-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="919d4-115">See also</span></span>

- [<span data-ttu-id="919d4-116">Steuern eines MediaElement-Objekts mit einem Storyboard</span><span class="sxs-lookup"><span data-stu-id="919d4-116">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
