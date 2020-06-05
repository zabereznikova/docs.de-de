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
ms.openlocfilehash: af57fc7d55c5cfda24a2fd9406b17dedee898760
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400098"
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)
Der Visual Basic-Compiler kann Dokumentations Kommentare in Ihrem Code in eine XML-Datei verarbeiten. Sie können zusätzliche Tools verwenden, um die XML-Datei in die Dokumentation zu verarbeiten.  
  
 XML-Kommentare sind für Codekonstrukte zulässig, wie z. b. Typen und Typmember. Bei partiellen Typen kann nur ein Teil des Typs XML-Kommentare enthalten, obwohl es keine Einschränkung für die Kommentierung der Member gibt.  
  
> [!NOTE]
> Dokumentations Kommentare können nicht auf Namespaces angewendet werden. Der Grund hierfür ist, dass ein Namespace mehrere Assemblys umfassen kann, und nicht alle Assemblys müssen gleichzeitig geladen werden.  
  
 Der Compiler verarbeitet alle Tags, die gültige XML-Daten sind. Die folgenden Tags stellen häufig verwendete Funktionen in der Benutzerdokumentation bereit.  
  
||||  
|---|---|---|  
|[\<c>](c.md)|[\<code>](code.md)|[\<example>](example.md)|  
|[\<exception>](exception.md)<sup>1</sup>|[\<include>](include.md)<sup>1</sup>|[\<list>](list.md)|  
|[\<para>](para.md)|[\<param>](param.md)<sup>1</sup>|[\<paramref>](paramref.md)|  
|[\<permission>](permission.md)<sup>1</sup>|[\<remarks>](remarks.md)|[\<returns>](returns.md)|  
|[\<see>](see.md)<sup>1</sup>|[\<seealso>](seealso.md)<sup>1</sup>|[\<summary>](summary.md)|  
|[\<typeparam>](typeparam.md)<sup>1</sup>|[\<value>](value.md)||  
  
 (<sup>1</sup> der Compiler überprüft die Syntax.)  
  
> [!NOTE]
> Wenn spitzen Klammern im Text eines Dokumentations Kommentars angezeigt werden sollen, verwenden Sie `&lt;` und `&gt;` . Die Zeichenfolge wird z `"&lt;text in angle brackets&gt;"` . b. als angezeigt `<text in angle brackets>` .  
  
## <a name="see-also"></a>Siehe auch

- [Dokumentieren von Code mit XML](../../programming-guide/program-structure/documenting-your-code-with-xml.md)
- [-doc](../../reference/command-line-compiler/doc.md)
- [Vorgehensweise: Erstellen einer XML-Dokumentation](../../programming-guide/program-structure/how-to-create-xml-documentation.md)
