---
title: cref-Attribut – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- cref [C#]
ms.assetid: 66a6b0e5-b961-4504-a461-3a4cf481fc8b
ms.openlocfilehash: d088e1fcd0a1d1910b1284909dccf7b7d7b1d479
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/19/2019
ms.locfileid: "69588170"
---
# <a name="cref-attribute-c-programming-guide"></a><span data-ttu-id="8188b-102">cref-Attribut (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="8188b-102">cref Attribute (C# Programming Guide)</span></span>
<span data-ttu-id="8188b-103">Das Attribut `cref` in einem XML-Dokumentationstag bedeutet „Codeverweis“.</span><span class="sxs-lookup"><span data-stu-id="8188b-103">The `cref` attribute in an XML documentation tag means "code reference."</span></span> <span data-ttu-id="8188b-104">Es gibt an, dass der innere Text des Tags ein Codeelement ist, wie z.B. ein Typ, eine Methode oder Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8188b-104">It specifies that the inner text of the tag is a code element, such as a type, method, or property.</span></span> <span data-ttu-id="8188b-105">Dokumentationstools wie [DocFX](https://dotnet.github.io/docfx/) und [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden die `cref`-Attribute zum automatischen Generieren von Hyperlinks auf der Seite, auf der der Typ oder Member dokumentiert wird.</span><span class="sxs-lookup"><span data-stu-id="8188b-105">Documentation tools like [DocFX](https://dotnet.github.io/docfx/) and [Sandcastle](https://github.com/EWSoftware/SHFB) use the `cref` attributes to automatically generate hyperlinks to the page where the type or member is documented.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8188b-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8188b-106">Example</span></span>  
 <span data-ttu-id="8188b-107">Das folgende Beispiel zeigt die Attribute `cref`, die in [\<see>](./see.md)-Tags verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8188b-107">The following example shows `cref` attributes used in [\<see>](./see.md) tags.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#3)]  
  
 <span data-ttu-id="8188b-108">Beim Kompilieren erzeugt das Programm die folgende XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="8188b-108">When compiled, the program produces the following XML file.</span></span> <span data-ttu-id="8188b-109">Beachten Sie, dass z.B. das Attribut `cref` für die `GetZero`-Methode vom Compiler in `"M:TestNamespace.TestClass.GetZero"` umgewandelt wurde.</span><span class="sxs-lookup"><span data-stu-id="8188b-109">Notice that the `cref` attribute for the `GetZero` method, for example, has been transformed by the compiler to `"M:TestNamespace.TestClass.GetZero"`.</span></span> <span data-ttu-id="8188b-110">Das Präfix „M:“ steht für „Methode“ und ist eine Konvention, die von Dokumentationstools wie DocFX und Sandcastle erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="8188b-110">The "M:" prefix means "method" and is a convention that is recognized by documentation tools such as DocFX and Sandcastle.</span></span> <span data-ttu-id="8188b-111">Eine vollständige Liste der Präfixe finden Sie unter [Verarbeiten der XML-Datei](./processing-the-xml-file.md).</span><span class="sxs-lookup"><span data-stu-id="8188b-111">For a complete list of prefixes, see [Processing the XML File](./processing-the-xml-file.md).</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>CRefTest</name>  
    </assembly>  
    <members>  
        <member name="T:TestNamespace.TestClass">  
            <summary>  
            TestClass contains cref examples.  
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
    </members>    <members>  
        <member name="T:TestNamespace.TestClass">  
            <summary>  
            TestClass contains two cref examples.  
            </summary>  
        </member>  
        <member name="M:TestNamespace.TestClass.GetZero">  
            <summary>  
            The GetZero method.  
            </summary>  
            <example> This sample shows how to call the <see cref="M:TestNamespace.TestClass.GetZero"/> method.  
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
  
## <a name="see-also"></a><span data-ttu-id="8188b-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8188b-112">See also</span></span>

- [<span data-ttu-id="8188b-113">XML-Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="8188b-113">XML Documentation Comments</span></span>](./index.md)
- [<span data-ttu-id="8188b-114">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="8188b-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
