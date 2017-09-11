---
title: Verweis auf die Assembly erforderlich &quot;&lt;Assemblyidentity&gt;&quot;mit Typ&quot;&lt;Typename&gt;&quot;, aber kein geeigneter Verweis konnte nicht gefunden werden, aufgrund der Mehrdeutigkeit der Projekte&lt;projectname1&gt;&quot;und&quot;&lt;projectname2&gt;&quot; | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30969
- vbc30969
dev_langs:
- VB
helpviewer_keywords:
- BC30969
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: 11
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
ms.openlocfilehash: bb5375366fa525a0ca9c16944d026ca499062ed8
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="reference-required-to-assembly-39ltassemblyidentitygt39-containing-type-39lttypenamegt39-but-a-suitable-reference-could-not-be-found-due-to-ambiguity-between-projects-39ltprojectname1gt39-and-39ltprojectname2gt39"></a><span data-ttu-id="63319-102">Verweis auf die Assembly erforderlich '&lt;Assemblyidentity&gt;'mit Typ'&lt;Typename&gt;', aber kein geeigneter Verweis konnte nicht gefunden werden, aufgrund der Mehrdeutigkeit der Projekte&lt;projectname1&gt;"und"&lt;projectname2&gt;'</span><span class="sxs-lookup"><span data-stu-id="63319-102">Reference required to assembly &#39;&lt;assemblyidentity&gt;&#39; containing type &#39;&lt;typename&gt;&#39;, but a suitable reference could not be found due to ambiguity between projects &#39;&lt;projectname1&gt;&#39; and &#39;&lt;projectname2&gt;&#39;</span></span>
<span data-ttu-id="63319-103">Ein Ausdruck verwendet einen Typ (z. B. eine Klasse, eine Struktur, eine Schnittstelle, eine Enumeration oder einen Delegaten), der außerhalb des Projekts definiert ist.</span><span class="sxs-lookup"><span data-stu-id="63319-103">An expression uses a type, such as a class, structure, interface, enumeration, or delegate, that is defined outside your project.</span></span> <span data-ttu-id="63319-104">Sie haben jedoch Projektverweise auf mehr als eine Assembly, die diesen Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="63319-104">However, you have project references to more than one assembly defining that type.</span></span>  
  
 <span data-ttu-id="63319-105">Die genannten Projekte erzeugen Assemblys mit demselben Namen.</span><span class="sxs-lookup"><span data-stu-id="63319-105">The cited projects produce assemblies with the same name.</span></span> <span data-ttu-id="63319-106">Daher kann der Compiler nicht bestimmen, welche Assembly für den Typ, auf den Sie zugreifen, verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="63319-106">Therefore, the compiler cannot determine which assembly to use for the type you are accessing.</span></span>  
  
 <span data-ttu-id="63319-107">Auf einen Typ in einer anderen Assembly definiert die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler benötigen einen Verweis auf diese Assembly.</span><span class="sxs-lookup"><span data-stu-id="63319-107">To access a type defined in another assembly, the [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler must have a reference to that assembly.</span></span> <span data-ttu-id="63319-108">Dabei muss es sich um einen einzelnen, eindeutigen Verweis handeln, der keine Zirkelverweise in Projekten verursacht.</span><span class="sxs-lookup"><span data-stu-id="63319-108">This must be a single, unambiguous reference that does not cause circular references among projects.</span></span>  
  
 <span data-ttu-id="63319-109">**Fehler-ID:** BC30969</span><span class="sxs-lookup"><span data-stu-id="63319-109">**Error ID:** BC30969</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="63319-110">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="63319-110">To correct this error</span></span>  
  
1.  <span data-ttu-id="63319-111">Bestimmen Sie, welches Projekt die Assembly erzeugt, auf die Ihr Projekt am besten verweisen kann.</span><span class="sxs-lookup"><span data-stu-id="63319-111">Determine which project produces the best assembly for your project to reference.</span></span> <span data-ttu-id="63319-112">Für diese Entscheidung können Sie Kriterien wie den einfachen Zugriff auf Dateien und die Häufigkeit von Updates verwenden.</span><span class="sxs-lookup"><span data-stu-id="63319-112">For this decision, you might use criteria such as ease of file access and frequency of updates.</span></span>  
  
2.  <span data-ttu-id="63319-113">Fügen Sie in den Projekteigenschaften einen Verweis auf die Datei mit der Assembly hinzu, die den von Ihnen verwendeten Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="63319-113">In your project properties, add a reference to the file that contains the assembly that defines the type you are using.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63319-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63319-114">See Also</span></span>  
 <span data-ttu-id="63319-115">[Verwalten von Verweise in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="63319-115">[Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="63319-116"> [Verweise auf deklarierte Elemente](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span><span class="sxs-lookup"><span data-stu-id="63319-116"> [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md) </span></span>  
<span data-ttu-id="63319-117"> [NIB: Vorgehensweise: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span><span class="sxs-lookup"><span data-stu-id="63319-117"> [NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span></span>  
<span data-ttu-id="63319-118"> [NIB Gewusst wie: Ändern von Projekteigenschaften und Konfigurationseinstellungen](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span><span class="sxs-lookup"><span data-stu-id="63319-118"> [NIB How to: Modify Project Properties and Configuration Settings](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67) </span></span>  
<span data-ttu-id="63319-119"> [Problembehandlung bei fehlerhaften Verweisen](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span><span class="sxs-lookup"><span data-stu-id="63319-119"> [Troubleshooting Broken References](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span></span>
