---
title: 'Vorgehensweise: Unterstützen von COM-Interop durch Anzeigen eines Windows Forms mit der ShowDialog-Methode'
ms.date: 03/30/2017
helpviewer_keywords:
- COM [Windows Forms]
- Windows Forms, unmanaged
- COM interop [Windows Forms], calling methods
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: 87aac8ad-3c04-43b3-9b0c-d0b00df9ee74
ms.openlocfilehash: f2fb48e07243694b14904b240bdcb0739175c2fc
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593525"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Vorgehensweise: Unterstützen von COM-Interop durch Anzeigen eines Windows Forms mit der ShowDialog-Methode
Sie können Probleme mit der Component Object Model (COM) Interoperabilität beheben, durch das Anzeigen von Ihrem Windows-Formular in einer Schleife der .NET Framework-Nachricht, die erstellt wird die <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> Methode.  
  
 Damit ein Formular aus einer COM-Clientanwendung heraus ordnungsgemäß funktioniert, müssen Sie es in einer Windows Forms-Nachrichtenschleife ausführen. Hierzu können Sie einen der folgenden Ansätze verwenden:  
  
- Verwenden Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode, um die Windows Form anzuzeigen.  
  
- Zeigen Sie jedes Windows Form in einem separaten Thread an. Weitere Informationen finden Sie unter [Vorgehensweise: Unterstützen von COM-Interop durch Anzeigen jedes Windows-Formular in einem eigenen Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).  
  
## <a name="procedure"></a>Prozedur  
 Mithilfe der <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode ist möglicherweise die einfachste Möglichkeit zum Anzeigen eines Formulars in einer .NET Framework-Nachrichtenschleife, da von allen Ansätzen, ist es erforderlich, am wenigsten Code implementieren.  
  
 Die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode unterbricht die Nachrichtenschleife der nicht verwalteten Anwendung und zeigt die Form als Dialogfeld an. Da die Nachrichtenschleife der hostanwendung angehalten wurde, die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> Methode erstellt eine neue .NET Framework-Meldungsschleife zum Verarbeiten der Nachrichten der Form.  
  
 Der Nachteil der <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode ist, dass die Form als modales Dialogfeld geöffnet wird. Dieses Verhalten blockiert solange jede Benutzeroberfläche (UI) in der aufrufenden Anwendung, wie die Windows Form geöffnet ist. Wenn der Benutzer das Formular verlässt, schließt die .NET Framework-Meldungsschleife und der früheren Anwendung Meldungsschleife erneut gestartet wird.  
  
 Sie können eine Klassenbibliothek in Windows Forms erstellen, die über eine Methode zum Anzeigen der Form verfügt, und die Klassenbibliothek anschließend für COM-Interop bauen. Sie können diese DLL-Datei aus Visual Basic 6.0 oder Microsoft Foundation Classes (MFC) verwenden, und Sie können in jeder dieser Umgebungen die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode aufrufen, um die Form anzuzeigen.  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>So unterstützen Sie COM-Interop durch Anzeigen einer Windows Form mit der ShowDialog-Methode  
  
- Ersetzen Sie alle Aufrufe der <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> Methode durch Aufrufe der <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode in der .NET Framework-Komponente.  
  
## <a name="see-also"></a>Siehe auch

- [Verfügbarmachen von .NET Framework-Komponenten in COM](../../interop/exposing-dotnet-components-to-com.md)
- [Vorgehensweise: Unterstützen von COM-Interop durch Anzeigen jedes Windows-Formular in einem eigenen Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [Windows Forms und nicht verwaltete Anwendungen](windows-forms-and-unmanaged-applications.md)
