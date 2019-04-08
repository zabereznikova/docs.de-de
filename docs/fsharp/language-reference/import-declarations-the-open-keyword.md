---
title: 'Importdeklarationen: Das open-Schlüsselwort'
description: Erfahren Sie mehr über F# Importdeklarationen und wie sie ein Modul oder einen Namespace angeben, dessen Elemente Sie ohne Verwendung eines vollqualifizierten Namens verweisen können.
ms.date: 04/04/2019
ms.openlocfilehash: ad64190c3243c57a185f3b864270fca80590f079
ms.sourcegitcommit: 68eb5c4928e2b082f178a42c16f73fedf52c2ab8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2019
ms.locfileid: "59055000"
---
# <a name="import-declarations-the-open-keyword"></a>Importdeklarationen: Die `open` Schlüsselwort

> [!NOTE]
> Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Ein *Importdeklaration* gibt ein Modul oder der Namespace, dessen Elemente Sie ohne Verwendung eines vollqualifizierten Namens verweisen können.

## <a name="syntax"></a>Syntax

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Hinweise

Verweisen auf Code mit den vollqualifizierten Pfad der Namespace- oder Modulebene kann jedem Code erstellen, die schwer zu schreiben, lesen und zu verwalten. Sie können stattdessen die `open` -Schlüsselwort für häufig verwendet, Module und Namespaces, damit Sie Folgendes: Wenn Sie ein Element dieses Moduls oder dieser Namespace verweisen, können Sie die Kurzform des Namens anstelle des vollqualifizierten Namens verwenden. Dieses Schlüsselwort ist ähnlich wie die `using` -Schlüsselwort in C#, `using namespace` in Visual C++ und `Imports` in Visual Basic.

Das Modul oder einen angegebenen Namespace muss sich im selben Projekt oder in einem Projekt verwiesen wird oder die Assembly sein. Wenn es nicht der Fall ist, können Sie fügen einen Verweis auf das Projekt, oder Verwenden der `-reference` Befehl`-`Befehlszeilenoption (oder dessen Abkürzung, `-r`). Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).

Die Import-Deklaration stellt die Namen, die in der Deklaration bis zum Ende des einschließenden Namespace, Modul, oder der Datei folgenden Code zur Verfügung.

Wenn Sie mehrere Deklarationen auf Importieren, verwenden sie in separaten Zeilen angezeigt werden sollen.

Der folgende Code zeigt die Verwendung der `open` Schlüsselwort, um Code zu vereinfachen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

Die F# Compiler gibt keine Fehler oder Warnung, wenn Mehrdeutigkeiten auftreten, bei der gleiche Namen in mehr als ein open-Modul oder einen Namespace. Wenn Mehrdeutigkeiten auftreten, bevorzugt F# die mehr zuletzt geöffneten Modul oder einen Namespace. In den folgenden Code, z. B. `empty` bedeutet, dass `Seq.empty`, auch wenn `empty` befindet sich in beiden die `List` und `Seq` Module.

```fsharp
open List
open Seq
printfn "%A" empty
```

Daher vorsichtig, wenn Sie Module oder Namespaces wie z. B. Öffnen `List` oder `Seq` , die Elemente, die identische Namen haben, erwägen Sie stattdessen mit dem qualifizierten Namen enthalten. Sie sollten alle Situation vermeiden, in der der Code hängt von der Reihenfolge der Importdeklarationen ist.

## <a name="namespaces-that-are-open-by-default"></a>Namespaces, die standardmäßig geöffnet werden.

Einige Namespaces dienen häufig in F# Code, dass sie ohne eine explizite Importdeklaration implizit geöffnet werden. Die folgende Tabelle zeigt die Namespaces, die standardmäßig geöffnet werden.

|Namespace|Beschreibung|
|---------|-----------|
|`Microsoft.FSharp.Core`|Enthält grundlegende F# Typdefinitionen für integrierte Typen wie `int` und `float`.|
|`Microsoft.FSharp.Core.Operators`|Enthält grundlegende arithmetische Operationen, z. B. `+` und `*`.|
|`Microsoft.FSharp.Collections`|Enthält die unveränderlichen Auflistungsklassen wie `List` und `Array`.|
|`Microsoft.FSharp.Control`|Enthält Typen zum Steuerelement-Konstrukten, z. B. verzögerte Auswertung und asynchronen Workflows.|
|`Microsoft.FSharp.Text`|Enthält Funktionen für formatierte e/a, wie z. B. die `printf` Funktion.|

## <a name="autoopen-attribute"></a>AutoOpen-Attribut

Sie können anwenden, die `AutoOpen` -Attribut auf eine Assembly, sollten Sie automatisch einen Namespace oder Modul geöffnet, wenn die Assembly verwiesen wird. Sie können auch anwenden, die `AutoOpen` -Attribut auf ein Modul das Modul automatisch geöffnet wird, wenn das übergeordnete Modul oder Namespace geöffnet wird. Weitere Informationen finden Sie unter [Core.AutoOpenAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).

## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess Attribute

Einige Module, Datensätzen oder union-Typen können angeben, die `RequireQualifiedAccess` Attribut. Wenn Sie diese Module, Datensätze und Unions Elemente verweisen, müssen Sie unabhängig davon, ob Sie eine Importdeklaration enthalten einen qualifizierten Namen verwenden. Wenn Sie dieses Attribut strategisch auf verwenden verwendet Namen, Typen, die häufig zu definieren, lassen sich Namenskonflikte zu vermeiden, und machen dadurch Code stabiler gegenüber Änderungen in Bibliotheken. Weitere Informationen finden Sie unter [Core.RequireQualifiedAccessAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Namespaces](namespaces.md)
- [Module](modules.md)
