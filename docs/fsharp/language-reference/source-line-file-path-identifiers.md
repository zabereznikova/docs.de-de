---
title: Quellzeilen-, Datei- und Pfadbezeichner (F#)
description: Erfahren Sie, wie mit integrierten F#-ID-Werte, die Sie auf die Zeilennummer der Quelle, Verzeichnis und Dateinamen in Ihrem Code zugreifen können.
ms.date: 05/16/2016
ms.openlocfilehash: 14f710d1412c3420ec627dc30216ba2e89f16bcd
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43865126"
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="630fa-103">Quellzeilen-, Datei- und Pfadbezeichner</span><span class="sxs-lookup"><span data-stu-id="630fa-103">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="630fa-104">Die Bezeichner `__LINE__`, `__SOURCE_DIRECTORY__` und `__SOURCE_FILE__` sind integrierte Werte, die Sie auf der Zeile, das Verzeichnis und Datei Quellenname in Ihrem Code zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="630fa-104">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>

## <a name="syntax"></a><span data-ttu-id="630fa-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="630fa-105">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="630fa-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="630fa-106">Remarks</span></span>

<span data-ttu-id="630fa-107">Jeder dieser Werte weist den Typ `string`.</span><span class="sxs-lookup"><span data-stu-id="630fa-107">Each of these values has type `string`.</span></span>

<span data-ttu-id="630fa-108">Die Quellzeile, Datei, und Pfadbezeichner, die in F# verfügbar sind, werden in der folgende Tabelle zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="630fa-108">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="630fa-109">Diese Bezeichner sind keine Präprozessormakros; Sie sind integrierte Werte, die vom Compiler erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="630fa-109">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="630fa-110">Vordefinierte Bezeichner</span><span class="sxs-lookup"><span data-stu-id="630fa-110">Predefined identifier</span></span>|<span data-ttu-id="630fa-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="630fa-111">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="630fa-112">Ergibt die aktuelle Zeilennummer, in Betracht ziehen `#line` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="630fa-112">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="630fa-113">Ergibt den aktuellen, vollständigen Pfad des Quellverzeichnisses, in Betracht ziehen `#line` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="630fa-113">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="630fa-114">Ergibt den aktuellen Dateinamen für die Quelle und des Pfads, in Betracht ziehen `#line` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="630fa-114">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|
<span data-ttu-id="630fa-115">Weitere Informationen zu den `#line` -Anweisung finden Sie unter [Compilerdirektiven](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="630fa-115">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="630fa-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="630fa-116">Example</span></span>

<span data-ttu-id="630fa-117">Das folgende Codebeispiel veranschaulicht die Verwendung der folgenden Werte an.</span><span class="sxs-lookup"><span data-stu-id="630fa-117">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="630fa-118">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="630fa-118">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="630fa-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="630fa-119">See also</span></span>

- [<span data-ttu-id="630fa-120">Compileranweisungen</span><span class="sxs-lookup"><span data-stu-id="630fa-120">Compiler Directives</span></span>](compiler-directives.md)
- [<span data-ttu-id="630fa-121">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="630fa-121">F# Language Reference</span></span>](index.md)
