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
ms.openlocfilehash: 81220ad4c0bf00a38abfe7257d5fc61e92e8d885
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61779092"
---
# <a name="how-to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>Vorgehensweise: Unterstützen von COM-Interop durch Anzeigen eines Windows Forms mit der ShowDialog-Methode
Sie können Probleme mit der Component Object Model-Interoperabilität (COM) beheben, indem Sie die Windows Form in einer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Nachrichtenschleife anzeigen, die Sie mit der <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> -Methode erstellen können.  
  
 Damit ein Formular aus einer COM-Clientanwendung heraus ordnungsgemäß funktioniert, müssen Sie es in einer Windows Forms-Nachrichtenschleife ausführen. Hierzu können Sie einen der folgenden Ansätze verwenden:  
  
- Verwenden Sie die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode, um die Windows Form anzuzeigen.  
  
- Zeigen Sie jedes Windows Form in einem separaten Thread an. Weitere Informationen finden Sie unter [Vorgehensweise: Unterstützen von COM-Interop durch Anzeigen jedes Windows-Formular in einem eigenen Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md).  
  
## <a name="procedure"></a>Prozedur  
 Die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode ist möglicherweise die einfachste Möglichkeit, eine Form in einer [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Nachrichtenschleife anzuzeigen, weil es von allen Ansätzen die geringste Codeimplementierung erfordert.  
  
 Die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode unterbricht die Nachrichtenschleife der nicht verwalteten Anwendung und zeigt die Form als Dialogfeld an. Da die Schleife der Hostanwendung angehalten wurde, erstellt die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode eine neue [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Nachrichtenschleife zum Verarbeiten der Nachrichten der Form.  
  
 Der Nachteil der <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode ist, dass die Form als modales Dialogfeld geöffnet wird. Dieses Verhalten blockiert solange jede Benutzeroberfläche (UI) in der aufrufenden Anwendung, wie die Windows Form geöffnet ist. Wenn der Benutzer die Form schließt, wird die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Nachrichtenschleife geschlossen und die zuvor erstellte Nachrichtenschleife der Anwendung erneut ausgeführt.  
  
 Sie können eine Klassenbibliothek in Windows Forms erstellen, die über eine Methode zum Anzeigen der Form verfügt, und die Klassenbibliothek anschließend für COM-Interop bauen. Sie können diese DLL-Datei aus Visual Basic 6.0 oder Microsoft Foundation Classes (MFC) verwenden, und Sie können in jeder dieser Umgebungen die <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode aufrufen, um die Form anzuzeigen.  
  
#### <a name="to-support-com-interop-by-displaying-a-windows-form-with-the-showdialog-method"></a>So unterstützen Sie COM-Interop durch Anzeigen einer Windows Form mit der ShowDialog-Methode  
  
- Ersetzen Sie in Ihrer <xref:System.Windows.Forms.Form.Show%2A?displayProperty=nameWithType> -Komponente alle Aufrufe der <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> -Methode durch Aufrufe der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] -Methode.  
  
## <a name="see-also"></a>Siehe auch

- [Verfügbarmachen von .NET Framework-Komponenten in COM](../../interop/exposing-dotnet-components-to-com.md)
- [Vorgehensweise: Unterstützen von COM-Interop durch Anzeigen jedes Windows-Formular in einem eigenen Thread](how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread.md)
- [Windows Forms und nicht verwaltete Anwendungen](windows-forms-and-unmanaged-applications.md)
