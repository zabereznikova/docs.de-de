---
title: XML-Dokumentationskommentare (C#-Programmierhandbuch)
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
ms.openlocfilehash: 4a8b6395209e95f3156354c4ee919291e05c7471
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2018
ms.locfileid: "42998423"
---
# <a name="xml-documentation-comments-c-programming-guide"></a><span data-ttu-id="dd149-102">XML-Dokumentationskommentare (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="dd149-102">XML Documentation Comments (C# Programming Guide)</span></span>
<span data-ttu-id="dd149-103">In Visual C# lässt sich eine Dokumentation des Codes erstellen. Dazu werden XML-Elemente in spezielle Kommentarfelder (angegeben durch drei Schrägstriche) des Quellcodes unmittelbar vor dem Codeblock eingefügt, auf den sie sich beziehen, z. B.:</span><span class="sxs-lookup"><span data-stu-id="dd149-103">In Visual C# you can create documentation for your code by including XML elements in special comment fields (indicated by triple slashes) in the source code directly before the code block to which the comments refer, for example:</span></span>  
  
```  
/// <summary>  
///  This class performs an important function.  
/// </summary>  
public class MyClass {}  
```  
  
 <span data-ttu-id="dd149-104">Wenn Sie mit der Option [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompilieren, sucht der Compiler alle XML-Tags im Quellcode und erstellt eine XML-Dokumentationsdatei.</span><span class="sxs-lookup"><span data-stu-id="dd149-104">When you compile with the [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) option, the compiler will search for all XML tags in the source code and create an XML documentation file.</span></span> <span data-ttu-id="dd149-105">Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd149-105">To create the final documentation based on the compiler-generated file, you can create a custom tool or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
 <span data-ttu-id="dd149-106">Zum Verweisen auf XML-Elemente (beispielsweise verarbeitet eine Funktion bestimmte XML-Elemente, die Sie in einem XML-Dokumentationskommentar beschreiben möchten) können Sie die Standardnotierungsart verwenden (`<` und `>`).</span><span class="sxs-lookup"><span data-stu-id="dd149-106">To refer to XML elements (for example, your function processes specific XML elements that you want to describe in an XML documentation comment), you can use the standard quoting mechanism (`<` and `>`).</span></span>  <span data-ttu-id="dd149-107">Zum Verweisen auf generische Bezeichner in Codeverweiselementen (`cref`-Elementen) können Sie entweder die Escapezeichen (z.B. `cref="List&lt;T&gt;"`) oder geschweifte Klammern (`cref="List{T}"`) verwenden.</span><span class="sxs-lookup"><span data-stu-id="dd149-107">To refer to generic identifiers in code reference (`cref`) elements, you can use either the escape characters (for example, `cref="List&lt;T&gt;"`) or braces (`cref="List{T}"`).</span></span>  <span data-ttu-id="dd149-108">Als Sonderfall analysiert der Compiler die geschweiften Klammern als spitze Klammern, um das Erstellen des Dokumentationskommentars beim Verweisen auf generische Bezeichner weniger schwerfällig zu gestalten.</span><span class="sxs-lookup"><span data-stu-id="dd149-108">As a special case, the compiler parses the braces as angle brackets to make the documentation comment less cumbersome to author when referring to generic identifiers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd149-109">XML-Dokumentationskommentare sind keine Metadaten und sind nicht in der kompilierten Assembly enthalten. Folglich ist der Zugriff auf sie über Reflektion nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="dd149-109">The XML documentation comments are not metadata; they are not included in the compiled assembly and therefore they are not accessible through reflection.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd149-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="dd149-110">In This Section</span></span>  
  
-   [<span data-ttu-id="dd149-111">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="dd149-111">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="dd149-112">Verarbeiten der XML-Datei</span><span class="sxs-lookup"><span data-stu-id="dd149-112">Processing the XML File</span></span>](../../../csharp/programming-guide/xmldoc/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="dd149-113">Trennzeichen für Dokumentationstags</span><span class="sxs-lookup"><span data-stu-id="dd149-113">Delimiters for Documentation Tags</span></span>](../../../csharp/programming-guide/xmldoc/delimiters-for-documentation-tags.md)  
  
-   [<span data-ttu-id="dd149-114">Gewusst wie: Verwenden der XML-Dokumentationsfunktionen</span><span class="sxs-lookup"><span data-stu-id="dd149-114">How to: Use the XML Documentation Features</span></span>](../../../csharp/programming-guide/xmldoc/how-to-use-the-xml-documentation-features.md)  
  
## <a name="related-sections"></a><span data-ttu-id="dd149-115">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="dd149-115">Related Sections</span></span>  
 <span data-ttu-id="dd149-116">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="dd149-116">For more information, see:</span></span>  
  
-   [<span data-ttu-id="dd149-117">/doc (Verarbeiten von Dokumentationskommentaren)</span><span class="sxs-lookup"><span data-stu-id="dd149-117">/doc (Process Documentation Comments)</span></span>](../../../csharp/language-reference/compiler-options/doc-compiler-option.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="dd149-118">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="dd149-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="dd149-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd149-119">See Also</span></span>  
 [<span data-ttu-id="dd149-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="dd149-120">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
