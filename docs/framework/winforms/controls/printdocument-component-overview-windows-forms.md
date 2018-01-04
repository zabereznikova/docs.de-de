---
title: "Übersicht über die PrintDocument-Komponente (Windows Forms)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: PrintDocument
helpviewer_keywords:
- PrintDocument component [Windows Forms], about PrintDocument component
- printing [Windows Forms], PrintDocument component
ms.assetid: b59b4b60-dce5-42ca-8421-3a54a2f7bab0
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 414a7972550558b40403b7f4cbfd9a49194666be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="printdocument-component-overview-windows-forms"></a>Übersicht über die PrintDocument-Komponente (Windows Forms)
Die Komponente [PrintDocument](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md) von Windows Forms wird verwendet, um die Eigenschaften festzulegen, die beschreiben, was gedruckt werden soll. Außerdem wird sie verwendet, um das Dokument in Windows-basierten Anwendungen drucken zu können. Sie kann zusammen mit der Komponente [PrintDialog](../../../../docs/framework/winforms/controls/printdialog-component-windows-forms.md) verwendet werden, um alle Aspekte des Druckens eines Dokuments zu steuern.  
  
## <a name="working-with-the-printdocument-component"></a>Arbeiten mit der PrintDocument-Komponente  
 Zwei der wichtigsten Szenarien, bei denen, die <xref:System.Drawing.Printing.PrintDocument> Komponente sind:  
  
-   Einfache Druckaufträge wie das Drucken einer einzelnen Textdatei. In diesem Fall fügen Sie der <xref:System.Drawing.Printing.PrintDocument> Komponente auf einem Windows Form hinzufügen dann Programmierlogik, der ausgibt, eine Datei in der <xref:System.Drawing.Printing.PrintDocument.PrintPage> -Ereignishandler. Die Programmierlogik muss mit der <xref:System.Drawing.Printing.PrintDocument.Print%2A> Methode, um das Dokument zu drucken. Diese Methode sendet eine <xref:System.Drawing.Graphics> in enthaltenes Objekt die <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> Eigenschaft von der <xref:System.Drawing.Printing.PrintPageEventArgs> -Klasse, an den Drucker. Ein Beispiel, das so drucken Sie ein Textdokument mit veranschaulicht die <xref:System.Drawing.Printing.PrintDocument> Komponente finden Sie unter [wie: Drucken einer mehrseitigen Textdatei in Windows Forms](../../../../docs/framework/winforms/advanced/how-to-print-a-multi-page-text-file-in-windows-forms.md).  
  
-   Komplexere Druckaufträge, z.B. eine Situation, in der Sie bereits geschriebene Drucklogik wiederverwenden möchten. In einem solchen Fall leiten Sie eine neue Komponente aus der <xref:System.Drawing.Printing.PrintDocument> Komponente und überschreiben (finden Sie unter [überschreibt](~/docs/visual-basic/language-reference/modifiers/overrides.md) für Visual Basic oder [überschreiben](~/docs/csharp/language-reference/keywords/override.md) für c#) die <xref:System.Drawing.Printing.PrintDocument.PrintPage> Ereignis.  
  
 Wenn sie zu einem Formular hinzugefügt wird die <xref:System.Drawing.Printing.PrintDocument> Komponente in der Taskleiste am unteren Rand der Windows Forms-Designer angezeigt.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Drawing.Graphics>  
 <xref:System.Drawing.Printing.PrintDocument>  
 [Druckunterstützung in Windows Forms](../../../../docs/framework/winforms/advanced/windows-forms-print-support.md)  
 [PrintDocument-Komponente](../../../../docs/framework/winforms/controls/printdocument-component-windows-forms.md)
