---
title: Empfohlene XML-Tags für Dokumentations Kommentare
ms.date: 07/20/2015
f1_keywords:
- vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
ms.openlocfilehash: 093c967557b899c8661fdec348d421996e948b94
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352335"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)
Der Visual Basic-Compiler kann Dokumentations Kommentare in Ihrem Code in eine XML-Datei verarbeiten. Sie können zusätzliche Tools verwenden, um die XML-Datei in die Dokumentation zu verarbeiten.  
  
 XML-Kommentare sind für Codekonstrukte zulässig, wie z. b. Typen und Typmember. Bei partiellen Typen kann nur ein Teil des Typs XML-Kommentare enthalten, obwohl es keine Einschränkung für die Kommentierung der Member gibt.  
  
> [!NOTE]
> Dokumentations Kommentare können nicht auf Namespaces angewendet werden. Der Grund hierfür ist, dass ein Namespace mehrere Assemblys umfassen kann, und nicht alle Assemblys müssen gleichzeitig geladen werden.  
  
 Der Compiler verarbeitet alle Tags, die gültige XML-Daten sind. Die folgenden Tags stellen häufig verwendete Funktionen in der Benutzerdokumentation bereit.  
  
||||  
|---|---|---|  
|[\<c>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<Ausnahme >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<>](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup> einschließen.|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<Berechtigung >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<siehe >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<seeauch >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> der Compiler überprüft die Syntax.)  
  
> [!NOTE]
> Wenn Sie möchten, dass im Text eines Dokumentations Kommentars spitzen Klammern angezeigt werden, verwenden Sie `&lt;` und `&gt;`. Beispielsweise wird die Zeichenfolge `"&lt;text in angle brackets&gt;"` als `<text in angle brackets>`angezeigt.  
  
## <a name="see-also"></a>Siehe auch

- [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [-doc](../../../visual-basic/reference/command-line-compiler/doc.md)
- [Gewusst wie: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
