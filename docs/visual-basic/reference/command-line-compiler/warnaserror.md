---
title: -warnaserror
ms.date: 03/13/2018
helpviewer_keywords:
- warnaserror compiler option [Visual Basic]
- /warnaserror compiler option [Visual Basic]
- -warnaserror compiler option [Visual Basic]
ms.assetid: 49819f1d-a1bd-4201-affe-5afe6d9712e1
ms.openlocfilehash: 94a8b43a891df9837925869e17fac4536a995264
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84414271"
---
# <a name="-warnaserror-visual-basic"></a><span data-ttu-id="801af-102">-warnaserror (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="801af-102">-warnaserror (Visual Basic)</span></span>
<span data-ttu-id="801af-103">Bewirkt, dass der Compiler das erste Vorkommen einer Warnung als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="801af-103">Causes the compiler to treat the first occurrence of a warning as an error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="801af-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="801af-104">Syntax</span></span>  
  
```console  
-warnaserror[+ | -][:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="801af-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="801af-105">Arguments</span></span>  
  
|<span data-ttu-id="801af-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="801af-106">Term</span></span>|<span data-ttu-id="801af-107">Definition</span><span class="sxs-lookup"><span data-stu-id="801af-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="801af-108">+ &#124; -</span><span class="sxs-lookup"><span data-stu-id="801af-108">+ &#124; -</span></span>|<span data-ttu-id="801af-109">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="801af-109">Optional.</span></span> <span data-ttu-id="801af-110">Standardmäßig ist `-warnaserror-` aktiviert, sodass Warnungen den Compiler nicht daran hindern, eine Ausgabedatei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="801af-110">By default, `-warnaserror-` is in effect; warnings do not prevent the compiler from producing an output file.</span></span> <span data-ttu-id="801af-111">Die `-warnaserror`-Option, die mit `-warnaserror+` identisch ist, bewirkt, dass Warnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="801af-111">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>|  
|`numberList`|<span data-ttu-id="801af-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="801af-112">Optional.</span></span> <span data-ttu-id="801af-113">Mit Kommas als Trennzeichen getrennte Liste der Warnungs-ID-Nummern, für die die `-warnaserror`-Option gilt.</span><span class="sxs-lookup"><span data-stu-id="801af-113">Comma-delimited list of the warning ID numbers to which the `-warnaserror` option applies.</span></span> <span data-ttu-id="801af-114">Ist keine Warnungs-ID angegeben, gilt die `-warnaserror`-Option für alle Warnungen.</span><span class="sxs-lookup"><span data-stu-id="801af-114">If no warning ID is specified, the `-warnaserror` option applies to all warnings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="801af-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="801af-115">Remarks</span></span>  
 <span data-ttu-id="801af-116">Die `-warnaserror`-Option bewirkt, dass alle Warnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="801af-116">The `-warnaserror` option treats all warnings as errors.</span></span> <span data-ttu-id="801af-117">Alle Nachrichten, die in der Regel als Warnungen gemeldet worden wären, werden stattdessen als Fehler gemeldet.</span><span class="sxs-lookup"><span data-stu-id="801af-117">Any messages that would ordinarily be reported as warnings are instead reported as errors.</span></span> <span data-ttu-id="801af-118">Der Compiler meldet weitere Vorkommen derselben Warnung als Warnungen.</span><span class="sxs-lookup"><span data-stu-id="801af-118">The compiler reports subsequent occurrences of the same warning as warnings.</span></span>  
  
 <span data-ttu-id="801af-119">Standardmäßig ist `-warnaserror-` aktiv, sodass Warnungen nur als Informationen gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="801af-119">By default, `-warnaserror-` is in effect, which causes the warnings to be informational only.</span></span> <span data-ttu-id="801af-120">Die `-warnaserror`-Option, die mit `-warnaserror+` identisch ist, bewirkt, dass Warnungen als Fehler behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="801af-120">The `-warnaserror` option, which is the same as `-warnaserror+`, causes warnings to be treated as errors.</span></span>  
  
 <span data-ttu-id="801af-121">Wenn nur bestimmte Warnungen als Fehler behandelt werden sollen, können Sie eine durch Kommas als Trennzeichen getrennte Liste mit Warnungsnummern angeben, die als Fehler behandelt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="801af-121">If you want only a few specific warnings to be treated as errors, you may specify a comma-separated list of warning numbers to treat as errors.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="801af-122">Die `-warnaserror`-Option steuert nicht, wie Warnungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="801af-122">The `-warnaserror` option does not control how warnings are displayed.</span></span> <span data-ttu-id="801af-123">Verwenden Sie die [-nowarn](nowarn.md)-Option, um Warnungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="801af-123">Use the [-nowarn](nowarn.md) option to disable warnings.</span></span>  
  
|<span data-ttu-id="801af-124">So legen Sie „-warnaserror“ so fest, dass alle Warnungen in der Visual Studio-IDE als Fehler behandelt werden</span><span class="sxs-lookup"><span data-stu-id="801af-124">To set -warnaserror to treat all warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="801af-125">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="801af-125">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="801af-126">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="801af-126">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="801af-127">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="801af-127">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="801af-128">3.  Deaktivieren Sie das Kontrollkästchen **Alle Warnungen deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="801af-128">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="801af-129">4.  Aktivieren Sie das Kontrollkästchen **Alle Warnungen als Fehler behandeln**.</span><span class="sxs-lookup"><span data-stu-id="801af-129">4.  Check the **Treat all warnings as errors** check box.</span></span>|  
  
|<span data-ttu-id="801af-130">So legen Sie „-warnaserror“ so fest, dass bestimmte Warnungen in der Visual Studio-IDE als Fehler behandelt werden</span><span class="sxs-lookup"><span data-stu-id="801af-130">To set -warnaserror to treat specific warnings as errors in the Visual Studio IDE</span></span>|  
|---|  
|<span data-ttu-id="801af-131">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="801af-131">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="801af-132">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="801af-132">On the **Project** menu, click **Properties**.</span></span><br /><span data-ttu-id="801af-133">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="801af-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="801af-134">3.  Deaktivieren Sie das Kontrollkästchen **Alle Warnungen deaktivieren**.</span><span class="sxs-lookup"><span data-stu-id="801af-134">3.  Make sure the **Disable all warnings** check box is unchecked.</span></span><br /><span data-ttu-id="801af-135">4.  Deaktivieren Sie das Kontrollkästchen **Alle Warnungen als Fehler behandeln**.</span><span class="sxs-lookup"><span data-stu-id="801af-135">4.  Make sure the **Treat all warnings as errors** check box is unchecked.</span></span><br /><span data-ttu-id="801af-136">5.  Wählen Sie **Fehler** in der **Benachrichtigung**-Spalte neben der Warnung aus, die als Fehler behandelt werden soll.</span><span class="sxs-lookup"><span data-stu-id="801af-136">5.  Select **Error** from the **Notification** column adjacent to the warning that should be treated as an error.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="801af-137">Beispiel</span><span class="sxs-lookup"><span data-stu-id="801af-137">Example</span></span>  
 <span data-ttu-id="801af-138">Im folgende Code wird `In.vb` kompiliert und wird der Compiler angewiesen, für das erste Vorkommen jeder von ihm gefundenen Warnung einen Fehler anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="801af-138">The following code compiles `In.vb` and directs the compiler to display an error for the first occurrence of every warning it finds.</span></span>  
  
```console
vbc -warnaserror in.vb  
```  
  
## <a name="example"></a><span data-ttu-id="801af-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="801af-139">Example</span></span>  
 <span data-ttu-id="801af-140">Im folgenden Code wird `T2.vb` kompiliert und nur die Warnung für nicht verwendete lokale Variablen (42024) als Fehler behandelt.</span><span class="sxs-lookup"><span data-stu-id="801af-140">The following code compiles `T2.vb` and treats only the warning for unused local variables (42024) as an error.</span></span>  
  
```console
vbc -warnaserror:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="801af-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="801af-141">See also</span></span>

- [<span data-ttu-id="801af-142">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="801af-142">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="801af-143">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="801af-143">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="801af-144">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="801af-144">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
