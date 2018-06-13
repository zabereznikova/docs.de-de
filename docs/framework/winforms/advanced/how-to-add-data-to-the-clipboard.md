---
title: 'Gewusst wie: Hinzufügen von Daten zur Zwischenablage'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- data [Windows Forms], copying to Clipboard
ms.assetid: 25152454-0e78-40a9-8a9e-a2a5a274e517
ms.openlocfilehash: 6002acfadfd0e688ef432baacbdabffb83890cb8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522066"
---
# <a name="how-to-add-data-to-the-clipboard"></a>Gewusst wie: Hinzufügen von Daten zur Zwischenablage
Die <xref:System.Windows.Forms.Clipboard> Klasse enthält Methoden, die Sie für die Interaktion mit der Zwischenablage-Feature des Windows-Betriebssystems verwenden können. Viele Anwendungen verwenden die Zwischenablage als temporäre Repository für Daten. Beispielsweise verwenden Textverarbeitungsprogramme Zwischenablage während Ausschneide- und Einfügevorgänge. Die Zwischenablage eignet sich auch zum Übertragen von Daten aus einer Anwendung in eine andere.  
  
 Wenn Sie Daten in die Zwischenablage hinzufügen, können Sie das Datenformat, die angeben, damit andere Anwendungen die Daten erkennen können, ob dieses Format verwendet werden kann. Sie können auch Daten hinzufügen, in die Zwischenablage in mehreren verschiedenen Formaten, um die Anzahl der anderen Anwendungen zu erhöhen, die möglicherweise die Daten verwenden können.  
  
 Ein Zwischenablageformat ist eine Zeichenfolge, die das Format identifiziert, damit eine Anwendung, die dieses Format wird verwendet, die zugehörigen Daten abrufen kann. Die <xref:System.Windows.Forms.DataFormats> Klasse bietet vordefinierte Formatnamen für Ihre Verwendung. Sie können auch eigene Formatnamen verwenden oder den Typ eines Objekts als Format.  
  
 Verwenden Sie zum Hinzufügen von Daten in einem oder mehreren Formaten in die Zwischenablage die <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> Methode. Sie können jedes Objekt an diese Methode übergeben, aber um Daten in mehreren Formaten hinzuzufügen, müssen Sie zuerst die Daten hinzufügen, auf ein separates Objekt dienen zum Arbeiten mit mehreren Formaten. In der Regel werden Sie Daten aus die Hinzufügen einer <xref:System.Windows.Forms.DataObject>, aber Sie können einen beliebigen Typ, der implementiert die <xref:System.Windows.Forms.IDataObject> Schnittstelle.  
  
 In [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)], Sie können Daten direkt in die Zwischenablage hinzufügen, mit der neue Methoden, um grundlegende Aufgaben der Zwischenablage zu vereinfachen. Verwenden Sie diese Methoden, bei der Arbeit mit Daten in einem einzelnen, gemeinsamen Format, z. B. Text.  
  
> [!NOTE]
>  Alle Windows-basierten Anwendungen Freigabe die Zwischenablage. Aus diesem Grund werden die Inhalte können geändert werden, beim Wechsel zu einer anderen Anwendung.  
>   
>  Die <xref:System.Windows.Forms.Clipboard> Klasse kann nur verwendet werden, in Threads auf Singlethread-Apartment (STA) Modus festgelegt. Zum Verwenden dieser Klasse sicher, dass Ihre `Main` Methode markiert ist, mit der <xref:System.STAThreadAttribute> Attribut.  
>   
>  Ein Objekt muss für ihn in die Zwischenablage zu versetzen serialisierbar sein. Um einen Typ serialisierbar zu machen, kennzeichnen Sie ihn mit der <xref:System.SerializableAttribute> Attribut. Wenn Sie ein nicht serialisierbares Objekt an eine Zwischenablage-Methode übergeben, wird die Methode fehl, ohne eine Ausnahme auszulösen. Weitere Informationen zur Serialisierung finden Sie unter <xref:System.Runtime.Serialization>.  
  
### <a name="to-add-data-to-the-clipboard-in-a-single-common-format"></a>Zum Hinzufügen von Daten in einem einzelnen, gemeinsamen-Format in die Zwischenablage  
  
1.  Verwenden der <xref:System.Windows.Forms.Clipboard.SetAudio%2A>, <xref:System.Windows.Forms.Clipboard.SetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.SetImage%2A>, oder <xref:System.Windows.Forms.Clipboard.SetText%2A> Methode. Diese Methoden stehen nur in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-add-data-to-the-clipboard-in-a-custom-format"></a>Zum Hinzufügen von Daten in einem benutzerdefinierten Format in die Zwischenablage  
  
1.  Verwenden der <xref:System.Windows.Forms.Clipboard.SetData%2A> Methode mit einem benutzerdefinierten Formatnamen. Diese Methode ist nur in verfügbar [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     Sie können auch die vordefinierten Formatnamen mit der <xref:System.Windows.Forms.Clipboard.SetData%2A> Methode. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-add-data-to-the-clipboard-in-multiple-formats"></a>Zum Hinzufügen von Daten in mehreren Formaten in die Zwischenablage  
  
1.  Verwenden der <xref:System.Windows.Forms.Clipboard.SetDataObject%2A> Methode und übergeben einer <xref:System.Windows.Forms.DataObject> , die Ihre Daten enthält. Verwenden Sie diese Methode zum Hinzufügen von Daten in die Zwischenablage in Versionen vor [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Siehe auch  
 [Drag & Drop-Vorgänge und Unterstützung der Zwischenablage](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [Gewusst wie: Abrufen von Daten aus der Zwischenablage](../../../../docs/framework/winforms/advanced/how-to-retrieve-data-from-the-clipboard.md)
