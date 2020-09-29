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
ms.openlocfilehash: ce1f24f25ea58cb6ddc2f5c582b6103d8f18d922
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91085164"
---
# <a name="-removeintchecks"></a><span data-ttu-id="67b92-102">-removeintchecks</span><span class="sxs-lookup"><span data-stu-id="67b92-102">-removeintchecks</span></span>

<span data-ttu-id="67b92-103">Aktiviert oder deaktiviert die Überprüfung auf Überlauffehler für Integervorgänge</span><span class="sxs-lookup"><span data-stu-id="67b92-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67b92-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="67b92-104">Syntax</span></span>  
  
```console  
-removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="67b92-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="67b92-105">Arguments</span></span>  
  
|<span data-ttu-id="67b92-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="67b92-106">Term</span></span>|<span data-ttu-id="67b92-107">Definition</span><span class="sxs-lookup"><span data-stu-id="67b92-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="67b92-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="67b92-108">`+` &#124; `-`</span></span>|<span data-ttu-id="67b92-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="67b92-109">Optional.</span></span> <span data-ttu-id="67b92-110">Die Option `-removeintchecks-` bewirkt, dass der Compiler alle Integerberechnungen auf Überlauffehler prüft.</span><span class="sxs-lookup"><span data-stu-id="67b92-110">The `-removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="67b92-111">Der Standardwert ist `-removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="67b92-111">The default is `-removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="67b92-112">Wenn Sie `-removeintchecks` oder `-removeintchecks+` angeben, wird die Fehlerüberprüfung verhindert, und Integerberechnungen können beschleunigt werden.</span><span class="sxs-lookup"><span data-stu-id="67b92-112">Specifying `-removeintchecks` or `-removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="67b92-113">Ohne Fehlerüberprüfung und bei einem Überlauf der Datentypkapazitäten können jedoch falsche Ergebnisse gespeichert werden, ohne dass ein Fehler ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="67b92-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="67b92-114">So legen Sie -removeintchecks in der Visual Studio-IDE fest</span><span class="sxs-lookup"><span data-stu-id="67b92-114">To set -removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="67b92-115">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="67b92-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="67b92-116">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="67b92-116">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="67b92-117">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="67b92-117">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="67b92-118">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="67b92-118">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="67b92-119">4.  Ändern Sie den Wert des Felds **Überprüfungen auf Ganzzahlüberlauf entfernen**.</span><span class="sxs-lookup"><span data-stu-id="67b92-119">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="67b92-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="67b92-120">Example</span></span>  

 <span data-ttu-id="67b92-121">Mit dem folgenden Code wird `Test.vb` kompiliert, und die Überprüfung auf Überlauffehler für Integerwerte wird deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="67b92-121">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```console
vbc -removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="67b92-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="67b92-122">See also</span></span>

- [<span data-ttu-id="67b92-123">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="67b92-123">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="67b92-124">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="67b92-124">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
