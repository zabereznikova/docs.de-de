---
title: cref-Attribut – C#-Programmierhandbuch
description: Erfahren Sie mehr über das cref-Attribut. „cref“ bedeutet „Codereferenz“ und weist darauf hin, dass der innere Text des Tags ein Codeelement ist.
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: 31fa1a3f182d7b72a1dfbe1ce47386f87fbbff75
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381995"
---
# <a name="cref-attribute-c-programming-guide"></a><span data-ttu-id="89406-104">cref-Attribut (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="89406-104">cref attribute (C# programming guide)</span></span>

<span data-ttu-id="89406-105">Das Attribut `cref` in einem XML-Dokumentationstag bedeutet „Codeverweis“.</span><span class="sxs-lookup"><span data-stu-id="89406-105">The `cref` attribute in an XML documentation tag means "code reference."</span></span> <span data-ttu-id="89406-106">Es gibt an, dass der innere Text des Tags ein Codeelement ist, wie z.B. ein Typ, eine Methode oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="89406-106">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="89406-107">Dokumentationstools wie [DocFX](https://dotnet.github.io/docfx/) und [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden die `cref`-Attribute zum automatischen Generieren von Hyperlinks auf der Seite, auf der der Typ oder Member dokumentiert wird.</span><span class="sxs-lookup"><span data-stu-id="89406-107">Documentation tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) use the `cref` attributes to automatically generate hyperlinks to the page where the type or member is documented.</span></span>

## <a name="example"></a><span data-ttu-id="89406-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="89406-108">Example</span></span>

<span data-ttu-id="89406-109">Das folgende Beispiel zeigt Attribute `cref`, die in [\<see>](./see.md)-Tags verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="89406-109">The following example shows `cref` attributes used in [\<see>](./see.md) tags.</span></span>

[!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]

<span data-ttu-id="89406-110">Beim Kompilieren erzeugt das Programm die folgende XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="89406-110">When compiled, the program produces the following XML file.</span></span> <span data-ttu-id="89406-111">Beachten Sie, dass z.B. das Attribut `cref` für die `GetZero`-Methode vom Compiler in `"M:TestNamespace.TestClass.GetZero"` umgewandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="89406-111">Notice that the `cref` attribute for the `GetZero` method, for example, has been transformed by the compiler to `"M:TestNamespace.TestClass.GetZero"`.</span></span> <span data-ttu-id="89406-112">Das Präfix „M:“ steht für „Methode“ und ist eine Konvention, die von Dokumentationstools wie DocFX und Sandcastle erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="89406-112">The "M:" prefix means "method" and is a convention that is recognized by documentation tools such as DocFX and Sandcastle.</span></span> <span data-ttu-id="89406-113">Eine vollständige Liste der Präfixe finden Sie unter [Verarbeiten der XML-Datei](./processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="89406-113">For a complete list of prefixes, see [Processing the XML File](./processing-the-xml-file.md).</span></span>

```xml  
<?xml version="1.0"?>
<doc>
    <assembly>
        <name>CRefTest</name>
    </assembly>
    <members>
        <member name="T:TestNamespace.TestClass">
            <summary>
            TestClass contains several cref examples.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor">
            <summary>
            This sample shows how to specify the <see cref="T:TestNamespace.TestClass"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.#ctor(System.Int32)">
            <summary>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.#ctor(System.Int32)"/> constructor as a cref attribute.
            </summary>
        </member>
        <member name="M:TestNamespace.TestClass.GetZero">
            <summary>
            The GetZero method.
            </summary>
            <example>
            This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.
            <code>
            class TestClass
            {
                static int Main()
                {
                    return GetZero();
                }
            }
            </code>
            </example>
        </member>
        <member name="M:TestNamespace.TestClass.GetGenericValue``1(``0)">
            <summary>
            The GetGenericValue method.
            </summary>
            <remarks>
            This sample shows how to specify the <see cref="M:TestNamespace.TestClass.GetGenericValue``1(``0)"/> method as a cref attribute.
            </remarks>
        </member>
        <member name="T:TestNamespace.GenericClass`1">
            <summary>
            GenericClass.
            </summary>
            <remarks>
            This example shows how to specify the <see cref="T:TestNamespace.GenericClass`1"/> type as a cref attribute.
            </remarks>
        </member>
    </members>
</doc>
```

## <a name="see-also"></a><span data-ttu-id="89406-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="89406-114">See also</span></span>

- [<span data-ttu-id="89406-115">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="89406-115">XML documentation comments</span></span>](./index.md)
- [<span data-ttu-id="89406-116">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="89406-116">Recommended tags for documentation comments</span></span>](./recommended-tags-for-documentation-comments.md)
