---
title: Quellzeilen-, Datei- und Pfadbezeichner (F#)
description: Erfahren Sie, wie integrierte f# Bezeichnerwerte verwenden, mit die Sie auf die Quellzeilennummer Verzeichnis und Dateinamen im Code zugreifen können.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 18a26f0aa0a0c1f9c0b448ec46eaebd540391324
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="source-line-file-and-path-identifiers"></a>Quellzeilen-, Datei- und Pfadbezeichner

Die Bezeichner `__LINE__`, `__SOURCE_DIRECTORY__` und `__SOURCE_FILE__` sind integrierte Werte, mit denen Sie auf der Zeile Anzahl, Verzeichnis- und Dateinamen Quellname in Ihrem Code zugreifen können.


## <a name="syntax"></a>Syntax

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>Hinweise
Jeder dieser Werte weist den Typ `string`.

In der folgenden Tabelle werden die Quellcodezeile, Datei und Pfadbezeichner, die in f# verfügbar sind. Diese Bezeichner sind keine Präprozessormakros; Sie sind integrierte Werte, die vom Compiler erkannt werden.

|Vordefinierte Bezeichner|Beschreibung|
|---------------------|-----------|
|`__LINE__`|Ergibt die aktuelle Zeilennummer Berücksichtigung `#line` Direktiven.|
|`__SOURCE_DIRECTORY__`|Ergibt den aktuellen vollständigen Pfad des Quellverzeichnisses Berücksichtigung `#line` Direktiven.|
|`__SOURCE_FILE__`|Der Name der aktuellen Quelldatei und der zugehörige Pfad ergibt Berücksichtigung `#line` Direktiven.|
Weitere Informationen zu den `#line` -Direktive finden Sie unter [Compilerdirektiven](compiler-directives.md).

## <a name="example"></a>Beispiel

Das folgende Codebeispiel veranschaulicht die Verwendung dieser Werte.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

Ausgabe:

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a>Siehe auch
[Compileranweisungen](compiler-directives.md)

[F#-Sprachreferenz](index.md)
