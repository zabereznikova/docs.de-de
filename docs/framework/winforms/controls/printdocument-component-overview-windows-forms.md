---
title: Übersicht über die PrintDocument-Komponente
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: a82cc0cdcb8cfae796c9c6bf60ab73873f85a291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728538"
---
# <a name="printdocument-component-overview-windows-forms"></a>Übersicht über die PrintDocument-Komponente (Windows Forms)

Die Komponente [PrintDocument](printdocument-component-windows-forms.md) von Windows Forms wird verwendet, um die Eigenschaften festzulegen, die beschreiben, was gedruckt werden soll. Außerdem wird sie verwendet, um das Dokument in Windows-basierten Anwendungen drucken zu können. Sie kann zusammen mit der Komponente [PrintDialog](printdialog-component-windows-forms.md) verwendet werden, um alle Aspekte des Druckens eines Dokuments zu steuern.

## <a name="working-with-the-printdocument-component"></a>Arbeiten mit der PrintDocument-Komponente

Zwei der wichtigsten Szenarien, die die <xref:System.Drawing.Printing.PrintDocument> Komponente einbeziehen, sind:

- Einfache Druckaufträge wie das Drucken einer einzelnen Textdatei. In einem solchen Fall würden Sie die <xref:System.Drawing.Printing.PrintDocument> Komponente zu einem Windows Form hinzufügen und dann eine Programmierlogik hinzufügen, die eine Datei im <xref:System.Drawing.Printing.PrintDocument.PrintPage>-Ereignishandler ausgibt. Die Programmierlogik sollte mit der <xref:System.Drawing.Printing.PrintDocument.Print%2A>-Methode zum Drucken des Dokuments in der Sprache stehen. Diese Methode sendet ein <xref:System.Drawing.Graphics> Objekt, das in der <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A>-Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs>-Klasse enthalten ist, an den Drucker. Ein Beispiel, das zeigt, wie Sie ein Textdokument mithilfe der <xref:System.Drawing.Printing.PrintDocument> Komponente drucken, finden Sie unter Gewusst [wie: Drucken einer mehrseitigen Textdatei in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).

- Komplexere Druckaufträge, z.B. eine Situation, in der Sie bereits geschriebene Drucklogik wiederverwenden möchten. In einem solchen Fall würden Sie eine neue Komponente aus der <xref:System.Drawing.Printing.PrintDocument> Komponente ableiten und [über](../../../visual-basic/language-reference/modifiers/overrides.md) schreiben (siehe [außer Kraft](../../../csharp/language-reference/keywords/override.md) setzungen für Visual Basic oder C#außer Kraft setzung für) das <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis.

Wenn Sie einem Formular hinzugefügt wird, wird die <xref:System.Drawing.Printing.PrintDocument> Komponente in der Leiste am unteren Rand des Windows Forms-Designer in Visual Studio angezeigt.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Druckunterstützung in Windows Forms](../advanced/windows-forms-print-support.md)
- [PrintDialog-Komponente](printdocument-component-windows-forms.md)
