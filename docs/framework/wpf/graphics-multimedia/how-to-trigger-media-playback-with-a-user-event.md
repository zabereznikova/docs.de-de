---
title: 'Vorgehensweise: Auslösen der Medienwiedergabe durch ein Benutzerereignis'
ms.date: 03/30/2017
helpviewer_keywords:
- synchronizing media playback with events [WPF]
- playback of media [WPF], synchronizing with events
- media [WPF], synchronizing playback with events
- multimedia [WPF], synchronizing media playback with events
ms.assetid: c4dbe632-6e7f-4d7f-9df5-98737a758bc3
ms.openlocfilehash: ae8ba54cc852bb85350492c95e3e890aebf6534f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150175"
---
# <a name="how-to-trigger-media-playback-with-a-user-event"></a><span data-ttu-id="907e8-102">Vorgehensweise: Auslösen der Medienwiedergabe durch ein Benutzerereignis</span><span class="sxs-lookup"><span data-stu-id="907e8-102">How to: Trigger Media Playback with a User Event</span></span>
<span data-ttu-id="907e8-103">In diesem Beispiel wird die Synchronisierung der Medienwiedergabe mit einem Ereignis dargestellt.</span><span class="sxs-lookup"><span data-stu-id="907e8-103">This example shows how to synchronize media playback with an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="907e8-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="907e8-104">Example</span></span>  
 <span data-ttu-id="907e8-105">Im folgenden Beispiel wird die <xref:System.Windows.Controls.MediaElement> Steuerelement und die <xref:System.Windows.Media.MediaTimeline> Klasse um einen Sound wiederzugeben, das auftritt, klickt der Benutzer eine <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="907e8-105">The following example uses the <xref:System.Windows.Controls.MediaElement> control and the <xref:System.Windows.Media.MediaTimeline> class to play a sound that occurs when the user clicks a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#SoundFromUserEventExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundFromUserEventExample.xaml#soundfromusereventexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="907e8-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="907e8-106">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.EventTrigger.RoutedEvent%2A>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="907e8-107">Gewusst wie-Themen</span><span class="sxs-lookup"><span data-stu-id="907e8-107">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="907e8-108">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="907e8-108">Graphics and Multimedia</span></span>](index.md)
