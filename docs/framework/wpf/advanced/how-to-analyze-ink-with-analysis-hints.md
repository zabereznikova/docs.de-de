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
# <a name="how-to-analyze-ink-with-analysis-hints"></a>Vorgehensweise: Analysieren von Freihandeingaben mit Analysehinweisen
Ein [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) stellt einen Hinweis für die [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) , das sie angefügt ist.  Der Hinweis gilt für den vom angegebenen Bereich der [System.Windows.Ink.ContextNode.Location%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) Eigenschaft der [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) und stellt zusätzlichen Kontext, um die Freihand-Analyse, um Verbessern Sie die Genauigkeit der Spracherkennung. Die [System.Windows.Ink.InkAnalyzer](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) gilt diese Kontextinformationen, beim Analysieren von Freihandeingaben aus innerhalb der Hinweis des Bereichs abgerufen werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine Anwendung, das mehrere [System.Windows.Ink.AnalysisHintNode](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) Objekte in einem Formular, die Freihandeingabe akzeptiert. Die Anwendung verwendet die [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) Eigenschaft, um Informationen zum Sitzungskontext für jeden Eintrag auf dem Formular bereitzustellen.  Die Anwendung verwendet eine Hintergrundanalyse zum Analysieren von Freihandeingaben und löscht die Form der Freihand vollständig fünf Sekunden, nachdem der Benutzer beendet das Hinzufügen von Freihandeingaben.  
  
 [!code-xaml[HowToAnalyzeInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
