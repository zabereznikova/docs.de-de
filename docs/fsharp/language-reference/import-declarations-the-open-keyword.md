---
title: 'Importdeklarationen: Das open-Schlüsselwort (F#)'
description: Erfahren Sie mehr über f# Importdeklarationen und wie sie ein Modul oder einen Namespace angeben, dessen Elemente Sie ohne Verwendung eines vollqualifizierten Namens verweisen können.
ms.date: 05/16/2016
ms.openlocfilehash: 8cae4b4f5418689bfb0933b7db4ec23a313d5ed8
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "46586622"
---
# <a name="import-declarations-the-open-keyword"></a>Importdeklarationen: Das `open` Schlüsselwort

> [!NOTE]
Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Ein *Importdeklaration* gibt ein Modul oder der Namespace, dessen Elemente Sie ohne Verwendung eines vollqualifizierten Namens verweisen können.

## <a name="syntax"></a>Syntax

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Hinweise

Verweisen auf Code mit den vollqualifizierten Pfad der Namespace- oder Modulebene kann jedem Code erstellen, die schwer zu schreiben, lesen und zu verwalten. Sie können stattdessen die `open` -Schlüsselwort für häufig verwendet, Module und Namespaces, damit Sie Folgendes: Wenn Sie ein Element dieses Moduls oder dieser Namespace verweisen, können Sie die Kurzform des Namens anstelle des vollqualifizierten Namens verwenden. Dieses Schlüsselwort ist ähnlich wie die `using` -Schlüsselwort in c#, `using namespace` in Visual C++ und `Imports` in Visual Basic.

Das Modul oder einen angegebenen Namespace muss sich im selben Projekt oder in einem Projekt verwiesen wird oder die Assembly sein. Wenn es nicht der Fall ist, können Sie fügen einen Verweis auf das Projekt, oder Verwenden der `-reference` Befehl`-`Befehlszeilenoption (oder dessen Abkürzung, `-r`). Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).

Die Import-Deklaration stellt die Namen, die in der Deklaration bis zum Ende des einschließenden Namespace, Modul, oder der Datei folgenden Code zur Verfügung.

Wenn Sie mehrere Deklarationen auf Importieren, verwenden sie in separaten Zeilen angezeigt werden sollen.

Der folgende Code zeigt die Verwendung der `open` Schlüsselwort, um Code zu vereinfachen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

F#-Compiler wird eine Fehlermeldung oder Warnung nicht ausgeben, wenn es sich bei Mehrdeutigkeiten auftreten, bei der gleiche Namen in mehr als ein open-Modul oder einen Namespace. Wenn Mehrdeutigkeiten auftreten, bevorzugt f# die mehr zuletzt geöffneten Modul oder einen Namespace. In den folgenden Code, z. B. `empty` bedeutet, dass `Seq.empty`, auch wenn `empty` befindet sich in beiden die `List` und `Seq` Module.

```fsharp
open List
open Seq
printfn "%A" empty
```

Daher vorsichtig, wenn Sie Module oder Namespaces wie z. B. Öffnen `List` oder `Seq` , die Elemente, die identische Namen haben, erwägen Sie stattdessen mit dem qualifizierten Namen enthalten. Sie sollten alle Situation vermeiden, in der der Code hängt von der Reihenfolge der Importdeklarationen ist.

## <a name="namespaces-that-are-open-by-default"></a>Namespaces, die standardmäßig geöffnet werden.

Einige Namespaces werden häufig in F#-Code verwendet, sie ohne eine explizite Importdeklaration implizit geöffnet sind. Die folgende Tabelle zeigt die Namespaces, die standardmäßig geöffnet werden.

|Namespace|Beschreibung|
|---------|-----------|
|`Microsoft.FSharp.Core`|Enthält grundlegende F#-Typdefinitionen für integrierte Typen wie z. B. `int` und `float`.|
|`Microsoft.FSharp.Core.Operators`|Enthält grundlegende arithmetische Operationen, z. B. `+` und `*`.|
|`Microsoft.FSharp.Collections`|Enthält die unveränderlichen Auflistungsklassen wie `List` und `Array`.|
|`Microsoft.FSharp.Control`|Enthält Typen zum Steuerelement-Konstrukten, z. B. verzögerte Auswertung und asynchronen Workflows.|
|`Microsoft.FSharp.Text`|Enthält Funktionen für formatierte e/a, wie z. B. die `printf` Funktion.|

## <a name="autoopen-attribute"></a>AutoOpen-Attribut

Sie können anwenden, die `AutoOpen` -Attribut auf eine Assembly, sollten Sie automatisch einen Namespace oder Modul geöffnet, wenn die Assembly verwiesen wird. Sie können auch anwenden, die `AutoOpen` -Attribut auf ein Modul das Modul automatisch geöffnet wird, wenn das übergeordnete Modul oder Namespace geöffnet wird. Weitere Informationen finden Sie unter [Core.AutoOpenAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).

## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess-Attribut

Einige Module, Datensätzen oder union-Typen können angeben, die `RequireQualifiedAccess` Attribut. Wenn Sie diese Module, Datensätze und Unions Elemente verweisen, müssen Sie unabhängig davon, ob Sie eine Importdeklaration enthalten einen qualifizierten Namen verwenden. Wenn Sie dieses Attribut strategisch auf verwenden verwendet Namen, Typen, die häufig zu definieren, lassen sich Namenskonflikte zu vermeiden, und machen dadurch Code stabiler gegenüber Änderungen in Bibliotheken. Weitere Informationen finden Sie unter [Core.RequireQualifiedAccessAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).

## <a name="see-also"></a>Siehe auch

- [-Sprachreferenz](index.md)
- [Namespaces](namespaces.md)
- [Module](modules.md)
