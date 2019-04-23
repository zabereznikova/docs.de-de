---
title: Speichern von Freihandeingaben
ms.date: 03/30/2017
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
ms.openlocfilehash: 4089aa7942105c14eb628c75edb7f53ffacfaeb0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182337"
---
# <a name="storing-ink"></a>Speichern von Freihandeingaben
Die <xref:System.Windows.Ink.StrokeCollection.Save%2A> Methoden bieten Unterstützung für das Speichern von Eingabehilfen als Format ISF (Ink Serialized). Konstruktoren für die <xref:System.Windows.Ink.StrokeCollection> Klasse bieten Unterstützung für das Lesen von Daten von Freihandeingaben.  
  
## <a name="ink-storage-and-retrieval"></a>Freihandeingaben speichern und Abrufen  
 In diesem Abschnitt wird erläutert, wie zum Speichern und Abrufen von Freihandeingaben auf der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Plattform.  
  
 Das folgende Beispiel implementiert einen Schaltfläche – Click-Ereignishandler, die stellt dem Benutzer das Dialogfeld Datei speichern, und speichert die Freihandeingaben aus einem <xref:System.Windows.Controls.InkCanvas> Out in einer Datei.  
  
 [!code-csharp[DigitalInkTopics#12](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 Das folgende Beispiel implementiert einen Schaltfläche – Click-Ereignishandler, die stellt dem Benutzer das Dialogfeld Datei öffnen, und liest von Freihandeingaben aus der Datei in eine <xref:System.Windows.Controls.InkCanvas> Element.  
  
 [!code-csharp[DigitalInkTopics#13](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.InkCanvas>
- [Windows Presentation Foundation](../index.md)
