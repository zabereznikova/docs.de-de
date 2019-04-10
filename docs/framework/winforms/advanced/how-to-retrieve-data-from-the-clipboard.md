---
title: 'Vorgehensweise: Abrufen von Daten aus der Zwischenablage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
ms.openlocfilehash: e8f77a4fd1047598d51c2e0932d9c1309a305a86
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295509"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>Vorgehensweise: Abrufen von Daten aus der Zwischenablage
Die <xref:System.Windows.Forms.Clipboard> -Klasse bietet Methoden, die Sie für die Interaktion mit der Windows-Betriebssystem-Zwischenablage-Funktion verwenden können. Viele Anwendungen verwenden die Zwischenablage als temporäre Repository für Daten. Beispielsweise werden die Zwischenablage von Textverarbeitungsprogrammen während Ausschneiden und Einfügen-Vorgänge verwenden. Die Zwischenablage ist auch nützlich für die Übertragung von Informationen von einer Anwendung in eine andere.  
  
 Einige Anwendungen speichern Daten in der Zwischenablage in verschiedenen Formaten, um die Anzahl von anderen Anwendungen zu erhöhen, die möglicherweise die Daten verwenden können. Ein Zwischenablageformat ist eine Zeichenfolge, die das Format angibt. Eine Anwendung, die dieses Format verwendet, kann die zugehörigen Daten in der Zwischenablage abrufen. Die <xref:System.Windows.Forms.DataFormats> Klasse stellt vordefinierte Formatnamen für Ihre Verwendung. Sie können auch eigene Formatnamen verwenden oder den Typ eines Objekts als Format. Weitere Informationen zum Hinzufügen von Daten in die Zwischenablage, finden Sie unter [Vorgehensweise: Hinzufügen von Daten in die Zwischenablage](how-to-add-data-to-the-clipboard.md).  
  
 Um zu bestimmen, ob die Zwischenablage Daten in einem bestimmten Format enthält, verwenden Sie eine der der `Contains` *Format* Methoden oder <xref:System.Windows.Forms.Clipboard.GetData%2A> Methode. Um Daten aus der Zwischenablage abzurufen, verwenden Sie eines der `Get` *Format* Methoden oder <xref:System.Windows.Forms.Clipboard.GetData%2A> Methode. Diese Methoden sind neu in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
 Um den Zugriff auf Daten aus der Zwischenablage mit Versionen vor [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], verwenden Sie die <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> Methode und rufen die Methoden des zurückgegebenen <xref:System.Windows.Forms.IDataObject>. Um zu bestimmen, ob ein bestimmtes Format in das zurückgegebene Objekt verfügbar ist, rufen Sie z. B. die <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> Methode.  
  
> [!NOTE]
>  Alle Windows-basierten Anwendungen Freigabe der Zwischenablage des Systems. Aus diesem Grund werden die Inhalte können geändert werden, wenn Sie in einer anderen Anwendung wechseln.  
>   
>  Die <xref:System.Windows.Forms.Clipboard> Klasse kann nur in Threads auf Singlethread-Apartment (STA) Modus verwendet werden. Um diese Klasse verwenden zu können, stellen sicher, dass Ihre `Main` Methode ist mit markiert die <xref:System.STAThreadAttribute> Attribut.  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>Zum Abrufen von Daten aus der Zwischenablage in einem einzelnen, gemeinsamen format  
  
1. Verwenden der <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, oder <xref:System.Windows.Forms.Clipboard.GetText%2A> Methode. Verwenden Sie optional den entsprechenden `Contains` *Format* Methoden, um zu bestimmen, ob die Daten in einem bestimmten Format verfügbar sind. Diese Methoden stehen nur in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>Zum Abrufen von Daten aus der Zwischenablage in einem benutzerdefinierten format  
  
1. Verwenden der <xref:System.Windows.Forms.Clipboard.GetData%2A> Methode mit einem benutzerdefinierten Format-Namen. Diese Methode ist nur in verfügbar [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     Sie können auch die Namen von vordefinierten Format mit der <xref:System.Windows.Forms.Clipboard.SetData%2A> Methode. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>Zum Abrufen von Daten aus der Zwischenablage in mehreren Formaten  
  
1. Verwenden Sie die <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>-Methode. Verwenden Sie diese Methode zum Abrufen von Daten aus der Zwischenablage in Versionen vor [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Siehe auch

- [Drag &amp; Drop-Operationen und Unterstützung der Zwischenablage](drag-and-drop-operations-and-clipboard-support.md)
- [Vorgehensweise: Hinzufügen von Daten zur Zwischenablage](how-to-add-data-to-the-clipboard.md)
