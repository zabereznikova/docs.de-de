---
title: 'Vorgehensweise: Aufrufen eines Druckdialogfelds'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: 4bad8158925fea8af529f70f92aad74e2a6bbec0
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70254110"
---
# <a name="how-to-invoke-a-print-dialog"></a>Vorgehensweise: Aufrufen eines Druckdialogfelds
Um die Möglichkeit zum Drucken von Ihrer Anwendung bereitzustellen, können Sie einfach ein <xref:System.Windows.Controls.PrintDialog> -Objekt erstellen und öffnen.  
  
## <a name="example"></a>Beispiel  
 Das <xref:System.Windows.Controls.PrintDialog> -Steuerelement stellt einen einzelnen Einstiegs [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)]Punkt für die-,-Konfigurations-und XPS-Auftrags Übermittlung bereit. Das-Steuerelement ist einfach zu verwenden und kann mithilfe [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] von Markup oder Code instanziiert werden. Im folgenden Beispiel wird veranschaulicht, wie das-Steuerelement im Code instanziiert und geöffnet wird und wie daraus gedruckt wird. Außerdem wird gezeigt, wie sichergestellt wird, dass im Dialogfeld der Benutzer die Möglichkeit erhält, einen bestimmten Seitenbereich festzulegen. Im Beispielcode wird davon ausgegangen, dass sich die Datei "FixedDocumentSequence. XPS" im Stammverzeichnis des Laufwerks C: befindet.  
  
 [!code-csharp[printdialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 Wenn das Dialogfeld geöffnet ist, können Benutzer aus den Druckern auswählen, die auf Ihrem Computer installiert sind. Sie haben auch die Möglichkeit, den [Microsoft XPS-Dokument-Writer](https://go.microsoft.com/fwlink/?LinkId=147319) auszuwählen, um eine XPS-Datei (XML Paper Specification) zu erstellen, anstatt Sie zu drucken.  
  
> [!NOTE]
> Das <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> Steuerelement [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)]von, das in diesem Thema erläutert wird, sollte nicht mit der <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> Komponente von Windows Forms verwechselt werden.  
  
 Streng genommen können Sie die <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> Methode verwenden, ohne das Dialogfeld zu öffnen. In diesem Sinne kann das Steuerelement als nicht gesehene Druckkomponente verwendet werden. Aus Leistungsgründen wäre es jedoch <xref:System.Printing.PrintQueue.AddJob%2A> besser, entweder die-Methode oder eine der vielen <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> -und- <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> Methoden von <xref:System.Windows.Xps.XpsDocumentWriter>zu verwenden. Weitere Informationen hierzu finden Sie unter [Programm gesteuertes Drucken von XPS-Dateien](how-to-programmatically-print-xps-files.md) und.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Controls.PrintDialog>
- [Dokumente in WPF](documents-in-wpf.md)
- [Übersicht über das Drucken](printing-overview.md)
- [Microsoft XPS-Dokumentwriter](https://go.microsoft.com/fwlink/?LinkId=147319)
