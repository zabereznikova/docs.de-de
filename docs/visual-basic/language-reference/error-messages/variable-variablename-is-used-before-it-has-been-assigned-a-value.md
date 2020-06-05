---
title: Die <variablename>-Variable wird verwendet, bevor ihr ein Wert zugewiesen wird.
ms.date: 07/20/2015
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
ms.openlocfilehash: 34718243172d3b1a238a813268e672d62c4eeb6c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84406533"
---
# <a name="variable-variablename-is-used-before-it-has-been-assigned-a-value"></a><span data-ttu-id="b1e59-102">Die \<variablename>-Variable wird verwendet, bevor ihr ein Wert zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b1e59-102">Variable '\<variablename>' is used before it has been assigned a value</span></span>
<span data-ttu-id="b1e59-103">Die-Variable \<variablename> wird verwendet, bevor ihr ein Wert zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="b1e59-103">Variable '\<variablename>' is used before it has been assigned a value.</span></span> <span data-ttu-id="b1e59-104">Zur Laufzeit kann eine NULL-Verweisausnahme auftreten.</span><span class="sxs-lookup"><span data-stu-id="b1e59-104">A null reference exception could result at run time.</span></span>  
  
 <span data-ttu-id="b1e59-105">Eine Anwendung verfügt über mindestens einen möglichen Pfad durch Ihren Code, der eine Variable liest, bevor ihr ein Wert zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="b1e59-105">An application has at least one possible path through its code that reads a variable before any value is assigned to it.</span></span>  
  
 <span data-ttu-id="b1e59-106">Wenn einer Variablen nie ein Wert zugewiesen wurde, enthält sie den Standardwert für ihren Datentyp.</span><span class="sxs-lookup"><span data-stu-id="b1e59-106">If a variable has never been assigned a value, it holds the default value for its data type.</span></span> <span data-ttu-id="b1e59-107">Bei Verweisdatentypen ist dieser Standardwert [Nothing](../nothing.md).</span><span class="sxs-lookup"><span data-stu-id="b1e59-107">For a reference data type, that default value is [Nothing](../nothing.md).</span></span> <span data-ttu-id="b1e59-108">Das Lesen einer Verweisvariablen, die den Wert `Nothing` aufweist, kann unter bestimmten Umständen zu einer <xref:System.NullReferenceException> führen.</span><span class="sxs-lookup"><span data-stu-id="b1e59-108">Reading a reference variable that has a value of `Nothing` can cause a <xref:System.NullReferenceException> in some circumstances.</span></span>  
  
 <span data-ttu-id="b1e59-109">Standardmäßig ist diese Meldung eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="b1e59-109">By default, this message is a warning.</span></span> <span data-ttu-id="b1e59-110">Weitere Informationen zum Ausblenden von Warnungen oder zum Behandeln von Warnungen als Fehler finden Sie unter [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="b1e59-110">For more information on hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="b1e59-111">**Fehler-ID:** BC42104</span><span class="sxs-lookup"><span data-stu-id="b1e59-111">**Error ID:** BC42104</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="b1e59-112">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="b1e59-112">To correct this error</span></span>  
  
- <span data-ttu-id="b1e59-113">Überprüfen Sie die Ablauf Steuerungslogik, und stellen Sie sicher, dass die Variable einen gültigen Wert aufweist, bevor die Steuerung an eine beliebige Anweisung weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="b1e59-113">Check your control flow logic and make sure the variable has a valid value before control passes to any statement that reads it.</span></span>  
  
- <span data-ttu-id="b1e59-114">Eine Möglichkeit, um sicherzustellen, dass die Variable immer einen gültigen Wert aufweist, ist die Initialisierung im Rahmen der Deklaration.</span><span class="sxs-lookup"><span data-stu-id="b1e59-114">One way to guarantee that the variable always has a valid value is to initialize it as part of its declaration.</span></span> <span data-ttu-id="b1e59-115">Siehe "Initialisierung" in der [Dim-Anweisung](../statements/dim-statement.md).</span><span class="sxs-lookup"><span data-stu-id="b1e59-115">See "Initialization" in [Dim Statement](../statements/dim-statement.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1e59-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1e59-116">See also</span></span>

- [<span data-ttu-id="b1e59-117">Dim-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b1e59-117">Dim Statement</span></span>](../statements/dim-statement.md)
- [<span data-ttu-id="b1e59-118">Variablen Deklaration</span><span class="sxs-lookup"><span data-stu-id="b1e59-118">Variable Declaration</span></span>](../../programming-guide/language-features/variables/variable-declaration.md)
- [<span data-ttu-id="b1e59-119">Problembehandlung bei Variablen</span><span class="sxs-lookup"><span data-stu-id="b1e59-119">Troubleshooting Variables</span></span>](../../programming-guide/language-features/variables/troubleshooting-variables.md)
