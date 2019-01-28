---
title: '&lt;Zusammenfassung&gt; – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <summary>
- summary
helpviewer_keywords:
- <summary> C# XML tag
- summary C# XML tag
ms.assetid: b4c43d92-2067-4eac-a59a-d32f5248c08b
ms.openlocfilehash: 5447b9ea129c26fdbb9effe1a3aeac6d7290764a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54740033"
---
# <a name="ltsummarygt-c-programming-guide"></a><span data-ttu-id="a5ac3-102">&lt;Zusammenfassung&gt; (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="a5ac3-102">&lt;summary&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="a5ac3-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5ac3-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a5ac3-104">Parameter</span><span class="sxs-lookup"><span data-stu-id="a5ac3-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="a5ac3-105">Eine Übersicht des Objekts.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a5ac3-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a5ac3-106">Remarks</span></span>  
 <span data-ttu-id="a5ac3-107">Das \<summary>-Tag sollte verwendet werden, um einen Typ oder einen Typmember zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-107">The \<summary> tag should be used to describe a type or a type member.</span></span> <span data-ttu-id="a5ac3-108">Verwenden Sie [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md), um zusätzliche Informationen zu einer Typbeschreibung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-108">Use [\<remarks>](../../../csharp/programming-guide/xmldoc/remarks.md) to add supplemental information to a type description.</span></span> <span data-ttu-id="a5ac3-109">Verwenden Sie das [cref-Attribut](../../../csharp/programming-guide/xmldoc/cref-attribute.md), um Dokumentationswerkzeuge wie [Sandcastle](https://github.com/EWSoftware/SHFB) zum Erstellen von internen Links zu Dokumentationsseiten für Codeelemente zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-109">Use the [cref Attribute](../../../csharp/programming-guide/xmldoc/cref-attribute.md) to enable documentation tools such as [Sandcastle](https://github.com/EWSoftware/SHFB) to create internal hyperlinks to documentation pages for code elements.</span></span>  
  
 <span data-ttu-id="a5ac3-110">Der Text für das \<summary>-Tag ist die einzige Informationsquelle über den Typ in IntelliSense und wird auch im Fenster des Objektkatalogs angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-110">The text for the \<summary> tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser Window.</span></span>  
  
 <span data-ttu-id="a5ac3-111">Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-111">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span> <span data-ttu-id="a5ac3-112">Zum Erstellen der endgültigen Dokumentation auf Grundlage der vom Compiler generierten Datei können Sie ein benutzerdefiniertes Tool erstellen oder ein Tool wie [Sandcastle](https://github.com/EWSoftware/SHFB) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-112">To create the final documentation based on the compiler-generated file, you can create a custom tool, or use a tool such as [Sandcastle](https://github.com/EWSoftware/SHFB).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a5ac3-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5ac3-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#12](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_1.cs)]  
  
 <span data-ttu-id="a5ac3-114">Das vorherige Beispiel erzeugt folgende XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-114">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:DotNetEvents.TestClass">  
            text for class TestClass  
        </member>  
        <member name="M:DotNetEvents.TestClass.DoWork(System.Int32)">  
            <summary>DoWork is a method in the TestClass class.  
            <para>Here's how you could make a second paragraph in a description. <see cref="M:System.Console.WriteLine(System.String)"/> for information about output statements.</para>  
            <seealso cref="M:DotNetEvents.TestClass.Main"/>  
            </summary>  
        </member>  
        <member name="M:DotNetEvents.TestClass.Main">  
            text for Main  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="example"></a><span data-ttu-id="a5ac3-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a5ac3-115">Example</span></span>  
 <span data-ttu-id="a5ac3-116">Das folgende Beispiel stellt dar, wie Sie einen `cref`-Verweis auf generische Typen erstellen.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-116">The following example shows how to make a `cref` reference to a generic type.</span></span>  
  
 [!code-csharp[csProgGuideDocComments#11](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/summary_2.cs)]  
  
 <span data-ttu-id="a5ac3-117">Das vorherige Beispiel erzeugt folgende XML-Datei.</span><span class="sxs-lookup"><span data-stu-id="a5ac3-117">The previous example produces the following XML file.</span></span>  
  
```xml  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>YourNamespace</name>  
    </assembly>  
    <members>  
        <member name="T:ExtensionMethodsDemo1.A">  
            <summary cref="T:ExtensionMethodsDemo1.C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.B">  
            <summary cref="T:C`1">  
            </summary>  
        </member>  
        <member name="T:ExtensionMethodsDemo1.C`1">  
            <summary cref="T:ExtensionMethodsDemo1.A">  
            </summary>  
            <typeparam name="T"></typeparam>  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a5ac3-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5ac3-118">See also</span></span>

- [<span data-ttu-id="a5ac3-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a5ac3-119">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="a5ac3-120">Empfohlene Tags für Dokumentationskommentare</span><span class="sxs-lookup"><span data-stu-id="a5ac3-120">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
