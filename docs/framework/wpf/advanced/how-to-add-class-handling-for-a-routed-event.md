---
title: 'Vorgehensweise: Hinzufügen einer Klassenbehandlung für ein Routingereignis'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
ms.openlocfilehash: 7b897954cbdab461dc0305c6290e67c1af5282c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59224270"
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a>Vorgehensweise: Hinzufügen einer Klassenbehandlung für ein Routingereignis
Routingereignisse können entweder durch die Klasse oder Instanzhandler auf einen beliebigen Knoten in der Route verarbeitet werden. Klassenhandler werden zuerst aufgerufen werden kann, und können von Klasse-Implementierungen verwendet werden, unterdrücken Ereignisse aus der Instanz behandeln, oder führen andere Ereignis bestimmter Verhaltensweisen zu Ereignissen, die von Basisklassen gehören. Dieses Beispiel zeigt zwei eng miteinander verwandte Techniken zum Implementieren von Klassen-Handler.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet eine benutzerdefinierte Klasse, die auf der Grundlage der <xref:System.Windows.Controls.Canvas> Bereich. Die Grundvoraussetzung für die Anwendung ist, dass die benutzerdefinierte Klasse führt die Verhaltensweisen auf seine untergeordneten Elemente einschließlich abfangen, die linken Maustaste klickt und behandelt, bevor die Klasse des untergeordneten Elements oder mögliche Instanzhandler darauf aufgerufen werden, das markieren.  
  
 Die <xref:System.Windows.UIElement> Klasse verfügbar macht, eine virtuelle Methode, die es eine Klassenbehandlung ermöglicht für das <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> Ereignis, indem Sie einfach überschreiben des Ereignisses. Dies ist die einfachste Möglichkeit, die Klassenbehandlung implementieren, wenn eine solche virtuelle Methode an einer beliebigen Stelle in der Klassenhierarchie verfügbar ist. Der folgende code zeigt die <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> Implementierung in "MyEditContainer", das von abgeleitet ist <xref:System.Windows.Controls.Canvas>. Die Implementierung kennzeichnet das Ereignis in den Argumenten behandelt, und fügt dann den Code, um dem Quellelement eine grundlegende sichtbare Änderung erhalten.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 Wenn kein virtuelles auf Basisklassen oder für die jeweilige Methode verfügbar ist, Klassenbehandlung kann hinzugefügt werden direkt über eine Hilfsmethode, die von der <xref:System.Windows.EventManager> -Klasse, <xref:System.Windows.EventManager.RegisterClassHandler%2A>. Diese Methode sollte nur in der statischen Initialisierung von Klassen aufgerufen werden, die Klassenbehandlung hinzufügen. In diesem Beispiel wird ein anderer Handler für <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , und in diesem Fall handelt es sich bei der registrierten Klasse um eine benutzerdefinierte Klasse. Im Gegensatz dazu bei Verwendung von, die registrierte Klasse ist wirklich die <xref:System.Windows.UIElement> Basisklasse. In Fällen, in denen die Basisklassen und -Unterklasse Klassenbehandlung registrieren, werden die Unterklassenhandler zuerst aufgerufen. Das Verhalten in einer Anwendung wäre, dass dieser Handler wird zuerst Meldungsfeld anzeigt, und klicken Sie dann die visuelle Änderung im Ereignishandler für die virtuelle Methode angezeigt werden sollen.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.EventManager>
- [Markieren von Routingereignissen als behandelt und Klassenbehandlung](marking-routed-events-as-handled-and-class-handling.md)
- [Behandeln eines Routingereignisses](how-to-handle-a-routed-event.md)
- [Übersicht über Routingereignisse](routed-events-overview.md)
