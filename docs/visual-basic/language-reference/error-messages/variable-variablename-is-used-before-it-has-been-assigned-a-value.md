---
title: Variable &#39; &lt;Variablename&gt; &#39; wird verwendet, bevor ihr einen Wert zugewiesen wurde.
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: f91343e850600c9e5f4b4b4eb2126798baf3d980
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647022"
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="ff521-102">Variable &#39; &lt;Variablename&gt; &#39; wird verwendet, bevor ihr einen Wert zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="ff521-102">Variable &#39;&lt;variablename&gt;&#39; is used before it has been assigned a value</span></span>
<span data-ttu-id="ff521-103">Variable "\<Variablenname >' wird verwendet, bevor sie einen Wert zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="ff521-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="ff521-104">Zur Laufzeit kann eine NULL-Verweisausnahme auftreten.</span><span class="sxs-lookup"><span data-stu-id="ff521-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="ff521-105">Eine Anwendung muss über mindestens einen möglichen Pfad durch den Code, der eine Variable liest, bevor ein Wert zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="ff521-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="ff521-106">Wenn einer Variablen nie ein Wert zugewiesen wurde, enthält sie den Standardwert für ihren Datentyp.</span><span class="sxs-lookup"><span data-stu-id="ff521-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="ff521-107">Bei Verweisdatentypen ist dieser Standardwert [Nothing](../../../visual-basic/language-reference/nothing.md).</span><span class="sxs-lookup"><span data-stu-id="ff521-107">For a reference data type, that default value is [Nothing](../../../visual-basic/language-reference/nothing.md).</span></span> <span data-ttu-id="ff521-108">Das Lesen einer Verweisvariablen, die den Wert `Nothing` aufweist, kann unter bestimmten Umständen zu einer <xref:System.NullReferenceException> führen.</span><span class="sxs-lookup"><span data-stu-id="ff521-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="ff521-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="ff521-109">By default, this message is a warning.</span></span> <span data-ttu-id="ff521-110">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="ff521-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="ff521-111">**Fehler-ID:** BC42104</span><span class="sxs-lookup"><span data-stu-id="ff521-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="ff521-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="ff521-112">To correct this error</span></span>  
  
-   <span data-ttu-id="ff521-113">Überprüfen Sie Ihre Ablaufsteuerungslogik, und stellen Sie sicher, dass die Variable einen gültigen Wert aufweist, bevor die Steuerung an eine Anweisung übergeben, die diese liest.</span><span class="sxs-lookup"><span data-stu-id="ff521-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
-   <span data-ttu-id="ff521-114">Eine Möglichkeit, um sicherzustellen, dass die Variable immer einen gültigen Wert aufweist, ist als Teil der Deklaration initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ff521-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="ff521-115">Finden Sie unter "Initialisierung" in [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="ff521-115">See "Initialization" in [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff521-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ff521-116">See also</span></span>
- [<span data-ttu-id="ff521-117">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="ff521-117">Dim Statement</span></span>](../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="ff521-118">Variablendeklaration</span><span class="sxs-lookup"><span data-stu-id="ff521-118">Variable Declaration</span></span>](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="ff521-119">Problembehandlung bei Variablen</span><span class="sxs-lookup"><span data-stu-id="ff521-119">Troubleshooting Variables</span></span>](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
