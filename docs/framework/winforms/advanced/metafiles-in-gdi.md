---
title: Metadateien in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504588"
---
# <a name="metafiles-in-gdi"></a>Metadateien in GDI+
GDI + bietet die <xref:System.Drawing.Imaging.Metafile> Klasse, sodass Sie aufzeichnen und Anzeigen von Metadateien. Eine Metadatei, auch einen Vektor Image bezeichnet, handelt es sich um ein Bild, das als eine Sequenz von Zeichnen-Befehle und Einstellungen gespeichert werden. Die Befehle und Einstellungen aufgezeichnet werden, einem <xref:System.Drawing.Imaging.Metafile> Objekt im Arbeitsspeicher gespeichert oder in einer Datei oder einem Stream gespeichert werden kann.  
  
## <a name="metafile-formats"></a>Metadatei-Formaten  
 GDI + kann Metadateien anzeigen, die in den folgenden Formaten gespeichert wurden:  
  
- Windows-Metadateien (WMF)  
  
- Erweiterte Metadatei (Enhanced Metafile, EMF)  
  
- EMF+  
  
 GDI + kann Metadateien im EMF und EMF +-Format, aber nicht in der WMF-Formats aufzeichnen.  
  
 EMF + ist eine Erweiterung, EMF, die von GDI +-Datensätze gespeichert werden kann. Es gibt zwei Variationen auf dem EMF +-Format: EMF + nur und duale EMF +. EMF + nur Metadateien enthalten nur um GDI +-Datensätze. Solche Metadateien können von GDI +, aber nicht von GDI angezeigt werden. Duale EMF +-Metadateien enthalten GDI + und GDI-Datensätze. Eine alternative GDI-Datensatz ist jeder GDI +-Datensatz in eine duale EMF +-Metadatei zugeordnet. Solche Metadateien können von GDI oder GDI angezeigt werden.  
  
 Das folgende Beispiel zeigt eine Metadatei, die zuvor als Datei gespeichert wurde. Die Metadatei wird angezeigt, mit der linken oberen Ecke an (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Siehe auch

- [Bilder, Bitmaps und Metadateien](images-bitmaps-and-metafiles.md)
