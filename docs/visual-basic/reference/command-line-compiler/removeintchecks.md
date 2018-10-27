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
ms.openlocfilehash: f061497083dc23fd07f61108938a4129c0af5f3a
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2018
ms.locfileid: "50188529"
---
# <a name="-removeintchecks"></a><span data-ttu-id="79267-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="79267-102">-removeintchecks</span></span>
<span data-ttu-id="79267-103">Aktiviert die Überlauf-fehlerüberprüfung für Ganzzahloperationen ein- oder ausschalten.</span><span class="sxs-lookup"><span data-stu-id="79267-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79267-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="79267-104">Syntax</span></span>  
  
```  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="79267-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="79267-105">Arguments</span></span>  
  
|<span data-ttu-id="79267-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="79267-106">Term</span></span>|<span data-ttu-id="79267-107">Definition</span><span class="sxs-lookup"><span data-stu-id="79267-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="79267-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="79267-108">`+` &#124; `-`</span></span>|<span data-ttu-id="79267-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="79267-109">Optional.</span></span> <span data-ttu-id="79267-110">Die `-removeintchecks-` Option veranlasst den Compiler, alle integerberechnungen auf Ganzzahlüberlauf-Fehler zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="79267-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="79267-111">Die Standardeinstellung ist `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="79267-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="79267-112">Angeben von `-removeintchecks` oder `-removeintchecks+` verhindert die Überprüfung von Fehlern und können ganzzahlige Berechnungen zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="79267-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="79267-113">Allerdings ohne Überprüfung von Fehlern, und wenn datenkapazitäten auf Typ ist ein Überlauf aufgetreten sind, können falsche Ergebnisse gespeichert werden, ohne dass ein Fehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="79267-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="79267-114">-Removeintchecks in der integrierten Entwicklungsumgebung von Visual Studio festlegen.</span><span class="sxs-lookup"><span data-stu-id="79267-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="79267-115">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="79267-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="79267-116">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="79267-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="79267-117">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="79267-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="79267-118">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="79267-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="79267-119">4.  Ändern Sie den Wert, der die **Überprüfungen auf Ganzzahlüberlauf entfernen** Feld.</span><span class="sxs-lookup"><span data-stu-id="79267-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="79267-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="79267-120">Example</span></span>  
 <span data-ttu-id="79267-121">Der folgende code kompiliert `Test.vb` Ganzzahlüberlauf Überprüfung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="79267-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="79267-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="79267-122">See Also</span></span>  
 [<span data-ttu-id="79267-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="79267-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="79267-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="79267-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
