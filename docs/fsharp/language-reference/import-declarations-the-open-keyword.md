---
title: 'Importdeklarationen: Das open-Schlüsselwort (F#)'
description: Erfahren Sie mehr über f# Importdeklarationen und wie sie ein Modul oder einen Namespace angeben, dessen Elemente, die Sie verweisen können, ohne einen vollqualifizierten Namen verwenden.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: ddbc1086e2adbe8dae408f4d39fd5af888d7fd5e
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="import-declarations-the-open-keyword"></a>Importdeklarationen: Das `open` Schlüsselwort

> [!NOTE]
Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Ein *importieren Deklaration* gibt ein Modul oder einen Namespace, dessen Elemente, die Sie verweisen können, ohne einen vollqualifizierten Namen verwenden.


## <a name="syntax"></a>Syntax

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Hinweise
Verweisen auf Code mithilfe des vollqualifizierten Pfads der Namespace- oder Modulebene kann jedem Code erstellen, die schwer zu schreiben, lesen und zu pflegen ist. Stattdessen können Sie die `open` -Schlüsselwort für häufig verwendete Module und Namespaces, damit Sie Folgendes: Wenn Sie ein Mitglied dieses Modul oder einen Namespace verweisen, können Sie die Kurzform des Namens anstelle des vollqualifizierten Namens verwenden. Dieses Schlüsselwort ähnelt der `using` -Schlüsselwort in c#, `using namespace` in Visual C++ und `Imports` in Visual Basic.

Das Modul oder einen angegebenen Namespace muss im selben Projekt oder in einem Projekt verwiesen wird oder die Assembly sein. Wenn es nicht der Fall ist, können Sie einen Verweis auf das Projekt hinzufügen oder verwenden Sie die `-reference` Befehl`-`Befehlszeilenoption (oder dessen Abkürzung `-r`). Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).

Die Importdeklaration stellt die Namen in der Deklaration bis zum Ende des einschließenden Namespace, Moduls oder Datei der folgende Code zur Verfügung.

Wenn Sie mehrere Importdeklarationen verwenden, sollten sie in separaten Zeilen angezeigt werden.

Der folgende Code zeigt die Verwendung der `open` Schlüsselwort, um Code zu vereinfachen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

F#-Compiler ausgeben, wenn Mehrdeutigkeiten auftreten, wenn es sich bei der gleiche Namen in mehr als eine open-Modul oder einen Namespace tritt auf, keinen Fehler oder eine Warnung. Wenn Mehrdeutigkeiten auftreten, bevorzugt f#, die mehr zuletzt geöffneten Modul oder einen Namespace. Im folgenden Code wird z. B. `empty` bedeutet `Seq.empty`, obwohl `empty` befindet sich in beiden die `List` und `Seq` Module.

```fsharp
open List
open Seq
printfn "%A" empty
```

Aus diesem Grund, seien Sie vorsichtig, wenn Sie Module oder Namespaces wie z. B. Öffnen `List` oder `Seq` , die Elemente, die identische Namen haben, erwägen Sie stattdessen mit dem qualifizierten Namen enthalten. Sie sollten jede Situation vermeiden, in der der Code die Reihenfolge der Importdeklarationen abhängig ist.


## <a name="namespaces-that-are-open-by-default"></a>Namespaces, die standardmäßig geöffnet sind
Einige Namespaces werden so häufig in f#-Code verwendet, sie ohne die Notwendigkeit einer Deklaration expliziter Import implizit geöffnet sind. In der folgenden Tabelle werden die Namespaces angezeigt, die standardmäßig geöffnet sind.

|Namespace|Beschreibung|
|---------|-----------|
|`Microsoft.FSharp.Core`|Enthält grundlegende F#-Typdefinitionen für integrierte Typen wie z. B. `int` und `float`.|
|`Microsoft.FSharp.Core.Operators`|Enthält grundlegende arithmetische Operationen wie `+` und `*`.|
|`Microsoft.FSharp.Collections`|Enthält die unveränderlichen Auflistungsklassen wie `List` und `Array`.|
|`Microsoft.FSharp.Control`|Enthält Typen zum Steuerelementkonstrukte, wie z. B. verzögerte Auswertung und asynchrone Workflows.|
|`Microsoft.FSharp.Text`|Enthält Funktionen für formatierte e/a, z. B. die `printf` Funktion.|

## <a name="autoopen-attribute"></a>AutoOpen-Attribut
Sie können Anwenden der `AutoOpen` -Attribut auf eine Assembly, wenn ein Namespace oder Modul automatisch geöffnet, wenn die Assembly verwiesen werden soll. Sie können auch anwenden, die `AutoOpen` -Attribut auf ein Modul, dass das Modul automatisch geöffnet, wenn das übergeordnete Modul oder einen Namespace geöffnet wird. Weitere Informationen finden Sie unter [Core.AutoOpenAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).


## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess-Attribut
Einige Module, Datensätze oder union-Typen können angeben, die `RequireQualifiedAccess` Attribut. Wenn Sie Elemente von diesen Modulen, Datensätze oder Unions verweisen, müssen Sie unabhängig davon, ob Sie eine Importdeklaration enthalten einen qualifizierten Namen verwenden. Wenn Sie dieses Attribut strategisch auf Typen, die häufig definieren Namen verwendet, lassen sich Namenskonflikte vermieden und somit Code stabiler auf Änderungen in Bibliotheken. Weitere Informationen finden Sie unter [Core.RequireQualifiedAccessAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).


## <a name="see-also"></a>Siehe auch
[-Sprachreferenz](index.md)

[Namespaces](namespaces.md)

[Module](modules.md)

