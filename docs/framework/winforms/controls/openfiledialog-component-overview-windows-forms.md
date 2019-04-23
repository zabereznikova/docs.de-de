---
title: Übersicht über die OpenFileDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: ec275a5923d332d23205c79442fa23bc6e402e3f
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59147334"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Übersicht über die OpenFileDialog-Komponente (Windows Forms)
Bei der Windows Forms-Komponente <xref:System.Windows.Forms.OpenFileDialog> handelt es sich um ein vorkonfiguriertes Dialogfeld. Dies entspricht dem **geöffnete Datei** (Dialogfeld), die von der Windows-Betriebssystem verfügbar gemacht werden. Sie erbt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.  
  
## <a name="using-this-component"></a>Diese Komponente verwenden  
 Verwenden Sie diese Komponente in der Windows-basierte Anwendung als einfache Lösung für die Dateiauswahl, anstatt ein eigenes Dialogfeld zu konfigurieren. Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind. Jedoch darüber im Klaren sein, die bei Verwendung der <xref:System.Windows.Forms.OpenFileDialog> -Komponente verwenden, müssen Sie Ihre eigene Logik zum Öffnen von Dateien schreiben.  
  
 Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen. Sie können die Benutzer zum Auswählen mehrerer Dateien geöffnet werden, ermöglichen die <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> Eigenschaft. Darüber hinaus können Sie mithilfe der <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> Eigenschaft, um zu bestimmen, ob ein nur-Lese Kontrollkästchen im Dialogfeld wird angezeigt. Die <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> Eigenschaft gibt an, ob das Kontrollkästchen "schreibgeschützt" ausgewählt ist. Zum Schluss die <xref:System.Windows.Forms.FileDialog.Filter%2A> Eigenschaft legt fest, die aktuelle Filterzeichenfolge für den Namen fest, die im Feld "Dateien des Typs" im Dialogfeld angezeigt werden.  
  
 Wenn es auf ein Formular hinzugefügt wird die <xref:System.Windows.Forms.OpenFileDialog> Komponente, die in der Taskleiste am unteren Rand der Windows Forms-Designer wird angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog-Komponente](openfiledialog-component-windows-forms.md)
