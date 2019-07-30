---
title: Quellzeilen-, Datei- und Pfadbezeichner
description: Erfahren Sie, wie Sie integrierte F# Bezeichnerwerte verwenden, die Ihnen den Zugriff auf die Quellzeilen Nummer, das Verzeichnis und den Dateinamen in Ihrem Code ermöglichen.
ms.date: 05/16/2016
ms.openlocfilehash: 5ff36210edc75370f8baf9ee7be057f3ac0c3979
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627114"
---
# <a name="source-line-file-and-path-identifiers"></a>Quellzeilen-, Datei- und Pfadbezeichner

Die Bezeichner und`__SOURCE_FILE__`sind integrierte Werte, mit denen Sie auf die Quell Zeilennummer, das Verzeichnis und den Dateinamen im Code zugreifen können. `__SOURCE_DIRECTORY__` `__LINE__`

## <a name="syntax"></a>Syntax

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>Hinweise

Jeder dieser Werte weist den Typ `string`auf.

Die Quellzeile, Datei, und Pfadbezeichner, die in F# verfügbar sind, werden in der folgende Tabelle zusammengefasst. Diese Bezeichner sind keine Präprozessormakros. Sie sind integrierte Werte, die vom Compiler erkannt werden.

|Vordefinierter Bezeichner|Beschreibung|
|---------------------|-----------|
|`__LINE__`|Wird als aktuelle Zeilennummer ausgewertet, wobei `#line` Direktiven berücksichtigt werden.|
|`__SOURCE_DIRECTORY__`|Wertet den aktuellen vollständigen Pfad des Quell Verzeichnisses aus, wobei `#line` Direktiven in Erwägung gezogen werden.|
|`__SOURCE_FILE__`|Ergibt den aktuellen Quell Dateinamen ohne den Pfad, in dem `#line` die Direktiven berücksichtigt werden.|

Weitere Informationen `#line` zur-Direktive finden Sie unter [Compilerdirektiven](compiler-directives.md).

## <a name="example"></a>Beispiel

Im folgenden Codebeispiel wird die Verwendung dieser Werte veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

Ausgabe:

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: Program.fs
```

## <a name="see-also"></a>Siehe auch

- [Compileranweisungen](compiler-directives.md)
- [F#-Sprachreferenz](index.md)
