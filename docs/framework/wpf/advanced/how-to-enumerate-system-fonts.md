---
title: 'Gewusst wie: Auflisten von Systemschriftarten'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
ms.openlocfilehash: 7fc996a2d3ba7042fce70afc20be5d64042c2b63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-enumerate-system-fonts"></a>Gewusst wie: Auflisten von Systemschriftarten
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird gezeigt, wie die Schriftarten in der schriftartenauflistung aufgezählt werden. Den Namen der Schriftfamilie der einzelnen <xref:System.Windows.Media.FontFamily> in <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> wird ein Kombinationsfeld als ein Element hinzugefügt.  
  
 [!code-csharp[TextOverview#100](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 Wenn mehrere Versionen der gleichen Schriftfamilie im selben Verzeichnis befinden sich die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Schriftart Aufzählung zurückgegeben, die neueste Version der Schriftart. Wenn die Versionsinformationen keine Lösung bereitstellt, wird die Schriftart, mit dem neuesten Zeitstempel zurückgegeben. Wenn Informationen für den Timestamp entspricht, wird die Schriftartdatei, das zuerst in alphabetischer Reihenfolge zurückgegeben.
