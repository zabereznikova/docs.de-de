---
title: /warnaserror (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 04b79b3d14a9c4a9f9721860cd1ed44032dfa5d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="warnaserror-visual-basic"></a><span data-ttu-id="0fa73-102">/warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0fa73-102">/warnaserror (Visual Basic)</span></span>
<span data-ttu-id="0fa73-103">Bewirkt, dass der Compiler das erste Vorkommen einer Warnung als Fehler behandeln.</span><span class="sxs-lookup"><span data-stu-id="0fa73-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fa73-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0fa73-104">Syntax</span></span>  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0fa73-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0fa73-105">Arguments</span></span>  
  
|<span data-ttu-id="0fa73-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="0fa73-106">Term</span></span>|<span data-ttu-id="0fa73-107">Definition</span><span class="sxs-lookup"><span data-stu-id="0fa73-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="0fa73-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="0fa73-108">+ &#124; -</span></span>|<span data-ttu-id="0fa73-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0fa73-109">Optional.</span></span> <span data-ttu-id="0fa73-110">Standardmäßig `/warnaserror-` ist faktisch; Warnungen verhindern nicht, dass den Compiler aus, erzeugt eine Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="0fa73-110">By default, `/warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="0fa73-111">Die `/warnaserror` Option, die die gleiche ist als `/warnaserror+`, bewirkt, dass Warnungen als Fehler behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0fa73-111">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="0fa73-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0fa73-112">Optional.</span></span> <span data-ttu-id="0fa73-113">Durch Trennzeichen getrennte Liste von Warnungs-ID, der Nummern der `/warnaserror` Option gilt.</span><span class="sxs-lookup"><span data-stu-id="0fa73-113">Comma-delimited list of the warning ID numbers to which the `/warnaserror` option applies.</span></span> <span data-ttu-id="0fa73-114">Wenn Sie keine Warnung-ID angegeben ist, die `/warnaserror` Option gilt für alle Warnungen.</span><span class="sxs-lookup"><span data-stu-id="0fa73-114">If no warning ID is specified, the `/warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0fa73-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0fa73-115">Remarks</span></span>  
 <span data-ttu-id="0fa73-116">Die `/warnaserror` Option, um alle Warnungen als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="0fa73-116">The `/warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="0fa73-117">Alle Nachrichten, die in der Regel gemeldet worden wären, wie Warnungen stattdessen als Fehler gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="0fa73-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="0fa73-118">Der Compiler meldet weitere Vorkommen des gleichen Warnung als Warnungen.</span><span class="sxs-lookup"><span data-stu-id="0fa73-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="0fa73-119">Standardmäßig `/warnaserror-` ist aktiv, wodurch die Warnungen, um nur Informationszwecken gemeldet werden soll.</span><span class="sxs-lookup"><span data-stu-id="0fa73-119">By default, `/warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="0fa73-120">Die `/warnaserror` Option, die die gleiche ist als `/warnaserror+`, bewirkt, dass Warnungen als Fehler behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0fa73-120">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="0fa73-121">Wenn Sie nur einige bestimmte Warnungen als Fehler behandelt werden soll, können Sie eine durch Trennzeichen getrennte Liste mit Warnungsnummern als Fehler behandeln angeben.</span><span class="sxs-lookup"><span data-stu-id="0fa73-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0fa73-122">Die `/warnaserror` Option steuert nicht die Anzeige von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="0fa73-122">The `/warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="0fa73-123">Verwenden der [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) Option zum Deaktivieren von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="0fa73-123">Use the [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="0fa73-124">/ Warnaserror, um alle Warnungen als Fehler in der Visual Studio-IDE behandeln festlegen</span><span class="sxs-lookup"><span data-stu-id="0fa73-124">To set /warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="0fa73-125">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0fa73-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0fa73-126">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0fa73-126">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="0fa73-127">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="0fa73-127">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="0fa73-128">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="0fa73-128">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0fa73-129">3.  Stellen Sie sicher, dass die **deaktivieren Sie alle Warnungen** das Kontrollkästchen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0fa73-129">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="0fa73-130">4.  Überprüfen Sie die **alle Warnungen als Fehler behandeln** Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="0fa73-130">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="0fa73-131">Festzulegende/warnaserror bestimmte Warnungen in der Visual Studio-IDE als Fehler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0fa73-131">To set /warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="0fa73-132">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0fa73-132">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0fa73-133">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0fa73-133">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="0fa73-134">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="0fa73-134">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0fa73-135">3.  Stellen Sie sicher, dass die **deaktivieren Sie alle Warnungen** das Kontrollkästchen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0fa73-135">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="0fa73-136">4.  Stellen Sie sicher, dass die **alle Warnungen als Fehler behandeln** das Kontrollkästchen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="0fa73-136">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="0fa73-137">5.  Wählen Sie **Fehler** aus der **Benachrichtigung** Spalte neben der Warnung, die als Fehler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0fa73-137">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0fa73-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0fa73-138">Example</span></span>  
 <span data-ttu-id="0fa73-139">Der folgende code kompiliert `In.vb` und leitet den Compiler einen Fehler für das erste Vorkommen des jede Warnung anzuzeigen, es findet.</span><span class="sxs-lookup"><span data-stu-id="0fa73-139">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="0fa73-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0fa73-140">Example</span></span>  
 <span data-ttu-id="0fa73-141">Der folgende code kompiliert `T2.vb` und nur die Warnung für nicht verwendete lokale Variablen (42024) als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="0fa73-141">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0fa73-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0fa73-142">See Also</span></span>  
 [<span data-ttu-id="0fa73-143">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="0fa73-143">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="0fa73-144">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="0fa73-144">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [<span data-ttu-id="0fa73-145">Konfigurieren von Warnungen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0fa73-145">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
