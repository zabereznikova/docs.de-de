---
title: Ein Verweis auf Assembly &#39;erforderlich; &lt;Assemblyidentity&gt;&#39; enthaltenden Typ &#39;&lt; TypeName&gt;&#39; aber kein geeigneter Verweis konnte nicht gefunden werden, aufgrund einer Mehrdeutigkeit zwischen Projekten &#39;&lt; projektname1&gt;&#39; und &#39;&lt; projektname2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5ca2454f5c306b3defd1c885dfd59ee130f3e828
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a><span data-ttu-id="14b47-102">Ein Verweis auf Assembly &#39;erforderlich; &lt;Assemblyidentity&gt;&#39; enthaltenden Typ &#39;&lt; TypeName&gt;&#39; aber kein geeigneter Verweis konnte nicht gefunden werden, aufgrund einer Mehrdeutigkeit zwischen Projekten &#39;&lt; projektname1&gt;&#39; und &#39;&lt; projektname2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="14b47-102">Reference required to assembly &#39;&lt;assemblyidentity&gt;&#39; containing type &#39;&lt;typename&gt;&#39;, but a suitable reference could not be found due to ambiguity between projects &#39;&lt;projectname1&gt;&#39; and &#39;&lt;projectname2&gt;&#39;</span></span>
<span data-ttu-id="14b47-103">Ein Ausdruck verwendet einen Typ (z. B. eine Klasse, eine Struktur, eine Schnittstelle, eine Enumeration oder einen Delegaten), der außerhalb des Projekts definiert ist.</span><span class="sxs-lookup"><span data-stu-id="14b47-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="14b47-104">Sie haben jedoch Projektverweise auf mehr als eine Assembly, die diesen Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="14b47-104">However, you have project references to more than one assembly defining that type.</span></span>  
  
 <span data-ttu-id="14b47-105">Die genannten Projekte erzeugen Assemblys mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="14b47-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="14b47-106">Daher kann der Compiler nicht bestimmen, welche Assembly für den Typ, auf den Sie zugreifen, verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="14b47-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>  
  
 <span data-ttu-id="14b47-107">Für den Zugriff auf einen Typ in einer anderen Assembly benötigt der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler einen Verweis auf diese Assembly.</span><span class="sxs-lookup"><span data-stu-id="14b47-107">To access a type defined in another assembly, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="14b47-108">Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.</span><span class="sxs-lookup"><span data-stu-id="14b47-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="14b47-109">**Fehler-ID:** BC30969</span><span class="sxs-lookup"><span data-stu-id="14b47-109">**Error ID:** BC30969</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="14b47-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="14b47-110">To correct this error</span></span>  
  
1.  <span data-ttu-id="14b47-111">Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="14b47-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="14b47-112">Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.</span><span class="sxs-lookup"><span data-stu-id="14b47-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="14b47-113">Fügen Sie in den Projekteigenschaften einen Verweis auf die Datei mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="14b47-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14b47-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="14b47-114">See Also</span></span>  
 [<span data-ttu-id="14b47-115">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="14b47-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="14b47-116">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="14b47-116">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [<span data-ttu-id="14b47-117">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="14b47-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="14b47-118">Problembehandlung bei fehlerhaften Verweisen</span><span class="sxs-lookup"><span data-stu-id="14b47-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
