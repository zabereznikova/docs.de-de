---
title: Übersicht über die SaveFileDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: ab8eb5409d017c6ea73a44e4e57ccec9cece4824
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54631060"
---
# <a name="savefiledialog-component-overview-windows-forms"></a>Übersicht über die SaveFileDialog-Komponente (Windows Forms)
Die <xref:System.Windows.Forms.SaveFileDialog>-Komponente von Windows Forms ist ein vorkonfiguriertes Dialogfeld. Dies entspricht dem als Standard **Datei speichern** Dialogfeld von Windows verwendet. Die Vererbung erfolgt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.  
  
## <a name="working-with-the-savefiledialog-component"></a>Arbeiten mit der SaveFileDialog-Komponente  
 Verwenden Sie es als eine einfache Lösung zum Aktivieren von Benutzern zum Speichern von Dateien anstatt ein eigenes Dialogfeld zu konfigurieren. Auf Windows-Standarddialogfelder ist, die grundlegende Funktionalität von Anwendungen, die Sie erstellen Benutzern sofort vertraut. Jedoch darüber im Klaren sein, die bei Verwendung der <xref:System.Windows.Forms.SaveFileDialog> -Komponente verwenden, müssen Sie Ihre eigene Logik zum Speichern von Dateien schreiben.  
  
 Sie können die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen. Öffnen Sie eine Datei im Lese-/Schreibzugriff mit der <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> Methode.  
  
 Wenn es auf ein Formular hinzugefügt wird die <xref:System.Windows.Forms.SaveFileDialog> Komponente, die in der Taskleiste am unteren Rand der Windows Forms-Designer wird angezeigt.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.SaveFileDialog>
- [SaveFileDialog-Komponente](../../../../docs/framework/winforms/controls/savefiledialog-component-windows-forms.md)
