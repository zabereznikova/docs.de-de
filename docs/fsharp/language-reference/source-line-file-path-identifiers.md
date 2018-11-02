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
# <a name="source-line-file-and-path-identifiers"></a>Quellzeilen-, Datei- und Pfadbezeichner

Die Bezeichner `__LINE__`, `__SOURCE_DIRECTORY__` und `__SOURCE_FILE__` sind integrierte Werte, die Sie auf der Zeile, das Verzeichnis und Datei Quellenname in Ihrem Code zugreifen können.

## <a name="syntax"></a>Syntax

```fsharp
__LINE__
__SOURCE_DIRECTORY__
__SOURCE_FILE__
```

## <a name="remarks"></a>Hinweise

Jeder dieser Werte weist den Typ `string`.

Die Quellzeile, Datei, und Pfadbezeichner, die in f# verfügbar sind, werden in der folgende Tabelle zusammengefasst. Diese Bezeichner sind keine Präprozessormakros; Sie sind integrierte Werte, die vom Compiler erkannt werden.

|Vordefinierte Bezeichner|Beschreibung|
|---------------------|-----------|
|`__LINE__`|Ergibt die aktuelle Zeilennummer, in Betracht ziehen `#line` Anweisungen.|
|`__SOURCE_DIRECTORY__`|Ergibt den aktuellen, vollständigen Pfad des Quellverzeichnisses, in Betracht ziehen `#line` Anweisungen.|
|`__SOURCE_FILE__`|Ergibt den aktuellen Dateinamen für die Quelle und des Pfads, in Betracht ziehen `#line` Anweisungen.|
Weitere Informationen zu den `#line` -Anweisung finden Sie unter [Compilerdirektiven](compiler-directives.md).

## <a name="example"></a>Beispiel

Das folgende Codebeispiel veranschaulicht die Verwendung der folgenden Werte an.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet7401.fs)]

Ausgabe:

```
Line: 4
Source Directory: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo
Source File: C:\Users\username\Documents\Visual Studio 2017\Projects\SourceInfo\SourceInfo\Program.fs
```

## <a name="see-also"></a>Siehe auch

- [Compileranweisungen](compiler-directives.md)
- [F#-Sprachreferenz](index.md)
