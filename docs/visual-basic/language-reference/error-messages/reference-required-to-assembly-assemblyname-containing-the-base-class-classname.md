---
title: Ein Verweis auf Assembly &#39;erforderlich; &lt;Assemblyname&gt;&#39; mit der Basisklasse &#39;&lt; Klassenname&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
helpviewer_keywords: BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f7413c82a9c61d13e7ca6fa18f27a4769a0937f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a><span data-ttu-id="c3239-102">Ein Verweis auf Assembly &#39;erforderlich; &lt;Assemblyname&gt;&#39; mit der Basisklasse &#39;&lt; Klassenname&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="c3239-102">Reference required to assembly &#39;&lt;assemblyname&gt;&#39; containing the base class &#39;&lt;classname&gt;&#39;</span></span>
<span data-ttu-id="c3239-103">Ein Verweis auf Assembly erforderlich "\<Assemblyname >' mit der Basisklasse\<Klassenname >'.</span><span class="sxs-lookup"><span data-stu-id="c3239-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="c3239-104">Fügen Sie dem Projekt einen Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="c3239-104">Add one to your project.</span></span>  
  
 <span data-ttu-id="c3239-105">Die Klasse ist in einer Dynamic Link Library (DLL) oder Assembly definiert, auf die in Ihrem Projekt nicht direkt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="c3239-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="c3239-106">Der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] -Compiler benötigt einen Verweis, um Mehrdeutigkeiten zu vermeiden, falls die Klasse in mehreren DLLs oder Assemblys definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c3239-106">The [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>  
  
 <span data-ttu-id="c3239-107">**Fehler-ID:** BC30007</span><span class="sxs-lookup"><span data-stu-id="c3239-107">**Error ID:** BC30007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c3239-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c3239-108">To correct this error</span></span>  
  
-   <span data-ttu-id="c3239-109">Nehmen Sie den Namen der nicht referenzierten DLL oder Assembly in Ihre Projektverweise auf.</span><span class="sxs-lookup"><span data-stu-id="c3239-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3239-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c3239-110">See Also</span></span>  
 [<span data-ttu-id="c3239-111">NIB: Gewusst wie: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds "Verweis hinzufügen"</span><span class="sxs-lookup"><span data-stu-id="c3239-111">NIB How to: Add or Remove References By Using the Add Reference Dialog Box</span></span>](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)  
 [<span data-ttu-id="c3239-112">Verwalten von Verweisen in einem Projekt</span><span class="sxs-lookup"><span data-stu-id="c3239-112">Managing references in a project</span></span>](/visualstudio/ide/managing-references-in-a-project)  
 [<span data-ttu-id="c3239-113">Problembehandlung bei fehlerhaften Verweisen</span><span class="sxs-lookup"><span data-stu-id="c3239-113">Troubleshooting Broken References</span></span>](/visualstudio/ide/troubleshooting-broken-references)
