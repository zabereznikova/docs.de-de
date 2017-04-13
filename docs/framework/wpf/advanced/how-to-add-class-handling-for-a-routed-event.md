---
title: "Gewusst wie: Hinzuf&#252;gen einer Klassenbehandlung f&#252;r ein Routingereignis | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Klassen-Handler, Routingereignisse"
  - "Routingereignisse, Klassen-Handler"
  - "task_core_add_class_handling_routed_event"
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Hinzuf&#252;gen einer Klassenbehandlung f&#252;r ein Routingereignis
Routingereignisse können entweder von Klassenhandlern oder Instanzhandlern verarbeitet werden, die sich auf beliebigen Knoten der Route befinden.  Klassenhandler werden zuerst aufgerufen und können von Klassenimplementierungen verwendet werden, um Ereignisse der Instanzbehandlung zu unterdrücken oder um andere ereignisspezifische Verhalten für Ereignisse auszulösen, deren Besitzer Basisklassen sind.  Dieses Beispiel zeigt zwei eng miteinander verwandte Verfahren zum Implementieren von Klassenhandlern.  
  
## Beispiel  
 In diesem Beispiel wird eine benutzerdefinierte Klasse basierend auf dem <xref:System.Windows.Controls.Canvas>\-Bereich verwendet.  Die Grundvoraussetzung der Anwendung besteht darin, dass die benutzerdefinierte Klasse Verhalten für ihre untergeordneten Elemente einführt, zum Beispiel das Abfangen aller Klicks mit der linken Maustaste und das Markieren als behandelt, bevor die Klasse des untergeordneten Elements oder beliebige Instanzhandler aufgerufen werden.  
  
 Die <xref:System.Windows.UIElement>\-Klasse legt eine virtuelle Methode offen, die die Klassenbehandlung für das <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown>\-Ereignis ermöglicht, indem das Ereignis einfach überschrieben wird.  Auf diese Weise können Sie die Klassenbehandlung am einfachsten implementieren, wenn eine virtuelle Methode dieser Art in der Klassenhierarchie verfügbar ist.  Der folgende Code zeigt die <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A>\-Implementierung in "MyEditContainer", die von <xref:System.Windows.Controls.Canvas> abgeleitet wird.  Die Implementierung markiert das Ereignis in den Argumenten als behandelt und fügt dann Code hinzu, um das Quellelement mit einer grundlegenden sichtbaren Änderung zu versehen.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 Wenn für die Basisklassen bzw. für die jeweilige Methode kein virtuelles Element verfügbar ist, können Sie die Klassenbehandlung direkt mithilfe einer Hilfsmethode der <xref:System.Windows.EventManager>\-Klasse hinzufügen, nämlich <xref:System.Windows.EventManager.RegisterClassHandler%2A>.  Sie sollten diese Methode nur innerhalb der statischen Initialisierung von Klassen aufrufen, die die Klassenbehandlung hinzufügen.  In diesem Beispiel wird ein weiterer Handler für <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> hinzugefügt, und in diesem Fall handelt es sich bei der registrierten Klasse um eine benutzerdefinierte Klasse.  Im Gegensatz dazu ist die registrierte Klasse bei Verwendung von virtuellen Elementen tatsächlich die <xref:System.Windows.UIElement>\-Basisklasse.  Falls Basisklassen und Unterklasse jeweils die Klassenbehandlung registrieren, werden die Unterklassenhandler zuerst aufgerufen.  In einer Anwendung wird dann ein Verhalten ausgeführt, bei dem dieser Handler zuerst ein Meldungsfeld anzeigt, bevor die visuelle Änderung im Handler der virtuellen Methode dargestellt wird.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## Siehe auch  
 <xref:System.Windows.EventManager>   
 [Markieren von Routingereignissen als behandelt und Klassenbehandlung](../../../../docs/framework/wpf/advanced/marking-routed-events-as-handled-and-class-handling.md)   
 [Behandeln eines Routingereignisses](../../../../docs/framework/wpf/advanced/how-to-handle-a-routed-event.md)   
 [Übersicht über Routingereignisse](../../../../docs/framework/wpf/advanced/routed-events-overview.md)