---
title: 'Importdeklarationen: Das open-Schlüsselwort'
description: 'Erfahren Sie mehr über F #-Import Deklarationen und wie Sie ein Modul oder einen Namespace angeben, auf dessen Elemente verwiesen werden kann, ohne einen voll qualifizierten Namen zu verwenden.'
ms.date: 08/15/2020
ms.openlocfilehash: 4d3fd159aa4b334e9db0d7f756047470ad9c0829
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739684"
---
# <a name="import-declarations-the-open-keyword"></a>Import Deklarationen: das- `open` Schlüsselwort

Eine *Import Deklaration* gibt ein Modul oder einen Namespace an, auf dessen Elemente verwiesen werden kann, ohne einen voll qualifizierten Namen zu verwenden.

## <a name="syntax"></a>Syntax

```fsharp
open module-or-namespace-name
open type type-name
```

## <a name="remarks"></a>Bemerkungen

Wenn Sie den voll qualifizierten Namespace-oder Modulpfad jedes Mal auf Code verweisen, können Sie Code erstellen, der schwer zu schreiben, zu lesen und zu warten ist. Stattdessen können Sie das `open` -Schlüsselwort für häufig verwendete Module und Namespaces verwenden, sodass Sie die Kurzform des Namens anstelle des voll qualifizierten Namens verwenden können, wenn Sie auf ein Member dieses Moduls oder Namespace verweisen. Dieses Schlüsselwort ähnelt dem `using` -Schlüsselwort in c#, `using namespace` in Visual C++ und `Imports` in Visual Basic.

Das angegebene Modul oder der angegebene Namespace muss sich im selben Projekt oder in einem referenzierten Projekt oder einer referenzierten Assembly befinden. Wenn dies nicht der Fall ist, können Sie dem Projekt einen Verweis hinzufügen oder die `-reference` Befehlszeilenoption (oder die Abkürzung, `-r` ) verwenden. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).

Die Import Deklaration stellt die Namen im Code, der der Deklaration folgt, bis zum Ende des einschließenden Namespace, Moduls oder der Datei zur Verfügung.

Wenn Sie mehrere Import Deklarationen verwenden, sollten diese in separaten Zeilen angezeigt werden.

Der folgende Code zeigt die Verwendung des- `open` Schlüssel Worts, um Code zu vereinfachen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

Der F #-Compiler gibt keinen Fehler oder eine Warnung aus, wenn Mehrdeutigkeiten auftreten, wenn derselbe Name in mehreren geöffneten Modulen oder Namespaces auftritt. Wenn Mehrdeutigkeiten auftreten, gibt F # dem zuletzt geöffneten Modul oder Namespace Vorrang. Im folgenden Code bedeutet beispielsweise, dass `empty` sich `Seq.empty` `empty` sowohl im `List` -Modul als auch im- `Seq` Modul befindet.

```fsharp
open List
open Seq
printfn %"{empty}"
```

Daher sollten Sie beim Öffnen von Modulen oder Namespaces wie oder, die Member `List` `Seq` mit identischen Namen enthalten, vorsichtig sein. verwenden Sie stattdessen die qualifizierten Namen. Vermeiden Sie jede Situation, in der der Code von der Reihenfolge der Import Deklarationen abhängig ist.

## <a name="open-type-declarations"></a>Open-Typdeklarationen

F # unterstützt `open` für einen Typ wie folgt:

```fsharp
open type System.Math
PI
```

Dadurch werden alle zugänglichen statischen Felder und Member für den-Typ verfügbar gemacht.

Sie können auch `open` F #-definierte [Daten Satz](records.md) -und Unterscheidungs [Union](discriminated-unions.md) -Typen zur Offenlegung statischer Member nutzen. Im Fall von Unterscheidungs-Unions können Sie auch die Union-Fälle verfügbar machen. Dies kann hilfreich sein, um auf Union-Fälle in einem Typ zuzugreifen, der innerhalb eines Moduls deklariert ist, das Sie möglicherweise nicht öffnen möchten, wie hier:

```fsharp
module M =
    type DU = A | B | C

    let someOtherFunction x = x + 1

// Open only the type inside the module
open type M.DU

printfn "%A" A
```

## <a name="namespaces-that-are-open-by-default"></a>Standardmäßig geöffnete Namespaces

Einige Namespaces werden so häufig in F #-Code verwendet, dass Sie implizit geöffnet werden, ohne dass eine explizite Import Deklaration erforderlich ist. In der folgenden Tabelle werden die standardmäßig geöffneten Namespaces angezeigt.

|Namespace|BESCHREIBUNG|
|---------|-----------|
|`FSharp.Core`|Enthält grundlegende F #-Typdefinitionen für integrierte Typen wie `int` und `float` .|
|`FSharp.Core.Operators`|Enthält grundlegende arithmetische Operationen wie `+` und `*` .|
|`FSharp.Collections`|Enthält unveränderliche Auflistungs Klassen, `List` z `Array` . b. und.|
|`FSharp.Control`|Enthält Typen für steuerungskonstrukte, wie z. b. Lazy Evaluation und asynchrone Workflows.|
|`FSharp.Text`|Enthält Funktionen für formatierte e/a, z `printf` . b. die Funktion.|

## <a name="autoopen-attribute"></a>AutoOpen-Attribut

Sie können das- `AutoOpen` Attribut auf eine Assembly anwenden, wenn Sie einen Namespace oder ein Modul automatisch öffnen möchten, wenn auf die Assembly verwiesen wird. Sie können auch das- `AutoOpen` Attribut auf ein Modul anwenden, um dieses Modul automatisch zu öffnen, wenn das übergeordnete Modul oder der übergeordnete Namespace geöffnet wird. Weitere Informationen finden Sie unter [AutoOpenAttribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-autoopenattribute.html).

## <a name="requirequalifiedaccess-attribute"></a>Requirements qualifiedaccess-Attribut

Einige Module, Datensätze oder Union-Typen können das- `RequireQualifiedAccess` Attribut angeben. Wenn Sie auf Elemente dieser Module, Datensätze oder Unions verweisen, müssen Sie einen qualifizierten Namen verwenden, unabhängig davon, ob Sie eine Import Deklaration einschließen. Wenn Sie dieses Attribut bei Typen, die häufig verwendete Namen definieren, strategisch verwenden, vermeiden Sie Namenskollisionen und sorgen dadurch für eine stabilere Codeänderung gegenüber den Änderungen in Bibliotheken. Weitere Informationen finden Sie unter "Requirements [qualifiedaccessattribute](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html)".

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [Namespaces](namespaces.md)
- [Module](modules.md)
