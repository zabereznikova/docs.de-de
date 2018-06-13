---
title: Übersicht über die SaveFileDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: be5f70e2e8b0d5143ef387819689ce95564a72d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33537446"
---
# <a name="savefiledialog-component-overview-windows-forms"></a>Übersicht über die SaveFileDialog-Komponente (Windows Forms)
Die <xref:System.Windows.Forms.SaveFileDialog>-Komponente von Windows Forms ist ein vorkonfiguriertes Dialogfeld. Es ist identisch mit dem Standard **Datei speichern** (Dialogfeld), die von Windows verwendet. Die Vererbung erfolgt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.  
  
## <a name="working-with-the-savefiledialog-component"></a>Arbeiten mit der SaveFileDialog-Komponente  
 Verwenden Sie es als einfache Lösung für das Aktivieren von Benutzern zum Speichern von Dateien anstatt ein eigenes Dialogfeld zu konfigurieren. Durch die Verwendung von auf Windows-Standarddialogfelder, ist die grundlegende Funktion der Anwendungen, die Sie erstellen, Benutzern sofort vertraut. Jedoch darüber im Klaren sein, die bei Verwendung der <xref:System.Windows.Forms.SaveFileDialog> -Komponente verwenden, müssen Sie Ihre eigene Logik zum Speichern der Datei schreiben.  
  
 Sie können die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen. Sie können eine Datei öffnen, im Modus "Lese-/Schreibzugriff" mithilfe der <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> Methode.  
  
 Wenn sie zu einem Formular hinzugefügt wird die <xref:System.Windows.Forms.SaveFileDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.SaveFileDialog>  
 [SaveFileDialog-Komponente](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
