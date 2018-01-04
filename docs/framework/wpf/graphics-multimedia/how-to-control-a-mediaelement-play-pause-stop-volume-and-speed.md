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
ms.workload: dotnet
ms.openlocfilehash: 57b140391526c5b2a0e73a8bab2355ae445b395b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a><span data-ttu-id="4785a-102">Gewusst wie: Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautstärke und Geschwindigkeit)</span><span class="sxs-lookup"><span data-stu-id="4785a-102">How to: Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>
<span data-ttu-id="4785a-103">Im folgende Beispiel wird gezeigt, wie zum Steuern der Wiedergabe von Medien mit einem <xref:System.Windows.Controls.MediaElement>.</span><span class="sxs-lookup"><span data-stu-id="4785a-103">The following example shows how to control playback of media using a <xref:System.Windows.Controls.MediaElement>.</span></span> <span data-ttu-id="4785a-104">Im Beispiel wird einen einfacher Media-Player, mit dem Sie wiedergeben, anhalten, beenden, und überspringen hin-und in den Medien sowie passen Sie das Volume und Geschwindigkeit Verhältnis erstellt.</span><span class="sxs-lookup"><span data-stu-id="4785a-104">The example creates a simple media player that allows you to play, pause, stop, and skip back and forth in the media as well as adjust the volume and speed ratio.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4785a-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4785a-105">Example</span></span>  
 <span data-ttu-id="4785a-106">Im nachstehenden Code wird die Benutzeroberfläche.</span><span class="sxs-lookup"><span data-stu-id="4785a-106">The code below creates the UI.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4785a-107">Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> Eigenschaft <xref:System.Windows.Controls.MediaElement> muss festgelegt werden, um `Manual` damit interaktiv zu beenden, Anhalten und Wiedergeben der Medien.</span><span class="sxs-lookup"><span data-stu-id="4785a-107">The <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> property of <xref:System.Windows.Controls.MediaElement> must be set to `Manual` in order to be able to interactively stop, pause, and play the media.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="4785a-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4785a-108">Example</span></span>  
 <span data-ttu-id="4785a-109">Der folgende Code implementiert die Funktionalität der Beispiel-UI-Steuerelemente.</span><span class="sxs-lookup"><span data-stu-id="4785a-109">The code below implements the functionality of the sample UI controls.</span></span> <span data-ttu-id="4785a-110">Die <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, und <xref:System.Windows.Controls.MediaElement.Stop%2A> Methoden bzw. wiedergeben, Anhalten und beenden die Medien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4785a-110">The <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, and <xref:System.Windows.Controls.MediaElement.Stop%2A> methods are used to respectively play, pause and stop the media.</span></span> <span data-ttu-id="4785a-111">Ändern der <xref:System.Windows.Controls.MediaElement.Position%2A> Eigenschaft von der <xref:System.Windows.Controls.MediaElement> können Sie in den Medien zu überspringen, um.</span><span class="sxs-lookup"><span data-stu-id="4785a-111">Changing the <xref:System.Windows.Controls.MediaElement.Position%2A> property of the <xref:System.Windows.Controls.MediaElement> allows you to skip around in the media.</span></span> <span data-ttu-id="4785a-112">Schließlich die <xref:System.Windows.Controls.MediaElement.Volume%2A> und <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> Eigenschaften werden verwendet, um die Geschwindigkeit Volume und die Wiedergabe des Mediums anpassen.</span><span class="sxs-lookup"><span data-stu-id="4785a-112">Finally, the <xref:System.Windows.Controls.MediaElement.Volume%2A> and <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> properties are used to adjust the volume and playback speed of the media.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="4785a-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4785a-113">See Also</span></span>  
 [<span data-ttu-id="4785a-114">Steuern eines MediaElement mit einem Storyboard</span><span class="sxs-lookup"><span data-stu-id="4785a-114">Control a MediaElement by Using a Storyboard</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)
