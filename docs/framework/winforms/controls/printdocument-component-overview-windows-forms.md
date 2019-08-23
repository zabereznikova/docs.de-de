---
title: Übersicht über die PrintDocument-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: 16a7f3a34ccb280f7bf91c52e29b20edc22130b9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69928997"
---
# <a name="printdocument-component-overview-windows-forms"></a>Übersicht über die PrintDocument-Komponente (Windows Forms)

Die Komponente [PrintDocument](printdocument-component-windows-forms.md) von Windows Forms wird verwendet, um die Eigenschaften festzulegen, die beschreiben, was gedruckt werden soll. Außerdem wird sie verwendet, um das Dokument in Windows-basierten Anwendungen drucken zu können. Sie kann zusammen mit der Komponente [PrintDialog](printdialog-component-windows-forms.md) verwendet werden, um alle Aspekte des Druckens eines Dokuments zu steuern.

## <a name="working-with-the-printdocument-component"></a>Arbeiten mit der PrintDocument-Komponente

Zwei der wichtigsten Szenarien, in denen die <xref:System.Drawing.Printing.PrintDocument> -Komponente enthalten ist, sind:

- Einfache Druckaufträge wie das Drucken einer einzelnen Textdatei. In einem solchen Fall würden Sie die <xref:System.Drawing.Printing.PrintDocument> Komponente zu einem Windows Form hinzufügen und dann eine Programmierlogik hinzufügen, die eine Datei <xref:System.Drawing.Printing.PrintDocument.PrintPage> im-Ereignishandler ausgibt. Die Programmierlogik sollte mit der <xref:System.Drawing.Printing.PrintDocument.Print%2A> -Methode zum Drucken des Dokuments in die-Methode münden. Diese Methode sendet ein <xref:System.Drawing.Graphics> -Objekt, das in <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> der-Eigenschaft <xref:System.Drawing.Printing.PrintPageEventArgs> der-Klasse enthalten ist, an den Drucker. Ein Beispiel für das Drucken eines Textdokuments mithilfe der <xref:System.Drawing.Printing.PrintDocument> -Komponente finden [Sie unter Gewusst wie: Drucken einer mehrseitigen Textdatei in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).

- Komplexere Druckaufträge, z.B. eine Situation, in der Sie bereits geschriebene Drucklogik wiederverwenden möchten. In <xref:System.Drawing.Printing.PrintDocument> einem solchen Fall würden Sie eine neue Komponente von der Komponente ableiten und [über](../../../visual-basic/language-reference/modifiers/overrides.md) schreiben (siehe außer Kraft setzungen für Visual Basic oder C# <xref:System.Drawing.Printing.PrintDocument.PrintPage> [außer Kraft](../../../csharp/language-reference/keywords/override.md) setzung für) das Ereignis.

Wenn Sie einem Formular hinzugefügt wird, wird <xref:System.Drawing.Printing.PrintDocument> die Komponente in der Leiste am unteren Rand des Windows Forms-Designer in Visual Studio angezeigt.

## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Druckunterstützung in Windows Forms](../advanced/windows-forms-print-support.md)
- [PrintDocument-Komponente](printdocument-component-windows-forms.md)
