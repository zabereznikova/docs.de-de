---
title: 'Gewusst wie: Extrahieren eines mit einer Datei verknüpften Symbols in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 21bce2f630649afb59272362a7f40055855ed512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>Gewusst wie: Extrahieren eines mit einer Datei verknüpften Symbols in Windows Forms
Viele Dateien verfügen über eingebettete Symbole, die eine visuelle Darstellung des zugeordneten Dateityps bereitstellen. Microsoft Word-Dokumente enthalten z. B. ein Symbol, das sie als Word-Dokumenten identifiziert. Zum Anzeigen von Dateien in einem Listensteuerelement oder Table-Steuerelement können Sie das Symbol für den Dateityp neben den einzelnen Dateinamen anzeigen möchten. Hierzu können Sie einfach mithilfe der <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie mit einer Datei verknüpften Symbols zu extrahieren und den Dateinamen und das zugehörige Symbol in einer <xref:System.Windows.Forms.ListView> Steuerelement.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um das Beispiel zu kompilieren:  
  
-   Fügen Sie den vorangehenden Code in einem Windows Form, und rufen die `ExtractAssociatedIconExample` Methode aus den Konstruktor des Formulars oder <xref:System.Windows.Forms.Form.Load> Ereignisbehandlungsmethode.  
  
     Sie müssen sicherstellen, dass das Formular importiert die <xref:System.IO> Namespace.  
  
## <a name="see-also"></a>Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)  
 [ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
