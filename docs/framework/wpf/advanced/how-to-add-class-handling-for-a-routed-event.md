---
title: 'Gewusst wie: Hinzufügen einer Klassenbehandlung für ein Routingereignis'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
ms.openlocfilehash: 85c3491c9035d807b4c654659a8641121bb5709f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33545362"
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a>Gewusst wie: Hinzufügen einer Klassenbehandlung für ein Routingereignis
Routingereignisse können entweder durch die Klasse oder Instanzhandler auf einen beliebigen Knoten in der Route behandelt werden. Klassenhandler werden zuerst aufgerufen und können von Klasse-Implementierungen verwendet werden, um Ereignisse aus der Instanz Behandlung zu unterdrücken, oder dass Sie andere Ereignis spezifische Verhalten auf Ereignisse, die im Besitz von Basisklassen eingeführt. Dieses Beispiel veranschaulicht zwei eng verwandte Techniken zum Implementieren von Klassenhandler.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet eine benutzerdefinierte Klasse, die auf der Grundlage der <xref:System.Windows.Controls.Canvas> Bereich. Die grundlegende Prämisse der Anwendung ist, dass die benutzerdefinierte Klasse Verhaltensweisen auf seine untergeordneten Elemente einschließlich abfangen, die linken Maustaste drückt, und behandelt führt, bevor die Klasse des untergeordneten Elements oder beliebige Instanzhandler aufgerufen werden, markieren.  
  
 Die <xref:System.Windows.UIElement> Klasse bereitstellt, eine virtuelle Methode, die ermöglicht eine Klassenbehandlung für das <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> Ereignis, indem das Ereignis einfach überschrieben. Dies ist die einfachste Methode zum Klassenbehandlung implementieren, wenn eine solche virtuelle Methode an einer beliebigen Stelle in der Klassenhierarchie verfügbar ist. Der folgende code zeigt die <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> Implementierung in "MyEditContainer", die abgeleitet ist <xref:System.Windows.Controls.Canvas>. Die Implementierung kennzeichnet das Ereignis in den Argumenten behandelt, und fügt dann Code für dem Quellelement eine grundlegende sichtbare Änderung erteilen.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 Wenn kein virtuelles auf Basisklassen oder für die jeweilige Methode verfügbar ist, Klassenbehandlung kann hinzugefügt werden direkt über eine Hilfsprogrammmethode, die von der <xref:System.Windows.EventManager> Klasse <xref:System.Windows.EventManager.RegisterClassHandler%2A>. Diese Methode sollte nur innerhalb der statischen Initialisierung von Klassen aufgerufen werden, die Klassenbehandlung hinzufügen möchten. In diesem Beispiel fügt einen anderen Handler für <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> , und die registrierte Klasse wird in diesem Fall die benutzerdefinierte Klasse. Im Gegensatz dazu bei Verwendung die registrierte Klasse wird tatsächlich die <xref:System.Windows.UIElement> Basisklasse. In Fällen, wo Basisklassen und -Unterklasse Klassenbehandlung registrieren, werden die Unterklassenhandler zuerst aufgerufen. Das Verhalten in einer Anwendung wäre, dass dieser Handler diese zuerst den Posteingang anzeigen würde und dann die visuelle Änderung im Handler für die virtuelle Methode angezeigt werden würden.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.EventManager>  
 [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)  
 [Behandeln eines Routingereignisses](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)  
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)
