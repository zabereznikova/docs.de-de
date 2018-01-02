---
title: Keine zugreifbare &#39; Main &#39; Methode mit einer entsprechenden Signatur wurde gefunden, &#39; &lt;Namen&gt;&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords: BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6a2d66c860b72bd3ef59c02f548ac563fab6b8c
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a><span data-ttu-id="aa197-102">Keine zugreifbare &#39; Main &#39; Methode mit einer entsprechenden Signatur wurde gefunden, &#39; &lt;Namen&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="aa197-102">No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;</span></span>
<span data-ttu-id="aa197-103">Befehlszeilenanwendungen benötigen eine `Sub Main` definiert.</span><span class="sxs-lookup"><span data-stu-id="aa197-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="aa197-104">`Main`muss deklariert werden, als `Public Shared` ggf. in einer Klasse oder als definierten `Public` Wenn in einem Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="aa197-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="aa197-105">**Fehler-ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="aa197-105">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="aa197-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="aa197-106">To correct this error</span></span>  
  
-   <span data-ttu-id="aa197-107">Definieren einer `Public Sub Main` Verfahren für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="aa197-107">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="aa197-108">Deklarieren Sie es als `Shared` nur, wenn Sie innerhalb einer Klasse zu definieren.</span><span class="sxs-lookup"><span data-stu-id="aa197-108">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa197-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa197-109">See Also</span></span>  
 [<span data-ttu-id="aa197-110">Struktur eines Visual Basic-Programms</span><span class="sxs-lookup"><span data-stu-id="aa197-110">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="aa197-111">Verfahren</span><span class="sxs-lookup"><span data-stu-id="aa197-111">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
