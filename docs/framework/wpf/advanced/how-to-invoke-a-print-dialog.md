---
title: 'Gewusst wie: Aufrufen eines Druckdialogfelds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: 75a4160366766efbd19d6e8ae26fbec102e7f95b
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/22/2020
ms.locfileid: "86924499"
---
# <a name="how-to-invoke-a-print-dialog"></a>Gewusst wie: Aufrufen eines Druckdialogfelds
Um die Möglichkeit zum Drucken von Ihrer Anwendung bereitzustellen, können Sie einfach ein-Objekt erstellen und öffnen <xref:System.Windows.Controls.PrintDialog> .  
  
## <a name="example"></a>Beispiel  
 Das- <xref:System.Windows.Controls.PrintDialog> Steuerelement stellt einen einzelnen Einstiegspunkt für die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] -,-Konfigurations-und XPS-Auftrags Übermittlung bereit. Das-Steuerelement ist einfach zu verwenden und kann mithilfe von Markup oder Code instanziiert werden [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] . Im folgenden Beispiel wird veranschaulicht, wie das-Steuerelement im Code instanziiert und geöffnet wird und wie daraus gedruckt wird. Außerdem wird gezeigt, wie sichergestellt wird, dass im Dialogfeld der Benutzer die Möglichkeit erhält, einen bestimmten Seitenbereich festzulegen. Im Beispielcode wird davon ausgegangen, dass sich die Datei "FixedDocumentSequence. XPS" im Stammverzeichnis des Laufwerks C: befindet.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Wenn das Dialogfeld geöffnet ist, können Benutzer aus den Druckern auswählen, die auf Ihrem Computer installiert sind. Sie haben auch die Möglichkeit, den [Microsoft XPS-Dokument-Writer](/windows/win32/printdocs/microsoft-xps-document-writer) auszuwählen, um eine XPS-Datei (XML Paper Specification) zu erstellen, anstatt Sie zu drucken.  
  
> [!NOTE]
> Das <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> WPF-Steuerelement, das in diesem Thema erläutert wird, sollte nicht mit der- <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> Komponente von Windows Forms verwechselt werden.  
  
 Streng genommen können Sie die Methode verwenden, <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> ohne das Dialogfeld zu öffnen. In diesem Sinne kann das Steuerelement als nicht gesehene Druckkomponente verwendet werden. Aus Leistungsgründen wäre es jedoch besser, entweder die <xref:System.Printing.PrintQueue.AddJob%2A> -Methode oder eine der vielen <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> -und- <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden von zu verwenden <xref:System.Windows.Xps.XpsDocumentWriter> . Weitere Informationen hierzu finden Sie unter [Programm gesteuertes Drucken von XPS-Dateien](how-to-programmatically-print-xps-files.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Windows.Controls.PrintDialog>
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
- [Microsoft XPS-Dokument-Generator](/windows/win32/printdocs/microsoft-xps-document-writer)
