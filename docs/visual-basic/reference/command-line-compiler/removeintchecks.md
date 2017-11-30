---
title: /removeintchecks
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4e765f0007eea8e196b1a1b3b55b969c5b074b52
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="removeintchecks"></a><span data-ttu-id="2b311-102">/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="2b311-102">/removeintchecks</span></span>
<span data-ttu-id="2b311-103">Aktiviert die Überlauf-Fehler beim Überprüfen der für Ganzzahloperationen ein- oder ausschalten.</span><span class="sxs-lookup"><span data-stu-id="2b311-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b311-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b311-104">Syntax</span></span>  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="2b311-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="2b311-105">Arguments</span></span>  
  
|<span data-ttu-id="2b311-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="2b311-106">Term</span></span>|<span data-ttu-id="2b311-107">Definition</span><span class="sxs-lookup"><span data-stu-id="2b311-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="2b311-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="2b311-108">`+` &#124; `-`</span></span>|<span data-ttu-id="2b311-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="2b311-109">Optional.</span></span> <span data-ttu-id="2b311-110">Die `/removeintchecks-` Option veranlasst den Compiler, überprüfen Sie alle Ganzzahl Berechnungen auf Ganzzahlüberlauf-Fehler.</span><span class="sxs-lookup"><span data-stu-id="2b311-110">The `/removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="2b311-111">Die Standardeinstellung ist `/removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="2b311-111">The default is `/removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="2b311-112">Angeben von `/removeintchecks` oder `/removeintchecks+` verhindert die Überprüfung von Fehlern und Integer Berechnungen schneller machen können.</span><span class="sxs-lookup"><span data-stu-id="2b311-112">Specifying `/removeintchecks` or `/removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="2b311-113">Allerdings ohne Überprüfung von Fehlern, und wenn der Typ der Datenkapazität überlaufen, möglicherweise falsche Ergebnisse gespeichert werden, ohne einen Fehler auszulösen.</span><span class="sxs-lookup"><span data-stu-id="2b311-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="2b311-114">Zum Festlegen von/removeintchecks in Visual Studio integrierte Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="2b311-114">To set /removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="2b311-115">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="2b311-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="2b311-116">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2b311-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="2b311-117">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="2b311-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="2b311-118">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="2b311-118">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="2b311-119">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="2b311-119">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="2b311-120">4.  Ändern Sie den Wert, der die **Überprüfungen auf Ganzzahlüberlauf entfernen** Feld.</span><span class="sxs-lookup"><span data-stu-id="2b311-120">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2b311-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b311-121">Example</span></span>  
 <span data-ttu-id="2b311-122">Der folgende code kompiliert `Test.vb` und Ganzzahlüberlauf Überprüfung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2b311-122">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b311-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b311-123">See Also</span></span>  
 [<span data-ttu-id="2b311-124">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="2b311-124">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="2b311-125">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="2b311-125">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
