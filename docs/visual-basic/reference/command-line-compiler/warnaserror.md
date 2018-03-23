---
title: -Warnaserror (Visual Basic)
ms.date: 03/13/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ae8ed68045529e626f2788f854d8e6a6933e7e2
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/22/2018
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="07fa1-102">-Warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07fa1-102">-warnaserror (Visual Basic)</span></span>
<span data-ttu-id="07fa1-103">Bewirkt, dass der Compiler das erste Vorkommen einer Warnung als Fehler behandeln.</span><span class="sxs-lookup"><span data-stu-id="07fa1-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07fa1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="07fa1-104">Syntax</span></span>  
  
```  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="07fa1-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="07fa1-105">Arguments</span></span>  
  
|<span data-ttu-id="07fa1-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="07fa1-106">Term</span></span>|<span data-ttu-id="07fa1-107">Definition</span><span class="sxs-lookup"><span data-stu-id="07fa1-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="07fa1-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="07fa1-108">+ &#124; -</span></span>|<span data-ttu-id="07fa1-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="07fa1-109">Optional.</span></span> <span data-ttu-id="07fa1-110">Standardmäßig `-warnaserror-` ist faktisch; Warnungen verhindern nicht, dass den Compiler aus, erzeugt eine Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="07fa1-110">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="07fa1-111">Die `-warnaserror` Option, die die gleiche ist als `-warnaserror+`, bewirkt, dass Warnungen als Fehler behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="07fa1-111">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="07fa1-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="07fa1-112">Optional.</span></span> <span data-ttu-id="07fa1-113">Durch Trennzeichen getrennte Liste von Warnungs-ID, der Nummern der `-warnaserror` Option gilt.</span><span class="sxs-lookup"><span data-stu-id="07fa1-113">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="07fa1-114">Wenn Sie keine Warnung-ID angegeben ist, die `-warnaserror` Option gilt für alle Warnungen.</span><span class="sxs-lookup"><span data-stu-id="07fa1-114">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07fa1-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="07fa1-115">Remarks</span></span>  
 <span data-ttu-id="07fa1-116">Die `-warnaserror` Option, um alle Warnungen als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="07fa1-116">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="07fa1-117">Alle Nachrichten, die in der Regel gemeldet worden wären, wie Warnungen stattdessen als Fehler gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="07fa1-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="07fa1-118">Der Compiler meldet weitere Vorkommen des gleichen Warnung als Warnungen.</span><span class="sxs-lookup"><span data-stu-id="07fa1-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="07fa1-119">Standardmäßig `-warnaserror-` ist aktiv, wodurch die Warnungen, um nur Informationszwecken gemeldet werden soll.</span><span class="sxs-lookup"><span data-stu-id="07fa1-119">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="07fa1-120">Die `-warnaserror` Option, die die gleiche ist als `-warnaserror+`, bewirkt, dass Warnungen als Fehler behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="07fa1-120">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="07fa1-121">Wenn Sie nur einige bestimmte Warnungen als Fehler behandelt werden soll, können Sie eine durch Trennzeichen getrennte Liste mit Warnungsnummern als Fehler behandeln angeben.</span><span class="sxs-lookup"><span data-stu-id="07fa1-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="07fa1-122">Die `-warnaserror` Option steuert nicht die Anzeige von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="07fa1-122">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="07fa1-123">Verwenden der [- Nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) Option zum Deaktivieren von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="07fa1-123">Use the [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="07fa1-124">-Warnaserror, um alle Warnungen als Fehler in der Visual Studio-IDE behandeln festlegen</span><span class="sxs-lookup"><span data-stu-id="07fa1-124">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="07fa1-125">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="07fa1-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="07fa1-126">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="07fa1-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="07fa1-127">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="07fa1-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="07fa1-128">3.  Stellen Sie sicher, dass die **deaktivieren Sie alle Warnungen** das Kontrollkästchen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="07fa1-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="07fa1-129">4.  Überprüfen Sie die **alle Warnungen als Fehler behandeln** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="07fa1-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="07fa1-130">-Warnaserror behandelt bestimmte Warnungen als Fehler in der Visual Studio-IDE festlegen</span><span class="sxs-lookup"><span data-stu-id="07fa1-130">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="07fa1-131">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="07fa1-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="07fa1-132">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="07fa1-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="07fa1-133">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="07fa1-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="07fa1-134">3.  Stellen Sie sicher, dass die **deaktivieren Sie alle Warnungen** das Kontrollkästchen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="07fa1-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="07fa1-135">4.  Stellen Sie sicher, dass die **alle Warnungen als Fehler behandeln** das Kontrollkästchen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="07fa1-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="07fa1-136">5.  Wählen Sie **Fehler** aus der **Benachrichtigung** Spalte neben der Warnung, die als Fehler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="07fa1-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="07fa1-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07fa1-137">Example</span></span>  
 <span data-ttu-id="07fa1-138">Der folgende code kompiliert `In.vb` und leitet den Compiler einen Fehler für das erste Vorkommen des jede Warnung anzuzeigen, es findet.</span><span class="sxs-lookup"><span data-stu-id="07fa1-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="07fa1-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07fa1-139">Example</span></span>  
 <span data-ttu-id="07fa1-140">Der folgende code kompiliert `T2.vb` und nur die Warnung für nicht verwendete lokale Variablen (42024) als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="07fa1-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="07fa1-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07fa1-141">See Also</span></span>  
 [<span data-ttu-id="07fa1-142">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="07fa1-142">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="07fa1-143">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="07fa1-143">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="07fa1-144">Konfigurieren von Warnungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="07fa1-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
