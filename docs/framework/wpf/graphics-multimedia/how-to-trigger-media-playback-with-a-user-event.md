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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59150175"
---
# <a name="how-to-trigger-media-playback-with-a-user-event"></a>Vorgehensweise: Auslösen der Medienwiedergabe durch ein Benutzerereignis
In diesem Beispiel wird die Synchronisierung der Medienwiedergabe mit einem Ereignis dargestellt.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die <xref:System.Windows.Controls.MediaElement> Steuerelement und die <xref:System.Windows.Media.MediaTimeline> Klasse um einen Sound wiederzugeben, das auftritt, klickt der Benutzer eine <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[MediaGallery_snippet#SoundFromUserEventExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundFromUserEventExample.xaml#soundfromusereventexamplewholepage)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.EventTrigger.RoutedEvent%2A>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Themen zu Vorgehensweisen](audio-and-video-how-to-topics.md)
- [Grafiken und Multimedia](index.md)
