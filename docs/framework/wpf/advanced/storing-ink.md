---
title: Speichern von Freihandeingaben
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
- ISF (Ink Serialized Format)
- storing ink [WPF]
- ink [WPF], storing
- retrieving ink [WPF]
- Ink Serialized Format (ISF)
ms.assetid: a3f6d16b-d682-4680-9965-907332b4d2b8
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 905ab04db2faafc47349d3b8d21098e9eb931cf3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="storing-ink"></a>Speichern von Freihandeingaben
Die <xref:System.Windows.Ink.StrokeCollection.Save%2A> Methoden bieten Unterstützung für das Speichern von Freihandeingaben als ISF Ink Serialized Format (). Konstruktoren für die <xref:System.Windows.Ink.StrokeCollection> Klasse bieten Unterstützung für das Lesen von Freihanddaten.  
  
## <a name="ink-storage-and-retrieval"></a>Freihand-speichern und Abrufen  
 In diesem Abschnitt wird erläutert, wie zum Speichern und Abrufen von Freihandeingaben in der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Plattform.  
  
 Das folgende Beispiel implementiert einen Schaltfläche – Click-Ereignishandler, die bietet dem Benutzer das Dialogfeld Datei speichern und speichert den Inhalt von einem <xref:System.Windows.Controls.InkCanvas> Out in eine Datei.  
  
 [!code-csharp[DigitalInkTopics#12](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 Das folgende Beispiel implementiert einen Schaltfläche – Click-Ereignishandler, die bietet dem Benutzer ein Dialogfeld Datei öffnen, und liest Freihandeingaben aus der Datei in ein <xref:System.Windows.Controls.InkCanvas> Element.  
  
 [!code-csharp[DigitalInkTopics#13](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Controls.InkCanvas>  
 [Windows Presentation Foundation](../../../../docs/framework/wpf/index.md)
