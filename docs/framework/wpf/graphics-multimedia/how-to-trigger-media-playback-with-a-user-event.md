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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769277"
---
# <a name="how-to-trigger-media-playback-with-a-user-event"></a><span data-ttu-id="871de-102">Vorgehensweise: Auslösen der Medienwiedergabe durch ein Benutzerereignis</span><span class="sxs-lookup"><span data-stu-id="871de-102">How to: Trigger Media Playback with a User Event</span></span>
<span data-ttu-id="871de-103">In diesem Beispiel wird die Synchronisierung der Medienwiedergabe mit einem Ereignis dargestellt.</span><span class="sxs-lookup"><span data-stu-id="871de-103">This example shows how to synchronize media playback with an event.</span></span>  
  
## <a name="example"></a><span data-ttu-id="871de-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="871de-104">Example</span></span>  
 <span data-ttu-id="871de-105">Im folgenden Beispiel wird die <xref:System.Windows.Controls.MediaElement> Steuerelement und die <xref:System.Windows.Media.MediaTimeline> Klasse um einen Sound wiederzugeben, das auftritt, klickt der Benutzer eine <xref:System.Windows.Controls.Button>.</span><span class="sxs-lookup"><span data-stu-id="871de-105">The following example uses the <xref:System.Windows.Controls.MediaElement> control and the <xref:System.Windows.Media.MediaTimeline> class to play a sound that occurs when the user clicks a <xref:System.Windows.Controls.Button>.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#SoundFromUserEventExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundFromUserEventExample.xaml#soundfromusereventexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="871de-106">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="871de-106">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.EventTrigger.RoutedEvent%2A>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="871de-107">Themen zu Vorgehensweisen</span><span class="sxs-lookup"><span data-stu-id="871de-107">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="871de-108">Grafiken und Multimedia</span><span class="sxs-lookup"><span data-stu-id="871de-108">Graphics and Multimedia</span></span>](index.md)
