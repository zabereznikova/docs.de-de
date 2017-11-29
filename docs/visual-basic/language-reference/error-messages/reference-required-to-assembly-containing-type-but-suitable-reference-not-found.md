---
title: Ein Verweis auf Assembly &#39;erforderlich; &lt;Assemblyidentity&gt;&#39; enthaltenden Typ &#39;&lt; TypeName&gt;&#39; aber kein geeigneter Verweis konnte nicht gefunden werden, aufgrund einer Mehrdeutigkeit zwischen Projekten &#39;&lt; projektname1&gt;&#39; und &#39;&lt; projektname2&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords: BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 04a1b16a10d2a3945d1efbe3a2bd0850f1da39fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a><span data-ttu-id="93e24-102">Ein Verweis auf Assembly &#39;erforderlich; &lt;Assemblyidentity&gt;&#39; enthaltenden Typ &#39;&lt; TypeName&gt;&#39; aber kein geeigneter Verweis konnte nicht gefunden werden, aufgrund einer Mehrdeutigkeit zwischen Projekten &#39;&lt; projektname1&gt;&#39; und &#39;&lt; projektname2&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="93e24-102">Reference required to assembly &#39;&lt;assemblyidentity&gt;&#39; containing type &#39;&lt;typename&gt;&#39;, but a suitable reference could not be found due to ambiguity between projects &#39;&lt;projectname1&gt;&#39; and &#39;&lt;projectname2&gt;&#39;</span></span>
<span data-ttu-id="93e24-103">Ein Ausdruck verwendet einen Typ (z. B. eine Klasse, eine Struktur, eine Schnittstelle, eine Enumeration oder einen Delegaten), der außerhalb des Projekts definiert ist.</span><span class="sxs-lookup"><span data-stu-id="93e24-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="93e24-104">Sie haben jedoch Projektverweise auf mehr als eine Assembly, die diesen Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="93e24-104">However, you have project references to more than one assembly defining that type.</span></span>  
  
 <span data-ttu-id="93e24-105">Die genannten Projekte erzeugen Assemblys mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="93e24-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="93e24-106">Daher kann der Compiler nicht bestimmen, welche Assembly für den Typ, auf den Sie zugreifen, verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="93e24-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>  
  
 <span data-ttu-id="93e24-107">Für den Zugriff auf einen Typ in einer anderen Assembly benötigt der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler einen Verweis auf diese Assembly.</span><span class="sxs-lookup"><span data-stu-id="93e24-107">To access a type defined in another assembly, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="93e24-108">Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.</span><span class="sxs-lookup"><span data-stu-id="93e24-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="93e24-109">**Fehler-ID:** BC30969</span><span class="sxs-lookup"><span data-stu-id="93e24-109">**Error ID:** BC30969</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="93e24-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="93e24-110">To correct this error</span></span>  
  
1.  <span data-ttu-id="93e24-111">Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="93e24-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="93e24-112">Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.</span><span class="sxs-lookup"><span data-stu-id="93e24-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="93e24-113">Fügen Sie in den Projekteigenschaften einen Verweis auf die Datei mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="93e24-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93e24-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="93e24-114">See Also</span></span>  
 [<span data-ttu-id="93e24-115">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="93e24-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="93e24-116">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="93e24-116">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="93e24-117">NIB: Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweis hinzufügen"</span><span class="sxs-lookup"><span data-stu-id="93e24-117">NIB How to: Add or Remove References By Using the Add Reference Dialog Box</span></span>](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [<span data-ttu-id="93e24-118">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="93e24-118">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="93e24-119">Problembehandlung bei fehlerhaften Verweisen</span><span class="sxs-lookup"><span data-stu-id="93e24-119">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
