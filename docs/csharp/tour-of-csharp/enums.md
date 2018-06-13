---
title: C#-Enumerationen – Überblick über C#
description: Hier lernen Sie Enumerationen kennen, separate benannte Konstanten in C#.
ms.date: 08/10/2016
ms.assetid: 7faba1cc-6ea9-4a19-adb9-0335e4b132e5
ms.openlocfilehash: 7fe2626381cb90e55842e3be17dd450eb73d5a5b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33353353"
---
# <a name="enums"></a>Enumerationen

Ein ***Enumerationstyp*** ist ein eindeutiger Werttyp mit einem Satz benannter Konstanten. Sie definieren die Enumerationen, wenn Sie einen Typ definieren müssen, der einen Satz von diskreten Werten haben kann. Die Enumerationen verwenden einen der ganzzahligen Werttypen als ihren zugrunde liegenden Speicher. Sie liefern die Bedeutung der diskreten Werte.

Das folgende Beispiel deklariert und verwendet einen `enum`-Typ mit dem Namen `Color` mit drei konstanten Werten, `Red`, `Green` und `Blue`.

[!code-csharp[EnumExample](../../../samples/snippets/csharp/tour/enums/Program.cs#L3-L36)]

Jeder `enum`-Typ verfügt über einen entsprechenden ganzzahligen Typ, der als der ***zugrunde liegende Typ*** des `enum`-Typs bezeichnet wird. Ein `enum`-Typ, der nicht explizit einen zugrunde liegenden Typ deklariert, verfügt über einen zugrunde liegenden `int`-Typ. Das Speicherformat eines `enum`-Typs und der Bereich der möglichen Werte werden durch den ihm zugrunde liegenden Typ bestimmt. Der Satz von Werten, die ein `enum`-Typ ausführen kann, ist nicht durch seine `enum`-Member beschränkt. Insbesondere jeder Wert des zugrunde liegenden Typs einer `enum` kann in den `enum`-Typ umgewandelt werden und ist ein eindeutiger gültiger Wert dieses `enum`-Typs.

Das folgende Beispiel deklariert einen `enum`-Typ mit dem Namen `Alignment` und einem zugrunde liegenden Typ `sbyte`.

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L38-L43)]

Wie im vorherigen Beispiel gezeigt, kann eine `enum`-Memberdeklaration einen konstanten Ausdruck beinhalten, der den Wert des Members angibt. Der konstante Wert für jeden `enum`-Member muss im Bereich des zugrunde liegenden Typs der `enum` sein. Wenn eine `enum`-Memberdeklaration nicht explizit einen Wert angibt, erhält der Member den Wert 0 (null) (falls dies der erste Member im `enum`-Typ ist) oder den Wert des textlich vorausgehenden `enum`-Members plus eins.

`Enum`-Werte können mit Typumwandlungen in ganzzahlige Werte und umgekehrt konvertiert werden. Zum Beispiel:

[!code-csharp[EnumStorage](../../../samples/snippets/csharp/tour/enums/Program.cs#L49-L50)]

Der Standardwert eines beliebigen `enum`-Typs ist der ganzzahlige Wert 0 (null) konvertiert in den `enum`-Typ. In Fällen, in denen Variablen automatisch auf einen Standardwert initialisiert werden, ist dies der Wert der Variablen von `enum`-Typen. Damit der Standardwert eines `enum`-Typs leicht verfügbar ist, wird das Literal `0` implizit in einen `enum`-Typ konvertiert. Daher ist Folgendes zugelassen.

[!code-csharp[EnumZero](../../../samples/snippets/csharp/tour/enums/Program.cs#L58-L58)]

>[!div class="step-by-step"]
[Zurück](interfaces.md)
[Weiter](delegates.md)
