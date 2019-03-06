---
title: 'Vorgehensweise: Auflisten von Systemschriftarten'
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
ms.openlocfilehash: c7e81b5d1b70ba911a0b505219f7977e019038cf
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352437"
---
# <a name="how-to-enumerate-system-fonts"></a>Vorgehensweise: Auflisten von Systemschriftarten
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie die Schriftarten in die systemschriftsammlung auflisten. Namen der Schriftfamilie der einzelnen <xref:System.Windows.Media.FontFamily> in <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> wird als ein Element an ein Kombinationsfeld hinzugefügt.  
  
 [!code-csharp[TextOverview#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 Wenn mehrere Versionen der gleichen Schriftfamilie im gleichen Verzeichnis befinden die [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] Schriftart Enumeration zurückgibt, die neueste Version der Schriftart. Die Versionsinformationen keine Lösung bereitstellt, wird die Schriftart mit dem neuesten Zeitstempel zurückgegeben. Wenn die Zeitstempelinformationen gleichwertig ist, wird die Schriftartdatei, das zuerst in alphabetischer Reihenfolge zurückgegeben.
