---
title: XML-Dokumentationskommentare (C#-Programmierhandbuch)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: cs.xml
helpviewer_keywords:
- XML [C#], code comments
- comments [C#], XML
- documentation comments [C#]
- C# source code files
- C# language, XML code comments
- XML documentation comments [C#]
ms.assetid: 803b7f7b-7428-4725-b5db-9a6cff273199
caps.latest.revision: "26"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e7f88a85dd493836a17a80310ab4bce8ebf47c23
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="02b3c-102">XML-Dokumentationskommentare (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="02b3c-102">XML Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="02b3c-103">In Visual C# lässt sich eine Dokumentation des Codes erstellen. Dazu werden XML-Elemente in spezielle Kommentarfelder (angegeben durch drei Schrägstriche) des Quellcodes unmittelbar vor dem Codeblock eingefügt, auf den sie sich beziehen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="02b3c-103">In Visual C# you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example:</span></span>  
  
```  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass{}  
```  
  
 <span data-ttu-id="02b3c-104">Wenn Sie mit der Option [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompilieren, sucht der Compiler alle XML-Tags im Quellcode und erstellt eine XML-Dokumentationsdatei.</span><span class="sxs-lookup"><span data-stu-id="02b3c-104">When you compile with the [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="02b3c-105">Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="02b3c-105">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="02b3c-106">Zum Verweisen auf XML-Elemente (beispielsweise verarbeitet eine Funktion bestimmte XML-Elemente, die Sie in einem XML-Dokumentationskommentar beschreiben möchten) können Sie die Standardnotierungsart verwenden (`<` und `>`).</span><span class="sxs-lookup"><span data-stu-id="02b3c-106">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="02b3c-107">Zum Verweisen auf generische Bezeichner in Codeverweiselementen (`cref`-Elementen) können Sie entweder die Escapezeichen (z.B. `cref="List<T>"`) oder geschweifte Klammern (`cref="List{T}"`) verwenden.</span><span class="sxs-lookup"><span data-stu-id="02b3c-107">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List<T>"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="02b3c-108">Als Sonderfall analysiert der Compiler die geschweiften Klammern als spitze Klammern, um das Erstellen des Dokumentationskommentars beim Verweisen auf generische Bezeichner weniger schwerfällig zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="02b3c-108">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02b3c-109">XML-Dokumentationskommentare sind keine Metadaten und sind nicht in der kompilierten Assembly enthalten. Folglich ist der Zugriff auf sie über Reflektion nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="02b3c-109">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="02b3c-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="02b3c-110">In This Section</span></span>  
  
-   [<span data-ttu-id="02b3c-111">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="02b3c-111">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="02b3c-112">Verarbeiten der XML-Datei</span><span class="sxs-lookup"><span data-stu-id="02b3c-112">Processing the XML File</span></span>](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="02b3c-113">Trennzeichen für Dokumentationstags</span><span class="sxs-lookup"><span data-stu-id="02b3c-113">Delimiters for Documentation Tags</span></span>](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [<span data-ttu-id="02b3c-114">Gewusst wie: Verwenden der XML-Dokumentationsfunktionen</span><span class="sxs-lookup"><span data-stu-id="02b3c-114">How to: Use the XML Documentation Features</span></span>](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a><span data-ttu-id="02b3c-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="02b3c-115">Related Sections</span></span>  
 <span data-ttu-id="02b3c-116">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="02b3c-116">For more information, see:</span></span>  
  
-   [<span data-ttu-id="02b3c-117">/doc (Verarbeiten von Dokumentationskommentaren)</span><span class="sxs-lookup"><span data-stu-id="02b3c-117">/doc (Process Documentation Comments)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="02b3c-118">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="02b3c-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="02b3c-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="02b3c-119">See Also</span></span>  
 [<span data-ttu-id="02b3c-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="02b3c-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
