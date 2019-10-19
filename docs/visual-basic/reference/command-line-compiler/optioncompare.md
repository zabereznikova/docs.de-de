---
title: -optioncompare
ms.date: 07/20/2015
f1_keywords:
- /optioncompare
- -optioncompare
helpviewer_keywords:
- optioncompare compiler option [Visual Basic]
- -optioncompare compiler option [Visual Basic]
- /optioncompare compiler option [Visual Basic]
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
ms.openlocfilehash: ac385880f8c13c23dffff67fc2a1ecc5609fd189
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2019
ms.locfileid: "72581420"
---
# <a name="-optioncompare"></a><span data-ttu-id="8aaba-102">-optioncompare</span><span class="sxs-lookup"><span data-stu-id="8aaba-102">-optioncompare</span></span>

<span data-ttu-id="8aaba-103">Gibt an, wie Zeichenfolgenvergleiche durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8aaba-103">Specifies how string comparisons are made.</span></span>

## <a name="syntax"></a><span data-ttu-id="8aaba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8aaba-104">Syntax</span></span>

```console
-optioncompare:{binary | text}
```

## <a name="remarks"></a><span data-ttu-id="8aaba-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8aaba-105">Remarks</span></span>

<span data-ttu-id="8aaba-106">Sie können `-optioncompare` in einer von zwei Formen angeben: `-optioncompare:binary`, um binäre Zeichen folgen Vergleiche zu verwenden, und `-optioncompare:text`, um Textzeichen folgen Vergleiche zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="8aaba-106">You can specify `-optioncompare` in one of two forms: `-optioncompare:binary` to use binary string comparisons, and `-optioncompare:text` to use text string comparisons.</span></span> <span data-ttu-id="8aaba-107">Standardmäßig verwendet der Compiler `-optioncompare:binary`.</span><span class="sxs-lookup"><span data-stu-id="8aaba-107">By default, the compiler uses `-optioncompare:binary`.</span></span>

<span data-ttu-id="8aaba-108">In Microsoft Windows bestimmt die aktuelle Codepage die binäre Sortierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="8aaba-108">In Microsoft Windows, the current code page determines the binary sort order.</span></span> <span data-ttu-id="8aaba-109">Eine typische binäre Sortierreihenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8aaba-109">A typical binary sort order is as follows:</span></span>

`A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`

<span data-ttu-id="8aaba-110">Textbasierte Zeichen folgen Vergleiche basieren auf einer Text Sortierreihenfolge ohne Beachtung der Groß-/Kleinschreibung, die vom Gebiets Schema des Systems bestimmt wird</span><span class="sxs-lookup"><span data-stu-id="8aaba-110">Text-based string comparisons are based on a case-insensitive text sort order determined by your system's locale.</span></span> <span data-ttu-id="8aaba-111">Eine typische Text Sortierreihenfolge lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="8aaba-111">A typical text sort order is as follows:</span></span>

`(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`

### <a name="to-set--optioncompare-in-the-visual-studio-ide"></a><span data-ttu-id="8aaba-112">To Set-optioncompare in der Visual Studio-IDE</span><span class="sxs-lookup"><span data-stu-id="8aaba-112">To set -optioncompare in the Visual Studio IDE</span></span>

1. <span data-ttu-id="8aaba-113">Ein Projekt auswählen in **Projektmappen-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="8aaba-113">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="8aaba-114">Klicken Sie im Menü **Projekt** auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8aaba-114">On the **Project** menu, click **Properties**.</span></span>

2. <span data-ttu-id="8aaba-115">Klicken Sie auf die Registerkarte **Kompilieren**.</span><span class="sxs-lookup"><span data-stu-id="8aaba-115">Click the **Compile** tab.</span></span>

3. <span data-ttu-id="8aaba-116">Ändern Sie den Wert im Feld **Optionen vergleichen** .</span><span class="sxs-lookup"><span data-stu-id="8aaba-116">Modify the value in the **Option Compare** box.</span></span>

### <a name="to-set--optioncompare-programmatically"></a><span data-ttu-id="8aaba-117">So legen Sie-optioncompare Programm gesteuert fest</span><span class="sxs-lookup"><span data-stu-id="8aaba-117">To set -optioncompare programmatically</span></span>

<span data-ttu-id="8aaba-118">Siehe [Option Compare-Anweisung](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8aaba-118">See [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md).</span></span>

## <a name="example"></a><span data-ttu-id="8aaba-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8aaba-119">Example</span></span>

<span data-ttu-id="8aaba-120">Der folgende Code kompiliert `ProjFile.vb` und verwendet binäre Zeichen folgen Vergleiche.</span><span class="sxs-lookup"><span data-stu-id="8aaba-120">The following code compiles `ProjFile.vb` and uses binary string comparisons.</span></span>

```console
vbc -optioncompare:binary projFile.vb
```

## <a name="see-also"></a><span data-ttu-id="8aaba-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8aaba-121">See also</span></span>

- [<span data-ttu-id="8aaba-122">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="8aaba-122">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="8aaba-123">-optionexplicit</span><span class="sxs-lookup"><span data-stu-id="8aaba-123">-optionexplicit</span></span>](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)
- [<span data-ttu-id="8aaba-124">-optionstrict</span><span class="sxs-lookup"><span data-stu-id="8aaba-124">-optionstrict</span></span>](../../../visual-basic/reference/command-line-compiler/optionstrict.md)
- [<span data-ttu-id="8aaba-125">-optioninfer</span><span class="sxs-lookup"><span data-stu-id="8aaba-125">-optioninfer</span></span>](../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [<span data-ttu-id="8aaba-126">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="8aaba-126">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [<span data-ttu-id="8aaba-127">Option Compare-Anweisung</span><span class="sxs-lookup"><span data-stu-id="8aaba-127">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="8aaba-128">VB-Standard, Projekte, Dialogfeld „Optionen“</span><span class="sxs-lookup"><span data-stu-id="8aaba-128">Visual Basic Defaults, Projects, Options Dialog Box</span></span>](/visualstudio/ide/reference/visual-basic-defaults-projects-options-dialog-box)
