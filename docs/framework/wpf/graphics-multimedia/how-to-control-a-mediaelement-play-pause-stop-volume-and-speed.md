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
ms.openlocfilehash: bb7319fc7ccec0220cbd79a32d5d015f9f2422d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182857"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="56fb7-102">Vorgehensweise: Steuern eines MediaElement-Objekts (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)</span><span class="sxs-lookup"><span data-stu-id="56fb7-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="56fb7-103">Das folgende Beispiel zeigt, wie Sie steuern die Wiedergabe von Medien mit einer <xref:System.Windows.Controls.MediaElement>.</span><span class="sxs-lookup"><span data-stu-id="56fb7-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="56fb7-104">Das Beispiel erstellt einen einfachen MediaPlayer, mit dem Sie wiedergeben, anhalten, beenden, und überspringen hin und her, auf dem Medium als auch das Verhältnis Lautstärke und Geschwindigkeit anpassen.</span><span class="sxs-lookup"><span data-stu-id="56fb7-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56fb7-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56fb7-105">Example</span></span>  
 <span data-ttu-id="56fb7-106">Der folgende Code erstellt die Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="56fb7-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56fb7-107">Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Eigenschaft <xref:System.Windows.Controls.MediaElement> muss festgelegt werden, um `Manual` um interaktiv zu beenden, Anhalten und Wiedergeben der Medien.</span><span class="sxs-lookup"><span data-stu-id="56fb7-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="56fb7-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56fb7-108">Example</span></span>  
 <span data-ttu-id="56fb7-109">Der folgende Code implementiert die Funktionalität von der Beispiel-UI-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="56fb7-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="56fb7-110">Die <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, und <xref:System.Windows.Controls.MediaElement.Stop%2A> Methoden zum jeweils wiedergeben, Anhalten und beenden die Medien.</span><span class="sxs-lookup"><span data-stu-id="56fb7-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="56fb7-111">Ändern der <xref:System.Windows.Controls.MediaElement.Position%2A> Eigenschaft der <xref:System.Windows.Controls.MediaElement> können Sie in den Medien zu überspringen, um.</span><span class="sxs-lookup"><span data-stu-id="56fb7-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="56fb7-112">Zum Schluss die <xref:System.Windows.Controls.MediaElement.Volume%2A> und <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> Eigenschaften verwendet, um die Geschwindigkeit Volume und Wiedergabe des Mediums anzupassen.</span><span class="sxs-lookup"><span data-stu-id="56fb7-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="56fb7-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56fb7-113">See also</span></span>

- [<span data-ttu-id="56fb7-114">Steuern eines MediaElement-Objekts mit einem Storyboard</span><span class="sxs-lookup"><span data-stu-id="56fb7-114">Control a MediaElement by Using a Storyboard</span></span>](how-to-control-a-mediaelement-by-using-a-storyboard.md)
