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
ms.openlocfilehash: 6d7bc322079718d17a921ef34af79145b021e3a7
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636093"
---
# <a name="how-to-invoke-a-print-dialog"></a>Gewusst wie: Aufrufen eines Druckdialogfelds
Um die Möglichkeit zum Drucken von Ihrer Anwendung bereitzustellen, können Sie einfach ein <xref:System.Windows.Controls.PrintDialog> Objekt erstellen und öffnen.  
  
## <a name="example"></a>Beispiel  
 Das <xref:System.Windows.Controls.PrintDialog>-Steuerelement stellt einen einzelnen Einstiegspunkt für die [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]-, Konfigurations-und XPS-Auftrags Übermittlung bereit. Das-Steuerelement ist einfach zu verwenden und kann mit [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] Markup oder Code instanziiert werden. Im folgenden Beispiel wird veranschaulicht, wie das-Steuerelement im Code instanziiert und geöffnet wird und wie daraus gedruckt wird. Außerdem wird gezeigt, wie sichergestellt wird, dass im Dialogfeld der Benutzer die Möglichkeit erhält, einen bestimmten Seitenbereich festzulegen. Im Beispielcode wird davon ausgegangen, dass sich die Datei "FixedDocumentSequence. XPS" im Stammverzeichnis des Laufwerks C: befindet.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Wenn das Dialogfeld geöffnet ist, können Benutzer aus den Druckern auswählen, die auf Ihrem Computer installiert sind. Sie haben auch die Möglichkeit, den [Microsoft XPS-Dokument-Writer](https://go.microsoft.com/fwlink/?LinkId=147319) auszuwählen, um eine XPS-Datei (XML Paper Specification) zu erstellen, anstatt Sie zu drucken.  
  
> [!NOTE]
> Die in diesem Thema beschriebene <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> Steuerung von WPF sollte nicht mit der <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> Komponente von Windows Forms verwechselt werden.  
  
 Streng genommen können Sie die <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A>-Methode verwenden, ohne das Dialogfeld zu öffnen. In diesem Sinne kann das Steuerelement als nicht gesehene Druckkomponente verwendet werden. Aus Leistungsgründen wäre es jedoch besser, entweder die <xref:System.Printing.PrintQueue.AddJob%2A>-Methode oder eine der vielen <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A>-und <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden der <xref:System.Windows.Xps.XpsDocumentWriter>zu verwenden. Weitere Informationen hierzu finden Sie unter [Programm gesteuertes Drucken von XPS-Dateien](how-to-programmatically-print-xps-files.md) und.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.PrintDialog>
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
- [Microsoft XPS-Dokumentwriter](https://go.microsoft.com/fwlink/?LinkId=147319)
