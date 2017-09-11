---
title: Option Compare-Anweisung | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Compare
- vb.OptionCompare
dev_langs:
- VB
helpviewer_keywords:
- case sensitivity, Option Compare statement
- Compare keyword
- binary comparison
- strings [Visual Basic], returning from functions
- binary comparison, Option Compare statement
- strings [Visual Basic], comparing
- string comparison [Visual Basic], Option Compare statement
- Text keyword, Option Compare statement
- Binary keyword, Option Compare statement
- string comparison [Visual Basic], sorting data
- Option Compare statement
- text [Visual Basic], comparing
ms.assetid: 54e8eeeb-3b0d-4fb9-acce-fbfbd5975f6e
caps.latest.revision: 37
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
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 00618cd914c06b896d68b4074464af866f747895
ms.contentlocale: de-de
ms.lasthandoff: 05/26/2017

---
# <a name="option-compare-statement"></a><span data-ttu-id="1392b-102">Option Compare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1392b-102">Option Compare Statement</span></span>
<span data-ttu-id="1392b-103">Deklariert die Standardvergleichsmethode, die beim Vergleichen von Zeichenfolgendaten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1392b-103">Declares the default comparison method to use when comparing string data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1392b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1392b-104">Syntax</span></span>  
  
```  
Option Compare { Binary | Text }  
```  
  
## <a name="parts"></a><span data-ttu-id="1392b-105">Teile</span><span class="sxs-lookup"><span data-stu-id="1392b-105">Parts</span></span>  
  
|<span data-ttu-id="1392b-106">Begriff</span><span class="sxs-lookup"><span data-stu-id="1392b-106">Term</span></span>|<span data-ttu-id="1392b-107">Definition</span><span class="sxs-lookup"><span data-stu-id="1392b-107">Definition</span></span>|  
|---|---|  
|`Binary`|<span data-ttu-id="1392b-108">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1392b-108">Optional.</span></span> <span data-ttu-id="1392b-109">Resultiert in Zeichenfolgenvergleichen basierend auf einer Sortierreihenfolge, die sich von den internen binären Darstellungen der Zeichen ableitet.</span><span class="sxs-lookup"><span data-stu-id="1392b-109">Results in string comparisons based on a sort order derived from the internal binary representations of the characters.</span></span><br /><br /> <span data-ttu-id="1392b-110">Diese Art von Vergleich ist besonders hilfreich, da die Zeichenfolgen Zeichen enthalten können, die nicht als Text interpretiert werden.</span><span class="sxs-lookup"><span data-stu-id="1392b-110">This type of comparison is useful especially if the strings can contain characters that are not to be interpreted as text.</span></span> <span data-ttu-id="1392b-111">In diesem Fall sollten Sie Vergleiche nicht alphabetischen Äquivalenzen, z. B. Groß-/Kleinschreibung vorziehen.</span><span class="sxs-lookup"><span data-stu-id="1392b-111">In this case, you do not want to bias comparisons with alphabetical equivalences, such as case insensitivity.</span></span>|  
|`Text`|<span data-ttu-id="1392b-112">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="1392b-112">Optional.</span></span> <span data-ttu-id="1392b-113">Führt zu einem Zeichenfolgenvergleich basierend auf einer schreibungsunabhängigen Textsortierreihenfolge, die durch das Gebietsschema des Systems bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="1392b-113">Results in string comparisons based on a case-insensitive text sort order determined by your system's locale.</span></span><br /><br /> <span data-ttu-id="1392b-114">Diese Art von Vergleich ist nützlich, wenn die Zeichenfolgen nur Textzeichen enthalten und Sie nur anhand alphabetischer Äquivalenzen z. B. Groß-/Kleinschreibung oder eng verwandter Buchstaben vergleichen möchten.</span><span class="sxs-lookup"><span data-stu-id="1392b-114">This type of comparison is useful if your strings contain all text characters, and you want to compare them taking into account alphabetic equivalences such as case insensitivity and closely related letters.</span></span> <span data-ttu-id="1392b-115">Sie könnten zum Beispiel `A` und `a` als gleich ansehen und `Ä` und `ä`, die vor `B` und `b` kommen.</span><span class="sxs-lookup"><span data-stu-id="1392b-115">For example, you might want to consider `A` and `a` to be equal, and `Ä` and `ä` to come before `B` and `b`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1392b-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1392b-116">Remarks</span></span>  
 <span data-ttu-id="1392b-117">Wenn sie verwendet wird, muss die `Option Compare`-Anweisung in einer Datei vor allen anderen Quellcodeanweisungen angeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="1392b-117">If used, the `Option Compare` statement must appear in a file before any other source code statements.</span></span>  
  
 <span data-ttu-id="1392b-118">Die `Option Compare`-Anweisung gibt die Zeichenfolgenvergleichsmethode vor (`Binary` oder `Text`).</span><span class="sxs-lookup"><span data-stu-id="1392b-118">The `Option Compare` statement specifies the string comparison method (`Binary` or `Text`).</span></span>  <span data-ttu-id="1392b-119">Die Standardmethode zum Textvergleich ist `Binary`.</span><span class="sxs-lookup"><span data-stu-id="1392b-119">The default text comparison method is `Binary`.</span></span>  
  
 <span data-ttu-id="1392b-120">Ein `Binary`-Vergleich vergleicht den numerischen Unicode-Wert jedes Zeichens in jeder Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1392b-120">A `Binary` comparison compares the numeric Unicode value of each character in each string.</span></span> <span data-ttu-id="1392b-121">Ein `Text`-Vergleich vergleicht alle Unicode-Zeichen anhand der lexikalische Bedeutung in der aktuellen Kultur.</span><span class="sxs-lookup"><span data-stu-id="1392b-121">A `Text` comparison compares each Unicode character based on its lexical meaning in the current culture.</span></span>  
  
 <span data-ttu-id="1392b-122">In Microsoft Windows wird die Sortierreihenfolge durch die Codepage festgelegt.</span><span class="sxs-lookup"><span data-stu-id="1392b-122">In Microsoft Windows, sort order is determined by the code page.</span></span> <span data-ttu-id="1392b-123">Weitere Informationen finden Sie unter [Codepages](https://docs.microsoft.com/cpp/c-runtime-library/code-pages).</span><span class="sxs-lookup"><span data-stu-id="1392b-123">For more information, see [Code Pages](https://docs.microsoft.com/cpp/c-runtime-library/code-pages).</span></span>  
  
 <span data-ttu-id="1392b-124">Im folgenden Beispiel werden Zeichen der Codepage für Westeuropäisch (ANSI 1252) mit `Option Compare Binary` sortiert, wodurch eine typische binäre Sortierreihenfolge erzeugt wird.</span><span class="sxs-lookup"><span data-stu-id="1392b-124">In the following example, characters in the English/European code page (ANSI 1252) are sorted by using `Option Compare Binary`, which produces a typical binary sort order.</span></span>  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 <span data-ttu-id="1392b-125">Wenn dieselben Zeichen in derselben Codepage `Option Compare Text` mit sortiert werden, wird die folgende Sortierreihenfolge erzeugt.</span><span class="sxs-lookup"><span data-stu-id="1392b-125">When the same characters in the same code page are sorted by using `Option Compare Text`, the following text sort order is produced.</span></span>  
  
 `(A=a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
## <a name="when-an-option-compare-statement-is-not-present"></a><span data-ttu-id="1392b-126">Wenn eine Option Compare-Anweisung nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="1392b-126">When an Option Compare Statement Is Not Present</span></span>  
 <span data-ttu-id="1392b-127">Enthält der Quellcode kein `Option Compare` -Anweisung, die **Option Compare** auf der [Seite kompilieren, Projekt-Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1392b-127">If the source code does not contain an `Option Compare` statement, the **Option Compare** setting on the [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic) is used.</span></span> <span data-ttu-id="1392b-128">Wenn Sie den Befehlszeilencompiler verwenden, wird die Einstellung angegeben, durch die [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) -Compileroption verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1392b-128">If you use the command-line compiler, the setting specified by the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option is used.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
#### <a name="to-set-option-compare-in-the-ide"></a><span data-ttu-id="1392b-129">Festelegen der Option Compare in der IDE</span><span class="sxs-lookup"><span data-stu-id="1392b-129">To set Option Compare in the IDE</span></span>  
  
1.  <span data-ttu-id="1392b-130">In **Projektmappen-Explorer**, wählen Sie ein Projekt.</span><span class="sxs-lookup"><span data-stu-id="1392b-130">In **Solution Explorer**, select a project.</span></span> <span data-ttu-id="1392b-131">Auf der **Projekt** Menü klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="1392b-131">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="1392b-132">Weitere Informationen finden Sie unter [NIB: Verwalten von Projekteigenschaften mit dem Projekt-Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span><span class="sxs-lookup"><span data-stu-id="1392b-132">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="1392b-133">Klicken Sie auf die **Kompilieren** Registerkarte.</span><span class="sxs-lookup"><span data-stu-id="1392b-133">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="1392b-134">Legen Sie den Wert der **Option Compare** Feld.</span><span class="sxs-lookup"><span data-stu-id="1392b-134">Set the value in the **Option Compare** box.</span></span>  
  
 <span data-ttu-id="1392b-135">Wenn Sie ein Projekt erstellen die **Option Compare** auf der **Kompilieren** Registerkarte auf festgelegt ist die **Option Compare** festlegen in der **Optionen** im Dialogfeld.</span><span class="sxs-lookup"><span data-stu-id="1392b-135">When you create a project, the **Option Compare** setting on the **Compile** tab is set to the **Option Compare** setting in the **Options** dialog box.</span></span> <span data-ttu-id="1392b-136">So ändern Sie diese Einstellung, auf die **Tools** Menü klicken Sie auf **Optionen**.</span><span class="sxs-lookup"><span data-stu-id="1392b-136">To change this setting, on the **Tools** menu, click **Options**.</span></span> <span data-ttu-id="1392b-137">In der **Optionen** Dialogfeld erweitern Sie **Projekte und Projektmappen**, und klicken Sie dann auf **VB-Standard**.</span><span class="sxs-lookup"><span data-stu-id="1392b-137">In the **Options** dialog box, expand **Projects and Solutions**, and then click **VB Defaults**.</span></span> <span data-ttu-id="1392b-138">Die ursprüngliche Standardeinstellung in **VB-Standard** ist **binäre**.</span><span class="sxs-lookup"><span data-stu-id="1392b-138">The initial default setting in **VB Defaults** is **Binary**.</span></span>  
  
#### <a name="to-set-option-compare-on-the-command-line"></a><span data-ttu-id="1392b-139">Festlegen der Option Compare in der Befehlszeile</span><span class="sxs-lookup"><span data-stu-id="1392b-139">To set Option Compare on the command line</span></span>  
  
-   <span data-ttu-id="1392b-140">Enthalten die [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) -Compileroption in der **Vbc** Befehl.</span><span class="sxs-lookup"><span data-stu-id="1392b-140">Include the [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) compiler option in the **vbc** command.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1392b-141">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1392b-141">Example</span></span>  
 <span data-ttu-id="1392b-142">Das folgenden Beispiel verwendet die `Option Compare`-Anweisung, um den binären Vergleich als die Standardzeichenfolgenvergleichsmethode festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1392b-142">The following example uses the `Option Compare` statement to set the binary comparison as the default string comparison method.</span></span> <span data-ttu-id="1392b-143">Um diesen Code zu verwenden, heben Sie die Auskommentierung der `Option Compare Binary`-Anweisung auf und positionieren Sie sie am Anfang der Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="1392b-143">To use this code, uncomment the `Option Compare Binary` statement, and put it at the top of the source file.</span></span>  
  
 <span data-ttu-id="1392b-144">[!code-vb[VbVbalrStatements&#45;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="1392b-144">[!code-vb[VbVbalrStatements#45](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_1.vb)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="1392b-145">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1392b-145">Example</span></span>  
 <span data-ttu-id="1392b-146">Im folgenden Beispiel wird die `Option Compare`-Anweisung verwendet, um die Textsortierreihenfolge als die Standardzeichenfolgenvergleichsmethode festzulegen.</span><span class="sxs-lookup"><span data-stu-id="1392b-146">The following example uses the `Option Compare` statement to set the case-insensitive text sort order as the default string comparison method.</span></span> <span data-ttu-id="1392b-147">Um diesen Code zu verwenden, heben Sie die Auskommentierung der `Option Compare Text`-Anweisung auf und positionieren Sie sie am Anfang der Quelldatei.</span><span class="sxs-lookup"><span data-stu-id="1392b-147">To use this code, uncomment the `Option Compare Text` statement, and put it at the top of the source file.</span></span>  
  
 <span data-ttu-id="1392b-148">[!code-vb[VbVbalrStatements&#46;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="1392b-148">[!code-vb[VbVbalrStatements#46](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/option-compare-statement_2.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1392b-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1392b-149">See Also</span></span>  
 <span data-ttu-id="1392b-150"><xref:Microsoft.VisualBasic.Strings.InStr%2A></xref:Microsoft.VisualBasic.Strings.InStr%2A></span><span class="sxs-lookup"><span data-stu-id="1392b-150"><xref:Microsoft.VisualBasic.Strings.InStr%2A></span></span>   
 <span data-ttu-id="1392b-151"><xref:Microsoft.VisualBasic.Strings.InStrRev%2A></xref:Microsoft.VisualBasic.Strings.InStrRev%2A></span><span class="sxs-lookup"><span data-stu-id="1392b-151"><xref:Microsoft.VisualBasic.Strings.InStrRev%2A></span></span>   
 <span data-ttu-id="1392b-152"><xref:Microsoft.VisualBasic.Strings.Replace%2A></xref:Microsoft.VisualBasic.Strings.Replace%2A></span><span class="sxs-lookup"><span data-stu-id="1392b-152"><xref:Microsoft.VisualBasic.Strings.Replace%2A></span></span>   
 <span data-ttu-id="1392b-153"><xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A></span><span class="sxs-lookup"><span data-stu-id="1392b-153"><xref:Microsoft.VisualBasic.Strings.Split%2A></span></span>   
 <span data-ttu-id="1392b-154"><xref:Microsoft.VisualBasic.Strings.StrComp%2A></xref:Microsoft.VisualBasic.Strings.StrComp%2A></span><span class="sxs-lookup"><span data-stu-id="1392b-154"><xref:Microsoft.VisualBasic.Strings.StrComp%2A></span></span>   
<span data-ttu-id="1392b-155"> [/ optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span><span class="sxs-lookup"><span data-stu-id="1392b-155"> [/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md) </span></span>  
<span data-ttu-id="1392b-156"> [Vergleichsoperatoren](../../../visual-basic/language-reference/operators/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="1392b-156"> [Comparison Operators](../../../visual-basic/language-reference/operators/comparison-operators.md) </span></span>  
<span data-ttu-id="1392b-157"> [Vergleichsoperatoren in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span><span class="sxs-lookup"><span data-stu-id="1392b-157"> [Comparison Operators in Visual Basic](../../../visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators.md) </span></span>  
<span data-ttu-id="1392b-158"> [LIKE-Operator](../../../visual-basic/language-reference/operators/like-operator.md) </span><span class="sxs-lookup"><span data-stu-id="1392b-158"> [Like Operator](../../../visual-basic/language-reference/operators/like-operator.md) </span></span>  
<span data-ttu-id="1392b-159"> [String-Funktionen](../../../visual-basic/language-reference/functions/string-functions.md) </span><span class="sxs-lookup"><span data-stu-id="1392b-159"> [String Functions](../../../visual-basic/language-reference/functions/string-functions.md) </span></span>  
<span data-ttu-id="1392b-160"> [Option Explicit-Anweisung](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span><span class="sxs-lookup"><span data-stu-id="1392b-160"> [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) </span></span>  
<span data-ttu-id="1392b-161"> [Option Strict-Anweisung](../../../visual-basic/language-reference/statements/option-strict-statement.md)</span><span class="sxs-lookup"><span data-stu-id="1392b-161"> [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)</span></span>
