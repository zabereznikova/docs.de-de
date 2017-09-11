---
title: "Verweis auf die Assembly erforderlich &quot;&lt;Assemblyname&gt;&quot;enthält die Basisklasse&quot;&lt;Classname&gt;&quot; | Microsoft-Dokumentation"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30007
- vbc30007
dev_langs:
- VB
helpviewer_keywords:
- BC30007
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: 9
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
ms.openlocfilehash: 131f8fd53fe025ac16450d9ff0019626444c6cc6
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="reference-required-to-assembly-39ltassemblynamegt39-containing-the-base-class-39ltclassnamegt39"></a><span data-ttu-id="fd1c1-102">Verweis auf die Assembly erforderlich '&lt;Assemblyname&gt;"enthält die Basisklasse"&lt;Classname&gt;'</span><span class="sxs-lookup"><span data-stu-id="fd1c1-102">Reference required to assembly &#39;&lt;assemblyname&gt;&#39; containing the base class &#39;&lt;classname&gt;&#39;</span></span>
<span data-ttu-id="fd1c1-103">Verweis auf die Assembly erforderlich '\<Assemblyname >', enthält der Basisklasse\<Classname >'.</span><span class="sxs-lookup"><span data-stu-id="fd1c1-103">Reference required to assembly '\<assemblyname>' containing the base class '\<classname>'.</span></span> <span data-ttu-id="fd1c1-104">Fügen Sie dem Projekt einen Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="fd1c1-104">Add one to your project.</span></span>  
  
 <span data-ttu-id="fd1c1-105">Die Klasse ist in einer Dynamic Link Library (DLL) oder Assembly definiert, auf die in Ihrem Projekt nicht direkt verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="fd1c1-105">The class is defined in a dynamic-link library (DLL) or assembly that is not directly referenced in your project.</span></span> <span data-ttu-id="fd1c1-106">Die [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Compiler benötigt einen Verweis, um Mehrdeutigkeit zu vermeiden, falls die Klasse in mehr als einer DLL oder Assembly definiert ist.</span><span class="sxs-lookup"><span data-stu-id="fd1c1-106">The [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler requires a reference to avoid ambiguity in case the class is defined in more than one DLL or assembly.</span></span>  
  
 <span data-ttu-id="fd1c1-107">**Fehler-ID:** BC30007</span><span class="sxs-lookup"><span data-stu-id="fd1c1-107">**Error ID:** BC30007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="fd1c1-108">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="fd1c1-108">To correct this error</span></span>  
  
-   <span data-ttu-id="fd1c1-109">Nehmen Sie den Namen der nicht referenzierten DLL oder Assembly in Ihre Projektverweise auf.</span><span class="sxs-lookup"><span data-stu-id="fd1c1-109">Include the name of the unreferenced DLL or assembly in your project references.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd1c1-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd1c1-110">See Also</span></span>  
 <span data-ttu-id="fd1c1-111">[NIB: Vorgehensweise: Hinzufügen oder Entfernen von Verweisen mithilfe des Dialogfelds „Verweis hinzufügen“](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span><span class="sxs-lookup"><span data-stu-id="fd1c1-111">[NIB How to: Add or Remove References By Using the Add Reference Dialog Box](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9) </span></span>  
<span data-ttu-id="fd1c1-112"> [Verwalten von Verweise in einem Projekt](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span><span class="sxs-lookup"><span data-stu-id="fd1c1-112"> [Managing references in a project](https://docs.microsoft.com/visualstudio/ide/managing-references-in-a-project) </span></span>  
<span data-ttu-id="fd1c1-113"> [Problembehandlung bei fehlerhaften Verweisen](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span><span class="sxs-lookup"><span data-stu-id="fd1c1-113"> [Troubleshooting Broken References](https://docs.microsoft.com/visualstudio/ide/troubleshooting-broken-references)</span></span>
