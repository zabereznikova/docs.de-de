---
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: f9ca5575e2a042d68fc490494f2e86991d58b80c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351707"
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="0c494-102">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0c494-102">-warnaserror (Visual Basic)</span></span>
<span data-ttu-id="0c494-103">Bewirkt, dass der Compiler das erste Vorkommen einer Warnung als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="0c494-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c494-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="0c494-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="0c494-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="0c494-105">Arguments</span></span>  
  
|<span data-ttu-id="0c494-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="0c494-106">Term</span></span>|<span data-ttu-id="0c494-107">Definition</span><span class="sxs-lookup"><span data-stu-id="0c494-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="0c494-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="0c494-108">+ &#124; -</span></span>|<span data-ttu-id="0c494-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0c494-109">Optional.</span></span> <span data-ttu-id="0c494-110">Standardmäßig ist `-warnaserror-` aktiviert, sodass Warnungen den Compiler nicht daran hindern, eine Ausgabedatei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c494-110">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="0c494-111">Die `-warnaserror`-Option, die mit `-warnaserror+` identisch ist, bewirkt, dass Warnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="0c494-111">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="0c494-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="0c494-112">Optional.</span></span> <span data-ttu-id="0c494-113">Mit Kommas als Trennzeichen getrennte Liste der Warnungs-ID-Nummern, für die die `-warnaserror`-Option gilt.</span><span class="sxs-lookup"><span data-stu-id="0c494-113">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="0c494-114">Ist keine Warnungs-ID angegeben, gilt die `-warnaserror`-Option für alle Warnungen.</span><span class="sxs-lookup"><span data-stu-id="0c494-114">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0c494-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="0c494-115">Remarks</span></span>  
 <span data-ttu-id="0c494-116">Die `-warnaserror`-Option bewirkt, dass alle Warnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="0c494-116">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="0c494-117">Alle Nachrichten, die in der Regel als Warnungen gemeldet worden wären, werden stattdessen als Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="0c494-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="0c494-118">Der Compiler meldet weitere Vorkommen derselben Warnung als Warnungen.</span><span class="sxs-lookup"><span data-stu-id="0c494-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="0c494-119">Standardmäßig ist `-warnaserror-` aktiv, sodass Warnungen nur als Informationen gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="0c494-119">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="0c494-120">Die `-warnaserror`-Option, die mit `-warnaserror+` identisch ist, bewirkt, dass Warnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="0c494-120">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="0c494-121">Wenn nur bestimmte Warnungen als Fehler behandelt werden sollen, können Sie eine durch Kommas als Trennzeichen getrennte Liste mit Warnungsnummern angeben, die als Fehler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0c494-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0c494-122">Die `-warnaserror`-Option steuert nicht, wie Warnungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="0c494-122">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="0c494-123">Verwenden Sie die [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)-Option, um Warnungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="0c494-123">Use the [-nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="0c494-124">So legen Sie „-warnaserror“ so fest, dass alle Warnungen in der Visual Studio-IDE als Fehler behandelt werden</span><span class="sxs-lookup"><span data-stu-id="0c494-124">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="0c494-125">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0c494-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0c494-126">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0c494-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="0c494-127">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="0c494-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0c494-128">3.  Deaktivieren Sie das Kontrollkästchen **Alle Warnungen deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="0c494-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="0c494-129">4.  Aktivieren Sie das Kontrollkästchen **Alle Warnungen als Fehler behandeln**.</span><span class="sxs-lookup"><span data-stu-id="0c494-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="0c494-130">So legen Sie „-warnaserror“ so fest, dass bestimmte Warnungen in der Visual Studio-IDE als Fehler behandelt werden</span><span class="sxs-lookup"><span data-stu-id="0c494-130">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="0c494-131">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="0c494-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="0c494-132">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="0c494-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="0c494-133">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="0c494-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="0c494-134">3.  Deaktivieren Sie das Kontrollkästchen **Alle Warnungen deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="0c494-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="0c494-135">4.  Deaktivieren Sie das Kontrollkästchen **Alle Warnungen als Fehler behandeln**.</span><span class="sxs-lookup"><span data-stu-id="0c494-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="0c494-136">5.  Wählen Sie **Fehler** in der **Benachrichtigung**-Spalte neben der Warnung aus, die als Fehler behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="0c494-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0c494-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c494-137">Example</span></span>  
 <span data-ttu-id="0c494-138">Im folgende Code wird `In.vb` kompiliert und wird der Compiler angewiesen, für das erste Vorkommen jeder von ihm gefundenen Warnung einen Fehler anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0c494-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="0c494-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c494-139">Example</span></span>  
 <span data-ttu-id="0c494-140">Im folgenden Code wird `T2.vb` kompiliert und nur die Warnung für nicht verwendete lokale Variablen (42024) als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="0c494-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="0c494-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c494-141">See also</span></span>

- [<span data-ttu-id="0c494-142">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="0c494-142">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="0c494-143">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="0c494-143">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="0c494-144">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="0c494-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
