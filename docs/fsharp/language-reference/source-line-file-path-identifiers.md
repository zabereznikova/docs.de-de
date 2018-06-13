---
title: Quellzeilen-, Datei- und Pfadbezeichner (F#)
description: Erfahren Sie, wie integrierte f# Bezeichnerwerte verwenden, mit die Sie auf die Quellzeilennummer Verzeichnis und Dateinamen im Code zugreifen können.
ms.date: 05/16/2016
ms.openlocfilehash: 76b705fec0d951b12655edbe69e7c9212f50779d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33565216"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="d44e6-103">Quellzeilen-, Datei- und Pfadbezeichner</span><span class="sxs-lookup"><span data-stu-id="d44e6-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="d44e6-104">Die Bezeichner `__LINE__`, `__SOURCE_DIRECTORY__` und `__SOURCE_FILE__` sind integrierte Werte, mit denen Sie auf der Zeile Anzahl, Verzeichnis- und Dateinamen Quellname in Ihrem Code zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="d44e6-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>


## <a name="syntax"></a><span data-ttu-id="d44e6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="d44e6-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="d44e6-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d44e6-106">Remarks</span></span>
<span data-ttu-id="d44e6-107">Jeder dieser Werte weist den Typ `string`.</span><span class="sxs-lookup"><span data-stu-id="d44e6-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="d44e6-108">In der folgenden Tabelle werden die Quellcodezeile, Datei und Pfadbezeichner, die in f# verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="d44e6-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="d44e6-109">Diese Bezeichner sind keine Präprozessormakros; Sie sind integrierte Werte, die vom Compiler erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="d44e6-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="d44e6-110">Vordefinierte Bezeichner</span><span class="sxs-lookup"><span data-stu-id="d44e6-110">Predefined identifier</span></span>|<span data-ttu-id="d44e6-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d44e6-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="d44e6-112">Ergibt die aktuelle Zeilennummer Berücksichtigung `#line` Direktiven.</span><span class="sxs-lookup"><span data-stu-id="d44e6-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="d44e6-113">Ergibt den aktuellen vollständigen Pfad des Quellverzeichnisses Berücksichtigung `#line` Direktiven.</span><span class="sxs-lookup"><span data-stu-id="d44e6-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="d44e6-114">Der Name der aktuellen Quelldatei und der zugehörige Pfad ergibt Berücksichtigung `#line` Direktiven.</span><span class="sxs-lookup"><span data-stu-id="d44e6-114">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|
<span data-ttu-id="d44e6-115">Weitere Informationen zu den `#line` -Direktive finden Sie unter [Compilerdirektiven](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="d44e6-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="d44e6-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d44e6-116">Example</span></span>

<span data-ttu-id="d44e6-117">Das folgende Codebeispiel veranschaulicht die Verwendung dieser Werte.</span><span class="sxs-lookup"><span data-stu-id="d44e6-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="d44e6-118">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="d44e6-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="d44e6-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d44e6-119">See Also</span></span>
[<span data-ttu-id="d44e6-120">Compileranweisungen</span><span class="sxs-lookup"><span data-stu-id="d44e6-120">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="d44e6-121">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="d44e6-121">F# Language Reference</span></span>](index.md)
