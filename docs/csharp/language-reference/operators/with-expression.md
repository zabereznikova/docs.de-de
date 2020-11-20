---
title: 'with-Ausdruck: C#-Referenz'
description: Hier erhalten Sie Informationen zu einem with-Ausdruck, der nicht destruktive Änderungen von C#-Datensätzen durchführt.
ms.date: 11/12/2020
f1_keywords:
- with_CSharpKeyword
helpviewer_keywords:
- with expression [C#]
- with operator [C#]
ms.openlocfilehash: 8412dfe8663703d3b201fe98b5f4752da1b344cf
ms.sourcegitcommit: f99115e12a5eb75638abe45072e023a3ce3351ac
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "94556711"
---
# <a name="with-expression-c-reference"></a>with-Ausdruck (C#-Referenz)

Ab C# 9.0 ist ein `with`-Ausdruck verfügbar, der eine Kopie des dazugehörigen [Datensatzoperanden](../../whats-new/csharp-9.md#record-types) mit den angegebenen Eigenschaften und bearbeiteten Feldern erzeugt:

:::code language="csharp" source="snippets/with-expression/BasicExample.cs" :::

Wie das vorherige Beispiel zeigt, verwenden Sie die [Objektinitialisierersyntax](../../programming-guide/classes-and-structs/object-and-collection-initializers.md), um anzugeben, welche Member bearbeitet und welche neuen Werte dazu verwendet werden sollen. In einem `with`-Ausdruck muss ein linker Operand den Typ „Datensatz“ aufweisen.

Das Ergebnis eines `with`-Ausdrucks weist denselben Runtimetyp auf wie der Operand des Ausdrucks. Sehen Sie sich dazu das folgende Beispiel an:

:::code language="csharp" source="snippets/with-expression/InheritanceExample.cs" :::

Wenn der Member den Typ eines Verweises aufweist, wird nur der Verweis auf eine Instanz kopiert, wenn ein Datensatz kopiert wird. Sowohl der kopierte als auch der ursprüngliche Datensatz haben Zugriff auf dieselbe Verweistypinstanz. Das folgende Beispiel veranschaulicht dieses Verhalten:

:::code language="csharp" source="snippets/with-expression/ExampleWithReferenceType.cs" :::

Jeder Datensatztyp weist den *Kopierkonstruktor* auf. Dabei handelt es sich um einen Konstruktor mit einzelnem Parameter, der den Typ des Datensatzes aufweist, in dem er enthalten ist. Der Zustand des dazugehörigen Arguments wird in eine neue Datensatzinstanz kopiert. Wenn ein `with`-Ausdruck ausgewertet wird, wird der Kopierkonstruktor aufgerufen, um eine neue Datensatzinstanz basierend auf dem ursprünglichen Datensatz zu instanziieren. Danach wird die neue Instanz entsprechend der angegebenen Änderungen aktualisiert. Standardmäßig ist der Kopierkonstruktor implizit, das heißt, vom Compiler generiert. Wenn Sie die Kopiersemantik des Datensatzes anpassen möchten, deklarieren Sie explizit einen Kopierkonstruktor mit gewünschtem Verhalten. Das folgende Beispiel aktualisiert das vorherige Beispiel mit einem expliziten Kopierkonstruktor. Das neue Kopierverhalten besteht darin, Listenelemente anstatt eines Listenverweises zu kopieren, wenn ein Datensatz kopiert wird:

:::code language="csharp" source="snippets/with-expression/UserDefinedCopyConstructor.cs" :::

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie in den folgenden Abschnitten des Artikels [Datensätze](~/_csharplang/proposals/csharp-9.0/records.md):

- [`with`-Ausdruck](~/_csharplang/proposals/csharp-9.0/records.md#with-expression)
- [Methoden zum Kopieren und Klonen von Membern](~/_csharplang/proposals/csharp-9.0/records.md#copy-and-clone-members)

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Operatoren und -Ausdrücke](index.md)
