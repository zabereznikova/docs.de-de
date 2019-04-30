---
title: Übersicht über die PrintDocument-Komponente (Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
ms.openlocfilehash: a3f08aa4bd5b63769cef35dbea2209d5d83261be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62012619"
---
# <a name="printdocument-component-overview-windows-forms"></a>Übersicht über die PrintDocument-Komponente (Windows Forms)
Die Komponente [PrintDocument](printdocument-component-windows-forms.md) von Windows Forms wird verwendet, um die Eigenschaften festzulegen, die beschreiben, was gedruckt werden soll. Außerdem wird sie verwendet, um das Dokument in Windows-basierten Anwendungen drucken zu können. Sie kann zusammen mit der Komponente [PrintDialog](printdialog-component-windows-forms.md) verwendet werden, um alle Aspekte des Druckens eines Dokuments zu steuern.  
  
## <a name="working-with-the-printdocument-component"></a>Arbeiten mit der PrintDocument-Komponente  
 Zwei der wichtigsten Szenarios, bei denen die <xref:System.Drawing.Printing.PrintDocument> Komponente sind:  
  
- Einfache Druckaufträge wie das Drucken einer einzelnen Textdatei. In diesem Fall fügen Sie der <xref:System.Drawing.Printing.PrintDocument> Komponente zu einem Windows-Formular hinzufügen anschließend Programmierlogik, die eine Datei im ausgibt der <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignishandler. Die Programmierlogik muss mit der <xref:System.Drawing.Printing.PrintDocument.Print%2A> Methode, um das Dokument zu drucken. Diese Methode sendet eine <xref:System.Drawing.Graphics> in enthaltene Objekt das <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> Eigenschaft der <xref:System.Drawing.Printing.PrintPageEventArgs> -Klasse, an den Drucker. Ein Beispiel für die zeigt, wie Sie ein Textdokument mit Drucken der <xref:System.Drawing.Printing.PrintDocument> Komponente finden Sie unter [Vorgehensweise: Drucken einer mehrseitigen Textdatei in Windows Forms](../advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).  
  
- Komplexere Druckaufträge, z.B. eine Situation, in der Sie bereits geschriebene Drucklogik wiederverwenden möchten. In diesem Fall würden Sie eine neue Komponente von Ableiten der <xref:System.Drawing.Printing.PrintDocument> Komponente und außer Kraft setzen (finden Sie unter [überschreibt](~/docs/visual-basic/language-reference/modifiers/overrides.md) für Visual Basic oder [überschreiben](~/docs/csharp/language-reference/keywords/override.md) für C#) die <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis.  
  
 Wenn es auf ein Formular hinzugefügt wird die <xref:System.Drawing.Printing.PrintDocument> Komponente, die in der Taskleiste am unteren Rand der Windows Forms-Designer wird angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Printing.PrintDocument>
- [Druckunterstützung in Windows Forms](../advanced/windows-forms-print-support.md)
- [PrintDocument-Komponente](printdocument-component-windows-forms.md)
