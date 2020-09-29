---
title: -nowarn
ms.date: 07/20/2015
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
ms.openlocfilehash: cde96fff975a65d6303ee62e6a811bfd83d5ff97
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91097682"
---
# <a name="-nowarn"></a><span data-ttu-id="fc2ac-102">-nowarn</span><span class="sxs-lookup"><span data-stu-id="fc2ac-102">-nowarn</span></span>

<span data-ttu-id="fc2ac-103">Unterdrückt die Compilerfunktion zum Generieren von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc2ac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc2ac-104">Syntax</span></span>  
  
```console  
-nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fc2ac-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="fc2ac-105">Arguments</span></span>  
  
|<span data-ttu-id="fc2ac-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="fc2ac-106">Term</span></span>|<span data-ttu-id="fc2ac-107">Definition</span><span class="sxs-lookup"><span data-stu-id="fc2ac-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="fc2ac-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-108">Optional.</span></span> <span data-ttu-id="fc2ac-109">Dies ist eine durch Trennzeichen getrennte Liste der Warnungs-ID-Nummern, die vom Compiler unterdrückt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="fc2ac-110">Wenn die Warnungs-IDs nicht angegeben werden, werden alle Warnungen unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc2ac-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fc2ac-111">Remarks</span></span>  

 <span data-ttu-id="fc2ac-112">Die Option `-nowarn` bewirkt, dass der Compiler kein Warnungen generiert.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-112">The `-nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="fc2ac-113">Fügen Sie nach der Option `-nowarn` und einem darauf folgenden Doppelpunkt die Warnungs-ID ein, um eine einzelne Warnung zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-113">To suppress an individual warning, supply the warning ID to the `-nowarn` option following the colon.</span></span> <span data-ttu-id="fc2ac-114">Trennen Sie mehrere Warnnummern durch ein Komma.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="fc2ac-115">Sie müssen lediglich den numerischen Teil des Warnungsbezeichners angeben.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="fc2ac-116">Geben Sie `-nowarn:42024` an, wenn Sie z. B. BC42024 unterdrücken möchten (Warnung für nicht verwendete lokale Variablen).</span><span class="sxs-lookup"><span data-stu-id="fc2ac-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `-nowarn:42024`.</span></span>  
  
 <span data-ttu-id="fc2ac-117">Weitere Informationen zu Warnungs-IDs finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="fc2ac-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="fc2ac-118">Festlegen von -nowarn in der integrierten Visual Studio-Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="fc2ac-118">To set -nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="fc2ac-119">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fc2ac-120">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-120">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="fc2ac-121">2.  Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-121">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="fc2ac-122">3.  Aktivieren Sie das Kontrollkästchen **Alle Warnungen deaktivieren**, um alle Warnungen zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-122">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="fc2ac-123">- oder -</span><span class="sxs-lookup"><span data-stu-id="fc2ac-123">- or -</span></span><br />     <span data-ttu-id="fc2ac-124">Klicken Sie in der Dropdownliste neben der Warnung auf **Keine**, um eine bestimmte Warnung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-124">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fc2ac-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc2ac-125">Example</span></span>  

 <span data-ttu-id="fc2ac-126">Mit dem folgenden Code wird `T2.vb` kompiliert, und es werden keine Warnungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-126">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```console
vbc -nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="fc2ac-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fc2ac-127">Example</span></span>  

 <span data-ttu-id="fc2ac-128">Mit dem folgenden Code wird `T2.vb` kompiliert, und es werden keine Warnungen für nicht verwendete lokale Variablen (42024) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fc2ac-128">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```console
vbc -nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fc2ac-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fc2ac-129">See also</span></span>

- [<span data-ttu-id="fc2ac-130">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="fc2ac-130">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="fc2ac-131">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="fc2ac-131">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
- [<span data-ttu-id="fc2ac-132">Configuring Warnings in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="fc2ac-132">Configuring Warnings in Visual Basic</span></span>](/visualstudio/ide/configuring-warnings-in-visual-basic)
