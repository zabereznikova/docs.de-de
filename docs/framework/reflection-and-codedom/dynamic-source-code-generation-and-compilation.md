---
title: Generieren und Kompilieren von dynamischem Quellcode
ms.date: 03/30/2017
helpviewer_keywords:
- Code Document Object Model
- System.CodeDom namespace
- language-independent source code modeling
- CodeDOM
- multiple languages supported by CodeDOM
- source code in multiple languages
- languages, multiple language support by CodeDOM
ms.assetid: d077a3e8-bd81-4bdf-b6a3-323857ea30fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5fb95ab7ff4fcac7169238d90637d7b83078d6dd
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046108"
---
# <a name="dynamic-source-code-generation-and-compilation"></a><span data-ttu-id="aa4f4-102">Generieren und Kompilieren von dynamischem Quellcode</span><span class="sxs-lookup"><span data-stu-id="aa4f4-102">Dynamic Source Code Generation and Compilation</span></span>
<span data-ttu-id="aa4f4-103">Das .NET Framework enthält einen Mechanismus, der „Code Document Object Model“ (CodeDOM) genannt wird, und mit dem Programmentwickler, die Quellcode ausgeben, Quellcode in mehreren Programmiersprachen zur Runtime generieren können und das alles auf Grundlage eines einzigen Modells, das den zu rendernden Code darstellt.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-103">The .NET Framework includes a mechanism called the Code Document Object Model (CodeDOM) that enables developers of programs that emit source code to generate source code in multiple programming languages at run time, based on a single model that represents the code to render.</span></span>  
  
 <span data-ttu-id="aa4f4-104">Um den Quellcode darzustellen, werden CodeDOM-Elemente miteinander verknüpft, damit sie eine Datenstruktur bilden, die als CodeDOM-Diagramm bekannt ist, der die Struktur von Quellcode modelliert.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-104">To represent source code, CodeDOM elements are linked to each other to form a data structure known as a CodeDOM graph, which models the structure of some source code.</span></span>  
  
 <span data-ttu-id="aa4f4-105">Der `System.CodeDom`-Namespace definiert Typen, die die logische Struktur des Quellcodes darstellen können, unabhängig von einer bestimmten Programmiersprache.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-105">The `System.CodeDom` namespace defines types that can represent the logical structure of source code, independent of a specific programming language.</span></span> <span data-ttu-id="aa4f4-106">Der `System.CodeDom.Compiler`-Namespace definiert Typen zum Generieren von Quellcode von CodeDOM-Diagrammen und zum Verwalten der Quellcodekompilierung in unterstützten Sprachen.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-106">The `System.CodeDom.Compiler` namespace defines types for generating source code from CodeDOM graphs and managing the compilation of source code in supported languages.</span></span> <span data-ttu-id="aa4f4-107">Compileranbieter oder Entwickler können die Reihe der unterstützten Sprachen erweitern.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-107">Compiler vendors or developers can extend the set of supported languages.</span></span>  
  
 <span data-ttu-id="aa4f4-108">Sprachunabhängige Quellcodemodellierung kann von Wert sein, wenn ein Programm Quellcode für ein Programm-Modell in mehreren Sprachen oder für eine ungenaue Zielsprache generieren muss.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-108">Language-independent source code modeling can be valuable when a program needs to generate source code for a program model in multiple languages or for an uncertain target language.</span></span> <span data-ttu-id="aa4f4-109">Einige Designer nutzen z.B. CodeDOM als Sprachabstraktions-Schnittstelle, um Quellcode in der korrekten Programmiersprache zu erstellen, falls die CodeDOM-Unterstützung für die Sprache verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-109">For example, some designers use the CodeDOM as a language abstraction interface to produce source code in the correct programming language, if CodeDOM support for the language is available.</span></span>  
  
 <span data-ttu-id="aa4f4-110">Das .NET Framework enthält Codegeneratoren und Codecompiler für <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider> und <xref:Microsoft.VisualBasic.VBCodeProvider>.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-110">The .NET Framework includes code generators and code compilers for <xref:Microsoft.CSharp.CSharpCodeProvider>, <xref:Microsoft.JScript.JScriptCodeProvider>, and <xref:Microsoft.VisualBasic.VBCodeProvider>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aa4f4-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="aa4f4-111">In This Section</span></span>  
 [<span data-ttu-id="aa4f4-112">Verwenden von CodeDOM</span><span class="sxs-lookup"><span data-stu-id="aa4f4-112">Using the CodeDOM</span></span>](using-the-codedom.md)  
 <span data-ttu-id="aa4f4-113">Beschreibt häufige Verwendungen und stellt die Erstellung eines einfachen Objektdiagramms mithilfe von CodeDOM dar.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-113">Describes common uses, and demonstrates building a simple object graph using the CodeDOM.</span></span>  
  
 [<span data-ttu-id="aa4f4-114">Generieren von Quellcode und Kompilieren eines Programms aus einem CodeDOM-Diagramm</span><span class="sxs-lookup"><span data-stu-id="aa4f4-114">Generating Source Code and Compiling a Program from a CodeDOM Graph</span></span>](generating-and-compiling-source-code-from-a-codedom-graph.md)  
 <span data-ttu-id="aa4f4-115">Beschreibt, wie Quellcode generiert und der generierte Code mit einem externen Compiler mithilfe von im `System.CodeDom.Compiler`-Namespace definierten Klassen kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-115">Describes how to generate source code and compile the generated code with an external compiler using classes defined in the `System.CodeDom.Compiler` namespace.</span></span>  
  
 [<span data-ttu-id="aa4f4-116">Vorgehensweise: Erstellen einer XML-Dokumentationsdatei mit CodeDOM</span><span class="sxs-lookup"><span data-stu-id="aa4f4-116">How to: Create an XML Documentation File Using CodeDOM</span></span>](how-to-create-an-xml-documentation-file-using-codedom.md)  
 <span data-ttu-id="aa4f4-117">Beschreibt, wie CodeDOM zum Generieren von Code mit Kommentaren der XML-Dokumentation verwendet wird und wie der generierte Code kompiliert wird, damit die Ausgabe der XML-Dokumentation erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-117">Describes how to use CodeDOM to generate code with XML documentation comments, and compile the generated code so that it creates the XML documentation output.</span></span>  
  
 [<span data-ttu-id="aa4f4-118">Vorgehensweise: Erstellen einer Klasse mit CodeDOM</span><span class="sxs-lookup"><span data-stu-id="aa4f4-118">How to: Create a Class Using CodeDOM</span></span>](how-to-create-a-class-using-codedom.md)  
 <span data-ttu-id="aa4f4-119">Beschreibt, wie CodeDOM zum Generieren einer Klasse verwendet wird, die Felder, Eigenschaften, eine Methode, einen Konstruktor und einen Einstiegspunkt enthält.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-119">Describes how to use CodeDOM to generate a class containing fields, properties, a method, a constructor, and an entry point.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="aa4f4-120">Referenz</span><span class="sxs-lookup"><span data-stu-id="aa4f4-120">Reference</span></span>  
 <xref:System.CodeDom>  
 <span data-ttu-id="aa4f4-121">Definiert Elemente, die Codeelemente in Programmiersprachen darstellen, die auf die Common Language Runtime abzielen.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-121">Defines elements that represent code elements in programming languages that target the common language runtime.</span></span>  
  
 <xref:System.CodeDom.Compiler>  
 <span data-ttu-id="aa4f4-122">Definiert Schnittstellen zum Generieren und Kompilieren von Code zur Runtime.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-122">Defines interfaces for generating and compiling code at run time.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="aa4f4-123">Verwandte Abschnitte</span><span class="sxs-lookup"><span data-stu-id="aa4f4-123">Related Sections</span></span>  
 <span data-ttu-id="aa4f4-124">[Kurzreferenz zum CodeDOM](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="aa4f4-124">[CodeDOM Quick Reference](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/f1dfsbhc(v=vs.100))</span></span>  
 <span data-ttu-id="aa4f4-125">Bietet Entwicklern einen schnellen Weg, die CodeDOM-Elemente zu finden, die Quellcodeelemente darstellen.</span><span class="sxs-lookup"><span data-stu-id="aa4f4-125">Provides a quick way for developers to find the CodeDOM elements that represent source code elements.</span></span>
