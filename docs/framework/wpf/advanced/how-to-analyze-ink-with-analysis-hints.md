---
title: 'Vorgehensweise: Analysieren von Freihandeingaben mit Analysehinweisen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], analyzing
- analyzing ink [WPF]
- ink [WPF], AnalysisHintNode objects [WPF]
- AnalysisHintNode objects [WPF]
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
ms.openlocfilehash: a4c38ddf52e9054fe9126df4b7e172548617b90d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61776999"
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a><span data-ttu-id="1d1f8-102">Vorgehensweise: Analysieren von Freihandeingaben mit Analysehinweisen</span><span class="sxs-lookup"><span data-stu-id="1d1f8-102">How to: Analyze Ink with Analysis Hints</span></span>
<span data-ttu-id="1d1f8-103">Ein [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) stellt einen Hinweis für die [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) , das sie angefügt ist.</span><span class="sxs-lookup"><span data-stu-id="1d1f8-103">An [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) provides a hint for the [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) to which it is attached.</span></span>  <span data-ttu-id="1d1f8-104">Der Hinweis gilt für den vom angegebenen Bereich der [System.Windows.Ink.ContextNode.Location%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) Eigenschaft der [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) und stellt zusätzlichen Kontext, um die Freihand-Analyse, um Verbessern Sie die Genauigkeit der Spracherkennung.</span><span class="sxs-lookup"><span data-stu-id="1d1f8-104">The hint applies to the area specified by the [System.Windows.Ink.ContextNode.Location%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) property of the [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) and provides extra context to the ink analyzer to improve recognition accuracy.</span></span> <span data-ttu-id="1d1f8-105">Die [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) gilt diese Kontextinformationen, beim Analysieren von Freihandeingaben aus innerhalb der Hinweis des Bereichs abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1d1f8-105">The [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) applies this context information when analyzing ink obtained from within the hint's area.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1d1f8-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1d1f8-106">Example</span></span>  
 <span data-ttu-id="1d1f8-107">Im folgende Beispiel wird eine Anwendung, das mehrere [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) Objekte in einem Formular, die Freihandeingabe akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="1d1f8-107">The following example is an application that uses multiple [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) objects on a form that accepts ink input.</span></span> <span data-ttu-id="1d1f8-108">Die Anwendung verwendet die [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) Eigenschaft, um Informationen zum Sitzungskontext für jeden Eintrag auf dem Formular bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1d1f8-108">The application uses the [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) property to provide context information for each entry on the form.</span></span>  <span data-ttu-id="1d1f8-109">Die Anwendung verwendet eine Hintergrundanalyse zum Analysieren von Freihandeingaben und löscht die Form der Freihand vollständig fünf Sekunden, nachdem der Benutzer beendet das Hinzufügen von Freihandeingaben.</span><span class="sxs-lookup"><span data-stu-id="1d1f8-109">The application uses background analysis to analyze the ink and clears the form of all ink five seconds after the user stops adding ink.</span></span>  
  
 [!code-xaml[HowToAnalyzeInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
