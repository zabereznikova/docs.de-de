---
title: Übersicht über die OpenFileDialog-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
ms.openlocfilehash: 24327ded50ac927642e2687b40b1f10de9bdf41e
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211697"
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Übersicht über die OpenFileDialog-Komponente (Windows Forms)

Bei der Windows Forms-Komponente <xref:System.Windows.Forms.OpenFileDialog> handelt es sich um ein vorkonfiguriertes Dialogfeld. Dies entspricht dem **geöffnete Datei** (Dialogfeld), die von der Windows-Betriebssystem verfügbar gemacht werden. Sie erbt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.

## <a name="use-this-component"></a>Verwenden Sie diese Komponente

Verwenden Sie diese Komponente in der Windows-basierte Anwendung als einfache Lösung für die Dateiauswahl, anstatt ein eigenes Dialogfeld zu konfigurieren. Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind. Jedoch darüber im Klaren sein, die bei Verwendung der <xref:System.Windows.Forms.OpenFileDialog> -Komponente verwenden, müssen Sie Ihre eigene Logik zum Öffnen von Dateien schreiben.

Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen. Sie können die Benutzer zum Auswählen mehrerer Dateien geöffnet werden, ermöglichen die <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> Eigenschaft. Darüber hinaus können Sie mithilfe der <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> Eigenschaft, um zu bestimmen, ob ein nur-Lese Kontrollkästchen im Dialogfeld wird angezeigt. Die <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> Eigenschaft gibt an, ob das Kontrollkästchen "schreibgeschützt" ausgewählt ist. Zum Schluss die <xref:System.Windows.Forms.FileDialog.Filter%2A> Eigenschaft legt fest, die aktuelle Filterzeichenfolge für den Namen fest, die im Feld "Dateien des Typs" im Dialogfeld angezeigt werden.

Wenn es auf ein Formular hinzugefügt wird die <xref:System.Windows.Forms.OpenFileDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer in Visual Studio angezeigt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Windows.Forms.OpenFileDialog>
- [OpenFileDialog-Komponente](openfiledialog-component-windows-forms.md)
