---
title: "Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic) | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.XmlDocComment
dev_langs:
- VB
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: 14
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: c6a47c12bc24864ef6ac9f80054becad98ec97f1
ms.lasthandoff: 03/13/2017

---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)
Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler Dokumentationskommentare im Code, um eine XML-Datei verarbeiten kann. Zusätzliche Tools können Sie um die XML-Datei in der Dokumentation zu verarbeiten.  
  
 XML-Kommentare dürfen für Codekonstrukte wie Typen und Typmember. Für partielle Typen kann nur ein Teil des Typs XML-Kommentare haben, obwohl es keine Einschränkung besteht hinsichtlich seiner Member kommentieren.  
  
> [!NOTE]
>  Dokumentationskommentare können nicht auf Namespaces angewendet werden. Der Grund ist, dass ein Namespace kann mehrere Assemblys umfassen, und nicht alle Assemblys gleichzeitig geladen werden.  
  
 Der Compiler verarbeitet jedes Tag, das gültiges XML darstellt. Die folgenden Tags bieten häufig verwendete Funktionen in der Dokumentation für die Benutzer.  
  
||||  
|---|---|---|  
|[\<c >](../../../visual-basic/language-reference/xmldoc/c.md)|[\<Code >](../../../visual-basic/language-reference/xmldoc/code.md)|[\<Beispiel >](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<Ausnahme >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<umfassen >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<Para >](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param>](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<Paramref >](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<Berechtigung >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<Hinweise >](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<Gibt >](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<see>](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<Seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<Zusammenfassung >](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<Typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<Wert >](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> der Compiler überprüft Syntax.)  
  
> [!NOTE]
>  Wenn spitze Klammern im Text eines angezeigt werden soll, verwenden Sie `<` und `>`. Z. B. die Zeichenfolge `"<text in angle brackets>"` erscheint als `<text in angle``brackets>`.  
  
## <a name="see-also"></a>Siehe auch  
 [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)   
 [/ doc](../../../visual-basic/reference/command-line-compiler/doc.md)   
 [Gewusst wie: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
