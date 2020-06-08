---
title: -utf8output
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 0a16cdc535de5ed0619bf080bb4637449b11cfef
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403056"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="e274b-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e274b-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="e274b-103">Zeigt die Compilerausgabe mit UTF-8-Codierung an.</span><span class="sxs-lookup"><span data-stu-id="e274b-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e274b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e274b-104">Syntax</span></span>  
  
```console  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="e274b-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="e274b-105">Arguments</span></span>  
 <span data-ttu-id="e274b-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="e274b-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="e274b-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e274b-107">Optional.</span></span> <span data-ttu-id="e274b-108">Der Standardwert für diese Option ist `-utf8output-`. Dies bedeutet, dass die Compilerausgabe keine UTF-8-Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="e274b-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="e274b-109">Die Angabe von `-utf8output` ist mit der Angabe von `-utf8output+` identisch.</span><span class="sxs-lookup"><span data-stu-id="e274b-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e274b-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e274b-110">Remarks</span></span>  
 <span data-ttu-id="e274b-111">Bei einigen internationalen Konfigurationen kann die Compilerausgabe nicht ordnungsgemäß in der Konsole angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e274b-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="e274b-112">Verwenden Sie in solchen Situationen `-utf8output`, und leiten Sie die Compilerausgabe an eine Datei weiter.</span><span class="sxs-lookup"><span data-stu-id="e274b-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e274b-113">Diese Option `-utf8output` steht nicht in der Visual Studio-Entwicklungsumgebung zur Verfügung. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="e274b-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e274b-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e274b-114">Example</span></span>  
 <span data-ttu-id="e274b-115">Der folgende Code kompiliert `In.vb` und weist den Compiler an, die Ausgabe mithilfe der UTF-8-Codierung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="e274b-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e274b-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e274b-116">See also</span></span>

- [<span data-ttu-id="e274b-117">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="e274b-117">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="e274b-118">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="e274b-118">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
