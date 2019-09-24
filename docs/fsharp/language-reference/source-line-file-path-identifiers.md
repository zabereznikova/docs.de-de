---
title: Quellzeilen-, Datei- und Pfadbezeichner
description: Erfahren Sie, wie Sie integrierte F# Bezeichnerwerte verwenden, die Ihnen den Zugriff auf die Quellzeilen Nummer, das Verzeichnis und den Dateinamen in Ihrem Code ermöglichen.
ms.date: 05/16/2016
ms.openlocfilehash: f22c3dfb3cb106fbe45883ffd7de01feac30db00
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216745"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="ce888-103">Quellzeilen-, Datei- und Pfadbezeichner</span><span class="sxs-lookup"><span data-stu-id="ce888-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="ce888-104">Die Bezeichner und`__SOURCE_FILE__`sind integrierte Werte, mit denen Sie auf die Quell Zeilennummer, das Verzeichnis und den Dateinamen im Code zugreifen können. `__SOURCE_DIRECTORY__` `__LINE__`</span><span class="sxs-lookup"><span data-stu-id="ce888-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="ce888-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="ce888-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="ce888-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="ce888-106">Remarks</span></span>

<span data-ttu-id="ce888-107">Jeder dieser Werte weist den Typ `string`auf.</span><span class="sxs-lookup"><span data-stu-id="ce888-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="ce888-108">Die Quellzeile, Datei, und Pfadbezeichner, die in F# verfügbar sind, werden in der folgende Tabelle zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="ce888-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="ce888-109">Diese Bezeichner sind keine Präprozessormakros. Sie sind integrierte Werte, die vom Compiler erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="ce888-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="ce888-110">Vordefinierter Bezeichner</span><span class="sxs-lookup"><span data-stu-id="ce888-110">Predefined identifier</span></span>|<span data-ttu-id="ce888-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ce888-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="ce888-112">Wird als aktuelle Zeilennummer ausgewertet, wobei `#line` Direktiven berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="ce888-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="ce888-113">Wertet den aktuellen vollständigen Pfad des Quell Verzeichnisses aus, wobei `#line` Direktiven in Erwägung gezogen werden.</span><span class="sxs-lookup"><span data-stu-id="ce888-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="ce888-114">Ergibt den aktuellen Quell Dateinamen ohne den Pfad, in dem `#line` die Direktiven berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="ce888-114">Evaluates to the current source file name, without its path, considering `#line` directives.</span></span>|

<span data-ttu-id="ce888-115">Weitere Informationen `#line` zur-Direktive finden Sie unter [Compilerdirektiven](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="ce888-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="ce888-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ce888-116">Example</span></span>

<span data-ttu-id="ce888-117">Im folgenden Codebeispiel wird die Verwendung dieser Werte veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="ce888-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="ce888-118">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="ce888-118">Output:</span></span>

```console
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a><span data-ttu-id="ce888-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce888-119">See also</span></span>

- [<span data-ttu-id="ce888-120">Compileranweisungen</span><span class="sxs-lookup"><span data-stu-id="ce888-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="ce888-121">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="ce888-121">F# Language Reference</span></span>](index.md)
