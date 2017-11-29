---
title: Quellzeilen-, Datei- und Pfadbezeichner (F#)
description: "Erfahren Sie, wie integrierte f# Bezeichnerwerte verwenden, mit die Sie auf die Quellzeilennummer Verzeichnis und Dateinamen im Code zugreifen können."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 4cfe7439-275c-4d08-980b-784e240bbf29
ms.openlocfilehash: 44cc0914226c120f2b877ce3decd25caa6817eec
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="source-line-file-and-path-identifiers"></a><span data-ttu-id="fd63a-104">Quellzeilen-, Datei- und Pfadbezeichner</span><span class="sxs-lookup"><span data-stu-id="fd63a-104">Source Line, File, and Path Identifiers</span></span>

<span data-ttu-id="fd63a-105">Die Bezeichner `__LINE__`, `__SOURCE_DIRECTORY__` und `__SOURCE_FILE__` sind integrierte Werte, mit denen Sie auf der Zeile Anzahl, Verzeichnis- und Dateinamen Quellname in Ihrem Code zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="fd63a-105">The identifiers `__LINE__`, `__SOURCE_DIRECTORY__` and `__SOURCE_FILE__` are built-in values that enable you to access the source line number, directory and file name in your code.</span></span>


## <a name="syntax"></a><span data-ttu-id="fd63a-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd63a-106">Syntax</span></span>

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a><span data-ttu-id="fd63a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd63a-107">Remarks</span></span>
<span data-ttu-id="fd63a-108">Jeder dieser Werte weist den Typ `string`.</span><span class="sxs-lookup"><span data-stu-id="fd63a-108">Each of these values has type `string`.</span></span>

<span data-ttu-id="fd63a-109">In der folgenden Tabelle werden die Quellcodezeile, Datei und Pfadbezeichner, die in f# verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="fd63a-109">The following table summarizes the source line, file, and path identifiers that are available in F#.</span></span> <span data-ttu-id="fd63a-110">Diese Bezeichner sind keine Präprozessormakros; Sie sind integrierte Werte, die vom Compiler erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="fd63a-110">These identifiers are not preprocessor macros; they are built-in values that are recognized by the compiler.</span></span>

|<span data-ttu-id="fd63a-111">Vordefinierte Bezeichner</span><span class="sxs-lookup"><span data-stu-id="fd63a-111">Predefined identifier</span></span>|<span data-ttu-id="fd63a-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fd63a-112">Description</span></span>|
|---------------------|-----------|
|`__LINE__`|<span data-ttu-id="fd63a-113">Ergibt die aktuelle Zeilennummer Berücksichtigung `#line` Direktiven.</span><span class="sxs-lookup"><span data-stu-id="fd63a-113">Evaluates to the current line number, considering `#line` directives.</span></span>|
|`__SOURCE_DIRECTORY__`|<span data-ttu-id="fd63a-114">Ergibt den aktuellen vollständigen Pfad des Quellverzeichnisses Berücksichtigung `#line` Direktiven.</span><span class="sxs-lookup"><span data-stu-id="fd63a-114">Evaluates to the current full path of the source directory, considering `#line` directives.</span></span>|
|`__SOURCE_FILE__`|<span data-ttu-id="fd63a-115">Der Name der aktuellen Quelldatei und der zugehörige Pfad ergibt Berücksichtigung `#line` Direktiven.</span><span class="sxs-lookup"><span data-stu-id="fd63a-115">Evaluates to the current source file name and its path, considering `#line` directives.</span></span>|
<span data-ttu-id="fd63a-116">Weitere Informationen zu den `#line` -Direktive finden Sie unter [Compilerdirektiven](compiler-directives.md).</span><span class="sxs-lookup"><span data-stu-id="fd63a-116">For more information about the `#line` directive, see [Compiler Directives](compiler-directives.md).</span></span>

## <a name="example"></a><span data-ttu-id="fd63a-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fd63a-117">Example</span></span>

<span data-ttu-id="fd63a-118">Das folgende Codebeispiel veranschaulicht die Verwendung dieser Werte.</span><span class="sxs-lookup"><span data-stu-id="fd63a-118">The following code example demonstrates the use of these values.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

<span data-ttu-id="fd63a-119">Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="fd63a-119">Output:</span></span>

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a><span data-ttu-id="fd63a-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd63a-120">See Also</span></span>
[<span data-ttu-id="fd63a-121">Compileranweisungen</span><span class="sxs-lookup"><span data-stu-id="fd63a-121">Compiler Directives</span></span>](compiler-directives.md)

[<span data-ttu-id="fd63a-122">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="fd63a-122">F# Language Reference</span></span>](index.md)
