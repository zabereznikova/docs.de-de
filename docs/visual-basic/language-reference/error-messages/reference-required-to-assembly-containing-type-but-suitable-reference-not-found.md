---
title: Ein Verweis auf Assembly erforderlich &#39; &lt;Assemblyidentity&gt; &#39; mit Typ &#39; &lt;Typename&gt;&#39;, jedoch kein geeigneter Verweis konnte aufgrund einer Mehrdeutigkeit zwischen nicht gefunden werden Projekte &#39; &lt;projektname1&gt; &#39; und &#39; &lt;projektname2&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: 670ac3ceb6a703a11b8f00a341dbcf868d4ceb7e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597444"
---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a><span data-ttu-id="4560f-102">Ein Verweis auf Assembly erforderlich &#39; &lt;Assemblyidentity&gt; &#39; mit Typ &#39; &lt;Typename&gt;&#39;, jedoch kein geeigneter Verweis konnte aufgrund einer Mehrdeutigkeit zwischen nicht gefunden werden Projekte &#39; &lt;projektname1&gt; &#39; und &#39; &lt;projektname2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="4560f-102">Reference required to assembly &#39;&lt;assemblyidentity&gt;&#39; containing type &#39;&lt;typename&gt;&#39;, but a suitable reference could not be found due to ambiguity between projects &#39;&lt;projectname1&gt;&#39; and &#39;&lt;projectname2&gt;&#39;</span></span>
<span data-ttu-id="4560f-103">Ein Ausdruck verwendet einen Typ (z. B. eine Klasse, eine Struktur, eine Schnittstelle, eine Enumeration oder einen Delegaten), der außerhalb des Projekts definiert ist.</span><span class="sxs-lookup"><span data-stu-id="4560f-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="4560f-104">Sie haben jedoch Projektverweise auf mehr als eine Assembly, die diesen Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="4560f-104">However, you have project references to more than one assembly defining that type.</span></span>  
  
 <span data-ttu-id="4560f-105">Die genannten Projekte erzeugen Assemblys mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="4560f-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="4560f-106">Daher kann der Compiler nicht bestimmen, welche Assembly für den Typ, auf den Sie zugreifen, verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4560f-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>  
  
 <span data-ttu-id="4560f-107">Für den Zugriff auf einen Typ in einer anderen Assembly definiert, muss Visual Basic-Compiler einen Verweis auf diese Assembly verfügen.</span><span class="sxs-lookup"><span data-stu-id="4560f-107">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="4560f-108">Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.</span><span class="sxs-lookup"><span data-stu-id="4560f-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="4560f-109">**Fehler-ID:** BC30969</span><span class="sxs-lookup"><span data-stu-id="4560f-109">**Error ID:** BC30969</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4560f-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4560f-110">To correct this error</span></span>  
  
1.  <span data-ttu-id="4560f-111">Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="4560f-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="4560f-112">Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.</span><span class="sxs-lookup"><span data-stu-id="4560f-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="4560f-113">Fügen Sie in den Projekteigenschaften einen Verweis auf die Datei mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="4560f-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4560f-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4560f-114">See Also</span></span>  
 [<span data-ttu-id="4560f-115">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="4560f-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="4560f-116">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="4560f-116">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [<span data-ttu-id="4560f-117">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="4560f-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="4560f-118">Problembehandlung bei fehlerhaften Verweisen</span><span class="sxs-lookup"><span data-stu-id="4560f-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
