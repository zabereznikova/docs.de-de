---
title: Empfohlene Tags für Dokumentationskommentare – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- XML [C#], tags
- XML documentation [C#], tags
ms.assetid: 6e98f7a9-38f4-4d74-b644-1ff1b23320fd
ms.openlocfilehash: 07594d70b92e2075c3d5aba605eab23d766faed6
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052747"
---
# <a name="recommended-tags-for-documentation-comments-c-programming-guide"></a>Empfohlene Tags für Dokumentationskommentare (C#-Programmierhandbuch)
Der C#-Compiler verarbeitet Dokumentationskommentare in Ihrem Code und formatiert diese als XML in einer Datei, deren Namen Sie in der Befehlszeilenoption **/doc** angeben. Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie z. B. [DocFX](https://dotnet.github.io/docfx/) oder [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.  
  
 Tags werden auf der Basis von Codekonstrukten wie Typen und Typmembern verarbeitet.  
  
> [!NOTE]
>  Dokumentationskommentare können nicht auf einen Namespace angewendet werden.  
  
 Der Compiler verarbeitet alle Tags, die gültige XML sind. Die folgenden Tags stellen allgemein verwendete Funktionen in der Benutzerdokumentation bereit.  
  
## <a name="tags"></a>Tags  
  
||||  
|---|---|---|  
|[\<c>](../../../csharp/programming-guide/xmldoc/code-inline.md)|[\<para>](../../../csharp/programming-guide/xmldoc/para.md)|[\<see>](../../../csharp/programming-guide/xmldoc/see.md)*|  
|[\<code>](../../../csharp/programming-guide/xmldoc/code.md)|[\<param>](../../../csharp/programming-guide/xmldoc/param.md)*|[\<seealso>](../../../csharp/programming-guide/xmldoc/seealso.md)*|  
|[\<example>](../../../csharp/programming-guide/xmldoc/example.md)|[\<paramref>](../../../csharp/programming-guide/xmldoc/paramref.md)|[\<summary>](../../../csharp/programming-guide/xmldoc/summary.md)|  
|[\<exception>](../../../csharp/programming-guide/xmldoc/exception.md)*|[\<permission>](../../../csharp/programming-guide/xmldoc/permission.md)*|[\<typeparam>](../../../csharp/programming-guide/xmldoc/typeparam.md)*|  
|[\<include>](../../../csharp/programming-guide/xmldoc/include.md)*|[\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md)|[\<typeparamref>](../../../csharp/programming-guide/xmldoc/typeparamref.md)|  
|[\<list>](../../../csharp/programming-guide/xmldoc/list.md)|[\<returns>](../../../csharp/programming-guide/xmldoc/returns.md)|[\<value>](../../../csharp/programming-guide/xmldoc/value.md)|  
  
 (* gibt an, dass der Compiler die Syntax überprüft.)  
  
 Wenn Sie möchten, dass im Text eines Dokumentationskommentars spitze Klammern erscheinen, verwenden Sie die HTML-Codierung für `<` und `>`: `&lt;` bzw. `&gt;`. Diese Codierung wird im folgenden Beispiel gezeigt:
  
```csharp  
/// <summary>
/// This property always returns a value &lt; 1.
/// </summary>
```
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [/doc (C#-Compileroptionen)](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)
- [XML-Dokumentationskommentare](../../../csharp/programming-guide/xmldoc/index.md)
