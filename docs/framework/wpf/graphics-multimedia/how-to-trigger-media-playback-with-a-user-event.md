---
title: 'Vorgehensweise: Auslösen der Medienwiedergabe durch ein Benutzerereignis'
ms.date: 03/30/2017
helpviewer_keywords:
- synchronizing media playback with events [WPF]
- playback of media [WPF], synchronizing with events
- media [WPF], synchronizing playback with events
- multimedia [WPF], synchronizing media playback with events
ms.assetid: c4dbe632-6e7f-4d7f-9df5-98737a758bc3
ms.openlocfilehash: 1d71e69bcd0332ba7119977dcf67356a3d79a368
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377975"
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
