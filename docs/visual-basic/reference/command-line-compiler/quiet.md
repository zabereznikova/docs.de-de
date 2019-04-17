---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: a22773e2e37eb60ab6f1e88305266f41764311e7
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2019
ms.locfileid: "59612588"
---
# <a name="-quiet"></a><span data-ttu-id="3bad5-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="3bad5-102">-quiet</span></span>

<span data-ttu-id="3bad5-103">Verhindert, dass der Compiler Code für syntaxbezogene Fehler und Warnungen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3bad5-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="3bad5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="3bad5-104">Syntax</span></span>

```
-quiet
```

## <a name="remarks"></a><span data-ttu-id="3bad5-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3bad5-105">Remarks</span></span>

<span data-ttu-id="3bad5-106">In der Standardeinstellung ist `-quiet` nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="3bad5-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="3bad5-107">Wenn der Compiler ein syntaxbezogene Fehler oder eine Warnung gemeldet, auch die Zeile aus dem Quellcode ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="3bad5-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="3bad5-108">Für Anwendungen, die Compiler-Ausgabe zu analysieren, kann es einfacher für den Compiler an, nur den Text der Diagnose ausgegeben sein.</span><span class="sxs-lookup"><span data-stu-id="3bad5-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>

<span data-ttu-id="3bad5-109">Im folgenden Beispiel `Module1` gibt einen Fehler aus, die bei der Kompilierung ohne Quellcode enthält `-quiet`.</span><span class="sxs-lookup"><span data-stu-id="3bad5-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

<span data-ttu-id="3bad5-110">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="3bad5-110">Output:</span></span>

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

<span data-ttu-id="3bad5-111">Mit kompiliert `-quiet`, der Compiler gibt nur die folgenden:</span><span class="sxs-lookup"><span data-stu-id="3bad5-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>

```
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> <span data-ttu-id="3bad5-112">Die `-quiet` Option ist nicht in der Visual Studio-Entwicklungsumgebung verfügbar, sondern nur, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="3bad5-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="3bad5-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3bad5-113">Example</span></span>

<span data-ttu-id="3bad5-114">Der folgende code kompiliert `T2.vb` und Code für syntaxbezogene Compilerdiagnose nicht angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3bad5-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>

```
vbc -quiet t2.vb
```

## <a name="see-also"></a><span data-ttu-id="3bad5-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3bad5-115">See also</span></span>

- [<span data-ttu-id="3bad5-116">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="3bad5-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="3bad5-117">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="3bad5-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
