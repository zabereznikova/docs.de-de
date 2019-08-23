---
title: -utf8output (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
ms.openlocfilehash: 789df84bb4011d1ad128c50a9c689d1217be6694
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937275"
---
# <a name="-utf8output-visual-basic"></a><span data-ttu-id="f5a39-102">-utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f5a39-102">-utf8output (Visual Basic)</span></span>
<span data-ttu-id="f5a39-103">Zeigt die Compilerausgabe mit UTF-8-Codierung an.</span><span class="sxs-lookup"><span data-stu-id="f5a39-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5a39-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f5a39-104">Syntax</span></span>  
  
```  
-utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="f5a39-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="f5a39-105">Arguments</span></span>  
 <span data-ttu-id="f5a39-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="f5a39-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="f5a39-107">Optional.</span><span class="sxs-lookup"><span data-stu-id="f5a39-107">Optional.</span></span> <span data-ttu-id="f5a39-108">Der Standardwert für diese Option `-utf8output-`ist. Dies bedeutet, dass die Compilerausgabe keine UTF-8-Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="f5a39-108">The default for this option is `-utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="f5a39-109">Die Angabe von `-utf8output` ist mit der Angabe von `-utf8output+` identisch.</span><span class="sxs-lookup"><span data-stu-id="f5a39-109">Specifying `-utf8output` is the same as specifying `-utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f5a39-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f5a39-110">Remarks</span></span>  
 <span data-ttu-id="f5a39-111">In einigen internationalen Konfigurationen kann die Compilerausgabe nicht ordnungsgemäß in der-Konsole angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f5a39-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="f5a39-112">Verwenden `-utf8output` Sie in solchen Situationen die Compilerausgabe, und leiten Sie Sie in eine Datei um.</span><span class="sxs-lookup"><span data-stu-id="f5a39-112">In such situations, use `-utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f5a39-113">Die `-utf8output` Option ist in der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="f5a39-113">The `-utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5a39-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f5a39-114">Example</span></span>  
 <span data-ttu-id="f5a39-115">Der folgende Code kompiliert und `In.vb` weist den Compiler an, die Ausgabe mit UTF-8-Codierung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f5a39-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```console  
vbc -utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="f5a39-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f5a39-116">See also</span></span>

- [<span data-ttu-id="f5a39-117">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="f5a39-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="f5a39-118">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="f5a39-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
