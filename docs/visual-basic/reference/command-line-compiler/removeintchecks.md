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
ms.openlocfilehash: bea6ca24ea6da9000267e754d52fe0ca152f7d7f
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005227"
---
# <a name="-removeintchecks"></a><span data-ttu-id="41d6a-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="41d6a-102">-removeintchecks</span></span>
<span data-ttu-id="41d6a-103">Schaltet die Überlauf Fehlerüberprüfung für ganzzahlige Vorgänge ein oder aus.</span><span class="sxs-lookup"><span data-stu-id="41d6a-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41d6a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="41d6a-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="41d6a-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="41d6a-105">Arguments</span></span>  
  
|<span data-ttu-id="41d6a-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="41d6a-106">Term</span></span>|<span data-ttu-id="41d6a-107">Definition</span><span class="sxs-lookup"><span data-stu-id="41d6a-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="41d6a-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="41d6a-108">`+` &#124; `-`</span></span>|<span data-ttu-id="41d6a-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="41d6a-109">Optional.</span></span> <span data-ttu-id="41d6a-110">Die Option `-removeintchecks-` bewirkt, dass der Compiler alle ganzzahligen Berechnungen auf Überlauf Fehler prüft.</span><span class="sxs-lookup"><span data-stu-id="41d6a-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="41d6a-111">Die Standardeinstellung ist `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="41d6a-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="41d6a-112">Wenn Sie `-removeintchecks` oder `-removeintchecks+` angeben, wird die Fehlerüberprüfung verhindert, und ganz Zahl Berechnungen können beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="41d6a-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="41d6a-113">Ohne Fehlerüberprüfung und bei einem Überlauf der Datentyp Kapazitäten können jedoch falsche Ergebnisse gespeichert werden, ohne dass ein Fehler ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="41d6a-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="41d6a-114">Zum Festlegen von "-removeintchecks" in der integrierten Entwicklungsumgebung von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="41d6a-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="41d6a-115">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="41d6a-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="41d6a-116">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="41d6a-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="41d6a-117">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="41d6a-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="41d6a-118">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="41d6a-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="41d6a-119">4.  Ändern Sie den Wert des Kontrollkästchens **ganzzahlige Überlauf entfernen** .</span><span class="sxs-lookup"><span data-stu-id="41d6a-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="41d6a-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="41d6a-120">Example</span></span>  
 <span data-ttu-id="41d6a-121">Mit dem folgenden Code wird `Test.vb` kompiliert und die ganzzahlige Überlauf Fehlerüberprüfung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="41d6a-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="41d6a-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="41d6a-122">See also</span></span>

- [<span data-ttu-id="41d6a-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="41d6a-123">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="41d6a-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="41d6a-124">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
