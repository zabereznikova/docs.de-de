---
title: / warnaserror (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8ed72415a75860b34e37c2bf4fc686cdae37f69e
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="warnaserror-visual-basic"></a><span data-ttu-id="e8af9-102">/warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e8af9-102">/warnaserror (Visual Basic)</span></span>
<span data-ttu-id="e8af9-103">Der Compiler das erste Vorkommen einer Warnung als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="e8af9-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8af9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8af9-104">Syntax</span></span>  
  
```  
/warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e8af9-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e8af9-105">Arguments</span></span>  
  
|<span data-ttu-id="e8af9-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="e8af9-106">Term</span></span>|<span data-ttu-id="e8af9-107">Definition</span><span class="sxs-lookup"><span data-stu-id="e8af9-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="e8af9-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="e8af9-108">+ &#124; -</span></span>|<span data-ttu-id="e8af9-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="e8af9-109">Optional.</span></span> <span data-ttu-id="e8af9-110">In der Standardeinstellung `/warnaserror-` ist aktiviert; Warnungen verhindern nicht, dass den Compiler erzeugt eine Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="e8af9-110">By default, `/warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="e8af9-111">Die `/warnaserror` Option, die die gleiche wird als `/warnaserror+`, werden Warnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e8af9-111">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="e8af9-112">Optional.</span><span class="sxs-lookup"><span data-stu-id="e8af9-112">Optional.</span></span> <span data-ttu-id="e8af9-113">Durch Kommas getrennte Liste der ID der Warnung auf die Zahlen der `/warnaserror` Option gilt.</span><span class="sxs-lookup"><span data-stu-id="e8af9-113">Comma-delimited list of the warning ID numbers to which the `/warnaserror` option applies.</span></span> <span data-ttu-id="e8af9-114">Wenn keine Warnung-ID angegeben wird, die `/warnaserror` Option gilt für alle Warnungen.</span><span class="sxs-lookup"><span data-stu-id="e8af9-114">If no warning ID is specified, the `/warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8af9-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8af9-115">Remarks</span></span>  
 <span data-ttu-id="e8af9-116">Die `/warnaserror` Option alle Warnungen als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="e8af9-116">The `/warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="e8af9-117">Alle Nachrichten, die in der Regel gemeldet werden, wie Warnungen stattdessen als Fehler gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="e8af9-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="e8af9-118">Der Compiler meldet nachfolgende Vorkommen der gleichen Warnung als Warnungen.</span><span class="sxs-lookup"><span data-stu-id="e8af9-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="e8af9-119">In der Standardeinstellung `/warnaserror-` ist gültig, wodurch die Warnungen, um nur zu Informationszwecken werden.</span><span class="sxs-lookup"><span data-stu-id="e8af9-119">By default, `/warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="e8af9-120">Die `/warnaserror` Option, die die gleiche wird als `/warnaserror+`, werden Warnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="e8af9-120">The `/warnaserror` option, which is the same as `/warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="e8af9-121">Wenn Sie nur einige bestimmte Warnungen als Fehler behandelt werden soll, können Sie eine durch Trennzeichen getrennte Liste von Warnungsnummern als Fehler behandelt angeben.</span><span class="sxs-lookup"><span data-stu-id="e8af9-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e8af9-122">Die `/warnaserror` Option steuert nicht die Anzeige von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="e8af9-122">The `/warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="e8af9-123">Verwenden der [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) Option zum Deaktivieren von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="e8af9-123">Use the [/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="e8af9-124">/ Warnaserror behandelt alle Warnungen als Fehler in der Visual Studio-IDE fest</span><span class="sxs-lookup"><span data-stu-id="e8af9-124">To set /warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="e8af9-125">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e8af9-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e8af9-126">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e8af9-126">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="e8af9-127">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="e8af9-127">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="e8af9-128">2.  Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="e8af9-128">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="e8af9-129">3.  Stellen Sie sicher, dass die **alle Warnungen deaktivieren** das Kontrollkästchen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e8af9-129">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="e8af9-130">4.  Überprüfen Sie die **alle Warnungen als Fehler behandeln** das Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="e8af9-130">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="e8af9-131">Festlegen von/warnaserror, bestimmte Warnungen als Fehler in der Visual Studio-IDE zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="e8af9-131">To set /warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="e8af9-132">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e8af9-132">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e8af9-133">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e8af9-133">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="e8af9-134">2.  Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="e8af9-134">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="e8af9-135">3.  Stellen Sie sicher, dass die **alle Warnungen deaktivieren** das Kontrollkästchen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e8af9-135">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="e8af9-136">4.  Stellen Sie sicher, dass die **alle Warnungen als Fehler behandeln** das Kontrollkästchen deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e8af9-136">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="e8af9-137">5.  Wählen Sie **Fehler** aus der **Benachrichtigung** Spalte neben der Warnung, die als Fehler behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8af9-137">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e8af9-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8af9-138">Example</span></span>  
 <span data-ttu-id="e8af9-139">Der folgende code kompiliert `In.vb` und leitet den Compiler einen Fehler für das erste Vorkommen eines jeder Warnung anzeigen gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="e8af9-139">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```  
vbc /warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="e8af9-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e8af9-140">Example</span></span>  
 <span data-ttu-id="e8af9-141">Der folgende code kompiliert `T2.vb` und nur die Warnung für nicht verwendete lokale Variablen (42024) wird als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="e8af9-141">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```  
vbc /warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e8af9-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8af9-142">See Also</span></span>  
 <span data-ttu-id="e8af9-143">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="e8af9-143">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="e8af9-144"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="e8af9-144"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="e8af9-145"> [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="e8af9-145"> [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span></span>
