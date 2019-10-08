---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 880fdf4931dadea547d64d0506bd3e978956468e
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005401"
---
# <a name="-nowarn"></a><span data-ttu-id="6efb0-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="6efb0-102">-nowarn</span></span>
<span data-ttu-id="6efb0-103">Unterdrückt die Compilerfunktion zum Generieren von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="6efb0-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6efb0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6efb0-104">Syntax</span></span>  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="6efb0-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6efb0-105">Arguments</span></span>  
  
|<span data-ttu-id="6efb0-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="6efb0-106">Term</span></span>|<span data-ttu-id="6efb0-107">Definition</span><span class="sxs-lookup"><span data-stu-id="6efb0-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="6efb0-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="6efb0-108">Optional.</span></span> <span data-ttu-id="6efb0-109">Eine durch Trennzeichen getrennte Liste der Warnungs-ID-Nummern, die vom Compiler unterdrückt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6efb0-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="6efb0-110">Wenn die Warnungs-IDs nicht angegeben werden, werden alle Warnungen unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="6efb0-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6efb0-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6efb0-111">Remarks</span></span>  
 <span data-ttu-id="6efb0-112">Die Option "`-nowarn`" bewirkt, dass der Compiler keine Warnungen generiert.</span><span class="sxs-lookup"><span data-stu-id="6efb0-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="6efb0-113">Um eine einzelne Warnung zu unterdrücken, geben Sie die Warnungs-ID an die `-nowarn`-Option nach dem Doppelpunkt an.</span><span class="sxs-lookup"><span data-stu-id="6efb0-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="6efb0-114">Trennen Sie mehrere Warnungs Nummern durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="6efb0-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="6efb0-115">Sie müssen nur den numerischen Teil des Warnungs Bezeichners angeben.</span><span class="sxs-lookup"><span data-stu-id="6efb0-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="6efb0-116">Wenn Sie z. b. BC42024 unterdrücken möchten, geben Sie die Warnung für nicht verwendete lokale Variablen an, `-nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="6efb0-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="6efb0-117">Weitere Informationen zu den Warnungs-ID-Nummern finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6efb0-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="6efb0-118">To Set-nowarn in der integrierten Entwicklungsumgebung von Visual Studio</span><span class="sxs-lookup"><span data-stu-id="6efb0-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="6efb0-119">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="6efb0-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="6efb0-120">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="6efb0-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="6efb0-121">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="6efb0-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="6efb0-122">3.  Aktivieren Sie das Kontrollkästchen **alle Warnungen deaktivieren** , um alle Warnungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6efb0-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="6efb0-123">- oder -</span><span class="sxs-lookup"><span data-stu-id="6efb0-123">- or -</span></span><br />     <span data-ttu-id="6efb0-124">Um eine bestimmte Warnung zu deaktivieren, klicken Sie in der Dropdown Liste neben der Warnung auf **keine** .</span><span class="sxs-lookup"><span data-stu-id="6efb0-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="6efb0-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6efb0-125">Example</span></span>  
 <span data-ttu-id="6efb0-126">Der folgende Code kompiliert `T2.vb` und zeigt keine Warnungen an.</span><span class="sxs-lookup"><span data-stu-id="6efb0-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="6efb0-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6efb0-127">Example</span></span>  
 <span data-ttu-id="6efb0-128">Der folgende Code kompiliert `T2.vb` und zeigt keine Warnungen für nicht verwendete lokale Variablen an (42024).</span><span class="sxs-lookup"><span data-stu-id="6efb0-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="6efb0-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6efb0-129">See also</span></span>

- [<span data-ttu-id="6efb0-130">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="6efb0-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="6efb0-131">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="6efb0-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="6efb0-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6efb0-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
