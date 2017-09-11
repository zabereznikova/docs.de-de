---
title: / nowarn | Microsoft-Dokumentation
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
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: 15
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
ms.openlocfilehash: 308bf24c2a397a75f36b97062dde7380b90c8994
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="nowarn"></a><span data-ttu-id="9bb78-102">/nowarn</span><span class="sxs-lookup"><span data-stu-id="9bb78-102">/nowarn</span></span>
<span data-ttu-id="9bb78-103">Unterdrückt die Compilerfunktion zum Generieren von Warnungen.</span><span class="sxs-lookup"><span data-stu-id="9bb78-103">Suppresses the compiler's ability to generate warnings.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9bb78-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9bb78-104">Syntax</span></span>  
  
```  
/nowarn[:numberList]  
```  
  
## <a name="arguments"></a><span data-ttu-id="9bb78-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="9bb78-105">Arguments</span></span>  
  
|<span data-ttu-id="9bb78-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="9bb78-106">Term</span></span>|<span data-ttu-id="9bb78-107">Definition</span><span class="sxs-lookup"><span data-stu-id="9bb78-107">Definition</span></span>|  
|---|---|  
|`numberList`|<span data-ttu-id="9bb78-108">Optional.</span><span class="sxs-lookup"><span data-stu-id="9bb78-108">Optional.</span></span> <span data-ttu-id="9bb78-109">Durch Kommas getrennte Liste von Warnung-ID-Nummern an, denen der Compiler unterdrücken soll.</span><span class="sxs-lookup"><span data-stu-id="9bb78-109">Comma-delimited list of the warning ID numbers that the compiler should suppress.</span></span> <span data-ttu-id="9bb78-110">Wenn die Warnung IDs nicht angegeben sind, werden alle Warnungen unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="9bb78-110">If the warning IDs are not specified, all warnings are suppressed.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9bb78-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9bb78-111">Remarks</span></span>  
 <span data-ttu-id="9bb78-112">Die `/nowarn` -Option bewirkt, dass den Compiler keine Warnungen generiert werden.</span><span class="sxs-lookup"><span data-stu-id="9bb78-112">The `/nowarn` option causes the compiler to not generate warnings.</span></span> <span data-ttu-id="9bb78-113">Um eine einzelne Warnung zu unterdrücken, geben Sie die ID der Warnung auf die `/nowarn` Option hinter dem Doppelpunkt.</span><span class="sxs-lookup"><span data-stu-id="9bb78-113">To suppress an individual warning, supply the warning ID to the `/nowarn` option following the colon.</span></span> <span data-ttu-id="9bb78-114">Trennen Sie mehrere Warnungsnummern jeweils durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="9bb78-114">Separate multiple warning numbers with commas.</span></span>  
  
 <span data-ttu-id="9bb78-115">Sie müssen nur den numerischen Teil des Warnungsbezeichners angeben.</span><span class="sxs-lookup"><span data-stu-id="9bb78-115">You need to specify only the numeric part of the warning identifier.</span></span> <span data-ttu-id="9bb78-116">Wenn Sie BC42024, die Warnung für nicht verwendete lokale Variablen unterdrücken möchten, z. B. Geben Sie `/nowarn:42024`.</span><span class="sxs-lookup"><span data-stu-id="9bb78-116">For example, if you want to suppress BC42024, the warning for unused local variables, specify `/nowarn:42024`.</span></span>  
  
 <span data-ttu-id="9bb78-117">Weitere Informationen über die Warnung-ID-Nummern, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9bb78-117">For more information on the warning ID numbers, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
|<span data-ttu-id="9bb78-118">Zum Festlegen von/nowarn in Visual Studio integrierte Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="9bb78-118">To set /nowarn in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="9bb78-119">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="9bb78-119">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="9bb78-120">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="9bb78-120">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="9bb78-121">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="9bb78-121">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="9bb78-122">2.  Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="9bb78-122">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="9bb78-123">3.  Wählen Sie die **alle Warnungen deaktivieren** Kontrollkästchen, um alle Warnungen deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="9bb78-123">3.  Select the **Disable all warnings** check box to disable all warnings.</span></span><br />     <span data-ttu-id="9bb78-124">- oder -</span><span class="sxs-lookup"><span data-stu-id="9bb78-124">- or -</span></span><br />     <span data-ttu-id="9bb78-125">Um eine bestimmte Warnung zu deaktivieren, klicken Sie auf **keine** aus der Dropdownliste neben der Warnung.</span><span class="sxs-lookup"><span data-stu-id="9bb78-125">To disable a particular warning, click **None** from the drop-down list adjacent to the warning.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9bb78-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bb78-126">Example</span></span>  
 <span data-ttu-id="9bb78-127">Der folgende code kompiliert `T2.vb` und keine Warnungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9bb78-127">The following code compiles `T2.vb` and does not display any warnings.</span></span>  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a><span data-ttu-id="9bb78-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="9bb78-128">Example</span></span>  
 <span data-ttu-id="9bb78-129">Der folgende code kompiliert `T2.vb` und die Warnung für nicht verwendete lokale Variablen (42024) wird nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9bb78-129">The following code compiles `T2.vb` and does not display the warnings for unused local variables (42024).</span></span>  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="9bb78-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9bb78-130">See Also</span></span>  
 <span data-ttu-id="9bb78-131">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="9bb78-131">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="9bb78-132"> [Beispiel für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span><span class="sxs-lookup"><span data-stu-id="9bb78-132"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md) </span></span>  
<span data-ttu-id="9bb78-133"> [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span><span class="sxs-lookup"><span data-stu-id="9bb78-133"> [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)</span></span>
