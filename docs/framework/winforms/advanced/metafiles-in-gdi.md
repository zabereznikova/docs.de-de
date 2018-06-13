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
ms.openlocfilehash: 73cacb7f701768b42121c31cfbc4f26905961231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525092"
---
# <a name="metafiles-in-gdi"></a>Metadateien in GDI+
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Stellt die <xref:System.Drawing.Imaging.Metafile> Klasse, damit Sie aufzeichnen und Anzeigen von Metadateien. Eine Metadatei, die so genannte ein Vektor-Image ist ein Bild, das als eine Sequenz von Zeichnen-Befehle und Einstellungen gespeichert werden. Die Befehle und Einstellungen aufgezeichnet werden, einem <xref:System.Drawing.Imaging.Metafile> Objekt im Arbeitsspeicher gespeichert oder in eine Datei oder den Stream gespeichert werden kann.  
  
## <a name="metafile-formats"></a>Metadatei-Formate  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Metadateien, die in den folgenden Formaten gespeichert wurden, können angezeigt werden:  
  
-   Windows-Metadatei (WMF)  
  
-   Erweiterte Metadatei (Enhanced Metafile, EMF)  
  
-   EMF +  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] kann Metadateien in den Formaten EMF und EMF +, jedoch nicht in der WMF-Format aufzeichnen.  
  
 EMF + ist eine Erweiterung, EMF, der ermöglicht [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Datensätze gespeichert werden. Es gibt zwei Variationen auf dem EMF-Format: EMF + Only und EMF + Dual. EMF + nur Metadateien enthalten nur [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Datensätze. Solche Metadateien können angezeigt werden, indem [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] jedoch nicht von [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]. EMF + Dual Metadateien enthalten [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] und [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Datensätze. Jede [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] Datensatz in einer EMF + Dual Metadatei wird zusammen mit einer alternativen [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] Datensatz. Solche Metadateien können angezeigt werden, indem [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] oder [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 Das folgende Beispiel zeigt eine Metadatei, die zuvor als Datei gespeichert wurde. Die Metadatei wird angezeigt, mit der linken oberen Ecke an (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Siehe auch  
 [Bilder, Bitmaps und Metadateien](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
