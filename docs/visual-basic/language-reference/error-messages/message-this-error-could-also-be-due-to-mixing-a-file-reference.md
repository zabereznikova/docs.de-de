---
title: <message> Dieser Fehler könnte auch auf das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly "<assemblyname>" zurückzuführen sein.
ms.date: 07/20/2015
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
ms.openlocfilehash: cd2c00bda5b63abbd6bf7069ef28d0a812b22044
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873787"
---
# <a name="message-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-assemblyname"></a><span data-ttu-id="b1639-102">\<message> Dieser Fehler könnte auch auf das Mischen eines Dateiverweises mit einem Projektverweis auf Assembly "\<assemblyname>" zurückzuführen sein.</span><span class="sxs-lookup"><span data-stu-id="b1639-102">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>'</span></span>

<span data-ttu-id="b1639-103">\<message> Dieser Fehler kann auch auf das Mischen eines Datei Verweises mit einem Projekt Verweis auf die Assembly "" zurückzuführen sein \<assemblyname> .</span><span class="sxs-lookup"><span data-stu-id="b1639-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="b1639-104">Ersetzen Sie in diesem Fall den Datei Verweis auf " \<assemblyfilename> " im Projekt "" \<projectname1> durch einen Projekt Verweis auf " \<projectname2> ".</span><span class="sxs-lookup"><span data-stu-id="b1639-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="b1639-105">Der Code in Ihrem Projekt greift auf einen Member eines anderen Projekts zu, aber die Konfiguration der Projekt Mappe lässt nicht zu, dass der Visual Basic Compiler den Verweis auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="b1639-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the Visual Basic compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="b1639-106">Für den Zugriff auf einen Typ, der in einer anderen Assembly definiert ist, muss der Visual Basic-Compiler über einen Verweis auf diese Assembly verfügen.</span><span class="sxs-lookup"><span data-stu-id="b1639-106">To access a type defined in another assembly, the Visual Basic compiler must have a reference to that assembly.</span></span> <span data-ttu-id="b1639-107">Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.</span><span class="sxs-lookup"><span data-stu-id="b1639-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="b1639-108">**Fehler-ID:** BC30971</span><span class="sxs-lookup"><span data-stu-id="b1639-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b1639-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b1639-109">To correct this error</span></span>  
  
1. <span data-ttu-id="b1639-110">Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="b1639-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="b1639-111">Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1639-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2. <span data-ttu-id="b1639-112">Fügen Sie in den Projekteigenschaften einen Verweis auf das Projekt mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="b1639-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1639-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1639-113">See also</span></span>

- [<span data-ttu-id="b1639-114">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="b1639-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)
- [<span data-ttu-id="b1639-115">References to Declared Elements</span><span class="sxs-lookup"><span data-stu-id="b1639-115">References to Declared Elements</span></span>](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md)

- [<span data-ttu-id="b1639-116">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="b1639-116">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
- [<span data-ttu-id="b1639-117">Problembehandlung bei fehlerhaften Verweisen</span><span class="sxs-lookup"><span data-stu-id="b1639-117">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
