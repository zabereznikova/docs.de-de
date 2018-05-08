---
title: 'Gewusst wie: Analysieren von Freihandeingaben mit Analysehinweisen'
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
ms.openlocfilehash: 74f8b3df5767888e8bca0d9f67e9c47630353fb0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a>Gewusst wie: Analysieren von Freihandeingaben mit Analysehinweisen
Ein [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) bietet einen Hinweis für die [System.Windows.Ink.InkAnalyzer](https://msdn.microsoft.com/library/system.windows.ink.inkanalyzer(v=vs.100).aspx) , dem er zugeordnet ist.  Der Hinweis gilt für den vom angegebenen Bereich der [System.Windows.Ink.ContextNode.Location%2A](https://msdn.microsoft.com/library/system.windows.ink.contextnode.location(v=vs.100).aspx) Eigenschaft von der [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) und stellt zusätzlichen Kontext, um die Freihand-Analyzer Verbessern Sie die Genauigkeit der Erkennung. Die [System.Windows.Ink.InkAnalyzer](https://msdn.microsoft.com/library/system.windows.ink.inkanalyzer(v=vs.100).aspx) gilt diese Kontextinformationen beim Analysieren von Freihandeingaben aus innerhalb der Hinweis Bereichs abgerufen werden.  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine Anwendung, das mehrere [System.Windows.Ink.AnalysisHintNode](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode(v=vs.100).aspx) Objekte in einem Formular, das Freihandeingaben akzeptiert. Die Anwendung verwendet die [System.Windows.Ink.AnalysisHintNode.Factoid%2A](https://msdn.microsoft.com/library/system.windows.ink.analysishintnode.factoid(v=vs.100)) -Eigenschaft Kontextinformationen für jeden Eintrag auf dem Formular bereit.  Die Anwendung Hintergrundanalyse verwendet, um die Freihandeingabe zu analysieren und löscht alle Freihand-Form fünf Sekunden, nachdem der Benutzer das Hinzufügen von Freihandeingaben beendet.  
  
 [!code-xaml[HowToAnalyzeInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
