---
title: "&#39; &lt;Schlüsselwort&gt;&#39; ist nur innerhalb einer Instanzmethode gültig"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30043
- vbc30043
helpviewer_keywords:
- BC30043
ms.assetid: 7973aa82-a681-440c-9bca-242627d7ba86
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a61314c036cec0fd1412a9c844a610fbd1401add
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="39ltkeywordgt39-is-valid-only-within-an-instance-method"></a><span data-ttu-id="d0d44-102">&#39; &lt;Schlüsselwort&gt;&#39; ist nur innerhalb einer Instanzmethode gültig</span><span class="sxs-lookup"><span data-stu-id="d0d44-102">&#39;&lt;keyword&gt;&#39; is valid only within an instance method</span></span>
<span data-ttu-id="d0d44-103">Die `Me`, `MyClass`, und `MyBase` Schlüsselwörter beziehen sich auf bestimmte Klasseninstanzen.</span><span class="sxs-lookup"><span data-stu-id="d0d44-103">The `Me`, `MyClass`, and `MyBase` keywords refer to specific class instances.</span></span> <span data-ttu-id="d0d44-104">Können Sie nicht in einem gemeinsam verwendeten `Function` oder `Sub` Prozedur.</span><span class="sxs-lookup"><span data-stu-id="d0d44-104">You cannot use them inside a shared `Function` or `Sub` procedure.</span></span>  
  
 <span data-ttu-id="d0d44-105">**Fehler-ID:** BC30043</span><span class="sxs-lookup"><span data-stu-id="d0d44-105">**Error ID:** BC30043</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="d0d44-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="d0d44-106">To correct this error</span></span>  
  
-   <span data-ttu-id="d0d44-107">Entfernen Sie das Schlüsselwort aus der Prozedur, oder Entfernen der `Shared` -Schlüsselwort aus der Deklaration der Prozedur.</span><span class="sxs-lookup"><span data-stu-id="d0d44-107">Remove the keyword from the procedure, or remove the `Shared` keyword from the procedure declaration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0d44-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d0d44-108">See Also</span></span>  
 [<span data-ttu-id="d0d44-109">Zuweisen von Objektvariablen</span><span class="sxs-lookup"><span data-stu-id="d0d44-109">Object Variable Assignment</span></span>](../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)  
 [<span data-ttu-id="d0d44-110">Me, My, MyBase und MyClass</span><span class="sxs-lookup"><span data-stu-id="d0d44-110">Me, My, MyBase, and MyClass</span></span>](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [<span data-ttu-id="d0d44-111">Grundlagen der Vererbung</span><span class="sxs-lookup"><span data-stu-id="d0d44-111">Inheritance Basics</span></span>](../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
