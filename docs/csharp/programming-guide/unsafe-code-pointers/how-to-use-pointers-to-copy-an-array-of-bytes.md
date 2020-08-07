---
title: 'Vorgehensweise: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierleitfaden)'
description: Erfahren Sie, wie Sie Zeiger verwenden, um ein Array aus Bytes zu kopieren. Hier finden Sie ein Codebeispiel und zusätzliche verfügbare Ressourcen.
ms.date: 04/20/2018
helpviewer_keywords:
- byte arrays [C#]
- arrays [C#], byte
- pointers [C#], to copy bytes
ms.openlocfilehash: 70ab1441d25ea69afb2244bd94bd404a3e32838d
ms.sourcegitcommit: 552b4b60c094559db9d8178fa74f5bafaece0caf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/29/2020
ms.locfileid: "87381787"
---
# <a name="how-to-use-pointers-to-copy-an-array-of-bytes-c-programming-guide"></a>Vorgehensweise: Verwenden von Zeigern zum Kopieren eines Bytearrays (C#-Programmierleitfaden)

In folgendem Beispiel werden Zeiger verwendet, um Bytes aus einem Array in ein anderes zu kopieren.

In diesem Beispiel wird das Schlüsselwort [unsafe](../../language-reference/keywords/unsafe.md) verwendet, mit dem Sie Zeiger in der `Copy`-Methode verwenden können. Die Anweisung [fixed](../../language-reference/keywords/fixed-statement.md) wird verwendet, um Zeiger auf das Quell- und Zielarray zu deklarieren. Diese `fixed`-Anweisung *heftet* den Speicherort des Quell- und Zielarrays im Speicher an, damit diese während der automatischen Speicherbereinigung nicht verschoben werden. Die Speicherblöcke der Arrays werden gelöst, wenn der `fixed`-Block abgeschlossen wird. Da die `Copy`-Methode in diesem Beispiel das Schlüsselwort `unsafe` verwendet, muss sie mit der Compileroption [-unsafe](../../language-reference/compiler-options/unsafe-compiler-option.md) kompiliert werden.

In diesem Beispiel werden Indizes anstelle eines zweiten nicht verwalteten Zeigers verwendet, um auf die Elemente beider Arrays zuzugreifen. Die Deklaration der Zeiger `pSource` und `pTarget` heftet die Arrays an. Dieses Feature ist ab C# 7.3 verfügbar.

## <a name="example"></a>Beispiel

[!code-csharp[Struct with embedded inline array](snippets/FixedKeywordExamples.cs#8)]

## <a name="see-also"></a>Weitere Informationen

- [C#-Programmierhandbuch](../index.md)
- [Unsicherer Code und Zeiger](index.md)
- [-unsafe (C#-Compileroptionen)](../../language-reference/compiler-options/unsafe-compiler-option.md)
- [Garbage Collection](../../../standard/garbage-collection/index.md)
