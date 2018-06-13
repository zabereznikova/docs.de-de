---
title: -removeintchecks
ms.date: 03/13/2018
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
ms.openlocfilehash: 26485fe2ba3f5647266147744cbe53f978694a9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33656125"
---
# <a name="-removeintchecks"></a><span data-ttu-id="b124e-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="b124e-102">-removeintchecks</span></span>
<span data-ttu-id="b124e-103">Aktiviert die Überlauf-Fehler beim Überprüfen der für Ganzzahloperationen ein- oder ausschalten.</span><span class="sxs-lookup"><span data-stu-id="b124e-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b124e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b124e-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="b124e-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b124e-105">Arguments</span></span>  
  
|<span data-ttu-id="b124e-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="b124e-106">Term</span></span>|<span data-ttu-id="b124e-107">Definition</span><span class="sxs-lookup"><span data-stu-id="b124e-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="b124e-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="b124e-108">`+` &#124; `-`</span></span>|<span data-ttu-id="b124e-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="b124e-109">Optional.</span></span> <span data-ttu-id="b124e-110">Die `-removeintchecks-` Option veranlasst den Compiler, überprüfen Sie alle Ganzzahl Berechnungen auf Ganzzahlüberlauf-Fehler.</span><span class="sxs-lookup"><span data-stu-id="b124e-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="b124e-111">Die Standardeinstellung ist `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="b124e-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="b124e-112">Angeben von `-removeintchecks` oder `-removeintchecks+` verhindert die Überprüfung von Fehlern und Integer Berechnungen schneller machen können.</span><span class="sxs-lookup"><span data-stu-id="b124e-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="b124e-113">Allerdings ohne Überprüfung von Fehlern, und wenn der Typ der Datenkapazität überlaufen, möglicherweise falsche Ergebnisse gespeichert werden, ohne einen Fehler auszulösen.</span><span class="sxs-lookup"><span data-stu-id="b124e-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="b124e-114">-Removeintchecks in der integrierten Visual Studio-Entwicklungsumgebung fest</span><span class="sxs-lookup"><span data-stu-id="b124e-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="b124e-115">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="b124e-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="b124e-116">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b124e-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="b124e-117">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="b124e-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="b124e-118">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="b124e-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="b124e-119">4.  Ändern Sie den Wert, der die **Überprüfungen auf Ganzzahlüberlauf entfernen** Feld.</span><span class="sxs-lookup"><span data-stu-id="b124e-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b124e-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b124e-120">Example</span></span>  
 <span data-ttu-id="b124e-121">Der folgende code kompiliert `Test.vb` und Ganzzahlüberlauf Überprüfung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b124e-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="b124e-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b124e-122">See Also</span></span>  
 [<span data-ttu-id="b124e-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="b124e-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="b124e-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="b124e-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
