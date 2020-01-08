---
title: XML-Dokumentationskommentare – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
ms.openlocfilehash: 08357017a29f05c11e316e037497b1ee24d06eff
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634975"
---
# <a name="xml-documentation-comments-c-programming-guide"></a>XML-Dokumentationskommentare (C#-Programmierhandbuch)
In Visual C# lässt sich eine Dokumentation des Codes erstellen. Dazu werden XML-Elemente in spezielle Kommentarfelder (angegeben durch drei Schrägstriche) des Quellcodes unmittelbar vor dem Codeblock eingefügt, auf den sie sich beziehen, z. B.:  
  
```csharp  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 Wenn Sie mit der Option [-doc](../../language-reference/compiler-options/doc-compiler-option.md) kompilieren, sucht der Compiler alle XML-Tags im Quellcode und erstellt eine XML-Dokumentationsdatei. Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie z. B. [DocFX](https://dotnet.github.io/docfx/) oder [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.  
  
 Zum Verweisen auf XML-Elemente (beispielsweise verarbeitet eine Funktion bestimmte XML-Elemente, die Sie in einem XML-Dokumentationskommentar beschreiben möchten) können Sie die Standardnotierungsart verwenden (`<` und `>`).  Zum Verweisen auf generische Bezeichner in Codeverweiselementen (`cref`-Elementen) können Sie entweder die Escapezeichen (z.B. `cref="List&lt;T&gt;"`) oder geschweifte Klammern (`cref="List{T}"`) verwenden.  Als Sonderfall analysiert der Compiler die geschweiften Klammern als spitze Klammern, um das Erstellen des Dokumentationskommentars beim Verweisen auf generische Bezeichner weniger schwerfällig zu gestalten.  
  
> [!NOTE]
> XML-Dokumentationskommentare sind keine Metadaten und sind nicht in der kompilierten Assembly enthalten. Folglich ist der Zugriff auf sie über Reflektion nicht möglich.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
  
- [Empfohlene Tags für Dokumentationskommentare](./recommended-tags-for-documentation-comments.md)  
  
- [Verarbeiten der XML-Datei](./processing-the-xml-file.md)  
  
- [Trennzeichen für Dokumentationstags](./delimiters-for-documentation-tags.md)  
  
- [Verwenden der XML-Dokumentationsfeatures](./how-to-use-the-xml-documentation-features.md)
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 Weitere Informationen finden Sie unter:  
  
- [-doc (Verarbeiten von Dokumentationskommentaren)](../../language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a>C#-Programmiersprachenspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../index.md)
