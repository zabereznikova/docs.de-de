---
title: "Gewusst wie: Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautst&#228;rke und Geschwindigkeit) | Microsoft Docs"
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
  - "Steuern der Medienwiedergabe"
  - "Medien, Steuern der Wiedergabe von"
  - "Multimedia, Steuern der Medienwiedergabe"
  - "Medienwiedergabe, Steuern"
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# Gewusst wie: Steuern eines MediaElement (Wiedergeben, Anhalten, Stoppen, Lautst&#228;rke und Geschwindigkeit)
Das folgende Beispiel zeigt, wie die Wiedergabe von Medien mit einem <xref:System.Windows.Controls.MediaElement> gesteuert werden kann.  In dem Beispiel wird ein einfacher Media Player erstellt, der Funktionen zur Wiedergabe, zum Anhalten, zum Stoppen, zum Vor\- und Zurückspringen und zum Einstellen von Lautstärke und Geschwindigkeitsverhältnis bietet.  
  
## Beispiel  
 Mit dem folgenden Code wird die Benutzeroberfläche erstellt.  
  
> [!NOTE]
>  Die <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A>\-Eigenschaft von <xref:System.Windows.Controls.MediaElement> muss auf `Manual` gesetzt werden, damit die Medien interaktiv wiedergegeben, angehalten und gestoppt werden können.  
  
 [!code-xml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## Beispiel  
 Mit dem folgenden Code werden die Funktionen der Beispieloberflächensteuerelemente implementiert.  Die Methoden <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A> und <xref:System.Windows.Controls.MediaElement.Stop%2A> werden jeweils zum Wiedergeben, Anhalten und Stoppen verwendet.  Indem Sie die <xref:System.Windows.Controls.MediaElement.Position%2A>\-Eigenschaft des <xref:System.Windows.Controls.MediaElement> ändern, können Sie in dem Medium von einer Position zu einer anderen wechseln.  Mit den Eigenschaften <xref:System.Windows.Controls.MediaElement.Volume%2A> und <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> können Sie die Lautstärke und die Wiedergabegeschwindigkeit regeln.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## Siehe auch  
 [Steuern eines MediaElement mit einem Storyboard](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)