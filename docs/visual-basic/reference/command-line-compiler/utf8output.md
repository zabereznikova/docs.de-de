---
title: /utf8output (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- -utf8output compiler option [Visual Basic]
- utf8output compiler option [Visual Basic]
- /utf8output compiler option [Visual Basic]
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 23c7c308865a6b6afb07443a42090fff3d9e2efb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="utf8output-visual-basic"></a><span data-ttu-id="3c1ec-102">/utf8output (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3c1ec-102">/utf8output (Visual Basic)</span></span>
<span data-ttu-id="3c1ec-103">Zeigt die Compilerausgabe mit UTF-8-Codierung an.</span><span class="sxs-lookup"><span data-stu-id="3c1ec-103">Displays compiler output using UTF-8 encoding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c1ec-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3c1ec-104">Syntax</span></span>  
  
```  
/utf8output[+ | -]  
```  
  
## <a name="arguments"></a><span data-ttu-id="3c1ec-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="3c1ec-105">Arguments</span></span>  
 <span data-ttu-id="3c1ec-106">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="3c1ec-106">`+` &#124; `-`</span></span>  
 <span data-ttu-id="3c1ec-107">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="3c1ec-107">Optional.</span></span> <span data-ttu-id="3c1ec-108">Der Standardwert für diese Option ist `/utf8output-`, d. h. Compilerausgabe nicht UTF-8-Codierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="3c1ec-108">The default for this option is `/utf8output-`, which means compiler output does not use UTF-8 encoding.</span></span> <span data-ttu-id="3c1ec-109">Angeben von `/utf8output` ist derselbe, als wenn `/utf8output+`.</span><span class="sxs-lookup"><span data-stu-id="3c1ec-109">Specifying `/utf8output` is the same as specifying `/utf8output+`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c1ec-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3c1ec-110">Remarks</span></span>  
 <span data-ttu-id="3c1ec-111">Bei einigen internationalen Konfigurationen kann nicht die Compilerausgabe ordnungsgemäß in der Konsole angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3c1ec-111">In some international configurations, compiler output cannot be displayed correctly in the console.</span></span> <span data-ttu-id="3c1ec-112">Verwenden Sie in solchen Situationen `/utf8output` und Compiler-Ausgabe in eine Datei umleiten.</span><span class="sxs-lookup"><span data-stu-id="3c1ec-112">In such situations, use `/utf8output` and redirect compiler output to a file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c1ec-113">Die `/utf8output` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar; er ist nur bei verfügbar über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="3c1ec-113">The `/utf8output` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c1ec-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3c1ec-114">Example</span></span>  
 <span data-ttu-id="3c1ec-115">Der folgende code kompiliert `In.vb` und die Compilerausgabe mit UTF-8-Codierung ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="3c1ec-115">The following code compiles `In.vb` and directs the compiler to display output using UTF-8 encoding.</span></span>  
  
```  
vbc /utf8output in.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c1ec-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3c1ec-116">See Also</span></span>  
 [<span data-ttu-id="3c1ec-117">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="3c1ec-117">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="3c1ec-118">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="3c1ec-118">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
