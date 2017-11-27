---
title: Zugriffssteuerung (F#)
description: Informationen Sie zum Steuern des Zugriffs auf Programmierelemente wie Typen, Methoden und Funktionen, die in der Programmiersprache f#.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 955b06fe-d1cd-431d-8db6-93e83b697453
ms.openlocfilehash: a02e20a585a0456577901f2762a0eeb0e3ecd2f0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="access-control"></a>Zugriffssteuerung

*Steuerung des Zugriffs* bezieht sich auf deklarieren, welche Clients bestimmte Programmelemente, wie Typen, Methoden und Funktionen verwenden können.


## <a name="basics-of-access-control"></a>Grundlagen der Zugriffssteuerung
In F# erläutert werden, die Zugriff steuern Spezifizierer `public`, `internal`, und `private` für Module, Typen, Methoden, Wertdefinitionen, Funktionen, Eigenschaften und explizite Felder angewendet werden können.


- `public`Gibt an, dass die Entität, die von allen Aufrufern zugegriffen werden kann.

- `internal`Gibt an, dass die Entität, die nur aus der gleichen Assembly zugegriffen werden kann.

- `private`Gibt an, dass die Entität, die nur aus dem einschließenden Typ oder Modul zugegriffen werden kann.


>[!NOTE] 
Der Zugriffsspezifizierer `protected` wird nicht in f# verwendet, obwohl es akzeptabel ist, bei Verwendung von Typen, die in Sprachen, unterstützen erstellte `protected` Zugriff. Wenn Sie eine geschützte Methode überschreiben, bleibt die Methode daher nur innerhalb der Klasse und die zugehörigen Nachfolgerelemente zugegriffen werden kann.

Im Allgemeinen wird der Spezifizierer vor den Namen der Entität, außer wenn versetzt einen `mutable` oder `inline` Formatbezeichner verwendet, die nach dem Steuerelement Zugriffsspezifizierer angezeigt werden.

Wenn keine Zugriffsspezifizierer verwendet wird, ist die Standardeinstellung `public`, mit Ausnahme von `let` Bindungen, die in einem Typ immer sind `private` in den Typ.

Signaturen in F# erläutert werden. Geben Sie einen anderen Mechanismus zum Steuern des Zugriffs auf f#-Programmelementen. Signaturen sind nicht für die Zugriffssteuerung erforderlich. Weitere Informationen finden Sie unter [Signaturen](signatures.md).


## <a name="rules-for-access-control"></a>Regeln für die Zugriffssteuerung
Die Zugriffssteuerung ist gemäß den folgenden Regeln:


- Vererbungsdeklarationen (d. h. die Verwendung von `inherit` eine Basisklasse für eine Klasse angeben) Schnittstellendeklarationen (das ist, gibt an, dass eine Klasse eine Schnittstelle implementiert) und abstrakte Member verfügen immer über den gleichen Zugriff wie der einschließende Typ. Aus diesem Grund kann ein Steuerelement Zugriffsspezifizierer auf diese Konstrukte verwendet werden.

- Einzelne Fälle, in eine Unterscheidungs-Union sind keine eigene Steuerelement-Zugriffsmodifizierer, die getrennt von den union-Typ.

- Einzelne Felder eines Datensatztyps sind keine eigene Steuerelement-Zugriffsmodifizierer, die getrennt von den Datensatztyp.


## <a name="example"></a>Beispiel
Der folgende Code veranschaulicht die Verwendung der Zugriffsspezifizierer-Steuerelement. Es gibt zwei Dateien im Projekt `Module1.fs` und `Module2.fs`. Jede Datei ist implizit ein Modul. Aus diesem Grund sind die beiden Module `Module1` und `Module2`. Einen privaten Typ und einen internen Typ sind in definiert `Module1`. Die private Typ kann nicht zugegriffen werden, aus `Module2`, aber Sie können der interne Typ.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet1.fs)]
    
Der folgende Code überprüft, den Zugriff auf die Typen im erstellten `Module1.fs`.

[!code-fsharp[Main](../../../samples/snippets/fsharp/access-control/snippet2.fs)]
    
## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Signaturen](signatures.md)
