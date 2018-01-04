---
title: 'Gewusst wie: Analysieren von Freihandeingaben mit Analysehinweisen'
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
- ink [WPF], analyzing
- analyzing ink [WPF]
- ink [WPF], AnalysisHintNode objects [WPF]
- AnalysisHintNode objects [WPF]
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b97f7fe0314b6bf839e4e639e32a48f9261def73
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a><span data-ttu-id="30be2-102">Gewusst wie: Analysieren von Freihandeingaben mit Analysehinweisen</span><span class="sxs-lookup"><span data-stu-id="30be2-102">How to: Analyze Ink with Analysis Hints</span></span>
<span data-ttu-id="30be2-103">Ein [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) bietet einen Hinweis für die [System.Windows.Ink.InkAnalyzer](https://msdn.microsoft.com/library/system.windows.ink.inkanalyzer(v=vs.100).aspx) , dem er zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="30be2-103">An [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) provides a hint for the [System.Windows.Ink.InkAnalyzer](https://msdn.microsoft.com/library/system.windows.ink.inkanalyzer(v=vs.100).aspx) to which it is attached.</span></span>  <span data-ttu-id="30be2-104">Der Hinweis gilt für den vom angegebenen Bereich der [System.Windows.Ink.ContextNode.Location%2A](https://msdn.microsoft.com/library/system.windows.ink.contextnode.location(v=vs.100).aspx) Eigenschaft von der [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) und stellt zusätzlichen Kontext, um die Freihand-Analyzer Verbessern Sie die Genauigkeit der Erkennung.</span><span class="sxs-lookup"><span data-stu-id="30be2-104">The hint applies to the area specified by the [System.Windows.Ink.ContextNode.Location%2A](https://msdn.microsoft.com/library/system.windows.ink.contextnode.location(v=vs.100).aspx) property of the [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) and provides extra context to the ink analyzer to improve recognition accuracy.</span></span> <span data-ttu-id="30be2-105">Die [System.Windows.Ink.InkAnalyzer](https://msdn.microsoft.com/library/system.windows.ink.inkanalyzer(v=vs.100).aspx) gilt diese Kontextinformationen beim Analysieren von Freihandeingaben aus innerhalb der Hinweis Bereichs abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="30be2-105">The [System.Windows.Ink.InkAnalyzer](https://msdn.microsoft.com/library/system.windows.ink.inkanalyzer(v=vs.100).aspx) applies this context information when analyzing ink obtained from within the hint's area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="30be2-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30be2-106">Example</span></span>  
 <span data-ttu-id="30be2-107">Im folgende Beispiel wird eine Anwendung, das mehrere [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) Objekte in einem Formular, das Freihandeingaben akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="30be2-107">The following example is an application that uses multiple [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) objects on a form that accepts ink input.</span></span> <span data-ttu-id="30be2-108">Die Anwendung verwendet die [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode.factoid(v=vs.100)) -Eigenschaft Kontextinformationen für jeden Eintrag auf dem Formular bereit.</span><span class="sxs-lookup"><span data-stu-id="30be2-108">The application uses the [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode.factoid(v=vs.100)) property to provide context information for each entry on the form.</span></span>  <span data-ttu-id="30be2-109">Die Anwendung Hintergrundanalyse verwendet, um die Freihandeingabe zu analysieren und löscht alle Freihand-Form fünf Sekunden, nachdem der Benutzer das Hinzufügen von Freihandeingaben beendet.</span><span class="sxs-lookup"><span data-stu-id="30be2-109">The application uses background analysis to analyze the ink and clears the form of all ink five seconds after the user stops adding ink.</span></span>  
  
 [!code-xaml[HowToAnalyzeInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
