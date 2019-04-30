---
title: 'Vorgehensweise: Hinzufügen von Daten zur Zwischenablage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
ms.openlocfilehash: 03d3a0c6026761fcdbc45472f2bbb7ac593f4394
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004470"
---
# <a name="how-to-add-data-to-the-clipboard"></a>Vorgehensweise: Hinzufügen von Daten zur Zwischenablage
Die <xref:System.Windows.Forms.Clipboard> -Klasse bietet Methoden, die Sie für die Interaktion mit der Windows-Betriebssystem-Zwischenablage-Funktion verwenden können. Viele Anwendungen verwenden die Zwischenablage als temporäre Repository für Daten. Beispielsweise werden die Zwischenablage von Textverarbeitungsprogrammen während Ausschneiden und Einfügen-Vorgänge verwenden. Die Zwischenablage eignet sich auch zum Übertragen von Daten aus einer Anwendung in eine andere.  
  
 Wenn Sie Daten in die Zwischenablage hinzufügen, können Sie das Format der Daten, die angeben, damit andere Anwendungen die Daten erkennen können, wenn sie dieses Format verwenden können. Sie können auch Daten hinzufügen, in die Zwischenablage in mehreren verschiedenen Formaten, um die Anzahl von anderen Anwendungen zu erhöhen, die möglicherweise die Daten verwenden können.  
  
 Ein Zwischenablageformat ist eine Zeichenfolge, die das Format identifiziert, so dass eine Anwendung, die dieses Format wird verwendet, die zugehörigen Daten abgerufen werden. Die <xref:System.Windows.Forms.DataFormats> Klasse stellt vordefinierte Formatnamen für Ihre Verwendung. Sie können auch eigene Formatnamen verwenden oder den Typ eines Objekts als Format.  
  
 Verwenden Sie zum Hinzufügen von Daten in einem oder mehreren Formaten in die Zwischenablage die <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> Methode. Sie können jedes beliebige Objekt an diese Methode übergeben, aber um die Daten in mehreren Formaten hinzufügen, müssen Sie zunächst die Daten hinzufügen, um ein separates Objekt mit mehreren Formaten funktionieren. In der Regel fügen Sie Ihre Daten in eine <xref:System.Windows.Forms.DataObject>, aber Sie können alle Typen, implementieren die <xref:System.Windows.Forms.IDataObject> Schnittstelle.  
  
 In [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], Sie können Daten direkt in die Zwischenablage hinzufügen, mit der neuen Methoden entwickelt, um grundlegende Aufgaben der Zwischenablage zu vereinfachen. Verwenden Sie diese Methoden, bei der Arbeit mit Daten in einem einzelnen, gemeinsamen Format z. B. Text.  
  
> [!NOTE]
>  Alle Teilen Windows-basierten Anwendungen sich die Zwischenablage. Aus diesem Grund werden die Inhalte können geändert werden, wenn Sie in einer anderen Anwendung wechseln.  
>   
>  Die <xref:System.Windows.Forms.Clipboard> Klasse kann nur in Threads auf Singlethread-Apartment (STA) Modus verwendet werden. Um diese Klasse verwenden zu können, stellen sicher, dass Ihre `Main` Methode ist mit markiert die <xref:System.STAThreadAttribute> Attribut.  
>   
>  Ein Objekt müssen Sie in der Zwischenablage abgelegt werden serialisierbar sein. Um einen Typ serialisierbar zu machen, markieren Sie sie mit der <xref:System.SerializableAttribute> Attribut. Wenn Sie ein nicht serialisierbares Objekt an eine Zwischenablage-Methode übergeben, wird die Methode fehlschlagen, ohne eine Ausnahme auszulösen. Weitere Informationen zur Serialisierung finden Sie unter <xref:System.Runtime.Serialization>.  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>Zum Hinzufügen von Daten in einem einzelnen, gemeinsamen Format in die Zwischenablage  
  
1. Verwenden der <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, oder <xref:System.Windows.Forms.Clipboard.SetText%2A> Methode. Diese Methoden stehen nur in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>Zum Hinzufügen von Daten in einem benutzerdefinierten Format in die Zwischenablage  
  
1. Verwenden der <xref:System.Windows.Forms.Clipboard.SetData%2A> Methode mit einem benutzerdefinierten Format-Namen. Diese Methode ist nur in verfügbar [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     Sie können auch die Namen von vordefinierten Format mit der <xref:System.Windows.Forms.Clipboard.SetData%2A> Methode. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>Zum Hinzufügen von Daten in die Zwischenablage in mehreren Formaten  
  
1. Verwenden der <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> -Methode und übergeben Sie einen <xref:System.Windows.Forms.DataObject> , die Ihre Daten enthält. Sie müssen diese Methode verwenden, zum Hinzufügen von Daten in die Zwischenablage auf Versionen vor [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Siehe auch

- [Drag & Drop-Vorgänge und Unterstützung der Zwischenablage](drag-and-drop-operations-and-clipboard-support.md)
- [Vorgehensweise: Abrufen von Daten aus der Zwischenablage](how-to-retrieve-data-from-the-clipboard.md)
