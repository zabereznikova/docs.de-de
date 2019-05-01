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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053370"
---
# <a name="storing-ink"></a><span data-ttu-id="23ef0-102">Speichern von Freihandeingaben</span><span class="sxs-lookup"><span data-stu-id="23ef0-102">Storing Ink</span></span>
<span data-ttu-id="23ef0-103">Die <xref:System.Windows.Ink.StrokeCollection.Save%2A> Methoden bieten Unterstützung für das Speichern von Eingabehilfen als Format ISF (Ink Serialized).</span><span class="sxs-lookup"><span data-stu-id="23ef0-103">The <xref:System.Windows.Ink.StrokeCollection.Save%2A> methods provide support for storing ink as Ink Serialized Format (ISF).</span></span> <span data-ttu-id="23ef0-104">Konstruktoren für die <xref:System.Windows.Ink.StrokeCollection> Klasse bieten Unterstützung für das Lesen von Daten von Freihandeingaben.</span><span class="sxs-lookup"><span data-stu-id="23ef0-104">Constructors for the <xref:System.Windows.Ink.StrokeCollection> class provide support for reading ink data.</span></span>  
  
## <a name="ink-storage-and-retrieval"></a><span data-ttu-id="23ef0-105">Freihandeingaben speichern und Abrufen</span><span class="sxs-lookup"><span data-stu-id="23ef0-105">Ink Storage and Retrieval</span></span>  
 <span data-ttu-id="23ef0-106">In diesem Abschnitt wird erläutert, wie zum Speichern und Abrufen von Freihandeingaben auf der [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Plattform.</span><span class="sxs-lookup"><span data-stu-id="23ef0-106">This section discusses how to store and retrieve ink in the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] platform.</span></span>  
  
 <span data-ttu-id="23ef0-107">Das folgende Beispiel implementiert einen Schaltfläche – Click-Ereignishandler, die stellt dem Benutzer das Dialogfeld Datei speichern, und speichert die Freihandeingaben aus einem <xref:System.Windows.Controls.InkCanvas> Out in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="23ef0-107">The following example implements a button-click event handler that presents the user with a File Save dialog box and saves the ink from an <xref:System.Windows.Controls.InkCanvas> out to a file.</span></span>  
  
 [!code-csharp[DigitalInkTopics#12](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#12)]
 [!code-vb[DigitalInkTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#12)]  
  
 <span data-ttu-id="23ef0-108">Das folgende Beispiel implementiert einen Schaltfläche – Click-Ereignishandler, die stellt dem Benutzer das Dialogfeld Datei öffnen, und liest von Freihandeingaben aus der Datei in eine <xref:System.Windows.Controls.InkCanvas> Element.</span><span class="sxs-lookup"><span data-stu-id="23ef0-108">The following example implements a button-click event handler that presents the user with a File Open dialog box and reads ink from the file into an <xref:System.Windows.Controls.InkCanvas> element.</span></span>  
  
 [!code-csharp[DigitalInkTopics#13](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#13)]
 [!code-vb[DigitalInkTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#13)]  
  
## <a name="see-also"></a><span data-ttu-id="23ef0-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="23ef0-109">See also</span></span>

- <xref:System.Windows.Controls.InkCanvas>
- [<span data-ttu-id="23ef0-110">Windows Presentation Foundation</span><span class="sxs-lookup"><span data-stu-id="23ef0-110">Windows Presentation Foundation</span></span>](../index.md)
