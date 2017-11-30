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
ms.openlocfilehash: 3f45dc17304c3c9d62b65760f2c1b5d461812a66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a><span data-ttu-id="a8f59-102">Keine zugreifbare &#39; Main &#39; Methode mit einer entsprechenden Signatur wurde gefunden, &#39; &lt;Namen&gt;&#39;</span><span class="sxs-lookup"><span data-stu-id="a8f59-102">No accessible &#39;Main&#39; method with an appropriate signature was found in &#39;&lt;name&gt;&#39;</span></span>
<span data-ttu-id="a8f59-103">Befehlszeilenanwendungen benötigen eine `Sub Main` definiert.</span><span class="sxs-lookup"><span data-stu-id="a8f59-103">Command-line applications must have a `Sub Main` defined.</span></span> <span data-ttu-id="a8f59-104">`Main`muss deklariert werden, als `Public Shared` ggf. in einer Klasse oder als definierten `Public` Wenn in einem Modul definiert.</span><span class="sxs-lookup"><span data-stu-id="a8f59-104">`Main` must be declared as `Public Shared` if it is defined in a class, or as `Public` if defined in a module.</span></span>  
  
 <span data-ttu-id="a8f59-105">Weitere Informationen zu `Main`, finden Sie unter [NIB: Visual Basic-Version von Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c).</span><span class="sxs-lookup"><span data-stu-id="a8f59-105">For more information on `Main`, see [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c).</span></span>  
  
 <span data-ttu-id="a8f59-106">**Fehler-ID:** BC30737</span><span class="sxs-lookup"><span data-stu-id="a8f59-106">**Error ID:** BC30737</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="a8f59-107">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="a8f59-107">To correct this error</span></span>  
  
-   <span data-ttu-id="a8f59-108">Definieren einer `Public Sub Main` Verfahren für das Projekt.</span><span class="sxs-lookup"><span data-stu-id="a8f59-108">Define a `Public Sub Main` procedure for your project.</span></span> <span data-ttu-id="a8f59-109">Deklarieren Sie es als `Shared` nur, wenn Sie innerhalb einer Klasse zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a8f59-109">Declare it as `Shared` if and only if you define it inside a class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f59-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a8f59-110">See Also</span></span>  
 [<span data-ttu-id="a8f59-111">NIB: Visual Basic-Version von Hello, World</span><span class="sxs-lookup"><span data-stu-id="a8f59-111">NIB: Visual Basic Version of Hello, World</span></span>](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [<span data-ttu-id="a8f59-112">Struktur eines Visual Basic-Programms</span><span class="sxs-lookup"><span data-stu-id="a8f59-112">Structure of a Visual Basic Program</span></span>](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [<span data-ttu-id="a8f59-113">Verfahren</span><span class="sxs-lookup"><span data-stu-id="a8f59-113">Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/index.md)
