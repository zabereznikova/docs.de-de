---
title: "&lt;Nachricht&gt; dieser Fehler ist möglicherweise auch aufgrund eines Dateiverweises mit einem Projektverweis auf Assembly &#39;&lt; AssemblyName&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
helpviewer_keywords: BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a30e5d5aca09e7b74e16dd05cdc0c5c361c1657d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="e0241-102">&lt;Nachricht&gt; dieser Fehler ist möglicherweise auch aufgrund eines Dateiverweises mit einem Projektverweis auf Assembly &#39;&lt; AssemblyName&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="e0241-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="e0241-103">\<Meldung > Dieser Fehler ist möglicherweise auch aufgrund eines Dateiverweises mit einem Projektverweis auf Assembly '\<Assemblyname >.</span><span class="sxs-lookup"><span data-stu-id="e0241-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="e0241-104">In diesem Fall versuchen Sie es, und Ersetzen Sie dabei den Dateiverweis auf "\<Assemblydateiname >" in Projekt "\<projektname1 >" mit einem Projektverweis auf "\<projektname2 >".</span><span class="sxs-lookup"><span data-stu-id="e0241-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="e0241-105">Code in Ihrem Projekt greift auf einen Member eines anderen Projekts zu, aufgrund der Konfiguration Ihrer Projektmappe kann der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler den Verweis aber nicht auflösen.</span><span class="sxs-lookup"><span data-stu-id="e0241-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="e0241-106">Für den Zugriff auf einen Typ in einer anderen Assembly benötigt der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler einen Verweis auf diese Assembly.</span><span class="sxs-lookup"><span data-stu-id="e0241-106">To access a type defined in another assembly, the [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="e0241-107">Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.</span><span class="sxs-lookup"><span data-stu-id="e0241-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="e0241-108">**Fehler-ID:** BC30971</span><span class="sxs-lookup"><span data-stu-id="e0241-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e0241-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="e0241-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="e0241-110">Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="e0241-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="e0241-111">Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0241-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="e0241-112">Fügen Sie in den Projekteigenschaften einen Verweis auf das Projekt mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="e0241-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0241-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0241-113">See Also</span></span>  
 [<span data-ttu-id="e0241-114">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="e0241-114">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="e0241-115">Verweise auf deklarierte Elemente</span><span class="sxs-lookup"><span data-stu-id="e0241-115">References to Declared Elements</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [<span data-ttu-id="e0241-116">NIB: Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweis hinzufügen"</span><span class="sxs-lookup"><span data-stu-id="e0241-116">NIB How to: Add or Remove References By Using the Add Reference Dialog Box</span></span>](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [<span data-ttu-id="e0241-117">Verwalten von Projekt- und Projektmappeneigenschaften</span><span class="sxs-lookup"><span data-stu-id="e0241-117">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)  
 [<span data-ttu-id="e0241-118">Problembehandlung bei fehlerhaften Verweisen</span><span class="sxs-lookup"><span data-stu-id="e0241-118">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
