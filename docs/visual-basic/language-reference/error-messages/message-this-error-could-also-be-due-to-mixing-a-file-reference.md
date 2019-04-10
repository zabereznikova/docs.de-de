---
title: <message> Dieser Fehler wird möglicherweise auch durch das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly '<assemblyname>"
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 951f90a9209ff31896f4426ceb75f05b012897a6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59335146"
---
# <a name="message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a><span data-ttu-id="8ea78-102">\<Meldung > Dieser Fehler wird möglicherweise auch durch das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly '\<Assemblyname >'</span><span class="sxs-lookup"><span data-stu-id="8ea78-102">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>'</span></span>
<span data-ttu-id="8ea78-103">\<Meldung > Dieser Fehler wird möglicherweise auch durch das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly '\<Assemblyname >.</span><span class="sxs-lookup"><span data-stu-id="8ea78-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="8ea78-104">In diesem Fall versuchen Sie es, und Ersetzen Sie dabei den Dateiverweis auf "\<Assemblydateiname >" in Projekt "\<projektnamen1 >' mit einem Projektverweis auf"\<projektname2 > ".</span><span class="sxs-lookup"><span data-stu-id="8ea78-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="8ea78-105">Code in Ihrem Projekt greift auf einen Member eines anderen Projekts, aber die Konfiguration Ihrer Lösung lässt sich nicht auf die Visual Basic-Compiler zum Auflösen des Verweises.</span><span class="sxs-lookup"><span data-stu-id="8ea78-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="8ea78-106">Zugriff auf einen Typ in einer anderen Assembly definiert, müssen die Visual Basic-Compiler einen Verweis auf diese Assembly.</span><span class="sxs-lookup"><span data-stu-id="8ea78-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="8ea78-107">Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.</span><span class="sxs-lookup"><span data-stu-id="8ea78-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="8ea78-108">**Fehler-ID:** BC30971</span><span class="sxs-lookup"><span data-stu-id="8ea78-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="8ea78-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="8ea78-109">To correct this error</span></span>  
  
1. <span data-ttu-id="8ea78-110">Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="8ea78-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="8ea78-111">Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ea78-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2. <span data-ttu-id="8ea78-112">Fügen Sie in den Projekteigenschaften einen Verweis auf das Projekt mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="8ea78-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea78-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ea78-113">See also</span></span>

- [<span data-ttu-id="8ea78-114">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="8ea78-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="8ea78-115">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="8ea78-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="8ea78-116">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="8ea78-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="8ea78-117">Troubleshooting Broken References</span><span class="sxs-lookup"><span data-stu-id="8ea78-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
