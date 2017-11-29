---
title: "Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlDocComment
helpviewer_keywords:
- tags, XML
- XML comments, recommended tags [Visual Basic]
- comments, recommended XML tags
ms.assetid: 294e0736-ff1e-498e-af83-6db71ed41a72
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 54712deb8bb2a5ed1e7b1f5fb8aa073dcdaf76d6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="recommended-xml-tags-for-documentation-comments-visual-basic"></a>Empfohlene XML-Tags für Dokumentationskommentare (Visual Basic)
Die [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Compiler Dokumentationskommentare in Ihrem Code in eine XML-Datei verarbeiten kann. Sie können zusätzliche Tools verwenden, zum Verarbeiten der XML-Datei in der Dokumentation.  
  
 XML-Kommentare dürfen auf Codekonstrukte wie Typen und Typmember. Für partielle Typen kann nur ein Teil des Typs XML-Kommentare, haben, obwohl es keine Einschränkung gibt für die Kommentierung von Membern.  
  
> [!NOTE]
>  Dokumentationskommentare können nicht auf Namespaces angewendet werden. Der Grund ist, dass ein Namespace mehrere Assemblys umfassen kann und nicht alle Assemblys gleichzeitig geladen werden soll.  
  
 Der Compiler verarbeitet alle Tags, die XML-Daten gültig sind. Die folgenden Tags stellen häufig verwendete Funktionen in der Dokumentation für die Benutzer bereit.  
  
||||  
|---|---|---|  
|[\<c>](../../../visual-basic/language-reference/xmldoc/c.md)|[\<code>](../../../visual-basic/language-reference/xmldoc/code.md)|[\<example>](../../../visual-basic/language-reference/xmldoc/example.md)|  
|[\<Ausnahme >](../../../visual-basic/language-reference/xmldoc/exception.md) <sup>1</sup>|[\<umfassen >](../../../visual-basic/language-reference/xmldoc/include.md) <sup>1</sup>|[\<list>](../../../visual-basic/language-reference/xmldoc/list.md)|  
|[\<para>](../../../visual-basic/language-reference/xmldoc/para.md)|[\<Param >](../../../visual-basic/language-reference/xmldoc/param.md) <sup>1</sup>|[\<paramref>](../../../visual-basic/language-reference/xmldoc/paramref.md)|  
|[\<Berechtigung >](../../../visual-basic/language-reference/xmldoc/permission.md) <sup>1</sup>|[\<remarks>](../../../visual-basic/language-reference/xmldoc/remarks.md)|[\<returns>](../../../visual-basic/language-reference/xmldoc/returns.md)|  
|[\<finden Sie unter >](../../../visual-basic/language-reference/xmldoc/see.md) <sup>1</sup>|[\<Seealso >](../../../visual-basic/language-reference/xmldoc/seealso.md) <sup>1</sup>|[\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md)|  
|[\<Typeparam >](../../../visual-basic/language-reference/xmldoc/typeparam.md) <sup>1</sup>|[\<value>](../../../visual-basic/language-reference/xmldoc/value.md)||  
  
 (<sup>1</sup> der Compiler überprüft die Syntax.)  
  
> [!NOTE]
>  Wenn Sie spitze Klammern, um im Text des kein Dokumentationskommentar angezeigt werden soll, verwenden `<` und `>`. Z. B. die Zeichenfolge `"<text in angle brackets>"` hostnamensadresse `<text in angle``brackets>`.  
  
## <a name="see-also"></a>Siehe auch  
 [Dokumentieren von Code mit XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)  
 [Gewusst wie: Erstellen einer XML-Dokumentation](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)
