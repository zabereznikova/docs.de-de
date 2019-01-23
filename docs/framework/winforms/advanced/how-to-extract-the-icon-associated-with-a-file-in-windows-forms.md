---
title: 'Vorgehensweise: Extrahieren Sie das Symbol für den eine Datei in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: f961345c4b9be43e73a8c7a11914cf82833a822f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54559020"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a>Vorgehensweise: Extrahieren Sie das Symbol für den eine Datei in Windows Forms
Viele Dateien verfügen über eingebettete Symbole, die eine visuelle Darstellung des zugeordneten Dateityps bereitstellen. Microsoft Word-Dokumente enthalten z. B. ein Symbol, das sie als Word-Dokumenten identifiziert. Zum Anzeigen von Dateien in einem Listensteuerelement oder Datentabellen-Steuerelement können Sie das Symbol für den Dateityp neben jedem Dateinamen anzeigen möchten. Sie können dazu einfach die <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> Methode.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie mit einer Datei verknüpften Symbols zu extrahieren und Anzeigen der Dateiname und das zugehörige Symbol im eine <xref:System.Windows.Forms.ListView> Steuerelement.  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Um das Beispiel zu kompilieren:  
  
-   Fügen Sie den vorherigen Code in einem Windows Form, und rufen die `ExtractAssociatedIconExample` Methode aus dem Konstruktor des Formulars oder <xref:System.Windows.Forms.Form.Load> Ereignisbehandlungsmethode.  
  
     Sie müssen sicherstellen, dass das Formular importiert die <xref:System.IO> Namespace.  
  
## <a name="see-also"></a>Siehe auch
- [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
- [ListView-Steuerelement](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
