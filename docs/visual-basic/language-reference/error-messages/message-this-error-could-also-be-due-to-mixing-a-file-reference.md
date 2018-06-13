---
title: '&lt;Nachricht&gt; dieser Fehler kann auch aufgrund eines Dateiverweises mit einem Projektverweis auf Assembly sein &#39; &lt;Assemblyname&gt;&#39;'
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: 498ca74497077e3268aa8cb25ce5121f3c9ea59d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588336"
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="956c6-102">&lt;Nachricht&gt; dieser Fehler kann auch aufgrund eines Dateiverweises mit einem Projektverweis auf Assembly sein &#39; &lt;Assemblyname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="956c6-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="956c6-103">\<Meldung > Dieser Fehler ist möglicherweise auch aufgrund eines Dateiverweises mit einem Projektverweis auf Assembly '\<Assemblyname >.</span><span class="sxs-lookup"><span data-stu-id="956c6-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="956c6-104">In diesem Fall versuchen Sie es, und Ersetzen Sie dabei den Dateiverweis auf "\<Assemblydateiname >" in Projekt "\<projektname1 >" mit einem Projektverweis auf "\<projektname2 >".</span><span class="sxs-lookup"><span data-stu-id="956c6-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="956c6-105">Code in Ihrem Projekt greift auf einen Member eines anderen Projekts, aber die Konfiguration Ihrer Projektmappe lässt sich nicht auf die Visual Basic-Compiler den Verweis aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="956c6-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="956c6-106">Für den Zugriff auf einen Typ in einer anderen Assembly definiert, muss Visual Basic-Compiler einen Verweis auf diese Assembly verfügen.</span><span class="sxs-lookup"><span data-stu-id="956c6-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="956c6-107">Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.</span><span class="sxs-lookup"><span data-stu-id="956c6-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="956c6-108">**Fehler-ID:** BC30971</span><span class="sxs-lookup"><span data-stu-id="956c6-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="956c6-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="956c6-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="956c6-110">Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="956c6-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="956c6-111">Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.</span><span class="sxs-lookup"><span data-stu-id="956c6-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="956c6-112">Fügen Sie in den Projekteigenschaften einen Verweis auf das Projekt mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="956c6-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="956c6-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="956c6-113">See Also</span></span>  
 [<span data-ttu-id="956c6-114">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="956c6-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="956c6-115">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="956c6-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
   
 [<span data-ttu-id="956c6-116">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="956c6-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="956c6-117">Problembehandlung bei fehlerhaften Verweisen</span><span class="sxs-lookup"><span data-stu-id="956c6-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
