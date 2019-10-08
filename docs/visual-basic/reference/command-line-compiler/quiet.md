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
ms.openlocfilehash: 6e773c60469e8426956c92a5aa377741ba5af4d3
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005281"
---
# <a name="-quiet"></a><span data-ttu-id="808f1-102">-quiet</span><span class="sxs-lookup"><span data-stu-id="808f1-102">-quiet</span></span>

<span data-ttu-id="808f1-103">Verhindert, dass der Compiler Code für syntaxbezogene Fehler und Warnungen anzeigt.</span><span class="sxs-lookup"><span data-stu-id="808f1-103">Prevents the compiler from displaying code for syntax-related errors and warnings.</span></span>

## <a name="syntax"></a><span data-ttu-id="808f1-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="808f1-104">Syntax</span></span>

```console
-quiet
```

## <a name="remarks"></a><span data-ttu-id="808f1-105">Hinweise</span><span class="sxs-lookup"><span data-stu-id="808f1-105">Remarks</span></span>

<span data-ttu-id="808f1-106">In der Standardeinstellung ist `-quiet` nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="808f1-106">By default, `-quiet` is not in effect.</span></span> <span data-ttu-id="808f1-107">Wenn der Compiler einen Syntax bezogenen Fehler oder eine Warnung meldet, gibt er auch die Zeile aus dem Quellcode aus.</span><span class="sxs-lookup"><span data-stu-id="808f1-107">When the compiler reports a syntax-related error or warning, it also outputs the line from source code.</span></span> <span data-ttu-id="808f1-108">Bei Anwendungen, die die Compilerausgabe analysieren, ist es möglicherweise bequemer, dass der Compiler nur den Text der Diagnose ausgibt.</span><span class="sxs-lookup"><span data-stu-id="808f1-108">For applications that parse compiler output, it may be more convenient for the compiler to output only the text of the diagnostic.</span></span>

<span data-ttu-id="808f1-109">Im folgenden Beispiel gibt `Module1` einen Fehler aus, der Quellcode enthält, wenn er ohne `-quiet` kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="808f1-109">In the following example, `Module1` outputs an error that includes source code when compiled without `-quiet`.</span></span>

```vb
Module Module1
    Sub Main()
        x()
    End Sub
End Module
```

<span data-ttu-id="808f1-110">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="808f1-110">Output:</span></span>

```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
```

<span data-ttu-id="808f1-111">Kompiliert mit `-quiet`: der Compiler gibt nur Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="808f1-111">Compiled with `-quiet`, the compiler outputs only the following:</span></span>

```console
E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.
```

> [!NOTE]
> <span data-ttu-id="808f1-112">Die Option "`-quiet`" ist innerhalb der Visual Studio-Entwicklungsumgebung nicht verfügbar. Sie ist nur verfügbar, wenn Sie über die Befehlszeile kompilieren.</span><span class="sxs-lookup"><span data-stu-id="808f1-112">The `-quiet` option is not available from within the Visual Studio development environment; it is available only when compiling from the command line.</span></span>

## <a name="example"></a><span data-ttu-id="808f1-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="808f1-113">Example</span></span>

<span data-ttu-id="808f1-114">Mit dem folgenden Code wird `T2.vb` kompiliert, und es wird kein Code für die Syntax bezogene Compilerdiagnose angezeigt:</span><span class="sxs-lookup"><span data-stu-id="808f1-114">The following code compiles `T2.vb` and does not display code for syntax-related compiler diagnostics:</span></span>

```console
vbc -quiet t2.vb
```

## <a name="see-also"></a><span data-ttu-id="808f1-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="808f1-115">See also</span></span>

- [<span data-ttu-id="808f1-116">Visual Basic-Befehlszeilencompiler</span><span class="sxs-lookup"><span data-stu-id="808f1-116">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="808f1-117">Beispiele für Kompilierungsbefehlszeilen</span><span class="sxs-lookup"><span data-stu-id="808f1-117">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
