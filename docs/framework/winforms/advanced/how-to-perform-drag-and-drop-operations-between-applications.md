---
title: 'Vorgehensweise: Ausführen von Drag & Drop-Operationen zwischen Anwendungen'
ms.date: 03/30/2017
helpviewer_keywords:
- drag and drop [Windows Forms], between applications
ms.assetid: fa347436-2b12-4dd6-8507-59d7241f6a06
ms.openlocfilehash: f7fecf2f90c56e5ac10ea5929f1c23b25bf181bc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59221755"
---
# <a name="how-to-perform-drag-and-drop-operations-between-applications"></a>Vorgehensweise: Ausführen von Drag & Drop-Operationen zwischen Anwendungen
Das Ausführen von Drag &amp; Drop-Vorgängen zwischen Anwendungen unterscheidet sich nicht vom Aktivieren dieser Aktion innerhalb einer Anwendung, so lange sich die beiden betroffenen Anwendungen gemäß dem „Vertrag“ verhalten, der zwischen den Eigenschaften <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> und <xref:System.Windows.Forms.DragEventArgs.Effect%2A> eingerichtet wurde.  
  
 Im folgenden Verfahren verwenden Sie eine von Ihnen erstellte Windows-basierte Anwendung und das im Windows-Betriebssystem enthaltene Textverarbeitungsprogramm WordPad, um Drag &amp; Drop-Vorgänge zwischen Anwendungen auszuführen. WordPad verfügt über einen bestimmten Satz an zulässigen Effekte für Drag &amp; Drop-Text. Die Windows-basierte Anwendung, für die Sie Code schreiben, arbeitet mit diesen Effekten, damit die Drag &amp; Drop-Vorgänge erfolgreich ausgeführt werden können.  
  
### <a name="to-perform-a-drag-and-drop-procedure-between-applications"></a>So führen Sie ein Drag &amp; Drop-Verfahren zwischen Anwendungen aus  
  
1.  Erstellen Sie eine neue Windows Forms-Anwendung.  
  
2.  Fügen Sie Ihrem Formular ein <xref:System.Windows.Forms.TextBox>-Steuerelement hinzu.  
  
3.  Konfigurieren Sie das <xref:System.Windows.Forms.TextBox>-Steuerelement, um abgelegte Daten zu empfangen.  
  
     Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Eine Drag & Drop-Vorgang in Windows Forms](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).  
  
4.  Führen Sie die Windows-basierte Anwendung aus. Während die Anwendung aktiv ist, führen Sie WordPad aus.  
  
     WordPad ist ein Text-Editor von Windows, der Drag & Drop-Vorgänge ermöglicht. Ist verfügbar durch Drücken der **starten** Schaltfläche auswählen **ausführen**, und geben dann `WordPad` in das Textfeld ein, der die **ausführen** Dialogfeld und klicken Sie auf **OK**.  
  
5.  Sobald WordPad geöffnet ist, geben Sie eine Textzeichenfolge ein.  
  
6.  Mit der Maus markieren Sie den Text, und ziehen Sie den markierten Text dann zum <xref:System.Windows.Forms.TextBox>-Steuerelement in der Windows-basierten Anwendung.  
  
     Wenn sich die Maus über dem <xref:System.Windows.Forms.TextBox>-Steuerelement befindet (und damit folglich das <xref:System.Windows.Forms.Control.DragEnter>-Ereignis ausgelöst wird), können Sie erkennen, dass sich der Cursor geändert hat. Sie können den markierten Text dann im <xref:System.Windows.Forms.TextBox>-Steuerelement ablegen.  
  
     Darüber hinaus können Sie das <xref:System.Windows.Forms.TextBox>-Steuerelement konfigurieren, damit Textzeichenfolgen per Drag &amp; Drop in WordPad eingefügt werden können. Weitere Informationen finden Sie unter [Exemplarische Vorgehensweise: Eine Drag & Drop-Vorgang in Windows Forms](walkthrough-performing-a-drag-and-drop-operation-in-windows-forms.md).  
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Hinzufügen von Daten zur Zwischenablage](how-to-add-data-to-the-clipboard.md)
- [Vorgehensweise: Abrufen von Daten aus der Zwischenablage](how-to-retrieve-data-from-the-clipboard.md)
- [Drag &amp; Drop-Operationen und Unterstützung der Zwischenablage](drag-and-drop-operations-and-clipboard-support.md)
