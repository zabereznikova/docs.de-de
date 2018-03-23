---
title: -removeintchecks
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- -removeintchecks
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25a14ffaca6e61c6e3306f8ff58de441e2ba2ade
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-removeintchecks"></a><span data-ttu-id="53296-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="53296-102">-removeintchecks</span></span>
<span data-ttu-id="53296-103">Aktiviert die Überlauf-Fehler beim Überprüfen der für Ganzzahloperationen ein- oder ausschalten.</span><span class="sxs-lookup"><span data-stu-id="53296-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53296-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="53296-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="53296-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="53296-105">Arguments</span></span>  
  
|<span data-ttu-id="53296-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="53296-106">Term</span></span>|<span data-ttu-id="53296-107">Definition</span><span class="sxs-lookup"><span data-stu-id="53296-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="53296-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="53296-108">`+` &#124; `-`</span></span>|<span data-ttu-id="53296-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="53296-109">Optional.</span></span> <span data-ttu-id="53296-110">Die `-removeintchecks-` Option veranlasst den Compiler, überprüfen Sie alle Ganzzahl Berechnungen auf Ganzzahlüberlauf-Fehler.</span><span class="sxs-lookup"><span data-stu-id="53296-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="53296-111">Die Standardeinstellung ist `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="53296-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="53296-112">Angeben von `-removeintchecks` oder `-removeintchecks+` verhindert die Überprüfung von Fehlern und Integer Berechnungen schneller machen können.</span><span class="sxs-lookup"><span data-stu-id="53296-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="53296-113">Allerdings ohne Überprüfung von Fehlern, und wenn der Typ der Datenkapazität überlaufen, möglicherweise falsche Ergebnisse gespeichert werden, ohne einen Fehler auszulösen.</span><span class="sxs-lookup"><span data-stu-id="53296-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="53296-114">-Removeintchecks in der integrierten Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="53296-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="53296-115">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="53296-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="53296-116">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="53296-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="53296-117">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="53296-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="53296-118">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="53296-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="53296-119">4.  Ändern Sie den Wert, der die **Überprüfungen auf Ganzzahlüberlauf entfernen** Feld.</span><span class="sxs-lookup"><span data-stu-id="53296-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="53296-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53296-120">Example</span></span>  
 <span data-ttu-id="53296-121">Der folgende code kompiliert `Test.vb` und Ganzzahlüberlauf Überprüfung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="53296-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="53296-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="53296-122">See Also</span></span>  
 [<span data-ttu-id="53296-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="53296-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="53296-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="53296-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
