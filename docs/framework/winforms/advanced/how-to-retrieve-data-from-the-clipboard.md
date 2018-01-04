---
title: 'Gewusst wie: Abrufen von Daten aus der Zwischenablage'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pasting Clipboard data
- Clipboard [Windows Forms], retrieving data
ms.assetid: 99612537-2c8a-449f-aab5-2b3b28d656e7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c009efe743865896341da268bd14bf24158df46d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>Gewusst wie: Abrufen von Daten aus der Zwischenablage
Die <xref:System.Windows.Forms.Clipboard> Klasse enthält Methoden, die Sie für die Interaktion mit der Zwischenablage-Feature des Windows-Betriebssystems verwenden können. Viele Anwendungen verwenden die Zwischenablage als temporäre Repository für Daten. Beispielsweise verwenden Textverarbeitungsprogramme Zwischenablage während Ausschneide- und Einfügevorgänge. Die Zwischenablage ist auch nützlich für Daten aus einer Anwendung in eine andere übertragen.  
  
 Einige Anwendungen speichern Daten in der Zwischenablage in verschiedenen Formaten, um die Anzahl der anderen Anwendungen zu erhöhen, die möglicherweise die Daten verwenden können. Ein Zwischenablageformat ist eine Zeichenfolge, die das Format bezeichnet. Eine Anwendung, die das angegebene Format wird verwendet, kann die zugehörigen Daten in der Zwischenablage abgerufen werden. Die <xref:System.Windows.Forms.DataFormats> Klasse bietet vordefinierte Formatnamen für Ihre Verwendung. Sie können auch eigene Formatnamen verwenden oder den Typ eines Objekts als Format. Informationen zum Hinzufügen von Daten in die Zwischenablage, finden Sie unter [wie: Hinzufügen von Daten in die Zwischenablage](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md).  
  
 Um zu bestimmen, ob die Zwischenablage Daten in einem bestimmten Format enthält, verwenden Sie eine von der `Contains` *Format* Methoden oder die <xref:System.Windows.Forms.Clipboard.GetData%2A> Methode. Um Daten aus der Zwischenablage abzurufen, verwenden Sie eine von der `Get` *Format* Methoden oder <xref:System.Windows.Forms.Clipboard.GetData%2A> Methode. Diese Methoden sind neu in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
 Um den Zugriff auf Daten aus der Zwischenablage mit Versionen vor [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)], verwenden Sie die <xref:System.Windows.Forms.Clipboard.GetDataObject%2A> Methode und rufen Sie die Methoden des zurückgegebenen <xref:System.Windows.Forms.IDataObject>. Um zu bestimmen, ob ein bestimmtes Format im zurückgegebenen Objekt verfügbar ist, rufen Sie z. B. die <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> Methode.  
  
> [!NOTE]
>  Alle Windows-basierten Anwendungen Freigabe der Zwischenablage des Systems. Aus diesem Grund werden die Inhalte können geändert werden, beim Wechsel zu einer anderen Anwendung.  
>   
>  Die <xref:System.Windows.Forms.Clipboard> Klasse kann nur verwendet werden, in Threads auf Singlethread-Apartment (STA) Modus festgelegt. Zum Verwenden dieser Klasse sicher, dass Ihre `Main` Methode markiert ist, mit der <xref:System.STAThreadAttribute> Attribut.  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>Zum Abrufen von Daten aus der Zwischenablage in einem einzelnen, gemeinsamen-format  
  
1.  Verwenden der <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>, <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>, <xref:System.Windows.Forms.Clipboard.GetImage%2A>, oder <xref:System.Windows.Forms.Clipboard.GetText%2A> Methode. Verwenden Sie optional das entsprechende `Contains` *Format* Methoden zuerst an, um zu bestimmen, ob Daten in einem bestimmten Format verfügbar sind. Diese Methoden stehen nur in [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
     [!code-vb[System.Windows.Forms.Clipboard#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>Zum Abrufen von Daten aus der Zwischenablage in einem benutzerdefinierten format  
  
1.  Verwenden der <xref:System.Windows.Forms.Clipboard.GetData%2A> Methode mit einem benutzerdefinierten Formatnamen. Diese Methode ist nur in verfügbar [!INCLUDE[dnprdnext](../../../../includes/dnprdnext-md.md)].  
  
     Sie können auch die vordefinierten Formatnamen mit der <xref:System.Windows.Forms.Clipboard.SetData%2A> Methode. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DataFormats>.  
  
     [!code-csharp[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
     [!code-vb[System.Windows.Forms.Clipboard#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>Zum Abrufen von Daten aus der Zwischenablage in mehreren Formaten  
  
1.  Verwenden Sie die <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>-Methode. Verwenden Sie diese Methode zum Abrufen von Daten aus der Zwischenablage in Versionen vor [!INCLUDE[dnprdnlong](../../../../includes/dnprdnlong-md.md)].  
  
     [!code-csharp[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
     [!code-vb[System.Windows.Forms.Clipboard#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]  
    [!code-csharp[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]  
  
## <a name="see-also"></a>Siehe auch  
 [Drag & Drop-Vorgänge und Unterstützung der Zwischenablage](../../../../docs/framework/winforms/advanced/drag-and-drop-operations-and-clipboard-support.md)  
 [Gewusst wie: Hinzufügen von Daten zur Zwischenablage](../../../../docs/framework/winforms/advanced/how-to-add-data-to-the-clipboard.md)
