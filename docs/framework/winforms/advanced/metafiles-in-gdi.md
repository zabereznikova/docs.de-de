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
ms.openlocfilehash: 7562de76d3875e25404a6aef68355f120184b840
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627615"
---
# <a name="metafiles-in-gdi"></a>Metadateien in GDI+
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Stellt die <xref:System.Drawing.Imaging.Metafile> Klasse, sodass Sie aufzeichnen und Anzeigen von Metadateien. Eine Metadatei, auch einen Vektor Image bezeichnet, handelt es sich um ein Bild, das als eine Sequenz von Zeichnen-Befehle und Einstellungen gespeichert werden. Die Befehle und Einstellungen aufgezeichnet werden, einem <xref:System.Drawing.Imaging.Metafile> Objekt im Arbeitsspeicher gespeichert oder in einer Datei oder einem Stream gespeichert werden kann.  
  
## <a name="metafile-formats"></a>Metadatei-Formaten  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Metadateien, die in den folgenden Formaten gespeichert wurden, können angezeigt werden:  
  
-   Windows-Metadateien (WMF)  
  
-   Erweiterte Metadatei (Enhanced Metafile, EMF)  
  
-   EMF+  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] kann die Metadateien im EMF und EMF +-Format, aber nicht in der WMF-Formats aufzeichnen.  
  
 EMF + ist eine Erweiterung EMF, die ermöglicht [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Datensätze gespeichert werden. Es gibt zwei Variationen auf dem EMF +-Format: EMF + nur und duale EMF +. EMF + nur Metadateien enthalten nur [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Datensätze. Solche Metadateien angezeigt werden können, indem [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] jedoch nicht von [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]. Duale EMF +-Metadateien enthalten [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Datensätze. Jede [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Datensatz in eine duale EMF + Metadatei wird zusammen mit einer alternativen [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Datensatz. Solche Metadateien angezeigt werden können, indem [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] oder [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 Das folgende Beispiel zeigt eine Metadatei, die zuvor als Datei gespeichert wurde. Die Metadatei wird angezeigt, mit der linken oberen Ecke an (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Siehe auch
- [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
