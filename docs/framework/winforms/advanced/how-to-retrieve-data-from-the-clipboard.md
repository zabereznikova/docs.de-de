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
ms.openlocfilehash: ca24615049abcc145698c033f31e6c98a38253bf
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70040570"
---
# <a name="how-to-retrieve-data-from-the-clipboard"></a>Vorgehensweise: Abrufen von Daten aus der Zwischenablage

Die <xref:System.Windows.Forms.Clipboard> -Klasse stellt Methoden bereit, die Sie verwenden können, um mit der Zwischenablage des Windows-Betriebssystems zu interagieren. Viele Anwendungen verwenden die Zwischenablage als temporäres Repository für-Daten. Beispielsweise wird die Zwischenablage von Word-Prozessoren während Ausschneide-und Einfügevorgängen verwendet. Die Zwischenablage eignet sich auch zum Übertragen von Informationen aus einer Anwendung in eine andere.

Einige Anwendungen speichern Daten in mehreren Formaten in der Zwischenablage, um die Anzahl von anderen Anwendungen zu erhöhen, die die Daten potenziell verwenden können. Ein Zwischenablage Format ist eine Zeichenfolge, die das Format angibt. Eine Anwendung, die das identifizierte Format verwendet, kann die zugeordneten Daten in der Zwischenablage abrufen. Die <xref:System.Windows.Forms.DataFormats> -Klasse stellt vordefinierte Format Namen für ihre Verwendung bereit. Sie können auch Ihre eigenen Format Namen verwenden oder den Typ eines Objekts als sein Format verwenden. Weitere Informationen zum Hinzufügen von Daten zur Zwischenablage [finden Sie unter Gewusst wie: Fügen Sie der Zwischenablage](how-to-add-data-to-the-clipboard.md)Daten hinzu.

Verwenden Sie eine der `Contains` *Format* Methoden oder die <xref:System.Windows.Forms.Clipboard.GetData%2A> -Methode, um zu bestimmen, ob die Zwischenablage Daten in einem bestimmten Format enthält. Verwenden Sie zum Abrufen von Daten aus der Zwischenablage eine `Get`der- *Format* Methoden <xref:System.Windows.Forms.Clipboard.GetData%2A> oder die-Methode. Diese Methoden sind neu in .NET Framework 2,0.

Für den Zugriff auf Daten aus der Zwischenablage mithilfe von Versionen vor .NET Framework 2,0 verwenden <xref:System.Windows.Forms.Clipboard.GetDataObject%2A?displayProperty=nameWithType> Sie die-Methode, und aufrufen Sie <xref:System.Windows.Forms.IDataObject>die-Methoden der zurückgegebenen. Um zu bestimmen, ob ein bestimmtes Format im zurückgegebenen Objekt verfügbar ist, können Sie Beispiels <xref:System.Windows.Forms.IDataObject.GetDataPresent%2A> Weise die-Methode aufzurufen.

> [!NOTE]
> Alle Windows-basierten Anwendungen nutzen die Zwischenablage des Systems gemeinsam. Daher können sich die Inhalte ändern, wenn Sie zu einer anderen Anwendung wechseln.
>
> Die <xref:System.Windows.Forms.Clipboard> -Klasse kann nur in Threads verwendet werden, die auf den STA-Modus (Single Thread Apartment) festgelegt sind. Um diese Klasse zu verwenden, stellen Sie `Main` sicher, dass die- <xref:System.STAThreadAttribute> Methode mit dem-Attribut gekennzeichnet ist.

### <a name="to-retrieve-data-from-the-clipboard-in-a-single-common-format"></a>So rufen Sie Daten aus der Zwischenablage in einem einzelnen, allgemeinen Format ab

1. Verwenden Sie <xref:System.Windows.Forms.Clipboard.GetAudioStream%2A>die <xref:System.Windows.Forms.Clipboard.GetFileDropList%2A>- <xref:System.Windows.Forms.Clipboard.GetImage%2A>,- <xref:System.Windows.Forms.Clipboard.GetText%2A> ,-oder-Methode. Verwenden Sie optional die entsprechenden `Contains`- *Format* Methoden, um zu bestimmen, ob Daten in einem bestimmten Format verfügbar sind. Diese Methoden sind nur in .NET Framework 2,0 verfügbar.

    [!code-csharp[System.Windows.Forms.Clipboard#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#2)]
    [!code-vb[System.Windows.Forms.Clipboard#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#2)]

### <a name="to-retrieve-data-from-the-clipboard-in-a-custom-format"></a>So rufen Sie Daten aus der Zwischenablage in einem benutzerdefinierten Format ab

1. Verwenden Sie <xref:System.Windows.Forms.Clipboard.GetData%2A> die-Methode mit einem benutzerdefinierten Format Namen. Diese Methode ist nur in .NET Framework 2,0 verfügbar.

    Sie können auch vordefinierte Format Namen mit der <xref:System.Windows.Forms.Clipboard.SetData%2A> -Methode verwenden. Weitere Informationen finden Sie unter <xref:System.Windows.Forms.DataFormats>.

    [!code-csharp[System.Windows.Forms.Clipboard#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#3)]
    [!code-vb[System.Windows.Forms.Clipboard#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#3)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

### <a name="to-retrieve-data-from-the-clipboard-in-multiple-formats"></a>So rufen Sie Daten aus der Zwischenablage in mehreren Formaten ab

1. Verwenden Sie die <xref:System.Windows.Forms.Clipboard.GetDataObject%2A>-Methode. Sie müssen diese Methode zum Abrufen von Daten aus der Zwischenablage in früheren Versionen als .NET Framework 2,0 verwenden.

    [!code-csharp[System.Windows.Forms.Clipboard#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#4)]
    [!code-vb[System.Windows.Forms.Clipboard#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#4)]
    [!code-csharp[System.Windows.Forms.Clipboard#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/CS/form1.cs#100)]
    [!code-vb[System.Windows.Forms.Clipboard#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Clipboard/vb/form1.vb#100)]

## <a name="see-also"></a>Siehe auch

- [Drag & Drop-Vorgänge und Unterstützung der Zwischenablage](drag-and-drop-operations-and-clipboard-support.md)
- [Vorgehensweise: Hinzufügen von Daten zur Zwischenablage](how-to-add-data-to-the-clipboard.md)
