---
title: 'Vorgehensweise: Extrahieren eines mit einer Datei verknüpften Symbols in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: d754dc5e8a57b3c4e2e5439bb2524a22d44813c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62004041"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>Vorgehensweise: Extrahieren eines mit einer Datei verknüpften Symbols in Windows Forms
Viele Dateien verfügen über eingebettete Symbole, die eine visuelle Darstellung des zugeordneten Dateityps bereitstellen. Microsoft Word-Dokumente enthalten z. B. ein Symbol, das sie als Word-Dokumenten identifiziert. Zum Anzeigen von Dateien in einem Listensteuerelement oder Datentabellen-Steuerelement können Sie das Symbol für den Dateityp neben jedem Dateinamen anzeigen möchten. Sie können dazu einfach die <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit einer Datei verknüpften Symbols zu extrahieren und Anzeigen der Dateiname und das zugehörige Symbol im eine <xref:System.Windows.Forms.ListView> Steuerelement.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um das Beispiel zu kompilieren:  
  
- Fügen Sie den vorherigen Code in einem Windows Form, und rufen die `ExtractAssociatedIconExample` Methode aus dem Konstruktor des Formulars oder <xref:System.Windows.Forms.Form.Load> Ereignisbehandlungsmethode.  
  
     Sie müssen sicherstellen, dass das Formular importiert die <xref:System.IO> Namespace.  
  
## <a name="see-also"></a>Siehe auch

- [Bilder, Bitmaps und Metadateien](images-bitmaps-and-metafiles.md)
- [ListView-Steuerelement](../controls/listview-control-windows-forms.md)
