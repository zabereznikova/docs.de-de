---
title: 'Importdeklarationen: Das open-Schlüsselwort'
description: Erfahren Sie mehr über die Importdeklarationen von F- und deren Angabe eines Moduls oder Namespaces, auf deren Elemente Sie verweisen können, ohne einen vollqualifizierten Namen zu verwenden.
ms.date: 04/04/2019
ms.openlocfilehash: 0baef27c7dc3181b9da0defb1c793fec04269c09
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021530"
---
# <a name="import-declarations-the-open-keyword"></a>Importdeklarationen: Das `open`-Schlüsselwort

> [!NOTE]
> Mit dem API-Referenz-Link in diesem Artikel gelangen Sie auf MSDN.  Die docs.microsoft.com-API-Referenz ist nicht abgeschlossen.

Eine *Importdeklaration* gibt ein Modul oder einen Namespace an, auf dessen Elemente Sie verweisen können, ohne einen vollqualifizierten Namen zu verwenden.

## <a name="syntax"></a>Syntax

```fsharp
open module-or-namespace-name
```

## <a name="remarks"></a>Bemerkungen

Das Verweisen auf Code mithilfe des vollqualifizierten Namespace- oder Modulpfads kann jedes Mal Code erstellen, der schwer zu schreiben, zu lesen und zu verwalten ist. Stattdessen können Sie `open` das Schlüsselwort für häufig verwendete Module und Namespaces verwenden, sodass Sie beim Verweisen auf ein Mitglied dieses Moduls oder Namespaces die Kurzform des Namens anstelle des vollqualifizierten Namens verwenden können. Dieses Schlüsselwort ähnelt `using` dem Schlüsselwort `using namespace` in C, In `Imports` Visual C++ und in Visual Basic.

Das angegebene Modul oder der bereitgestellte Namespace muss sich im selben Projekt oder in einem referenzierten Projekt oder einer Assembly begeben. Ist dies nicht der Fall, können Sie einen `-reference` Verweis auf das Projekt `-r`hinzufügen oder die Befehlszeilenoption (oder deren Abkürzung, ) verwenden. Weitere Informationen finden Sie unter [Compileroptionen](compiler-options.md).

Die Importdeklaration stellt die Namen im Code zur Verfügung, der auf die Deklaration folgt, bis zum Ende des einschließenden Namespace, Moduls oder der Datei.

Wenn Sie mehrere Importdeklarationen verwenden, sollten sie in separaten Zeilen angezeigt werden.

Der folgende Code zeigt `open` die Verwendung des Schlüsselworts, um Code zu vereinfachen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet6801.fs)]

Der F-Compiler gibt keinen Fehler oder eine Warnung aus, wenn Mehrdeutigkeiten auftreten, wenn derselbe Name in mehr als einem geöffneten Modul oder Namespace auftritt. Wenn Mehrdeutigkeiten auftreten, bevorzugt f. das kürzlich geöffnete Modul oder den Namespace. Im folgenden Code bedeutet `empty` z. `Seq.empty`B., obwohl `empty` `List` es `Seq` sich sowohl in der als auch in den Modulen befindet.

```fsharp
open List
open Seq
printfn "%A" empty
```

Achten Sie daher darauf, wenn Sie Module `List` `Seq` oder Namespaces öffnen, z. B. oder die Member mit identischen Namen enthalten. Stattdessen sollten Sie die verwendungsberechtigten Namen verwenden. Sie sollten jede Situation vermeiden, in der der Code von der Reihenfolge der Einfuhrdeklarationen abhängig ist.

## <a name="namespaces-that-are-open-by-default"></a>Namespaces, die standardmäßig geöffnet sind

Einige Namespaces werden so häufig in F-Code verwendet, dass sie implizit geöffnet werden, ohne dass eine explizite Importdeklaration erforderlich ist. Die folgende Tabelle zeigt die standardmäßig geöffneten Namespaces.

|Namespace|BESCHREIBUNG|
|---------|-----------|
|`Microsoft.FSharp.Core`|Enthält grundlegende F-Typdefinitionen für integrierte `int` Typen `float`wie und .|
|`Microsoft.FSharp.Core.Operators`|Enthält grundlegende arithmetische `+` Operationen `*`wie und .|
|`Microsoft.FSharp.Collections`|Enthält unveränderliche Auflistungsklassen wie `List` und `Array`.|
|`Microsoft.FSharp.Control`|Enthält Typen für Steuerelementkonstrukte, z. B. verzögerte Auswertung und asynchrone Workflows.|
|`Microsoft.FSharp.Text`|Enthält Funktionen für formatierte E/A, z. B. die `printf` Funktion.|

## <a name="autoopen-attribute"></a>AutoOpen-Attribut

Sie können `AutoOpen` das Attribut auf eine Assembly anwenden, wenn Sie automatisch einen Namespace oder ein Modul öffnen möchten, wenn auf die Assembly verwiesen wird. Sie können das `AutoOpen` Attribut auch auf ein Modul anwenden, um dieses Modul automatisch zu öffnen, wenn das übergeordnete Modul oder der Namespace geöffnet wird. Weitere Informationen finden Sie unter [Core.AutoOpenAttribute Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.autoopenattribute-class-%5bfsharp%5d).

## <a name="requirequalifiedaccess-attribute"></a>RequireQualifiedAccess-Attribut

Einige Module, Datensätze oder Union-Typen `RequireQualifiedAccess` können das Attribut angeben. Wenn Sie auf Elemente dieser Module, Datensätze oder Unions verweisen, müssen Sie einen qualifizierten Namen verwenden, unabhängig davon, ob Sie eine Importdeklaration einschließen. Wenn Sie dieses Attribut strategisch für Typen verwenden, die häufig verwendete Namen definieren, können Sie Namenskonflikte vermeiden und dadurch Code widerstandsfähiger gegenüber Änderungen in Bibliotheken machen. Weitere Informationen finden Sie unter [Core.RequireQualifiedAccessAttribute-Klasse](https://msdn.microsoft.com/visualfsharpdocs/conceptual/core.requirequalifiedaccessattribute-class-%5Bfsharp%5D).

## <a name="see-also"></a>Weitere Informationen

- [Sprachreferenz](index.md)
- [Namespaces](namespaces.md)
- [Module](modules.md)
