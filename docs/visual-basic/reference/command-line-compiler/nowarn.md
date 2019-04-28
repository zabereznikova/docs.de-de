---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: 31f7a2b771cfa1bcc6581d720aa0de3505aec826
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788985"
---
# <a name="-nowarn"></a><span data-ttu-id="e30a1-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="e30a1-102">-nowarn</span></span>
<span data-ttu-id="e30a1-103">Unterdrückt die Compilerfunktion zum Generieren von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="e30a1-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e30a1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e30a1-104">Syntax</span></span>  
  
```  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e30a1-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e30a1-105">Arguments</span></span>  
  
|<span data-ttu-id="e30a1-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="e30a1-106">Term</span></span>|<span data-ttu-id="e30a1-107">Definition</span><span class="sxs-lookup"><span data-stu-id="e30a1-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="e30a1-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e30a1-108">Optional.</span></span> <span data-ttu-id="e30a1-109">Durch Trennzeichen getrennte Liste mit der ID-Warnzahlen, die der Compiler unterdrücken soll.</span><span class="sxs-lookup"><span data-stu-id="e30a1-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="e30a1-110">Wenn keine Warnungs-IDs angegeben sind, werden alle Warnungen unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="e30a1-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e30a1-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e30a1-111">Remarks</span></span>  
 <span data-ttu-id="e30a1-112">Die `-nowarn` Option bewirkt, dass den Compiler keine Warnungen generiert werden.</span><span class="sxs-lookup"><span data-stu-id="e30a1-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="e30a1-113">Um eine einzelne Warnung zu unterdrücken, geben Sie die ID der Warnung, die die `-nowarn` Option, die hinter dem Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="e30a1-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="e30a1-114">Trennen Sie mehrere Warnungsnummern jeweils durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="e30a1-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="e30a1-115">Sie müssen nur den numerischen Teil des Warnungsbezeichners angeben.</span><span class="sxs-lookup"><span data-stu-id="e30a1-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="e30a1-116">Wenn Sie BC42024, die Warnung für nicht verwendete lokale Variablen, unterdrücken möchten, z. B. Geben Sie `-nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="e30a1-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="e30a1-117">Weitere Informationen zu die Warnung-ID-Nummern, finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e30a1-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="e30a1-118">-Nowarn in der integrierten Entwicklungsumgebung von Visual Studio festlegen.</span><span class="sxs-lookup"><span data-stu-id="e30a1-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e30a1-119">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="e30a1-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e30a1-120">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="e30a1-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="e30a1-121">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="e30a1-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="e30a1-122">3.  Wählen Sie die **alle Warnungen deaktivieren** Kontrollkästchen, um alle Warnungen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e30a1-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="e30a1-123">- oder -</span><span class="sxs-lookup"><span data-stu-id="e30a1-123">- or -</span></span><br />     <span data-ttu-id="e30a1-124">Um eine bestimmte Warnung zu deaktivieren, klicken Sie auf **keine** aus der Dropdown-Liste neben der Warnung.</span><span class="sxs-lookup"><span data-stu-id="e30a1-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e30a1-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e30a1-125">Example</span></span>  
 <span data-ttu-id="e30a1-126">Der folgende code kompiliert `T2.vb` und keine Warnungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e30a1-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="e30a1-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e30a1-127">Example</span></span>  
 <span data-ttu-id="e30a1-128">Der folgende code kompiliert `T2.vb` und die Warnungen für nicht verwendete lokale Variablen (42024) nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e30a1-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e30a1-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e30a1-129">See also</span></span>

- [<span data-ttu-id="e30a1-130">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="e30a1-130">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="e30a1-131">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="e30a1-131">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="e30a1-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e30a1-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
