---
title: Variable &quot;&lt;Variablename&gt;&quot; wird verwendet, bevor ihr ein Wert zugewiesen wurde, hat | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
dev_langs:
- VB
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
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
ms.openlocfilehash: dfc924ebbebb8b20654156b8871684dcfad6848a
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="9157c-102">Variable "&lt;Variablename&gt;' wird verwendet, bevor ihr ein Wert zugewiesen wurde, hat</span><span class="sxs-lookup"><span data-stu-id="9157c-102">Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value</span></span>
<span data-ttu-id="9157c-103">Variable "\<Variablename >" wird verwendet, bevor er einen Wert zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="9157c-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="9157c-104">Zur Laufzeit kann eine NULL-Verweisausnahme auftreten.</span><span class="sxs-lookup"><span data-stu-id="9157c-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="9157c-105">Eine Anwendung muss über mindestens einen möglichen Codepfad auf, der eine Variable liest, bevor ein Wert zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="9157c-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="9157c-106">Wenn einer Variablen nie ein Wert zugewiesen wurde, enthält sie den Standardwert für ihren Datentyp.</span><span class="sxs-lookup"><span data-stu-id="9157c-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="9157c-107">Der Datentyp ein Verweistyp ist, Standardwert [nichts](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="9157c-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="9157c-108">Lesen einer Verweisvariablen mit dem Wert der `Nothing` kann dazu führen, dass ein <xref:System.NullReferenceException>unter bestimmten Umständen.</xref:System.NullReferenceException></span><span class="sxs-lookup"><span data-stu-id="9157c-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="9157c-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="9157c-109">By default, this message is a warning.</span></span> <span data-ttu-id="9157c-110">Weitere Informationen zu Ausblenden von Warnungen oder Warnungen als Fehler behandeln, finden Sie unter [Konfigurieren von Warnungen in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="9157c-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="9157c-111">**Fehler-ID:** BC42104</span><span class="sxs-lookup"><span data-stu-id="9157c-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="9157c-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="9157c-112">To correct this error</span></span>  
  
-   <span data-ttu-id="9157c-113">Überprüfen Sie die Ablaufsteuerungslogik, und stellen Sie sicher, dass die Variable einen gültigen Wert aufweist, bevor die Steuerung an eine Anweisung übergeben, die diese liest.</span><span class="sxs-lookup"><span data-stu-id="9157c-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
-   <span data-ttu-id="9157c-114">Eine Möglichkeit, um sicherzustellen, dass die Variable immer einen gültigen Wert aufweist, ist als Teil der Deklaration initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="9157c-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="9157c-115">Siehe "Initialisierung" in [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="9157c-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9157c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9157c-116">See Also</span></span>  
 <span data-ttu-id="9157c-117">[Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md) </span><span class="sxs-lookup"><span data-stu-id="9157c-117">[Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md) </span></span>  
<span data-ttu-id="9157c-118"> [Deklaration von Objektvariablen](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span><span class="sxs-lookup"><span data-stu-id="9157c-118"> [Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md) </span></span>  
<span data-ttu-id="9157c-119"> [Problembehandlung bei Variablen](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)</span><span class="sxs-lookup"><span data-stu-id="9157c-119"> [Troubleshooting Variables](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)</span></span>
