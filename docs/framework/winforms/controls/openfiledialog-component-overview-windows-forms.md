---
title: "Übersicht über die OpenFileDialog-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: OpenFileDialog
helpviewer_keywords:
- OpenFileDialog component [Windows Forms], about OpenFileDialog
- Open File dialog box [Windows Forms], displaying in Windows Forms
ms.assetid: cd717300-46b6-4f82-8207-b218fa7fa407
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 35c947e3efbb9b2e5df775f83ffc6068e49c84e8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="openfiledialog-component-overview-windows-forms"></a>Übersicht über die OpenFileDialog-Komponente (Windows Forms)
Bei der Windows Forms-Komponente <xref:System.Windows.Forms.OpenFileDialog> handelt es sich um ein vorkonfiguriertes Dialogfeld. Er ist der gleiche **Dateiöffnungsmodus** (Dialogfeld), die von Windows-Betriebssystems verfügbar gemacht werden. Die Vererbung erfolgt von der <xref:System.Windows.Forms.CommonDialog>-Klasse.  
  
## <a name="using-this-component"></a>Verwenden diese Komponente  
 Verwenden Sie diese Komponente in der Windows-basierten Anwendung als einfache Lösung für die Dateiauswahl anstatt ein eigenes Dialogfeld zu konfigurieren. Durch die Verwendung von Windows-Standarddialogfeldern erstellen Sie Anwendungen, deren Basisfunktionen Benutzern sofort vertraut sind. Jedoch darüber im Klaren sein, die bei Verwendung der <xref:System.Windows.Forms.OpenFileDialog> -Komponente verwenden, müssen Sie Ihre eigene Logik zum Öffnen von Dateien schreiben.  
  
 Verwenden der <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> Methode, um das Dialogfeld zur Laufzeit anzuzeigen. Sie können Benutzern mit mehreren Dateien geöffnet werden, ermöglichen die <xref:System.Windows.Forms.OpenFileDialog.Multiselect%2A> Eigenschaft. Darüber hinaus können Sie die <xref:System.Windows.Forms.OpenFileDialog.ShowReadOnly%2A> Eigenschaft, um zu bestimmen, ob ein Kontrollkästchen schreibgeschützt sind und im Dialogfeld angezeigt wird. Die <xref:System.Windows.Forms.OpenFileDialog.ReadOnlyChecked%2A> Eigenschaft gibt an, ob das Kontrollkästchen "schreibgeschützt" ausgewählt ist. Schließlich die <xref:System.Windows.Forms.FileDialog.Filter%2A> Eigenschaft legt die aktuelle Filterzeichenfolge für den Namen fest, die im Feld "Dateien des Typs" im Dialogfeld angezeigt werden.  
  
 Wenn sie zu einem Formular hinzugefügt wird die <xref:System.Windows.Forms.OpenFileDialog> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.OpenFileDialog>  
 [OpenFileDialog-Komponente](../../../../docs/framework/winforms/controls/openfiledialog-component-windows-forms.md)
