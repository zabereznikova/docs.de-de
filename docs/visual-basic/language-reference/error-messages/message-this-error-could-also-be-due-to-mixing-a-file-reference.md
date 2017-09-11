---
title: '&lt;Nachricht&gt; dieser Fehler kann auch aufgrund eines Dateiverweises mit einem Projektverweis auf Assembly &quot;&lt;Assemblyname&gt;&quot; | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30971
- vbc30971
dev_langs:
- VB
helpviewer_keywords:
- BC30971
ms.assetid: 75d2e8b5-2fdc-4623-8b32-cba805dab7db
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c0908b1a13b9b9c54fb533201404987e479c6138
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="ltmessagegt-this-error-could-also-be-due-to-mixing-a-file-reference-with-a-project-reference-to-assembly-39ltassemblynamegt39"></a><span data-ttu-id="2d61e-102">&lt;Nachricht&gt; dieser Fehler kann auch aufgrund eines Dateiverweises mit einem Projektverweis auf Assembly '&lt;Assemblyname&gt;'</span><span class="sxs-lookup"><span data-stu-id="2d61e-102">&lt;message&gt; This error could also be due to mixing a file reference with a project reference to assembly &#39;&lt;assemblyname&gt;&#39;</span></span>
<span data-ttu-id="2d61e-103">\<Nachricht > dieser Fehler kann auch aufgrund eines Dateiverweises mit einem Projektverweis auf Assembly '\<Assemblyname >.</span><span class="sxs-lookup"><span data-stu-id="2d61e-103">\<message> This error could also be due to mixing a file reference with a project reference to assembly '\<assemblyname>.</span></span> <span data-ttu-id="2d61e-104">In diesem Fall versuchen, ersetzen den Verweis auf "\<Assemblyfilename >" im Projekt "\<projectname1 >" durch einen Projektverweis auf '\<projectname2 >'.</span><span class="sxs-lookup"><span data-stu-id="2d61e-104">In this case, try replacing the file reference to '\<assemblyfilename>' in project '\<projectname1>' with a project reference to '\<projectname2>'.</span></span>  
  
 <span data-ttu-id="2d61e-105">Der Code im Projekt greift auf einen Member eines anderen Projekts, die Konfiguration der Projektmappe lässt jedoch keine der [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler zum Auflösen des Verweises.</span><span class="sxs-lookup"><span data-stu-id="2d61e-105">Code in your project accesses a member of another project, but the configuration of your solution does not allow the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler to resolve the reference.</span></span>  
  
 <span data-ttu-id="2d61e-106">Auf einen Typ in einer anderen Assembly definiert die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler benötigen einen Verweis auf diese Assembly.</span><span class="sxs-lookup"><span data-stu-id="2d61e-106">To access a type defined in another assembly, the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="2d61e-107">Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.</span><span class="sxs-lookup"><span data-stu-id="2d61e-107">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="2d61e-108">**Fehler-ID:** BC30971</span><span class="sxs-lookup"><span data-stu-id="2d61e-108">**Error ID:** BC30971</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="2d61e-109">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="2d61e-109">To correct this error</span></span>  
  
1.  <span data-ttu-id="2d61e-110">Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="2d61e-110">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="2d61e-111">Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d61e-111">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="2d61e-112">Fügen Sie in den Projekteigenschaften einen Verweis auf das Projekt mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="2d61e-112">In your project properties, add a reference to the project that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d61e-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2d61e-113">See Also</span></span>  
 <span data-ttu-id="2d61e-114">[Verwalten von Verweise in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="2d61e-114">[Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="2d61e-115"> [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="2d61e-115"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="2d61e-116"> [NIB: Vorgehensweise: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span><span class="sxs-lookup"><span data-stu-id="2d61e-116"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span></span>  
<span data-ttu-id="2d61e-117"> [NIB Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span><span class="sxs-lookup"><span data-stu-id="2d61e-117"> [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span></span>  
<span data-ttu-id="2d61e-118"> [Problembehandlung bei fehlerhaften Verweisen](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span><span class="sxs-lookup"><span data-stu-id="2d61e-118"> [Troubleshooting Broken References](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span></span>
