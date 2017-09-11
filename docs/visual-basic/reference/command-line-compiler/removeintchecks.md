---
title: / removeintchecks | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- removeintchecks
- /removeintchecks
dev_langs:
- VB
helpviewer_keywords:
- removeintchecks compiler option [Visual Basic]
- /removeintchecks compiler option [Visual Basic]
- -removeintchecks compiler option [Visual Basic]
ms.assetid: c1835bd5-1e38-4fba-bd2f-6984774765d4
caps.latest.revision: 14
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
ms.openlocfilehash: 25f67774238c6e9a6b3a2c50b3702e43d5a6374c
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="removeintchecks"></a><span data-ttu-id="fdaa9-102">/removeintchecks</span><span class="sxs-lookup"><span data-stu-id="fdaa9-102">/removeintchecks</span></span>
<span data-ttu-id="fdaa9-103">Aktiviert die Ganzzahlüberlauf-Überprüfung für Ganzzahloperationen ein- oder ausschalten.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-103">Turns overflow-error checking for integer operations on or off.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fdaa9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="fdaa9-104">Syntax</span></span>  
  
```  
/removeintchecks[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="fdaa9-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="fdaa9-105">Arguments</span></span>  
  
|<span data-ttu-id="fdaa9-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="fdaa9-106">Term</span></span>|<span data-ttu-id="fdaa9-107">Definition</span><span class="sxs-lookup"><span data-stu-id="fdaa9-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="fdaa9-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="fdaa9-108">`+` &#124; `-`</span></span>|<span data-ttu-id="fdaa9-109">Optional.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-109">Optional.</span></span> <span data-ttu-id="fdaa9-110">Die `/removeintchecks-` Option bewirkt, dass der Compiler alle ganzzahligen Berechnungen für Überlauffehler überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-110">The `/removeintchecks-` option causes the compiler to check all integer calculations for overflow errors.</span></span> <span data-ttu-id="fdaa9-111">Die Standardeinstellung ist `/removeintchecks-`.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-111">The default is `/removeintchecks-`.</span></span><br /><br /> <span data-ttu-id="fdaa9-112">Angeben von `/removeintchecks` oder `/removeintchecks+` verhindert die Überprüfung von Fehlern und Ganzzahl Berechnungen schneller machen können.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-112">Specifying `/removeintchecks` or `/removeintchecks+` prevents error checking and can make integer calculations faster.</span></span> <span data-ttu-id="fdaa9-113">Allerdings ohne die Überprüfung von Fehlern, wenn Typ Datenkapazität überlaufen, möglicherweise falsche Ergebnisse ohne das Auslösen eines Fehlers gespeichert.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-113">However, without error checking, and if data type capacities are overflowed, incorrect results may be stored without raising an error.</span></span>|  
  
|<span data-ttu-id="fdaa9-114">Zum Festlegen von/removeintchecks in Visual Studio integrierte Entwicklungsumgebung</span><span class="sxs-lookup"><span data-stu-id="fdaa9-114">To set /removeintchecks in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="fdaa9-115">1.  Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-115">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="fdaa9-116">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-116">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="fdaa9-117">Weitere Informationen finden Sie unter [Einführung in den Projekt-Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="fdaa9-117">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="fdaa9-118">2.  Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-118">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="fdaa9-119">3.  Klicken Sie auf die Schaltfläche **Erweitert** .</span><span class="sxs-lookup"><span data-stu-id="fdaa9-119">3.  Click the **Advanced** button.</span></span><br /><span data-ttu-id="fdaa9-120">4.  Ändern Sie den Wert von der **Überprüfungen auf Ganzzahlüberlauf entfernen** Feld.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-120">4.  Modify the value of the **Remove integer overflow checks** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fdaa9-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fdaa9-121">Example</span></span>  
 <span data-ttu-id="fdaa9-122">Der folgende code kompiliert `Test.vb` und Ganzzahlüberlauf Überprüfung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="fdaa9-122">The following code compiles `Test.vb` and turns off integer overflow-error checking.</span></span>  
  
```  
vbc /removeintchecks+ test.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="fdaa9-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fdaa9-123">See Also</span></span>  
 <span data-ttu-id="fdaa9-124">[Visual Basic-Befehlszeilencompiler](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="fdaa9-124">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="fdaa9-125"> [Beispiele für Kompilierungsbefehlszeilen](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="fdaa9-125"> [Sample Compilation Command Lines](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)</span></span>
