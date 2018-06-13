---
title: 'Gewusst wie: Erstellen einer XML-Dokumentation in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 7fb56da8a28367a6dcd5e28f208b4519510d7d95
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33650880"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a>Gewusst wie: Erstellen einer XML-Dokumentation in Visual Basic
Dieses Beispiel zeigt, wie Sie XML-Dokumentationskommentare in den Code einfügen.  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a>Zum Erstellen von XML-Dokumentation für einen Typ oder member  
  
1.  In der **Code-Editor**, positionieren Sie den Cursor in der Zeile oben den Typ oder Member, für die Sie Dokumentation erstellen möchten.  
  
2.  Typ `'''` (drei einfache Anführungszeichen).  
  
     Ein XML-Skelett für den Typ oder Member wird hinzugefügt, der **Code-Editor**.  
  
3.  Fügen Sie beschreibende Informationen zwischen den entsprechenden Tags hinzu.  
  
    > [!NOTE]
    >  Wenn Sie zusätzliche Zeilen innerhalb der XML-Dokumentation Block hinzufügen, muss jede Zeile mit beginnen `'''`.  
  
4.  Fügen Sie zusätzlichen Code, der den Typ oder Member mit dem neuen XML-Dokumentationskommentare verwendet.  
  
     IntelliSense zeigt den Text aus dem \<summary >-Tag für den Typ oder Member.  
  
5.  Kompilieren Sie den Code zum Generieren einer XML-Datei, die die Dokumentationskommentare enthält. Weitere Informationen finden Sie unter [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [XML-Kommentartags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)
