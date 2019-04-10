---
title: Es ist ein Verweis auf die Assembly '<assemblyidentity>' erforderlich, die den Typ '<typename>' enthält, aber aufgrund der Mehrdeutigkeit der Projekte '<projectname1>' und '<projectname2>' wurde kein geeigneter Verweis gefunden
ms.date: 07/20/2015
f1_keywords:
- bc30969
- vbc30969
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
ms.openlocfilehash: 9868598b32ae17ef5bfb5dd738f8a7541515f5ec
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59310670"
---
# <a name="reference-required-to-assembly-assemblyidentity-containing-type-typename-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-projectname1-and-projectname2"></a><span data-ttu-id="a3590-102">Verweis auf die Assembly erforderlich "\<Assemblyidentity >' mit Typ"\<Typename > ", aber kein geeigneter Verweis konnte nicht gefunden werden, aufgrund der Mehrdeutigkeit der Projekte\<projektname1 >" und "\< projektname2 > "</span><span class="sxs-lookup"><span data-stu-id="a3590-102">Reference required to assembly '\<assemblyidentity>' containing type '\<typename>', but a suitable reference could not be found due to ambiguity between projects '\<projectname1>' and '\<projectname2>'</span></span>
<span data-ttu-id="a3590-103">Ein Ausdruck verwendet einen Typ (z. B. eine Klasse, eine Struktur, eine Schnittstelle, eine Enumeration oder einen Delegaten), der außerhalb des Projekts definiert ist.</span><span class="sxs-lookup"><span data-stu-id="a3590-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="a3590-104">Sie haben jedoch Projektverweise auf mehr als eine Assembly, die diesen Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="a3590-104">However, you have project references to more than one assembly defining that type.</span></span>  
  
 <span data-ttu-id="a3590-105">Die genannten Projekte erzeugen Assemblys mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="a3590-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="a3590-106">Daher kann der Compiler nicht bestimmen, welche Assembly für den Typ, auf den Sie zugreifen, verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a3590-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>  
  
 <span data-ttu-id="a3590-107">Zugriff auf einen Typ in einer anderen Assembly definiert, müssen die Visual Basic-Compiler einen Verweis auf diese Assembly.</span><span class="sxs-lookup"><span data-stu-id="a3590-107">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="a3590-108">Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.</span><span class="sxs-lookup"><span data-stu-id="a3590-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="a3590-109">**Fehler-ID:** BC30969</span><span class="sxs-lookup"><span data-stu-id="a3590-109">**Error ID:** BC30969</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a3590-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a3590-110">To correct this error</span></span>  
  
1. <span data-ttu-id="a3590-111">Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="a3590-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="a3590-112">Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.</span><span class="sxs-lookup"><span data-stu-id="a3590-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2. <span data-ttu-id="a3590-113">Fügen Sie in den Projekteigenschaften einen Verweis auf die Datei mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="a3590-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3590-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3590-114">See also</span></span>

- [<span data-ttu-id="a3590-115">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="a3590-115">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="a3590-116">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="a3590-116">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="a3590-117">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="a3590-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="a3590-118">Troubleshooting Broken References</span><span class="sxs-lookup"><span data-stu-id="a3590-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
