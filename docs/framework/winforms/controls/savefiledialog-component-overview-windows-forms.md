---
title: Übersicht über die SaveFileDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- SaveFileDialog
helpviewer_keywords:
- Save File dialog box [Windows Forms], displaying
- SaveFileDialog component [Windows Forms], about SaveFileDialog
ms.assetid: be7a625f-46fd-4d06-9985-b613dcbf9bd2
ms.openlocfilehash: 93bf0f63e18ee3a384aa062c80faa991b68a6abe
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721501"
---
# <a name="savefiledialog-component-overview-windows-forms"></a>Übersicht über die SaveFileDialog-Komponente (Windows Forms)
Bei der Windows Forms-Komponente <xref:System.Windows.Forms.SaveFileDialog> handelt es sich um ein vorkonfiguriertes Dialogfeld. Dies entspricht dem als Standard **Datei speichern** Dialogfeld von Windows verwendet. Sie erbt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.  
  
## <a name="working-with-the-savefiledialog-component"></a>Arbeiten mit der SaveFileDialog-Komponente  
 Verwenden Sie es als eine einfache Lösung zum Aktivieren von Benutzern zum Speichern von Dateien anstatt ein eigenes Dialogfeld zu konfigurieren. Auf Windows-Standarddialogfelder ist, die grundlegende Funktionalität von Anwendungen, die Sie erstellen Benutzern sofort vertraut. Jedoch darüber im Klaren sein, die bei Verwendung der <xref:System.Windows.Forms.SaveFileDialog> -Komponente verwenden, müssen Sie Ihre eigene Logik zum Speichern von Dateien schreiben.  
  
 Sie können die <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen. Öffnen Sie eine Datei im Lese-/Schreibzugriff mit der <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> Methode.  
  
 Wenn es auf ein Formular hinzugefügt wird die <xref:System.Windows.Forms.SaveFileDialog> Komponente, die in der Taskleiste am unteren Rand der Windows Forms-Designer wird angezeigt.  
  
## <a name="see-also"></a>Siehe auch
- <xref:System.Windows.Forms.SaveFileDialog>
- [SaveFileDialog-Komponente](savefiledialog-component-windows-forms.md)
